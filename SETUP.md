# AI Memory Workspace Setup Index

This is the only setup entrypoint the user needs.

Read one stage at a time. Do not load every setup file at once.

## User Prompt

```text
Set up my AI memory workspace from this repository:
https://github.com/Fryingpannn/ai-memory-workspace-starter

Start with SETUP.md and follow the setup index.
```

## Goal

Prepare Hermes, create or open the user's private memory workspace, connect approved
existing projects, personalize the memory routes, and stop for review before saving.

## Global Rules

- Ask only questions the current stage cannot answer safely.
- Ask before downloading or running an installer.
- Ask before provider authentication or other account access.
- Use an existing Codex/ChatGPT or supported Claude subscription for Hermes; never use
  AWS Bedrock.
- Use local Google Chrome for browser tasks. Do not add a separate web-search provider.
- Never personalize the public starter repository.
- Never overwrite a non-empty destination.
- Never move, copy, or edit an existing project during setup.
- Never read secrets or broad source trees during project intake.
- Ask before creating a repository, committing, or pushing.
- Stop at every review or handoff gate.

## Route 1: Prepare Hermes

Check whether Hermes is installed and whether its required capabilities are configured.

If the current agent is Claude, Codex, or another non-Hermes agent:

1. Read `prompts/INSTALL-HERMES.md`.
2. Install Hermes only when needed.
3. Configure and verify the required Hermes capabilities.
4. Stop at the Hermes handoff.
5. Tell the user to open an empty directory, start Hermes, and paste the same short
   prompt from this file.

Do not perform the workspace personalization inside the installing agent. The tutorial
should visibly hand control to Hermes.

If the current agent is already Hermes and the required capabilities work, continue to
Route 2.

## Route 2: Create or Open the Workspace

Read `prompts/START-HERE.md`.

That stage owns:

- public starter versus private copy detection;
- destination and GitHub questions;
- cloning and remote safety;
- local-only fallback;
- entry into the staged workspace setup.

## Route 3: Discover and Personalize

After the local clone is validated, read `prompts/HERMES-SETUP.md`.

Follow only the next file it names:

1. `prompts/setup/01-DISCOVER.md`
2. `prompts/setup/02-CONNECT-PROJECTS.md`, when existing projects are approved
3. `prompts/setup/03-PERSONALIZE-MEMORY.md`
4. `prompts/setup/04-OPTIONAL-REORGANIZE.md`, only when explicitly requested

Stop at each confirmation gate. Do not commit or push during these stages.

## Route 4: Review and Save

After personalization:

1. Show every changed file.
2. Show `git diff --stat` and `git status`.
3. Confirm connected projects were not changed.
4. Confirm the local path map is ignored.
5. Ask for approval before the first commit.
6. Ask separately before pushing to a private remote.

## Route 5: Fresh-Session Proof

In a visibly fresh Hermes session at the workspace root, read:

`prompts/VERIFY-WORKSPACE.md`

Do not claim long-term memory works until that verification passes.

## Completion States

- `HERMES_HANDOFF`: Hermes is ready and the user must start a Hermes session.
- `USER_CONFIRMATION`: a setup mode or inspection scope needs approval.
- `USER_REVIEW`: workspace changes are ready to inspect.
- `FRESH_SESSION_REQUIRED`: setup is ready for a clean-session test.
- `COMPLETE`: the fresh-session test passed and approved Git actions are finished.
