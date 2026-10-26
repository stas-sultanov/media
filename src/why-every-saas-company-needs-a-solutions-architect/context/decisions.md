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
