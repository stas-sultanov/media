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
- **Status / author decision:** Approved and implemented on 2026-10-26. After reviewing the insertion in the section, the author authorized it with “Да? Хорошо. Добавь”.
- **Agreed replacement text:** Separate paragraph after the SA-03 committee paragraph in “How does the SA do this in practice?”, before the concluding “Only when a single role owns this process end to end…” statement:

  > Large products may have more than one Solutions Architect, but accountability for the end-to-end solution must be clearly owned.

- **Implemented:** Yes — inserted in [article.md](../article.md); surrounding text preserved.
- **History:** [Author decision](decisions.md#sa-04--multiple-sas-and-end-to-end-accountability--2026-10-26) and [discussion and approval](conversations/2026-10-26-sa-04-multiple-architects.md).

## SA-05 — Explain what internal promotion changes

- **Block:** 3
- **Proposal:** State that promotion grants title and mandate, not competence.
- **Reasoning:** The author rejected restricting this argument to missing experience with other systems or technologies. An architecture title does not itself create missing competence even within the person's original specialty, such as .NET engineering.
- **Status / author decision:** Approved and implemented on 2026-10-26. The author approved the revised wording with “Да” and separately confirmed implementation as an individual SA-05 commit.
- **Agreed replacement text:** Separate paragraph in “3. Level up an internal employee”, after the assumption and before the existing explanation of how experience is accumulated:

  > Promotion grants title and mandate, not competence.

- **Implemented:** Yes — inserted in [article.md](../article.md); surrounding text preserved.
- **History:** [Author decision](decisions.md#sa-05--promotion-and-competence--2026-10-26) and [discussion and approvals](conversations/2026-10-26-sa-05-promotion-and-competence.md).

## SA-06 — Explain mentoring and exposure constraints

- **Block:** 3
- **Proposal:** Make the missing-mentor constraint explicit and retain the varied-experience argument with a continuous enumeration.
- **Reasoning:** A company without an experienced SA may lack the mentor needed to develop one. The author requested a forceful formulation, removed the repeated promotion/competence clause, and rejected the monotonous “multiple” list.
- **Status / author decision:** Approved and implemented on 2026-10-26. The author accepted the revised enumeration, then confirmed implementation as a separate SA-06 commit with “Да, давай”.
- **Agreed replacement text:** Add after SA-05 in “3. Level up an internal employee”:

  > Without an experienced SA to mentor, a SaaS company rarely develops one.

  Replace the repetitive bullet list with the following enumeration, joined to the existing sentence about pressures and failures:

  > across different customers and business models, domains with different regulatory traps, technology stacks and scaling problems, production outages and cost crises.

- **Implemented:** Yes — mentor sentence added and enumeration revised in [article.md](../article.md); the rest of the article is preserved.
- **History:** [Author decision](decisions.md#sa-06--mentoring-constraints-and-varied-experience--2026-10-26) and [discussion and approval](conversations/2026-10-26-sa-06-mentoring-and-experience.md).

## SA-07 — Describe the consulting-company exception

- **Block:** 3
- **Proposal:** Mention mature consulting or outsourcing practices with senior mentors and rotations.
- **Reasoning:** Multiple clients and industries can provide structured exposure to different architectures, failures and constraints. This explains a development mechanism; it is not evidence that only outsourcing firms can grow architects.
- **Status / author decision:** Skipped on 2026-10-26. After reviewing the proposed caveat, the author questioned its necessity and accepted omission with “Отлично, пропускаем и идем дальше”.
- **Decision rationale:** Existing “rarely” and “usually” wording already permits exceptions. An explanation of architect development in consulting companies would distract from the article's SaaS focus.
- **Agreed replacement text:** None — the proposed addition was not adopted; see the discussion record for its wording.
- **Implemented:** No article change; closed as skipped rather than pending.
- **History:** [Author decision](decisions.md#sa-07--consulting-company-caveat-skipped--2026-10-26) and [discussion and final decision](conversations/2026-10-26-sa-07-consulting-exception-skipped.md).

## SA-08 — Explain experience requirements

- **Block:** 3
- **Proposal:** Keep strong seniority expectations and explain the practical depth, production responsibility and accumulated breadth behind years of experience.
- **Reasoning:** Years must represent deep hands-on expertise, responsibility for production outcomes and exposure to different business and technical conditions. The author defended the existence and relevance of the profile; the assistant withdrew its initial near-impossibility claim. This addition preserves the existing year thresholds.
- **Status / author decision:** Approved and implemented on 2026-10-26. After reviewing the exact sentence and placement, the author accepted it with “Да. Берем”.
- **Agreed replacement text:** Add as a separate paragraph in “Who can play this role?”, immediately before “A strong SA typically has:”:

  > The years of experience described below must reflect deep hands-on expertise, responsibility for production outcomes, and exposure to different business and technical conditions.

- **Implemented:** Yes — added to [article.md](../article.md). The requirements list, year thresholds and the existing SA-06 paragraph are preserved.
- **History:** [Author decision](decisions.md#sa-08--depth-and-breadth-behind-experience--2026-10-26) and [discussion and approval](conversations/2026-10-26-sa-08-depth-and-breadth.md).

## SA-09 — External SA engagement of at least 12 months

- **Block:** 4
- **Proposal / author decision:** Engage an external senior SA and plan for at least 12 months, replacing the 12–36 month range.
- **Reasoning:** Onboarding, organizational constraints and implementation into production require sustained participation. Mandatory succession was rejected; contract end does not remove the need for an SA.
- **Status:** Approved and implemented, 2026-10-26.
- **Agreed replacement text:** The most realistic approach is to engage a senior Solutions Architect from outside the company. Plan for at least 12 months: the architect needs time to understand the business, domain, solution, and team, work through organizational constraints, and carry improvements through implementation into production.
- **Implemented:** Yes, first paragraph of “How can a company get a Solutions Architect?”.
- **History:** [Discussion and approval](conversations/2026-10-26-sa-09-engagement.md).

## SA-10 — Describe permanent recruitment as another route

- **Block:** 4
- **Proposal:** Allow permanent recruitment and external contract engagement.
- **Reasoning:** The capability matters regardless of employment model. SA-09 removed the dedicated-contractor restriction and already allows both paths.
- **Status / author decision:** Closed as covered by SA-09, approved 2026-10-26. No additional article wording needed.
- **Agreed replacement text:** No separate addition; use the approved SA-09 paragraph.
- **Implemented:** Covered by SA-09; article unchanged in this decision.
- **History:** [Discussion and approval](conversations/2026-10-26-sa-10-covered.md).

## SA-11 — Require named consultancy accountability

- **Block:** 4
- **Proposal:** Require an individual architect accountable for the complete solution when using a consultancy.
- **Reasoning:** SA-02–SA-04 already establish personal accountability and unified solution vision, regardless of engagement model. Repeating this separately for consultancy would duplicate the argument.
- **Status / author decision:** Closed as covered by SA-02–SA-04, approved 2026-10-26.
- **Agreed replacement text:** No additional wording.
- **Implemented:** Covered by existing edits; no article change in this decision.
- **History:** [Discussion summary and approval](conversations/2026-10-26-sa-11-covered.md).

## SA-12 — Narrow claims about architects' tenure

- **Block:** 4
- **Proposal:** Remove or qualify the assertion that SAs by nature do not stay long at one company.
- **Reasoning:** Varied experience does not require continued rotation after the architect joins. Its benefits are already covered elsewhere; this paragraph creates an unnecessary expectation of early departure.
- **Status / author decision:** Approved deletion of the entire paragraph on 2026-10-26; author replied “да”.
- **Agreed replacement text:** None; delete the paragraph beginning “Note that SAs, by nature, don’t stay long at a single company”.
- **Implemented:** Yes — paragraph removed from [article.md](../article.md).
- **History:** [Discussion and removed text](conversations/2026-10-26-sa-12-tenure.md).

## SA-13 — Explain vendor incentives

- **Block:** 4
- **Proposal:** Explain the concern through commercial interests, delivery obligations and accountability.
- **Reasoning:** Vendor and SaaS-company interests may align, but alignment cannot be assumed. The company needs an SA accountable for the whole solution, including decisions conflicting with vendor interests. This replaces a universal claim about vendor-architect behavior with the structural concern.
- **Status / author decision:** Approved and implemented, 2026-10-26; author replied “отлично . да”.
- **Agreed replacement text:**

  > A vendor-provided architect operates within their employer’s commercial interests and delivery obligations. These may align with the SaaS company’s interests, but that alignment cannot be assumed.
  >
  > The SaaS company needs a Solutions Architect accountable for the whole solution, including decisions that may conflict with the vendor’s interests.

- **Implemented:** Yes — two explanatory paragraphs in “4. Borrow from a vendor”.
- **History:** [Discussion and approval](conversations/2026-10-26-sa-13-vendor-incentives.md).

## SA-14 — Distinguish function from formal title

- **Block:** 1
- **Proposal:** Explain that the SA function can be performed under another formal job title.
- **Reasoning:** Formal naming does not establish or remove the capability. The person must have the qualification, authority, time and end-to-end accountability described by the article.
- **Status / author decision:** Approved and implemented, 2026-10-26. The author refined the wording and requested a quote.
- **Agreed replacement text:** Addition as a Markdown blockquote:

  > Of course, the formal job title may differ. The title itself does not matter; what matters is that a qualified person has the authority, time, and end-to-end accountability to perform this role.

- **Implemented:** Yes — after “That role is the **Solutions Architect**.”, before the next section separator.
- **History:** [Discussion and approval](conversations/2026-10-26-sa-14-formal-title.md).

## SA-15 — Restate the model in the conclusion

- **Block:** 1
- **Proposal:** Link coherent solution vision with the Demand/Capability model in the conclusion.
- **Reasoning:** Reinforce the SA's concrete purpose: hold the whole solution vision and balance Business + Domain with Software + Infrastructure throughout ongoing work.
- **Status / author decision:** Approved and implemented, 2026-10-26; author replied “да”.
- **Agreed replacement text:**

  > The SA maintains a coherent vision for the whole solution and continuously balances Demand (Business + Domain) against Capability (Software + Infrastructure). This keeps the product deliverable, operable, and economically viable.

- **Implemented:** Yes — replaced the conclusion paragraph beginning “With an SA, that balance is actively protected”.
- **History:** [Original, proposal and approval](conversations/2026-10-26-sa-15-conclusion.md).

## SA-16 — Show the failure mechanism

- **Block:** 2
- **Proposal:** Explain how local decisions can create duplication, conflicting designs and operational complexity, leading to business costs, failures and slower delivery.
- **Reasoning:** Makes the mechanism concrete rather than merely saying groups pull the solution apart. “Can” frames these as possible consequences.
- **Status / author decision:** Approved and implemented, 2026-10-26. Author requested “However” and accepted the revised paragraph.
- **Agreed replacement text:**

  > Individually, each of these priorities is rational. However, without someone evaluating their combined impact on the whole solution, local decisions can create duplicated capabilities, conflicting designs, and growing operational complexity. The business pays through higher costs, more failures, and slower delivery.

- **Implemented:** Yes — paragraph following the group-priority list in “Why does no one own the balance?”.
- **History:** [Discussion and approval](conversations/2026-10-26-sa-16-local-decisions.md).

## SA-17 — Strengthen continuity through delivery and operation

- **Block:** 5
- **Proposal:** Extend the SA's involvement through operation and use production feedback and incident findings to refine the solution.
- **Reasoning:** Consequences of architectural decisions emerge in production. Continued involvement enables the SA to learn from operation and preserve the agreed solution shape as it evolves.
- **Status / author decision:** Approved and implemented, 2026-10-26; author replied “подходит”.
- **Agreed replacement text:**

  - **Stay through implementation and operation**: ensure what gets delivered still matches that agreed shape and has not been quietly degraded into something unstable, unmaintainable, or unprofitable. Use production feedback and incident findings to refine the solution as it evolves.

- **Implemented:** Yes — final process bullet in “How does the SA do this in practice?”.
- **History:** [Discussion and approval](conversations/2026-10-26-sa-17-operation.md).

## SA-18 — Perform a final language pass

- **Block:** 5
- **Proposal:** Correct wording and typographical issues, including Infrastructure realtiy → Infrastructure reality.
- **Reasoning:** Language errors can distract from a senior professional argument. Perform after substantive decisions so editing does not obscure changes in meaning.
- **Status / author decision:** Proposal; no separate approval recorded.
- **Agreed replacement text:** Pending; no final wording approved in the supplied discussion.
- **Implemented:** No.

