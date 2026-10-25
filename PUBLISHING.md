# Publication formats

Each article's `article.md` is the canonical Markdown document. Generate additional variants only when requested. Existing DEV front matter is retained during migration; future editorial normalization must be explicit.

| Channel | Deliverable path relative to article | Adaptation |
| --- | --- | --- |
| Markdown (default) | `article.md` | Full canonical article. |
| DEV Community | `publications/devto/article.md` | Full article, channel metadata/front matter as needed; preserve links and code. |
| LinkedIn post | `publications/linkedin/post.txt` | Plain-text post adapted for feed reading, with a clear opening and requested link strategy. Do not mechanically truncate the article. Verify current platform limits when generating. |
| LinkedIn article | `publications/linkedin/article.html` | Full-length editorial adaptation as simple import/copy HTML; verify platform support before upload. |
| Medium | `publications/medium/article.html` | Simple semantic HTML preserving headings, links, lists, images and code; verify the current import/copy workflow before delivery. |
| Generic HTML | `publications/html/article.html` | Standalone UTF-8 HTML with escaped content and readable layout. |

Beside each generated variant create `generation.json` containing `source_commit` (full SHA), `canonical_path`, `context_paths`, `generated_on`, `channel`, `adaptation_notes` and `publication_status` (initially `not_published`). Never invent source revisions or publication URLs.

These are generation instructions for agents, not an automated publishing pipeline or a promise that platform-specific files already exist. Keep generated content traceable to canonical text and accepted decisions. Cross-check meaning, links, code, rendering and platform constraints. External publication is a separate explicitly requested action.
