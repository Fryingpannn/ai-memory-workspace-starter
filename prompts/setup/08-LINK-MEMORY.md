# Stage 8: Link the Hermes Harness to Shared Memory

Use the canonical root `AGENTS.md` produced by Hermes `/init`, explicitly preserved from
before setup, or supplied by the documented fallback. This stage adds only the shared
memory and repository routing that native `/init` could not infer before personalization.

The root `USER.md` is the canonical portable user profile. `wiki/index.md` points to it;
do not create a duplicate wiki profile.

Use this exact block, adding only lines not already represented:

```text
## Shared Workspace Routing

- Read `USER.md` for confirmed user context and working preferences.
- Use `wiki/index.md` as long-term memory and follow `wiki/SCHEMA.md` when storing durable entities and relationships.
- Read `projects/index.md` before entering a child project.
- Before work requiring current code, fast-forward the outer tracked branch when a remote exists, then update submodules recursively to the commits pinned by the parent. If no outer remote exists, report that the workspace is local-only and continue from verified local state. Preserve local changes and stop on divergence.
```

## Canonical AGENTS.md

- If Hermes created a new `AGENTS.md` in Stage 4, append or merge the block and show the
  exact diff.
- If native `/init` failed and the starter fallback was used, keep its equivalent
  routing and remove no content.
- If `AGENTS.md` existed before setup, do not replace it. Show the exact proposed block
  and insertion location, then ask for confirmation.
- Never duplicate equivalent instructions.

For a fallback default only, replace bracketed purpose placeholders with user-confirmed
information and show the values.

## CLAUDE.md Compatibility Bridge

`AGENTS.md` remains canonical. A missing `CLAUDE.md` receives the starter bridge:

```text
Read AGENTS.md. It is the canonical entry document for this workspace. Everything there applies here.
```

If `CLAUDE.md` existed before setup and lacks an equivalent reference, show that exact
line and insertion location, then ask before adding it. Do not copy the full routing
block into `CLAUDE.md`.

Show the exact diff before continuing.
