# Wiki Schema

This wiki is the workspace's long-term, interlinked knowledge layer.

The root `USER.md` is the canonical portable user profile. Link to it from
`wiki/index.md`; do not duplicate it under `wiki/pages/`.

## Layers

- `raw/`: source records and provenance; do not silently rewrite source material.
- `pages/`: maintained synthesis about entities, concepts, projects, and decisions.
- `index.md`: discovery map for every durable page.
- `log.md`: append-only history of ingests, updates, queries, and lint passes.
- `inbox.md`: unprocessed or uncertain material.

## Page Rules

- Give one durable subject or relationship a clear home.
- Link related pages using relative Markdown links.
- Cite the source file or user confirmation behind durable claims.
- Mark uncertainty, contradictions, and stale claims explicitly.
- Update all affected pages when new evidence changes an existing relationship.
- Keep current project state in project files; the wiki stores durable synthesis.

## Operations

### Ingest

Read approved sources, discuss uncertain conclusions, update affected pages and the
index, then append a dated log entry.

### Query

Read `index.md` first, follow only relevant links, and cite the local pages and sources
used. Read the linked root `USER.md` when user context matters. File durable new
synthesis back into the wiki when the user approves.

### Lint

Check for contradictions, stale claims, orphan pages, missing links, unsupported claims,
and important entities without pages.

## Log Format

```text
## [YYYY-MM-DD] action | Short title
```

Vector search, embeddings, databases, and RAG are not required for this starter.
