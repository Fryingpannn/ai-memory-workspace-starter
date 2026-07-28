# Workspace Instructions

## Purpose

This workspace helps [OWNER OR TEAM] manage [AREAS OF WORK] and produce
[IMPORTANT OUTPUTS].

## Start Here

1. Read `AGENTS.md`.
2. Read `README.md`.
3. Inspect only the files needed for the current task.

## Workspace Map

- `projects/`: active work and current project state
- `docs/`: operating references
- `skills/`: reusable procedures
- `outputs/`: reviewable deliverables
- `memory/`: recent dated working context
- `wiki/pages/`: durable facts and decisions
- `wiki/raw/`: source records and evidence
- `wiki/index.md`: discovery map for durable knowledge
- `wiki/inbox.md`: unsynthesized material queue
- `wiki/log.md`: dated durable-wiki changes

## Read Routing

- Treat the current chat as temporary.
- Read the newest relevant `memory/YYYY-MM-DD.md` when recent state matters.
- Use `wiki/index.md` to find durable facts and decisions.
- Open `wiki/raw/` only when provenance or verification is needed.

## Write-Back Routing

- Put recent working context in `memory/YYYY-MM-DD.md`.
- Put durable facts and decisions in `wiki/pages/`.
- Link new durable pages from `wiki/index.md` and log them in `wiki/log.md`.
- Put unprocessed sources in `wiki/raw/` or queue them in `wiki/inbox.md`.
- Put active work under `projects/`.
- Put reusable procedures under `skills/`.
- Put reviewable deliverables under `outputs/`.

## Source-of-Truth Rules

- `AGENTS.md` is canonical for operating rules.
- `wiki/pages/` is canonical for durable synthesis.
- `wiki/raw/` preserves source records.
- Project files are canonical for current project state.
- `memory/` is recent context, not the permanent home for durable decisions.
- `outputs/` contains deliverables, not memory.
- `CLAUDE.md` is only a compatibility bridge.

## Working Rules

- Preserve existing work and unrelated changes.
- Load the smallest relevant context.
- Cite the local file used for durable claims.
- Never invent missing context. Stop and report what is missing.
- Never commit passwords, API keys, tokens, credentials, or secret environment files.
- Ask before publishing, sending messages, or taking irreversible external actions.

## Definition of Done

- The requested artifact exists.
- The result is verified.
- Durable decisions are written to the correct file.
- Git status is reviewed.

