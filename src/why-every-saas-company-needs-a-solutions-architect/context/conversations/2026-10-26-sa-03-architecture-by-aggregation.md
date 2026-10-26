# SA-03 — Architecture by aggregation — 2026-10-26

Record of the article-related SA-03 discussion supplied in this session. Quoted author statements and the English proposal are verbatim; explanatory passages are summaries. Repeated readings and operational acknowledgments are omitted. This is not a full transcript of every message or tool action.

## Proposal — summary and verbatim wording

After SA-02 was committed, the author requested the next improvement. The assistant introduced SA-03: explain why a collection of narrow or partial perspectives does not automatically replace a sufficiently competent Solutions Architect with an integrated understanding of the solution.

The proposed addition was:

> A committee of partial views does not create one complete mind; they lack shared context and unified accountability.

The proposed location was in “How does the SA do this in practice?”, after the paragraph beginning “This process cannot be reliably split across multiple roles.”, including the approved SA-02 sentence, and before “Only when a single role owns this process end to end does the balance hold and the product remain viable.”

## Author request to review the section — verbatim

> Так, давай-ка прочитай мне всю секцию целиком, где мы хотим это вставить. Ты считаешь секцию, говоришь ба-ба-ба-ба А тут мы хотим ставить вот это и читаешь до конца

The assistant read the surrounding process/vision passage, identified the proposed SA-03 insertion, and continued through the section's final two sentences. The supplied continuation summarizes the earlier process steps rather than quoting them all.

## Reviewed ending, including the proposed insertion

> This process cannot be reliably split across multiple roles. Activities can be delegated, but the solution vision can only live in one mind, with corresponding accountability for decisions. When it is fragmented, every group protects its own priority, and nobody owns the balance.
>
> A committee of partial views does not create one complete mind; they lack shared context and unified accountability.
>
> Only when a single role owns this process end to end does the balance hold and the product remain viable.
>
> That single accountable role is the **Solutions Architect**.

The committee sentence is the proposed addition; the other sentences above are the existing source at [commit 6c95061](https://github.com/stas-sultanov/media/blob/6c950618d7cdaaa1c92a79234f200f492206d069/src/why-every-saas-company-needs-a-solutions-architect/article.md).

## Author approval and implementation request — verbatim

> Угу. Хорошо, да, давай вставляем, добавляем

## Outcome — summary

The author approved the exact proposed sentence and its reviewed placement. It is implemented as a separate paragraph in [article.md](../../article.md), with the remaining article text preserved. The change follows the agreed one-commit-per-SA-item workflow and resolves only SA-03.

The rationale is the author's distinction between contributing partial expertise and maintaining an integrated understanding with unified accountability. It supplements SA-02's distinction between delegated activities and a unified solution vision.

See [author decision](../decisions.md#sa-03--architecture-by-aggregation--2026-10-26) and [backlog entry](../improvements.md#sa-03--explain-architecture-by-aggregation).
