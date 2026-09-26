---
title: Serving RSA and ECDSA from One ASP.NET Core Kestrel Endpoint
published: true
tags:
  - aspnet
  - dotnet
  - tls
  - security
---

Most web servers are built for clients whose security behavior is handled by mainstream general-purpose operating systems.<br>
In that world, TLS handling by the web server is usually straightforward: one server name, one endpoint, one certificate chain, and broad interoperability across the signature schemes those stacks support.

The situation is different when clients fall outside that mainstream.<br>
In IoT, device fleets, industrial gateways, legacy SDKs, or application-to-application integrations, clients often have hard restrictions on which server authentication algorithms, certificate public key types, and certificate signature schemes they can use.

One important subset of those cases concerns the signature algorithms supported by the client.<br>
Cryptographic algorithms evolved over time, and different generations of clients ended up with support for different sets of algorithms.
As a result, one client may support only RSA, another may support only ECDSA, and a third may support both.<br>

When implementing a web server that must serve all those clients, this creates a specific requirement for the server.<br>
During the TLS handshake, it must inspect the client's capabilities and present a certificate with a signature algorithm that the client supports.

This article is about how to handle that requirement directly in ASP.NET Core Kestrel, without moving certificate management into a reverse proxy, external gateway, or other edge tier.

> Note: ASP.NET Core implementation, and most of the information available on this topic, focus on SNI-based certificate selection, where different server names map to different certificates, which is not the case here.<br>
Because of that, most people and LLM-based AI assistants conclude that this scenario is impossible to implement in ASP.NET Core Kestrel.

> Note: The reader should have a deep understanding of TLS, especially the negotiation phase of the handshake.

### Visualization

The visualization below illustrates the exact case addressed in this article.<br>
The backend exposes one endpoint and clients have different capabilities.

[![](https://mermaid.ink/img/pako:eNqVVU1vozAU_CuWo96ggvBtVdUSCqf2sulpl1XlgJOgODayjdpslP--hkDzQSptD0i8eeMZv7EFe1jwkkAEl5S_F2ssFHj-mbO7O8A0LnOWq0UjK0akfOarqvidw1lfPyzEY4fl8E_Hw8WGsPJNPzWvmGqpRwikPdQzC1oRpt7UriZvWNOSrgZtDeJW9uc8BpzR3Q3-4oo_G_i49Ume5vGNRcXVoqRd1JHPbRSVL5jhFRGa_vo8b0nbI9AxdCgrwZu6S0U2i5XA9Rr0Y5-m7dXO9Y71RZAt1JJbVUEoVhVnchQOeDDNR3Cd7CiT_6MVX9OuMWCaJrjc_6nqZS6n0WNItaP9lbmS-7EHco1rgsBSmEUlisMtFkIoPdvTyVA3Xun4Lmo4rmtaFV14o-x0-3jmo7i-7BRXHSzlE1mC_upIJfiGmO9VqdbIvvfqD6OHSqzHEwLvEOOM9CiauIHn-ZGxrChFk3SahpllFJxygSZWZgfT-MJFj_h9CysLfD_tLZIkm2X2YGE7bupeWpzF9X2rmes51jBNlmZOEgxWQeh4VnZhNZzk930cx7U9b_AJszhLxql1d224yqDjKoGZrLHQR_WpFbmxMwuNyz3c2oEP3MHkeGqtCa3YZt4ZlWSJGzoMgya-G7jhzBjPBg24ElUJ0RJTSQy4JWKL2xrucwZADtWabEkOkX4tsdjk0DjiFO94o4bGSmhOzg5arsbsF-dbqOdrtKD-AK3Wn_JNXWJFniq9AJ8oOhIiEt4wBZHtdxIQ7eEHRE5473mOPXWs0PNCzwoMuNOc6fTe9aPQD117GkWRHR0M-LcztTR_6odR4Hu2a0WRGxqQlJXi4uX43-h-H4d_Umo0eg?type=png)](https://mermaid.live/edit#pako:eNqVVU1vozAU_CuWo96ggvBtVdUSCqf2sulpl1XlgJOgODayjdpslP--hkDzQSptD0i8eeMZv7EFe1jwkkAEl5S_F2ssFHj-mbO7O8A0LnOWq0UjK0akfOarqvidw1lfPyzEY4fl8E_Hw8WGsPJNPzWvmGqpRwikPdQzC1oRpt7UriZvWNOSrgZtDeJW9uc8BpzR3Q3-4oo_G_i49Ume5vGNRcXVoqRd1JHPbRSVL5jhFRGa_vo8b0nbI9AxdCgrwZu6S0U2i5XA9Rr0Y5-m7dXO9Y71RZAt1JJbVUEoVhVnchQOeDDNR3Cd7CiT_6MVX9OuMWCaJrjc_6nqZS6n0WNItaP9lbmS-7EHco1rgsBSmEUlisMtFkIoPdvTyVA3Xun4Lmo4rmtaFV14o-x0-3jmo7i-7BRXHSzlE1mC_upIJfiGmO9VqdbIvvfqD6OHSqzHEwLvEOOM9CiauIHn-ZGxrChFk3SahpllFJxygSZWZgfT-MJFj_h9CysLfD_tLZIkm2X2YGE7bupeWpzF9X2rmes51jBNlmZOEgxWQeh4VnZhNZzk930cx7U9b_AJszhLxql1d224yqDjKoGZrLHQR_WpFbmxMwuNyz3c2oEP3MHkeGqtCa3YZt4ZlWSJGzoMgya-G7jhzBjPBg24ElUJ0RJTSQy4JWKL2xrucwZADtWabEkOkX4tsdjk0DjiFO94o4bGSmhOzg5arsbsF-dbqOdrtKD-AK3Wn_JNXWJFniq9AJ8oOhIiEt4wBZHtdxIQ7eEHRE5473mOPXWs0PNCzwoMuNOc6fTe9aPQD117GkWRHR0M-LcztTR_6odR4Hu2a0WRGxqQlJXi4uX43-h-H4d_Umo0eg)

## The Common Approach

This case is not unique and occurs frequently in some areas.<br>
It is often addressed by offloading TLS certificate management to a dedicated edge service placed in front of the web server.<br>
More specifically, that edge service is often a reverse proxy such as NGINX or HAProxy, a managed edge gateway such as Azure Application Gateway, or a Kubernetes Gateway implementation.

While this approach certainly works, it also brings drawbacks, such as:
- one more network hop,
- one more system to provision,
- one more failure domain,
- one more place where TLS configuration can drift,
- one more operational surface that costs money and must be managed.

In mutual TLS scenarios, this is even less attractive.<br>
Once certificate negotiation and identity extraction move to an edge service, authentication logic gets split across services.
The edge service now owns part of the security model, while the application owns another part.
This is especially problematic in regulated or protocol-driven environments that require strict end-to-end client authentication and certificate binding at the application layer.<br>
In zero-trust environments, it may also be unacceptable to leave traffic unencrypted between the edge service and the web server.

### Visualization

[![](https://mermaid.ink/img/pako:eNqVVctuozAU_RXLUXek4v2wqmoIAc2i3Uy6mmFUOeAQFGIjY9Rmovz7GAJNIInULCLic889h_uQ2cOEpQQiuCrYR7LGXICXXzF9eABU4lVMY7Gsq5ySqnphWZ78ieGsOz8t-XOLxfBvy8PJhtD0Xf5KllPRUI8QCDuoYyZFTqh4F7uSvGNJC9ozaM7Ab2R_LXzAaLG7wl-O-LOejxufYL7wryQlo6SgSWrJ5zaiqF4xxRnhkv72smhI2yPQMmRTMs7qsu1KVS8zjss16Mo-VdupnVFImhEZD-XjK3hud0Sa1GEeLssiT7DIGf3Jqqah_gkBDXQmNxjTQLF9yJfnpGgzq4sZgKfp9BmMB3jR-u_Rktu0MQam0ykY9uF06mSGZckyKrErus0cyf3Yg2qNS4LAik-TnCeHayyEUHj2TidDGXgrLldewmdtv-idDB9X66JdNyPJKIKrak5WoNvQSnC2IdOPPBVrpD1a5afSQSmW5XGOd4gySjoUTUzHsmxPWeVFgSahHrqRqiSsYBxN1EhzdH_gIku830KNHNsOO4sgiGaR1ltohhmaQ4vzLb3bamZahtpXE4WRETi9leMalhoNrPpJ3u9jGKZmWb2PG_lRcNm1dtf6VQYtV3BMqxJzOaovLc_0jZmrDN_h2hvYwOxNjlM7mTSXxG2Huec4qv0NBxMYvYOnm6oanhxG18ltM92yjXB2n5kWGr7b9qzI6WbRGqZkheuinw2a2KZjumPdZlRQgRnPU4hWuKiIAreEb3FzhvuYAhBDsSZbeXci-TfFfBND5YgXeMdq0QcyLjkxPUi5EtPfjG2hrK-WgvLaztZf8nWZYkHmuUzAJ4qcMOEBq6mAyGsVINrDT4gM99GyDE03VNeyXEt1FLiDSNP1R9P2XNs1Nd3zPM07KPBf66lKvm67nuOpjm45qqtAkuaC8dfjt7b95B7-A0W6pSY?type=png)](https://mermaid.live/edit#pako:eNqVVctuozAU_RXLUXek4v2wqmoIAc2i3Uy6mmFUOeAQFGIjY9Rmovz7GAJNIInULCLic889h_uQ2cOEpQQiuCrYR7LGXICXXzF9eABU4lVMY7Gsq5ySqnphWZ78ieGsOz8t-XOLxfBvy8PJhtD0Xf5KllPRUI8QCDuoYyZFTqh4F7uSvGNJC9ozaM7Ab2R_LXzAaLG7wl-O-LOejxufYL7wryQlo6SgSWrJ5zaiqF4xxRnhkv72smhI2yPQMmRTMs7qsu1KVS8zjss16Mo-VdupnVFImhEZD-XjK3hud0Sa1GEeLssiT7DIGf3Jqqah_gkBDXQmNxjTQLF9yJfnpGgzq4sZgKfp9BmMB3jR-u_Rktu0MQam0ykY9uF06mSGZckyKrErus0cyf3Yg2qNS4LAik-TnCeHayyEUHj2TidDGXgrLldewmdtv-idDB9X66JdNyPJKIKrak5WoNvQSnC2IdOPPBVrpD1a5afSQSmW5XGOd4gySjoUTUzHsmxPWeVFgSahHrqRqiSsYBxN1EhzdH_gIku830KNHNsOO4sgiGaR1ltohhmaQ4vzLb3bamZahtpXE4WRETi9leMalhoNrPpJ3u9jGKZmWb2PG_lRcNm1dtf6VQYtV3BMqxJzOaovLc_0jZmrDN_h2hvYwOxNjlM7mTSXxG2Huec4qv0NBxMYvYOnm6oanhxG18ltM92yjXB2n5kWGr7b9qzI6WbRGqZkheuinw2a2KZjumPdZlRQgRnPU4hWuKiIAreEb3FzhvuYAhBDsSZbeXci-TfFfBND5YgXeMdq0QcyLjkxPUi5EtPfjG2hrK-WgvLaztZf8nWZYkHmuUzAJ4qcMOEBq6mAyGsVINrDT4gM99GyDE03VNeyXEt1FLiDSNP1R9P2XNs1Nd3zPM07KPBf66lKvm67nuOpjm45qqtAkuaC8dfjt7b95B7-A0W6pSY)

## The Optimal Approach

For the specific case discussed in this article, the optimal design is to keep certificate selection inside the application host.

That produces a much cleaner model:

- There is no extra hop and no extra failure point.
- TLS management stays with the host that actually owns the endpoint.
- Certificate selection is implemented exactly where the handshake happens.
- In mutual TLS (mTLS) scenarios, client certificate negotiation and application-side identity handling are in one place.

### Visualization

[![](https://mermaid.ink/img/pako:eNqVVctu4jAU_RXLqLtQ5f2wqmpCmmgW7WboaiajyiQGIowdOY5aBvHv47x4BCq1CwQ-Pj7H99wbsocZzwlEcEn5e7bGQoLnXym7uwNM4VXKUrmoq4KRqnrmqyL7k8JZv35YiMcWS-HfloezDWH5m_qUvGCyoXYQiHuoZ2a0IEy-yV1J3rCiRe0aNGsQNrK_5iHgjO5u8Bcj_mzg48YnepqHNw5lo0NRc6gln9tIWr1ghldEKPrr87whbTugZahQVoLXZZtKVS9WApdr0Jd9qrZXO6PgsqRFhmXB2U9eNcGEJwQ00PHM-S0G5KIBHdjYsP5LXUsQ2mpVV-mCh-n0EYxbcxXq12jZ57QxBqbTKbgs5bTqZS7LUmVUckf7mRvJ_diDao1LgsBSTLNCZIdbLIRQfHank6HaeKXXw6zgs0ZcZae2u6G5iuvTnWy0g6vqiSxBP3uVFHxDpu9FLtfIuHfKD62HcqzKEwLvEOOM9Cia2J7juIG2LChFk9iM_UTXMk65QBM9MTwzvHBRJX7fQk881417iyhKZokxWBiWHduXFudz-22rme1Y-lBNEidW5A1Wnm85enJhNXTy-z6WZRuOM_j4SZhE16m1szaMMmi5UmBWlVioVh21Aju0Zr52eYdbN3CBPZh0XTuZjB7_z81Mx7Xi2RfMbGAdmxRbod9WRAu2mbeGOVnimg7JoYlre7Y_1m2ChBpciSKHaIlpRTS4JWKLmzXcpwyAFMo12ZIUIvUzx2KTQq3DKd7xWg4bK6E4KTsouRKz35xvoaqvVoLq73K1PsrXZY4leSrUAXyiqPyJiHjNJERBqwDRHn5AZPn3jmMZpqX7juM7uqfBHUSGad7bbuC7vm2YQRAYwUGD_1pPXfFN1w-8QPdMx9N9DZK8kFy8dO-49lV3-A9AT3R7?type=png)](https://mermaid.live/edit#pako:eNqVVctu4jAU_RXLqLtQ5f2wqmpCmmgW7WboaiajyiQGIowdOY5aBvHv47x4BCq1CwQ-Pj7H99wbsocZzwlEcEn5e7bGQoLnXym7uwNM4VXKUrmoq4KRqnrmqyL7k8JZv35YiMcWS-HfloezDWH5m_qUvGCyoXYQiHuoZ2a0IEy-yV1J3rCiRe0aNGsQNrK_5iHgjO5u8Bcj_mzg48YnepqHNw5lo0NRc6gln9tIWr1ghldEKPrr87whbTugZahQVoLXZZtKVS9WApdr0Jd9qrZXO6PgsqRFhmXB2U9eNcGEJwQ00PHM-S0G5KIBHdjYsP5LXUsQ2mpVV-mCh-n0EYxbcxXq12jZ57QxBqbTKbgs5bTqZS7LUmVUckf7mRvJ_diDao1LgsBSTLNCZIdbLIRQfHank6HaeKXXw6zgs0ZcZae2u6G5iuvTnWy0g6vqiSxBP3uVFHxDpu9FLtfIuHfKD62HcqzKEwLvEOOM9Cia2J7juIG2LChFk9iM_UTXMk65QBM9MTwzvHBRJX7fQk881417iyhKZokxWBiWHduXFudz-22rme1Y-lBNEidW5A1Wnm85enJhNXTy-z6WZRuOM_j4SZhE16m1szaMMmi5UmBWlVioVh21Aju0Zr52eYdbN3CBPZh0XTuZjB7_z81Mx7Xi2RfMbGAdmxRbod9WRAu2mbeGOVnimg7JoYlre7Y_1m2ChBpciSKHaIlpRTS4JWKLmzXcpwyAFMo12ZIUIvUzx2KTQq3DKd7xWg4bK6E4KTsouRKz35xvoaqvVoLq73K1PsrXZY4leSrUAXyiqPyJiHjNJERBqwDRHn5AZPn3jmMZpqX7juM7uqfBHUSGad7bbuC7vm2YQRAYwUGD_1pPXfFN1w-8QPdMx9N9DZK8kFy8dO-49lV3-A9AT3R7)

### Performance Overhead

The claim that TLS processing within the same machine that hosts the application introduces significant CPU overhead is based on an outdated view of how modern TLS stacks execute cryptography.

TLS is implemented in highly optimized native libraries such as OpenSSL, BoringSSL, or SChannel, which map cryptographic operations to CPU-level optimizations across the entire TLS pipeline.

Symmetric cryptography (AES-GCM, ChaCha20-Poly1305) is directly accelerated by dedicated CPU instruction set extensions such as **AES-NI**, **VAES**, and **PCLMULQDQ**, enabling hardware-level execution of bulk encryption operations.

Asymmetric cryptography (RSA, ECDSA, ECDH), used during handshake and certificate validation, is accelerated through highly optimized big-integer arithmetic, vectorized CPU instructions (AVX2/AVX-512), and constant-time implementations in modern cryptographic libraries.

As a result, both symmetric and asymmetric components of TLS benefit from CPU-level hardware acceleration and low-level optimizations, eliminating the notion of TLS as a general-purpose CPU-heavy workload in modern systems.

## How Certificate Selection Works During TLS

Before moving forward, it is important to clarify how server-side certificate selection works.

This process must occur during the initial phase of the TLS handshake: after the client sends [ClientHello][rfc_8446_clienthello] and before the server responds with [ServerHello][rfc_8446_serverhello].

The server-side flow is as follows:

1. Receive the incoming TLS record.
2. Parse the record as [TLSPlaintext][rfc_8446_tlsplaintext] and verify that it contains a [Handshake][rfc_8446_handshake] message with a [ClientHello][rfc_8446_clienthello] body.
3. Extract the client capabilities relevant to certificate selection from ClientHello.
4. Select the appropriate certificate based on those capabilities and your server's selection policy.
5. Respond with [ServerHello][rfc_8446_serverhello] and continue handshake, including Certificate message.

### How to get client capabilities

To determine which certificates are compatible, the [ClientHello][rfc_8446_clienthello] message must be inspected.

The exact location of the information needed for certificate selection depends on the TLS version:

| Version | Primary Source                        | Secondary Source                 |
| :-----: | ------------------------------------- | -------------------------------- |
|   1.2   | `signature_algorithms` extension      | `cipher_suites` field            |
|   1.3   | `signature_algorithms_cert` extension | `signature_algorithms` extension |

### How the Server Chooses a Certificate

The actual certificate to present is chosen by considering both the client's capabilities and the web server's certificate selection policy.

The specific selection policy is determined by the server implementation and may depend on organizational requirements or security policies.

Typical strategies include:
- Prefer the certificate with the strongest algorithm supported by both server and client.
- Present a default certificate if it matches the client’s capabilities.
- If no compatible certificate is available, abort the handshake.

This is the core mechanism for dynamic certificate selection based on client capabilities.

## Implement with ASP.NET Core Kestrel

Since ASP.NET Core 2.1, Kestrel provides the ability to configure TLS handshake behavior via [`HttpsConnectionAdapterOptions`][ms_learn_HttpsConnectionAdapterOption].

The `HttpsConnectionAdapterOptions` provides a [`ServerCertificateSelector`][ms_learn_HttpsConnectionAdapterOptions_ServerCertificateSelector] property that allows configuration of a callback that is called during the TLS negotiation phase.

> Historically, this API was designed for SNI-based certificate selection, where the server name influences which certificate is returned.<br>
However, nothing prevents using a different certificate-selection logic, such as client capabilities provided in `ClientHello` and implementation-specific policies.

The method assigned to `ServerCertificateSelector` accepts an argument of type [`ConnectionContext`][ms_learn_ConnectionContext].

The [`ConnectionContext`][ms_learn_ConnectionContext] implements the [`IMemoryPoolFeature`][ms_learn_IMemoryPoolFeature] interface, which exposes a [`MemoryPool`][ms_learn_IMemoryPoolFeature_MemoryPool] property.

The `MemoryPool` property can be used to access the raw TLS records as bytes sent by the client during the handshake. The relevant TLS record is a `TLSPlaintext` struct that carries a `Handshake` message with a `ClientHello` body. This enables custom parsing of handshake data if needed.

Starting with ASP.NET Core 10.0, `HttpsConnectionAdapterOptions` also provides the [`TlsClientHelloBytesCallback`][ms_learn_HttpsConnectionAdapterOptions_ClientHelloBytesCallback] property.<br>
This callback enables inspection of the incoming `ClientHello` before the certificate selection callback is invoked.

These APIs provide all the necessary hooks to implement dynamic certificate selection in Kestrel based on client capabilities, not just SNI.

## Reference Implementation

Everything required to implement the optimal approach described in this article has already been implemented by me in the following GitHub repository:

- [tls-server-certificate-selection][demo-repo]

This is not a toy demo.<br>
The repository contains production-grade code for parsing `ClientHello` and extracting the data required for certificate selection.

It also contains tests that can be used to study the behavior in detail, including integration tests that show how to wire the mechanism into ASP.NET Core Kestrel.

More specifically, the repository provides:

- low-level parsing of `ClientHello`,
- extraction of the TLS data relevant to certificate selection,
- a reusable implementation that can be inspected independently from the article,
- Kestrel-based integration tests that demonstrate end-to-end certificate selection behavior.

The repository shows the implementation in full, with tests that make the behavior easy to verify and explore.

## Conclusion

If you have one logical endpoint and heterogeneous non-browser clients, deploying an extra TLS tier should not be your default response.

When the requirement is simply:

- same host,
- same application,
- different certificate algorithms per client capability,

Kestrel can solve it where the problem actually lives: inside the server during TLS negotiation.

---

If you found this article useful, feel free to buy the author [a cup of coffee](https://ko-fi.com/stas_sultanov) ☕.

----

[demo-repo]: https://github.com/stas-sultanov/tls-server-certificate-selection
[rfc_8446]: https://www.rfc-editor.org/rfc/rfc8446
[rfc_8446_handshake]: https://www.rfc-editor.org/rfc/rfc8446#section-4
[rfc_8446_clienthello]: https://www.rfc-editor.org/rfc/rfc8446#section-4.1.2
[rfc_8446_tlsplaintext]: https://www.rfc-editor.org/rfc/rfc8446#section-5.1
[rfc_8446_serverhello]: https://www.rfc-editor.org/rfc/rfc8446#section-4.1.3
[rfc_8446_extensions]: https://www.rfc-editor.org/rfc/rfc8446#section-4.2
[rfc_8446_signature_scheme_list]: https://www.rfc-editor.org/rfc/rfc8446#section-4.2.3
[ms_learn_HttpsConnectionAdapterOption]: https://learn.microsoft.com/dotnet/api/microsoft.aspnetcore.server.kestrel.https.httpsconnectionadapteroptions
[ms_learn_HttpsConnectionAdapterOptions_ServerCertificateSelector]: https://learn.microsoft.com/dotnet/api/microsoft.aspnetcore.server.kestrel.https.httpsconnectionadapteroptions.servercertificateselector
[ms_learn_HttpsConnectionAdapterOptions_ClientHelloBytesCallback]: https://learn.microsoft.com/en-us/dotnet/api/microsoft.aspnetcore.server.kestrel.https.httpsconnectionadapteroptions.tlsclienthellobytescallback
[ms_learn_ConnectionContext]: https://learn.microsoft.com/dotnet/api/microsoft.aspnetcore.connections.connectioncontext
[ms_learn_IMemoryPoolFeature]: https://learn.microsoft.com/dotnet/api/microsoft.aspnetcore.connections.features.imemorypoolfeature
[ms_learn_IMemoryPoolFeature_MemoryPool]: https://learn.microsoft.com/dotnet/api/microsoft.aspnetcore.connections.features.imemorypoolfeature.memorypool
[ms-learn-X509Certificate2]: https://learn.microsoft.com/dotnet/api/system.security.cryptography.x509certificates.x509certificate2
