# Workspace Instructions

## Purpose

This workspace helps [OWNER OR TEAM] manage [AREAS OF WORK] and produce
[IMPORTANT OUTPUTS].

## Start Here

1. Read `AGENTS.md`.
2. Read `README.md`.
3. Read `USER.md` for confirmed user context and working preferences.
4. Use `wiki/index.md` as long-term memory and follow `wiki/SCHEMA.md` to store durable entities and relationships as an interlinked Markdown knowledge graph.
5. Read `projects/index.md` when project context matters.
6. Inspect only the files needed for the current task.

## Workspace Map

- `projects/index.md`: tracked project discovery map
- `projects/<project-id>.md`: tracked project profiles
- `projects/local-paths.md`: gitignored locations for external projects
- `USER.md`: canonical portable user profile for this workspace
- `skills/`: reusable procedures
- `outputs/`: reviewable deliverables
- `memory/`: recent dated working context
- `wiki/pages/`: durable facts and decisions
- `wiki/raw/`: source records and evidence
- `wiki/SCHEMA.md`: knowledge structure and maintenance rules
- `wiki/index.md`: discovery map for durable knowledge
- `wiki/inbox.md`: unsynthesized material queue
- `wiki/log.md`: dated durable-wiki changes

## Read Routing

- Treat the current chat as temporary.
- Use `projects/index.md` to discover connected projects.
- Read the project profile before opening a connected project.
- Use a profile's root-relative path for projects inside this workspace.
- Use `projects/local-paths.md` only for projects outside this workspace.
- Read the newest relevant `memory/YYYY-MM-DD.md` when recent state matters.
- Use `wiki/index.md` to find durable facts and decisions.
- Open `wiki/raw/` only when provenance or verification is needed.

## Write-Back Routing

- Put recent working context in `memory/YYYY-MM-DD.md`.
- Update `USER.md` only with compact, durable, user-confirmed profile information.
- Put durable facts and decisions in `wiki/pages/`.
- Link new durable pages from `wiki/index.md` and log them in `wiki/log.md`.
- Put unprocessed sources in `wiki/raw/` or queue them in `wiki/inbox.md`.
- Put cross-project discovery information in `projects/index.md`.
- Put stable project summaries in `projects/<project-id>.md`.
- Keep machine-specific external-project paths only in `projects/local-paths.md`.
- Put reusable procedures under `skills/`.
- Put reviewable deliverables under `outputs/`.

## Source-of-Truth Rules

- `AGENTS.md` is canonical for operating rules.
- `USER.md` is canonical for portable user context in this workspace.
- `wiki/pages/` is canonical for durable synthesis.
- `wiki/raw/` preserves source records.
- Project files are canonical for current project state.
- Project profiles summarize projects but do not replace their source files.
- `projects/local-paths.md` is external-project connection data, not durable knowledge.
- `memory/` is recent context, not the permanent home for durable decisions.
- `outputs/` contains deliverables, not memory.
- `CLAUDE.md` is only a compatibility bridge.

## Working Rules

- Preserve existing work and unrelated changes.
- Before work that needs current Git-backed project state, fetch and fast-forward the
  outer repository from its tracked remote default branch, normally `origin/main`.
- For submodules, sync URLs and update recursively to the commits pinned by the outer
  repository. Do not independently advance a submodule beyond its pinned commit.
- Preserve local changes and stop on divergence instead of overwriting work.
- Load the smallest relevant context.
- Cite the local file used for durable claims.
- Do not broadly scan connected project source code when high-signal docs are enough.
- Do not move, copy, or rewrite a connected project without approval.
- Never invent missing context. Stop and report what is missing.
- Never commit passwords, API keys, tokens, credentials, or secret environment files.
- Ask before publishing, sending messages, or taking irreversible external actions.

## Definition of Done

- The requested artifact exists.
- The result is verified.
- Durable decisions are written to the correct file.
- Git status is reviewed.
