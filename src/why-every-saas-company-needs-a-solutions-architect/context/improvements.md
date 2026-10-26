# Article improvement backlog

Source: article-review discussion supplied in this session. IDs preserve the original SA-01–SA-18 list. Explanations below consolidate that discussion; they are not a verbatim transcript. Nothing is marked implemented by this migration.

## Working organization

| Block | Scope | IDs |
| --- | --- | --- |
| 1 | Thesis and scope | SA-01, SA-14, SA-15 |
| 2 | Vision and accountability | SA-02, SA-03, SA-04, SA-16 |
| 3 | Competence and development | SA-05, SA-06, SA-07, SA-08 |
| 4 | Acquiring capability | SA-09, SA-10, SA-11, SA-12, SA-13 |
| 5 | Lifecycle and language | SA-17, SA-18 |

Suggested order: 1 → 2 → 3 → 4 → 5. Original high-value subset: SA-02, SA-03, SA-05, SA-06, SA-09, SA-14, SA-15.

## SA-01 — Add an explicit scope disclaimer

- **Block:** 1
- **Proposal:** Clarify that many businesses relying on IT solutions need an IT Solutions Architect, then explain the article's focus on SaaS businesses.
- **Reasoning:** The author chose a business-centered explanation: in SaaS, the IT solution is itself the product, and building and operating it is the core of the business. This explains why the role is especially important without claiming it is the most important company role or that the need is exclusive to SaaS.
- **Status / author decision:** Approved and implemented on 2026-10-26. The author corrected the initial IT-solution framing to a business perspective and approved the final paragraph with “Отлично. Добавляй”.
- **Agreed replacement text:** Addition before the existing opening:

  > While many businesses that rely on IT solutions need an IT Solutions Architect, this article focuses on SaaS companies, where the IT solution itself is the product. Building and operating it is the core of the business, making the Solutions Architect’s role especially important.

- **Implemented:** Yes — prepended to [article.md](../article.md); existing article text preserved.
- **History:** [Author decision](decisions.md#sa-01--business-scope-introduction--2026-10-26) and [discussion excerpts](conversations/2026-10-26-sa-01-scope.md).

## SA-02 — Distinguish distributed work from unified vision

- **Block:** 2
- **Proposal:** Explain that activities can be delegated while the solution vision lives in one mind, with corresponding accountability for decisions.
- **Reasoning:** Distinguishes distributed execution from the author's integrated vision-holder thesis. “Solution vision” preserves the broader scope; “can only” expresses the author's intended restriction rather than the prescription conveyed by “must”.
- **Status / author decision:** Approved and implemented on 2026-10-26. The author chose the final wording and approved it with “Да, так и оставляем”.
- **Agreed replacement text:** Addition immediately after “This process cannot be reliably split across multiple roles.”:

  > Activities can be delegated, but the solution vision can only live in one mind, with corresponding accountability for decisions.

- **Implemented:** Yes — added to [article.md](../article.md) in “How does the SA do this in practice?”; surrounding text preserved.
- **History:** [Author decision](decisions.md#sa-02--delegated-activities-and-solution-vision--2026-10-26) and [discussion excerpts and approval](conversations/2026-10-26-sa-02-solution-vision.md).

## SA-03 — Explain architecture by aggregation

- **Block:** 2
- **Proposal:** Explain why several people with partial competence do not automatically constitute one sufficiently broad architect.
- **Reasoning:** Knowledge can remain fragmented, communication loses context, incentives conflict and no participant necessarily assesses the entire solution at once. Avoid claiming that collaboration itself cannot work.
- **Status / author decision:** Approved and implemented on 2026-10-26. After reviewing the insertion in context, the author authorized it with “Угу. Хорошо, да, давай вставляем, добавляем”.
- **Agreed replacement text:** Separate paragraph after the process/vision paragraph in “How does the SA do this in practice?”, before “Only when a single role owns this process end to end does the balance hold and the product remain viable.”:

  > A committee of partial views does not create one complete mind; they lack shared context and unified accountability.

- **Implemented:** Yes — inserted in [article.md](../article.md); surrounding text preserved.
- **History:** [Author decision](decisions.md#sa-03--architecture-by-aggregation--2026-10-26) and [discussion and approval](conversations/2026-10-26-sa-03-architecture-by-aggregation.md).

## SA-04 — Allow multiple SAs with coherent direction

- **Block:** 2
- **Proposal:** Explain that large products can have multiple SAs with clear boundaries and a coherent overall architectural direction.
- **Reasoning:** Avoids an artificial one-person constraint while preserving accountability for integration across domains, platforms and components.
- **Status / author decision:** Author explicitly allowed multiple SAs; wording pending.
- **Agreed replacement text:** Pending; no final wording approved in the supplied discussion.
- **Implemented:** No.

## SA-05 — Explain what internal promotion changes

- **Block:** 3
- **Proposal:** Add that promotion grants title, authority and mandate; it does not supply missing experience or skills.
- **Reasoning:** Product familiarity or being the strongest developer does not itself produce breadth across systems, businesses, infrastructure, failures and trade-offs.
- **Status / author decision:** Explicit addition requested by author; wording pending.
- **Agreed replacement text:** Pending; no final wording approved in the supplied discussion.
- **Implemented:** No.

## SA-06 — Explain mentoring and exposure constraints

- **Block:** 3
- **Proposal:** Ask who will develop the candidate and how varied architectural exposure will be provided.
- **Reasoning:** A company without a mature architect may lack the mentor and environment needed to develop one. A single product may not provide the needed breadth quickly; promotion alone does not solve that.
- **Status / author decision:** Author raised the mechanism problem; final scope and wording pending.
- **Agreed replacement text:** Pending; no final wording approved in the supplied discussion.
- **Implemented:** No.

## SA-07 — Describe the consulting-company exception

- **Block:** 3
- **Proposal:** Mention mature consulting or outsourcing practices with senior mentors and rotations.
- **Reasoning:** Multiple clients and industries can provide structured exposure to different architectures, failures and constraints. This explains a development mechanism; it is not evidence that only outsourcing firms can grow architects.
- **Status / author decision:** Proposal; no separate approval recorded.
- **Agreed replacement text:** Pending; no final wording approved in the supplied discussion.
- **Implemented:** No.

## SA-08 — Explain experience requirements

- **Block:** 3
- **Proposal:** Keep strong seniority expectations and explain the production judgment and accumulated breadth behind years of experience.
- **Reasoning:** Exact year thresholds can distract from the real requirement: having built, operated and changed systems and lived the consequences. The profile exists; the assistant withdrew its initial near-impossibility claim.
- **Status / author decision:** Proposal; author defended the existence and relevance of the profile.
- **Agreed replacement text:** Pending; no final wording approved in the supplied discussion.
- **Implemented:** No.

## SA-09 — Retain the defined-period external-SA model

- **Block:** 4
- **Proposal:** Present 12–36 months as a practical capability-establishment option, with scope and transition outcomes.
- **Reasoning:** Answers how a company without architecture capability can acquire it. Work includes vision, principles, target state, governance, implementation involvement and developing or recruiting a successor. Duration is a proposed engagement range, not an evidenced universal norm.
- **Status / author decision:** Author defended the model; exact revised framing pending.
- **Agreed replacement text:** Pending; no final wording approved in the supplied discussion.
- **Implemented:** No.

## SA-10 — Describe permanent recruitment as another route

- **Block:** 4
- **Proposal:** Present permanent hire and temporary external engagement as legitimate acquisition choices.
- **Reasoning:** Keeps the focus on acquiring capability and reduces the impression that the thesis depends on selling one engagement model. Do not assume permanent hiring is always best or temporary hiring always fastest.
- **Status / author decision:** Proposal; no separate approval recorded.
- **Agreed replacement text:** Pending; no final wording approved in the supplied discussion.
- **Implemented:** No.

## SA-11 — Require named consultancy accountability

- **Block:** 4
- **Proposal:** When using a consultancy, identify the individual architect accountable for the complete solution.
- **Reasoning:** A collection of consultants, workshops and documents can reproduce fragmentation if nobody owns integration and architectural decisions.
- **Status / author decision:** Proposal; no separate approval recorded.
- **Agreed replacement text:** Pending; no final wording approved in the supplied discussion.
- **Implemented:** No.

## SA-12 — Narrow claims about architects' tenure

- **Block:** 4
- **Proposal:** Remove or qualify the assertion that SAs by nature do not stay long at one company.
- **Reasoning:** Tenure is not intrinsic to the function. Explain the benefit of varied experience and transition periods without an unnecessary unsupported universal claim.
- **Status / author decision:** Proposal; no separate approval recorded.
- **Agreed replacement text:** Pending; no final wording approved in the supplied discussion.
- **Implemented:** No.

## SA-13 — Explain vendor incentives

- **Block:** 4
- **Proposal:** Frame the concern as incentive alignment and scope of responsibility rather than a universal accusation about ethics.
- **Reasoning:** Vendor architects operate within commercial and delivery constraints. The company's architecture owner must be able to recommend alternatives or less technology when appropriate.
- **Status / author decision:** Proposal; no separate approval recorded.
- **Agreed replacement text:** Pending; no final wording approved in the supplied discussion.
- **Implemented:** No.

## SA-14 — Distinguish function from formal title

- **Block:** 1
- **Proposal:** Explain that a suitably qualified, empowered person may perform the SA function under another formal title.
- **Reasoning:** Prevents dismissal based on corporate nomenclature, while retaining the author's requirement for competence, focus and integrated accountability. A title alone does not establish the capability.
- **Status / author decision:** Proposal; no separate approval recorded.
- **Agreed replacement text:** Pending; no final wording approved in the supplied discussion.
- **Implemented:** No.

## SA-15 — Restate the model in the conclusion

- **Block:** 1
- **Proposal:** Make coherent architectural vision and the balance of Business + Domain against Software + Infrastructure the final takeaway.
- **Reasoning:** Leaves the reader with the article's causal model rather than merely a hiring recommendation. Preserves Demand and Capability as the central conceptual structure.
- **Status / author decision:** Proposal; no separate approval recorded.
- **Agreed replacement text:** Pending; no final wording approved in the supplied discussion.
- **Implemented:** No.

## SA-16 — Show the failure mechanism

- **Block:** 2
- **Proposal:** Add a concise chain from local optimization through inconsistent choices and duplication to operational complexity, cost and risk.
- **Reasoning:** Makes the business case tangible and explains why missing integration matters to executives. Use it as a plausible mechanism, not an inevitable outcome of every local decision.
- **Status / author decision:** Proposal; no separate approval recorded.
- **Agreed replacement text:** Pending; no final wording approved in the supplied discussion.
- **Implemented:** No.

## SA-17 — Strengthen continuity through delivery and operation

- **Block:** 5
- **Proposal:** Emphasize implementation, production feedback, incidents, evolution and major changes.
- **Reasoning:** Architectural quality is tested by consequences in operation, not diagrams alone. Continuity supports learning and prevents erosion of the agreed design.
- **Status / author decision:** Proposal; no separate approval recorded.
- **Agreed replacement text:** Pending; no final wording approved in the supplied discussion.
- **Implemented:** No.

## SA-18 — Perform a final language pass

- **Block:** 5
- **Proposal:** Correct wording and typographical issues, including Infrastructure realtiy → Infrastructure reality.
- **Reasoning:** Language errors can distract from a senior professional argument. Perform after substantive decisions so editing does not obscure changes in meaning.
- **Status / author decision:** Proposal; no separate approval recorded.
- **Agreed replacement text:** Pending; no final wording approved in the supplied discussion.
- **Implemented:** No.

