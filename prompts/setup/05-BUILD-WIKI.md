# Stage 5: Build the Long-Term Wiki

Read the confirmed workspace purpose from the root `USER.md`. If the user declined
onboarding and the purpose is still unknown, ask only for that one sentence.

Spawn one clean-context wiki architect subagent when supported.

Give it:

- the confirmed outer workspace root;
- this prompt;
- the confirmed workspace purpose from `USER.md`;
- Andrej Karpathy's LLM Wiki idea file:
  `https://gist.githubusercontent.com/karpathy/442a6bf555914893e9891c11519de94f/raw/ac46de1ad27f92b28ac95459c782c07f6b8c964a/llm-wiki.md`

The source communicates the design pattern. Adapt it to this workspace; do not copy it
verbatim.

## Required Architecture

Use three layers:

1. raw sources that remain unchanged;
2. an incrementally maintained, interlinked Markdown wiki;
3. a local schema that tells agents how to ingest, query, and maintain it.

Create missing pieces under the outer workspace root:

```text
wiki/
├── index.md
├── SCHEMA.md
├── inbox.md
├── log.md
├── pages/
└── raw/
```

Preserve existing wiki files. Propose additions rather than replacing them.
If a wiki already contains user content, show the adaptation plan and ask before
editing it.

## Wiki Rules

- `wiki/index.md` is the discovery map and must link every durable page.
- `wiki/SCHEMA.md` defines page types, links, sourcing, ingest, query, and lint rules.
- `wiki/log.md` is append-only and uses dated, consistently formatted entries.
- `wiki/raw/` preserves source records; wiki pages synthesize them.
- Durable entities and relationships become linked Markdown pages.
- New evidence may update several related pages and must preserve provenance.
- Contradictions, uncertainty, and stale claims must be visible.
- Do not add vector search, embeddings, a database, or RAG.

Seed only confirmed workspace-level knowledge. Project-specific knowledge is added in
Stage 6. Link the root `USER.md` from `wiki/index.md`; do not duplicate personal facts
in a wiki user-profile page.

Return the created or changed files and the proposed wiki schema for user review.
