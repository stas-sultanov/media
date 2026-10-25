# DEV publication comparison — 2026-10-25

## Inputs

- Repository: `stas-sultanov/media`, branch `main`, source commit `e28af2097c65ac32b365827f26e7b9710d8cb91c`.
- Original file: `src/why-every-saas-company-needs-a-solutions-architect.md`.
- Original blob: `2d895a992b99daeb50f32e9fec0bf976f40c5d66`.
- Migrated file: [article.md](../article.md); content preserved unchanged.
- Public page: https://dev.to/stas-sultanov/why-every-saas-company-needs-a-solutions-architect-31a1

## Method and limitation

Compared the complete repository Markdown with the article body in the web retrieval's rendered-text extraction, from the introductory paragraph through the conclusion and author footer. The retrieval reports a crawl from last month; its text must not be treated as proof of the live page's exact current state. The page displays “Posted on Oct 28, 2025 • Edited on Jan 12” without a year on the edit label.

Attempting the public DEV article API through the local network returned HTTP 403. The web retrieval tool also could not access that API endpoint. Therefore no fresh public Markdown body was obtained and byte-for-byte or current-live synchronization is not confirmed.

## Differences visible in the retrieved page

| Location | Repository | Retrieved DEV article |
| --- | --- | --- |
| Title | No title heading or front matter in the source body; represented by filename | Page title: Why Every SaaS Company Needs a Solutions Architect |
| CTO assumption | “so they can also do the SA job.” | “so can also do the SA job.” |
| Footer | Ends after the final SA/function statement | Adds a separator and a coffee-support link to https://ko-fi.com/stas_sultanov |
| Layout | Markdown emphasis, list syntax and blank lines | Rendered page; whitespace/layout differs |

The substantive sections and argument align in this comparison; no additional substantive textual difference was identified. Both retain the typo “Infrastructure realtiy”. Proposed SA-01–SA-18 revisions are not present in the repository source or the retrieved public text.

## Result

**Substantively aligned with the retrieved DEV text, but not identical; exact current live equality remains unverified.** No article or public-site content was changed during this comparison. Recheck against a fresh DEV source/export before a future publication sync.
