# Workspace Overview

This outer workspace keeps shared user context, durable knowledge, and routing for its
projects. Treat each child repository as a separate project and follow its local
instructions when working inside it.

## Memory Reads

- Read `USER.md` when user context or working preferences matter.
- Start durable knowledge lookup at `wiki/index.md` and follow only relevant links if
  any.

## Memory Writes

- Update `USER.md` only with compact, durable, user-confirmed information.
- For durable facts, decisions, and relationships, follow the write workflow in
  `wiki/index.md`. Use a focused clean-context subagent when supported.

## Repository Map

- `projects/index.md`: project registry and discovery map
- `projects/<project-id>.md`: stable project profiles
- `wiki/`: durable linked knowledge
- `skills/`: reusable procedures
- `outputs/`: reviewable deliverables
- Before work requiring current code, sync the outer tracked branch when a remote
  exists. For submodules, update to the commits pinned by the outer repository.

## Working Style

- Prefer practical, concise, execution-focused help. Answer only what was asked.
- Ask the user when unsure instead of guessing. Pair long answers with a visual.
- Turn ambiguous business ideas into a task queue, and concrete deliverables by
  breaking them down by default.
- Keep prompts and docs harness-agnostic: write “the agent” or “the harness.”
- Work to a staff-engineering standard: prefer extendable designs and test beyond unit
  tests by running the actual end-to-end flow like a real human QA.
