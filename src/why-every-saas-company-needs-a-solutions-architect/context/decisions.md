# Author decisions

## Repository workflow — 2026-10-25

The author requested a directory per article containing the full available article-related context, conversations and supporting materials, to be used when generating the final article. Markdown is the default; other channels, including LinkedIn and Medium, must be supported by the workflow.

This migration preserves the existing article text. It does not approve all editorial proposals.

## Article direction — supplied review discussion

- The author insists on an integrated architectural vision holder. Multiple SAs may contribute; several people with partial competence do not automatically replace a sufficiently competent architect.
- The author explicitly requested adding the distinction that internal promotion provides title and mandate, but not missing skills/experience.
- The author proposed an opening scope note: many IT solutions need an SA; this article focuses on SaaS. Final wording is still to be agreed.
- The author defended the practical, defined-period external-SA acquisition model. Do not remove it based on the assistant's initial objection. Exact presentation and alternatives remain proposals.
- The author rejected the claim that the experience profile was almost impossible, citing their own experience. The assistant withdrew that characterization.
- The review backlog and five-block organization are working proposals. No blanket approval or agreed final replacement prose was supplied.

## History preservation — renewed instruction, 2026-10-25

The author explicitly requested implementing the repository structure and saving all available discussion about the current article changes in GitHub for history. The structure was already present when checked. The [dialogue supplement](conversations/2026-10-25-review-dialogue-supplement.md) now preserves both sides of the substantive review, including original objections, subsequent corrections, proposed wording and the original 18-item list. It supplements the earlier excerpts and summary; it does not replace them or change proposal approvals. The canonical article remains unchanged by this context sync.

## SA-01 — Business scope introduction — 2026-10-26

- **Status:** Approved by the author and implemented in [article.md](../article.md).
- **What changed:** Prepended the agreed scope paragraph before the existing opening. The rest of the article is preserved.
- **Why:** Explain the article's focus from the company's business perspective. In SaaS, the IT solution itself is the product; building and operating it is the core of the business. This makes the SA role especially important.
- **Author correction:** Focus on types of businesses rather than types of IT solutions.
- **Wording choice:** “Especially important” avoids implying that the SA is the most important role in the company.
- **Provenance:** The author corrected the initial framing, reviewed the final paragraph, and authorized insertion with “Отлично. Добавляй”. See [discussion excerpts and approval](conversations/2026-10-26-sa-01-scope.md).
- **Scope:** This decision resolves the earlier pending SA-01 wording. It does not approve other backlog items.
- **Agreed addition:**

> While many businesses that rely on IT solutions need an IT Solutions Architect, this article focuses on SaaS companies, where the IT solution itself is the product. Building and operating it is the core of the business, making the Solutions Architect’s role especially important.

## SA-02 — Delegated activities and solution vision — 2026-10-26

- **Status:** Approved by the author and implemented in [article.md](../article.md).
- **What changed:** Added one sentence immediately after “This process cannot be reliably split across multiple roles.” in “How does the SA do this in practice?”.
- **Why:** Distinguish delegable activities from the author's requirement for an integrated solution vision held in one mind, with corresponding accountability for decisions.
- **Author corrections:** Use “solution vision” rather than “architectural vision” to retain a broader vision of the solution; use “can only” rather than “must” to express the intended restriction rather than a prescriptive instruction.
- **Provenance:** The author approved the final sentence with “Да, так и оставляем” and then authorized the separate-commit workflow with “Давай”. See [discussion excerpts and approvals](conversations/2026-10-26-sa-02-solution-vision.md).
- **Scope:** Only SA-02 is resolved by this change. Other backlog items retain their existing status.
- **Agreed addition:**

> Activities can be delegated, but the solution vision can only live in one mind, with corresponding accountability for decisions.

## Revision commit workflow — 2026-10-26

The author asked whether to apply revisions together or as separate commits, accepted the recommendation of one commit per approved SA item, and authorized SA-02 on that basis. Each such commit includes the article change together with its date, rationale, agreed wording, discussion provenance and backlog status. See [workflow discussion](conversations/2026-10-26-sa-02-solution-vision.md#commit-workflow-discussion--verbatim).

## SA-03 — Architecture by aggregation — 2026-10-26

- **Status:** Approved by the author and implemented in [article.md](../article.md).
- **What changed:** Added the agreed sentence as a separate paragraph after the process/vision paragraph in “How does the SA do this in practice?”, before “Only when a single role owns this process end to end does the balance hold and the product remain viable.”
- **Why:** Explain why combining partial perspectives does not automatically supply the integrated understanding and unified accountability expected from the SA. This supports the distinction between delegated work and unified solution vision established in SA-02.
- **Provenance:** After the assistant read the surrounding passage and identified the insertion, the author approved with “Угу. Хорошо, да, давай вставляем, добавляем”. See [discussion and approval](conversations/2026-10-26-sa-03-architecture-by-aggregation.md).
- **Scope:** Only SA-03 is resolved by this change; other backlog statuses are preserved. The article addition and supporting history belong to one separate SA-03 commit.
- **Agreed addition:**

> A committee of partial views does not create one complete mind; they lack shared context and unified accountability.

## SA-04 — Multiple SAs and end-to-end accountability — 2026-10-26

- **Status:** Approved by the author and implemented in [article.md](../article.md).
- **What changed:** Added the agreed sentence as a separate paragraph after the SA-03 committee paragraph and before the section's concluding “Only when a single role owns this process end to end…” statement.
- **Why:** Clarify that a large product may have several Solutions Architects while accountability for the complete solution remains clearly owned. This preserves the unified-vision thesis without implying that only one architect may contribute.
- **Provenance:** After hearing the section with the proposed insertion, the author authorized the change with “Да? Хорошо. Добавь”. See [discussion and approval](conversations/2026-10-26-sa-04-multiple-architects.md).
- **Scope:** Only SA-04 is resolved by this change. Other backlog statuses and the surrounding article are preserved. The article addition and supporting history belong to one separate SA-04 commit.
- **Agreed addition:**

> Large products may have more than one Solutions Architect, but accountability for the end-to-end solution must be clearly owned.

## SA-05 — Promotion and competence — 2026-10-26

- **Status:** Approved by the author and implemented in [article.md](../article.md).
- **What changed:** Added the agreed sentence as a separate paragraph in “3. Level up an internal employee”, after the assumption and before “This rarely succeeds. Correct judgment in this role…”.
- **Why:** Promotion grants formal title and mandate; it does not itself create missing competence. The author emphasized that this applies even within the person's original specialty, such as .NET engineering, rather than only to experience with other systems, domains or technologies.
- **Author correction:** Reject the narrower “other systems” emphasis and use the general statement about competence.
- **Provenance:** The author approved the revised sentence with “Да” and confirmed the assistant's plan to implement SA-05 as a separate commit with a second “Да”. See [discussion and approvals](conversations/2026-10-26-sa-05-promotion-and-competence.md).
- **Placement clarification:** The initial assistant response named “Who can play this role?” while referring to the internal-promotion passage. The insertion is in the actual “Level up an internal employee” subsection, where the agreed sentence directly precedes the existing explanation.
- **Scope:** Only SA-05 is resolved by this change. Other backlog statuses and the remaining article text are preserved.
- **Agreed addition:**

> Promotion grants title and mandate, not competence.

## SA-06 — Mentoring constraints and varied experience — 2026-10-26

- **Status:** Approved by the author and implemented in [article.md](../article.md).
- **What changed:** Added the shortened mentor sentence after SA-05 in “3. Level up an internal employee”. Replaced the five bullets beginning with “multiple” with the approved continuous enumeration.
- **Why:** Make the missing-mentor constraint explicit. Avoid repeating SA-05's point about promotion and competence, and remove the monotonous repetition of “multiple” in the experience examples.
- **Author corrections:** Remove “promotion alone doesn’t create the competence” from the new sentence; use one continuous enumeration instead of repeating “multiple” in every list item.
- **Provenance:** After reviewing and shortening the proposed text, the author accepted the enumeration with “Хреново звучит Да, оставляем так”, then explicitly confirmed the separate-commit implementation with “Да, давай”. See [discussion and approval](conversations/2026-10-26-sa-06-mentoring-and-experience.md).
- **Scope:** Only SA-06 is resolved by this change. Other backlog statuses and the rest of the article are preserved. The colon/list transition is joined to the approved “across” phrase as continuous prose.
- **Agreed addition:**

> Without an experienced SA to mentor, a SaaS company rarely develops one.

- **Agreed experience enumeration:**

> across different customers and business models, domains with different regulatory traps, technology stacks and scaling problems, production outages and cost crises.

- **Resulting explanation:**

> This rarely succeeds. Correct judgment in this role comes from years of exposure to different pressures and failures across different customers and business models, domains with different regulatory traps, technology stacks and scaling problems, production outages and cost crises.

## SA-07 — Consulting-company caveat skipped — 2026-10-26

- **Status:** Skipped by the author; no change to [article.md](../article.md).
- **Proposal considered:** Add a final paragraph to “3. Level up an internal employee” describing mature consulting companies with experienced SA mentors, a structured development process and exposure to different clients, domains and solutions.
- **Why omitted:** The existing “rarely” and “usually” wording already permits exceptions. Explaining how consulting companies develop architects would distract from the article's SaaS focus.
- **Provenance:** After hearing the proposed caveat in context, the author asked “А вообще нам это надо” and accepted the recommendation to omit it with “Отлично, пропускаем и идем дальше”. See [discussion and final decision](conversations/2026-10-26-sa-07-consulting-exception-skipped.md).
- **Scope:** This closes SA-07 as skipped and supersedes the earlier invitation to explore the addition. It does not approve or apply any other item.

## SA-08 — Depth and breadth behind experience — 2026-10-26

- **Status:** Approved by the author and implemented in [article.md](../article.md).
- **What changed:** Added the agreed sentence as a separate paragraph in “Who can play this role?”, immediately before “A strong SA typically has:”.
- **Why:** Explain that the stated years must reflect deep practical expertise, responsibility for production outcomes and experience across different business and technical conditions.
- **Seniority preserved:** Existing Software and Infrastructure year thresholds and the rest of the requirements list are retained. The SA-06 paragraph about varied experience inside the internal-development subsection is not changed.
- **Provenance:** The author asked for the before-and-after wording and the concrete addition, then approved the exact sentence and placement with “Да. Берем”. See [discussion and approval](conversations/2026-10-26-sa-08-depth-and-breadth.md).
- **Scope:** Only SA-08 is implemented by this article edit. SA-07 remains skipped; all other statuses are preserved.
- **Agreed addition:**

> The years of experience described below must reflect deep hands-on expertise, responsibility for production outcomes, and exposure to different business and technical conditions.

## SA-09 — External engagement of at least 12 months — 2026-10-26

- **Status:** Approved and implemented.
- **Change:** Replaced the first paragraph of “How can a company get a Solutions Architect?” with the agreed wording below.
- **Why:** Allow time to understand business, domain, solution and team, address organizational constraints, and deliver improvements into production. The minimum year is the author's planning recommendation, not a universal measured threshold.
- **Author correction:** Replace 12–36 months with at least 12 months; do not require a successor or assume an internal employee will become qualified during the engagement.
- **Provenance:** [Discussion](conversations/2026-10-26-sa-09-engagement.md); final paragraph approved with “окей”.

> The most realistic approach is to engage a senior Solutions Architect from outside the company. Plan for at least 12 months: the architect needs time to understand the business, domain, solution, and team, work through organizational constraints, and carry improvements through implementation into production.

## SA-10 — Covered by SA-09 — 2026-10-26

- **Status:** Closed as covered by SA-09; no additional article edit.
- **Why:** SA-09 replaced the dedicated-contractor wording with “engage a senior Solutions Architect from outside the company”, allowing both permanent recruitment and contract engagement. Another paragraph would duplicate that clarification.
- **Author approval:** “ок.\nзапиши и идавай дальше”.
- **History:** [Discussion summary and approval](conversations/2026-10-26-sa-10-covered.md).

## SA-11 — Covered by SA-02–SA-04 — 2026-10-26

- **Status:** Closed as covered; no additional article edit.
- **Why:** Existing edits require unified solution vision and individual accountability regardless of whether the architect comes from a consultancy. A consultancy-specific repetition adds no new principle.
- **Author approval:** “окей. да . давай дальше”.
- **History:** [Discussion summary](conversations/2026-10-26-sa-11-covered.md).

## SA-12 — Remove intrinsic short-tenure claim — 2026-10-26

- **Status:** Approved and implemented.
- **Change:** Deleted the entire paragraph beginning “Note that SAs, by nature, don’t stay long at a single company” from “How can a company get a Solutions Architect?”.
- **Why:** Varied experience is already explained. Its value does not imply an experienced architect must keep changing companies. The paragraph also creates an unnecessary expectation of early departure.
- **Author approval:** The assistant proposed deleting the complete paragraph with this rationale; the author replied “да”.
- **History:** [Discussion and removed text](conversations/2026-10-26-sa-12-tenure.md).
- **Scope:** Only this paragraph is removed; all remaining article text and other backlog statuses are preserved.

## SA-13 — Vendor incentives and accountability — 2026-10-26

- **Status:** Approved and implemented.
- **Change:** Replaced the two explanatory paragraphs following “Assumption…” in “4. Borrow from a vendor”.
- **Why:** Explain the structural difference in commercial interests, delivery obligations and accountability. Avoid the unsupported universal claim that vendor architects will always be forced to prioritize their employer.
- **Author approval:** “отлично . да”, approving the exact replacement below.
- **History:** [Original wording, proposal and approval](conversations/2026-10-26-sa-13-vendor-incentives.md).
- **Scope:** Only SA-13 is applied; the heading, assumption and rest of the article are preserved.
- **Agreed replacement:**

> A vendor-provided architect operates within their employer’s commercial interests and delivery obligations. These may align with the SaaS company’s interests, but that alignment cannot be assumed.
>
> The SaaS company needs a Solutions Architect accountable for the whole solution, including decisions that may conflict with the vendor’s interests.

## SA-14 — Function versus formal title — 2026-10-26

- **Status:** Approved and implemented.
- **Change:** Inserted the agreed paragraph as a Markdown blockquote after “That role is the **Solutions Architect**.” and before the section separator preceding “What does a Solutions Architect actually do?”.
- **Why:** A different formal job title does not remove the need for the qualified person, authority, time and end-to-end accountability described in the article. This keeps the argument focused on the function.
- **Author refinement:** Add “Of course” and explicitly state that the title itself does not matter. The assistant clarified the English distinction between “does not matter” and “does not make sense”.
- **Approval and formatting:** The author accepted the final wording with “отлично”, then requested “отлично и добавим это как quote”. The approved text is therefore formatted as a blockquote in the article.
- **History:** [Discussion and approval](conversations/2026-10-26-sa-14-formal-title.md).
- **Scope:** Only SA-14 is applied; all existing article text and other backlog statuses are preserved.
- **Agreed addition:**

> Of course, the formal job title may differ. The title itself does not matter; what matters is that a qualified person has the authority, time, and end-to-end accountability to perform this role.

## SA-15 — Vision and Demand/Capability in the conclusion — 2026-10-26

- **Status:** Approved and implemented.
- **Change:** Replaced the conclusion paragraph beginning “With an SA, that balance is actively protected” with the approved paragraph below.
- **Why:** Leave the reader with the concrete purpose of the SA: maintain a coherent vision of the whole solution and continuously balance business/domain demand against software/infrastructure capability.
- **Author approval:** “да”, in response to the exact proposed replacement and rationale.
- **History:** [Original, proposal and approval](conversations/2026-10-26-sa-15-conclusion.md).
- **Scope:** Only this conclusion paragraph is changed; other article text and backlog statuses are preserved.

> The SA maintains a coherent vision for the whole solution and continuously balances Demand (Business + Domain) against Capability (Software + Infrastructure). This keeps the product deliverable, operable, and economically viable.

## SA-16 — Local decisions and business consequences — 2026-10-26

- **Status:** Approved and implemented.
- **Change:** Replaced the two sentences following the group-priority list in “Why does no one own the balance?” with the approved paragraph below.
- **Why:** Explain the mechanism from local decisions to duplication, conflicting designs, operational complexity and business costs, failures and delivery delays.
- **Author refinement:** Add “However” before “without” to connect individually rational priorities to their combined consequences.
- **Author approval:** “отлично . принимаем записываем и дальше”.
- **History:** [Original, refinement and approval](conversations/2026-10-26-sa-16-local-decisions.md).
- **Scope:** Only SA-16 is applied; all other article text and backlog statuses are preserved.

> Individually, each of these priorities is rational. However, without someone evaluating their combined impact on the whole solution, local decisions can create duplicated capabilities, conflicting designs, and growing operational complexity. The business pays through higher costs, more failures, and slower delivery.

## SA-17 — Continue through implementation and operation — 2026-10-26

- **Status:** Approved and implemented.
- **Change:** Expanded the final process bullet in “How does the SA do this in practice?” to include operation and using production feedback and incident findings to refine the evolving solution.
- **Why:** Consequences of architectural decisions emerge during operation; the SA needs to use that experience in the solution's continued development.
- **Author approval:** “подходит”, in response to the exact replacement below.
- **History:** [Original, proposed wording and approval](conversations/2026-10-26-sa-17-operation.md).
- **Scope:** Only the agreed process bullet changes. Other article text and backlog statuses are preserved.
- **Agreed replacement:**

- **Stay through implementation and operation**: ensure what gets delivered still matches that agreed shape and has not been quietly degraded into something unstable, unmaintainable, or unprofitable. Use production feedback and incident findings to refine the solution as it evolves.
