# AI Memory Workspace Setup Manager

This is the only setup entrypoint the user needs.

Read one stage at a time. Keep the current Codex, Claude, or other file-aware agent as
the manager for the entire setup.

## User Prompt

```text
Set up my AI memory workspace from this repository:
https://github.com/Fryingpannn/ai-memory-workspace-starter

Read SETUP.md from GitHub before cloning. If a clone is needed, use a temporary staging
directory, not my current folder. Then follow the setup index.
```

## Goal

Turn one outer folder into a files-first memory workspace without moving or rewriting
its existing projects.

The starter repository supplies instructions and missing skeleton files. It is not the
user's personalized workspace.

## Global Rules

- Ask only questions the current stage cannot answer safely.
- Keep the current Codex, Claude, or other agent as setup manager. Run only the
  supervised Hermes onboarding and `/init` stage inside Hermes, then return.
- Never replace existing content. Use only reviewed, targeted edits.
- Never move or edit an existing project during setup.
- Never read secrets, generated dependencies, or broad source trees.
- Show proposed changes before editing an existing `USER.md`, `AGENTS.md`, or
  `CLAUDE.md`.
- Ask before installing software, authenticating an account, initializing Git,
  committing, creating a remote, or pushing.
- Do not support scattered projects in the guided setup. They can be connected later.
- Read only the next routed prompt.

## Stage 0: Make the Starter Available

If this repository is not already available locally, clone it into an agent-created
temporary staging directory.

- Do not clone it over the user's outer folder.
- Do not personalize the staging clone.
- Keep its Git history and remote separate from the user's workspace.
- Record the staging path for the scaffold stage.

If the starter was already cloned directly into an originally empty working folder:

1. Stop before personalization.
2. Confirm no user files were displaced.
3. Move that clone to an agent-created temporary staging path.
4. Restore the original empty folder as the candidate outer workspace.

If prior contents are uncertain, stop and ask instead of moving anything.

## Routed Workflow

Follow these prompts in order:

1. `prompts/setup/01-CHOOSE-WORKSPACE.md`
2. `prompts/setup/02-INSTALL-HERMES.md`
3. `prompts/setup/03-SCAFFOLD-WORKSPACE.md`
4. `prompts/setup/04-INITIALIZE-WITH-HERMES.md`
5. `prompts/setup/05-ONBOARD-USER.md`
6. `prompts/setup/06-BUILD-WIKI.md`
7. `prompts/setup/07-ANALYZE-PROJECTS.md`, only when projects already exist
8. `prompts/setup/08-LINK-MEMORY.md`
9. `prompts/setup/09-INITIALIZE-GIT.md`
10. `prompts/VERIFY-WORKSPACE.md`

The manager owns user questions and approval gates. Spawn clean-context subagents only
where a stage explicitly requests them. If subagents are unavailable, execute that
stage in isolation and avoid unrelated context.

After Stage 1, use the confirmed outer workspace as the working directory and project
root for every remaining stage.

## Completion

Setup is complete when:

- one outer workspace root is confirmed;
- Hermes is installed and its required local capabilities are verified;
- Hermes points to the confirmed outer folder as its active project and terminal
  working directory;
- missing skeleton files exist without replacing prior work;
- Hermes `/init` created or merge-updated the canonical root `AGENTS.md`, a pre-existing
  file was explicitly preserved, or a documented fallback was used;
- Hermes onboarding completed or was explicitly declined;
- a reviewed root `USER.md` exists or onboarding was explicitly declined;
- `wiki/` has an index, schema, log, raw-source area, and interlinked pages;
- approved existing projects have sourced wiki entries;
- memory routing is present or was explicitly declined;
- the outer workspace is a Git repository;
- project profiles match final live Git paths, remotes, and connection modes;
- the user has reviewed all changes;
- a fresh session can retrieve user context and sourced knowledge through `USER.md` and
  `wiki/index.md`.
