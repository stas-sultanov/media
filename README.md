# Media

Article workspaces: one directory per article under `src/`.

| Article | Canonical Markdown | Context |
| --- | --- | --- |
| Azure Observability Without Reinventing the Wheel | [article.md](src/extra-monitor/article.md) | [context](src/extra-monitor/context/README.md) |
| Serving RSA and ECDSA from One ASP.NET Core Kestrel Endpoint | [article.md](src/kestrel-tls-certificate-selection/article.md) | [context](src/kestrel-tls-certificate-selection/context/README.md) |
| Why Every SaaS Company Needs a Solutions Architect | [article.md](src/why-every-saas-company-needs-a-solutions-architect/article.md) | [context](src/why-every-saas-company-needs-a-solutions-architect/context/README.md) |

## Workflow

1. Read this repository's [agent instructions](AGENTS.md) and the article's context.
2. Append supplied conversations to `context/conversations/`; maintain the context index, decisions, and improvement backlog. Preserve author wording and distinguish proposals from decisions.
3. Keep research, references, code and visual sources in the article's `materials/` directory.
4. Revise `article.md` using explicit author decisions. Markdown is the default final format.
5. On request, generate channel-specific derivatives in `publications/<channel>/`, using [PUBLISHING.md](PUBLISHING.md). Record the source Git commit, generation date and adaptation decisions.
6. Compare with the live publication before claiming synchronization. Commit locally authorized repository changes; publishing externally requires an explicit request.

The migration preserves all three original source blobs unchanged at their new paths. No editorial review proposals were applied during migration. Existing history retains the old paths.

Conversation records contain only article-related context actually supplied in this session. Older unavailable conversations are not represented as recovered. This repository is public: keep unrelated personal, employer and confidential information out.
