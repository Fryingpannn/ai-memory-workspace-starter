# AI Memory Workspace Setup

An agent-run installer for adding portable, files-first memory to a new or existing
outer workspace.

This repository is not the user's workspace. The user's existing file-aware agent reads
`SETUP.md`, temporarily downloads this package when needed, and installs only the
missing scaffold files from `templates/workspace/`.

## One Setup Prompt

Paste this into the agent you already use:

```text
Set up my AI memory workspace from this repository:
https://github.com/Fryingpannn/ai-memory-workspace-starter

Start with SETUP.md. Use this repository only as temporary setup instructions and a
template source; do not turn its clone into my workspace. Do not create a CLAUDE.md.
Install skills/connect-project/SKILL.md into the workspace and reference it from
AGENTS.md. When setup finishes, connect projects with that skill. Do not ask me to
paste a separate connect prompt.
```

The setup manager asks whether an outer workspace already exists. It uses that folder
or creates one after approval. Existing projects stay in place.

## What This Package Contains

- `SETUP.md`: the only setup entrypoint.
- `prompts/setup/`: short, ordered setup stages.
- `prompts/VERIFY-WORKSPACE.md`: fresh-session acceptance test.
- `prompts/CONNECT-INNER-PROJECTS.md`: final handoff. It uses the connect-project
  skill, then removes the temporary setup clone.
- `templates/workspace/`: missing-only files for the user's outer workspace,
  including `skills/connect-project/SKILL.md`.
- `docs/`: reference material for the setup agent and implementing user.

The temporary clone is removed after verification and the final handoff. Its Git history
and remote are never copied into the user's workspace.

## Setup Flow

1. Confirm or create the outer workspace.
2. Copy only missing supporting files from `templates/workspace/`.
3. Build the portable root `USER.md`.
4. Build the interlinked `wiki/`.
5. Analyze approved existing child projects read-only.
6. Create or review a fused canonical `AGENTS.md`.
7. Review or initialize the outer Git repository.
8. Prove retrieval from a fresh session.
9. Connect a requested project with the connect-project skill, then remove the
   temporary setup clone. Do not deliver a paste prompt.

## Ownership Boundaries

The portable workspace owns:

- root `USER.md`;
- canonical `AGENTS.md`, and no generated `CLAUDE.md`. A user who needs Claude-only
  notes can add a `CLAUDE.md` whose first line is `@AGENTS.md`;
- `projects/`, `skills/` (including `skills/connect-project/SKILL.md`), `outputs/`,
  and `wiki/`.

Existing target files are preserved except for a user-confirmed replacement of
`AGENTS.md` with its reviewed fused proposal. Git initialization, commits, remote
creation, and pushes remain approval-gated.

This installer uses the file-aware agent the user already has. Installing another
harness is a separate optional workflow.
