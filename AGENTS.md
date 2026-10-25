# Article workflow for agents

## Read first

Read `README.md`, `PUBLISHING.md`, then the selected article's `metadata.json`, `context/README.md`, `context/decisions.md`, `context/improvements.md`, relevant conversations/materials, and finally `article.md`.

## Sources of truth

- `article.md`: canonical current article, default Markdown deliverable.
- `context/conversations/`: append-only supplied conversation records. Label verbatim excerpts versus summaries; do not fabricate missing turns or claim an abridgment is a full transcript.
- `context/decisions.md`: explicit author choices with provenance. Assistant recommendations are proposals until accepted.
- `context/improvements.md`: stable IDs, proposal, strong reasoning, status, author decision and agreed wording. Never renumber or silently approve items.
- `materials/`: supporting evidence, references, code, diagrams and publication comparison reports. Attribute evidence and record limitations.
- `publications/`: channel-specific derivatives, never an independent source of architectural claims.
- `metadata.json`: title, source location, public URLs and migration provenance; do not infer publication status from front matter alone.

## Context updates

On an explicit context-sync request, append available relevant conversation, update the concise index and decisions, preserve objections and unresolved questions, and report unavailable history honestly. Keep original-language author statements. Never include unrelated personal or employer details. Do not fetch or export every past chat automatically.

## Editing and generation

Use approved decisions and source materials to produce the article. Context alone does not authorize applying every suggestion. Maintain the author's unified-vision thesis, substantive distinctions and voice. Surface unsupported generalizations for discussion instead of silently inventing evidence. Do not generate a new article or platform adaptation during a structural migration.

For derivatives follow `PUBLISHING.md`. Record the exact source commit, context used, date, audience, changes and publication state. A LinkedIn post is an editorial adaptation; HTML conversion is a format transformation. Distinguish these operations. Never mark an output as published merely because it was generated.

## Validation

Check file/link integrity and migration blob identity. For substantive revisions check approved items, terminology and supporting evidence. For publication comparisons specify whether source Markdown, rendered text or a cached extraction was compared; list differences and limitations. Never claim byte equality after comparing only rendered text.
