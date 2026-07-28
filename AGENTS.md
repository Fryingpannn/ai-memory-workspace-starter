# Workspace Instructions

## Setup Routing

- If the user says "set up this project", "set up this workspace", or similar while
  starter placeholders remain, read `prompts/HERMES-SETUP.md`.
- Follow its staged setup prompts in order.
- Do not move, copy, symlink, or edit existing projects during setup without approval.

## Purpose

This workspace helps [OWNER OR TEAM] manage [AREAS OF WORK] and produce
[IMPORTANT OUTPUTS].

## Start Here

1. Read `AGENTS.md`.
2. Read `README.md`.
3. Read `projects/index.md` when project context matters.
4. Read `projects/local-paths.md` only when a connected project must be located.
5. Inspect only the files needed for the current task.

## Workspace Map

- `projects/index.md`: tracked project discovery map
- `projects/<project-id>.md`: tracked project profiles
- `projects/local-paths.md`: gitignored machine-local project locations
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
- Use `projects/index.md` to discover connected projects.
- Read the project profile before opening a connected project.
- Use `projects/local-paths.md` to locate projects on this machine.
- Read the newest relevant `memory/YYYY-MM-DD.md` when recent state matters.
- Use `wiki/index.md` to find durable facts and decisions.
- Open `wiki/raw/` only when provenance or verification is needed.

## Write-Back Routing

- Put recent working context in `memory/YYYY-MM-DD.md`.
- Put durable facts and decisions in `wiki/pages/`.
- Link new durable pages from `wiki/index.md` and log them in `wiki/log.md`.
- Put unprocessed sources in `wiki/raw/` or queue them in `wiki/inbox.md`.
- Put cross-project discovery information in `projects/index.md`.
- Put stable project summaries in `projects/<project-id>.md`.
- Keep machine-specific paths only in `projects/local-paths.md`.
- Put reusable procedures under `skills/`.
- Put reviewable deliverables under `outputs/`.

## Source-of-Truth Rules

- `AGENTS.md` is canonical for operating rules.
- `wiki/pages/` is canonical for durable synthesis.
- `wiki/raw/` preserves source records.
- Project files are canonical for current project state.
- Project profiles summarize projects but do not replace their source files.
- `projects/local-paths.md` is local connection data, not durable knowledge.
- `memory/` is recent context, not the permanent home for durable decisions.
- `outputs/` contains deliverables, not memory.
- `CLAUDE.md` is only a compatibility bridge.

## Working Rules

- Preserve existing work and unrelated changes.
- Load the smallest relevant context.
- Cite the local file used for durable claims.
- Do not broadly scan connected project source code when high-signal docs are enough.
- Do not move, copy, symlink, or rewrite a connected project without approval.
- Never invent missing context. Stop and report what is missing.
- Never commit passwords, API keys, tokens, credentials, or secret environment files.
- Ask before publishing, sending messages, or taking irreversible external actions.

## Definition of Done

- The requested artifact exists.
- The result is verified.
- Durable decisions are written to the correct file.
- Git status is reviewed.
