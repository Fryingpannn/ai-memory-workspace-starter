# AI Memory Workspace Setup

An agent-run installer for adding portable, files-first memory to a new or existing
outer workspace.

This repository is not the user's workspace. Codex, Claude, or another file-aware agent
reads `SETUP.md`, temporarily downloads this package when needed, and installs only the
missing scaffold files from `templates/workspace/`.

## One Setup Prompt

Paste this into the agent you already use:

```text
Set up my AI memory workspace from this repository:
https://github.com/Fryingpannn/ai-memory-workspace-starter

Start with SETUP.md. Use this repository only as temporary setup instructions and a
template source; do not turn its clone into my workspace.
```

The setup manager asks whether an outer workspace already exists. It uses that folder
or creates one after approval. Existing projects stay in place.

## What This Package Contains

- `SETUP.md`: the only setup entrypoint.
- `prompts/setup/`: short, ordered setup stages.
- `prompts/VERIFY-WORKSPACE.md`: fresh-session acceptance test.
- `templates/workspace/`: missing-only files for the user's outer workspace.
- `docs/`: reference material for the setup agent and implementing user.

The temporary clone is removed after verification. Its Git history and remote are never
copied into the user's workspace.

## Setup Flow

1. Confirm or create the outer workspace.
2. Install and configure Hermes, then register that outer folder.
3. Copy only missing supporting files from `templates/workspace/`, reserving a missing
   root `AGENTS.md` for Hermes.
4. Run one supervised Hermes session for profile onboarding and native `/init`.
5. Return to the original setup manager.
6. Build the portable root `USER.md` and interlinked `wiki/`.
7. Analyze approved existing child projects read-only.
8. Add shared memory routing to canonical `AGENTS.md`.
9. Review or initialize the outer Git repository.
10. Prove retrieval from a fresh session, then remove the temporary setup clone.

## Ownership Boundaries

Hermes natively owns:

- user-level configuration and `SOUL.md`;
- consent-gated Hermes profile memory;
- root `AGENTS.md` creation or merge-update through `/init`.

The portable workspace owns:

- root `USER.md`;
- the `CLAUDE.md` compatibility bridge;
- `memory/`, `projects/`, `skills/`, `outputs/`, and `wiki/`.

Existing target files are preserved. Software installation, authentication, Git
initialization, commits, remote creation, and pushes remain approval-gated.
