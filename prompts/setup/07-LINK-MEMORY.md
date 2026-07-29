# Stage 7: Link Agents to Long-Term Memory

The wiki exists independently of any one model or harness. This stage makes it
discoverable from future Codex and Claude sessions.

The root `USER.md` is the canonical portable user profile. `wiki/index.md` points to it;
do not create a duplicate wiki profile.

Use this exact one-line bridge:

```text
Read `USER.md` for confirmed user context. Use `wiki/index.md` as long-term memory and follow `wiki/SCHEMA.md` to store durable entities and relationships as an interlinked Markdown knowledge graph.
```

## Missing Operating Files

If `AGENTS.md` or `CLAUDE.md` did not exist before setup, the scaffold stage may add
the starter default containing this route.

For a newly created default only, replace bracketed purpose placeholders with
user-confirmed information. Show the proposed values first.

## Existing Operating Files

If either file existed before setup:

1. Do not replace or rewrite it.
2. Show the exact one-line bridge and proposed insertion location.
3. Ask the user for confirmation.
4. If approved, insert only that line.
5. If declined, record that wiki routing must be invoked manually.

Do not add broader policy, rewrite formatting, or duplicate equivalent existing
instructions.

Show the exact diff before continuing.
