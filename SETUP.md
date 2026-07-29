# AI Memory Workspace Setup Manager

This is the only setup entrypoint the user needs.

Read one stage at a time. Keep the user's current file-aware agent as the manager for
the entire setup.

## User Prompt

```text
Set up my AI memory workspace from this repository:
https://github.com/Fryingpannn/ai-memory-workspace-starter

Start with SETUP.md. Use this repository only as temporary setup instructions and a
template source; do not turn its clone into my workspace.
```

## Goal

Turn one outer folder into a files-first memory workspace without moving or rewriting
its existing projects.

This repository supplies instructions and missing-file templates. Its clone is never
the user's personalized workspace.

## Global Rules

- Ask only questions the current stage cannot answer safely.
- Keep the user's current agent as setup manager for the entire workflow.
- Never replace existing content except the explicitly reviewed `AGENTS.md` fusion in
  Stage 6. Use only reviewed, targeted edits.
- Never move or edit an existing project during setup.
- Never read secrets, generated dependencies, or broad source trees.
- Show proposed changes before editing an existing `USER.md`, `AGENTS.md`, or
  `CLAUDE.md`.
- Ask before initializing Git, committing, creating a remote, or pushing.
- Do not support scattered projects in the guided setup. They can be connected later.
- Read only the next routed prompt.

## Stage 0: Make the Starter Available

If this repository is not already available locally, clone it into an agent-created
temporary staging directory.

- Do not clone it over the user's outer folder.
- Do not personalize the staging clone.
- Keep its Git history and remote separate from the user's workspace.
- Record the staging path for the entire setup workflow.

If this repository was already cloned directly into an originally empty working folder:

1. Stop before personalization.
2. Confirm no user files were displaced.
3. Move that clone to an agent-created temporary staging path.
4. Restore the original empty folder as the candidate outer workspace.

If prior contents are uncertain, stop and ask instead of moving anything.

## Routed Workflow

Follow these prompts in order:

1. `prompts/setup/01-CHOOSE-WORKSPACE.md`
2. `prompts/setup/02-SCAFFOLD-WORKSPACE.md`
3. `prompts/setup/03-ONBOARD-USER.md`
4. `prompts/setup/04-BUILD-WIKI.md`
5. `prompts/setup/05-ANALYZE-PROJECTS.md`, only when projects already exist
6. `prompts/setup/06-FINALIZE-AGENTS.md`
7. `prompts/setup/07-INITIALIZE-GIT.md`
8. `prompts/VERIFY-WORKSPACE.md`
9. `prompts/CONNECT-INNER-PROJECTS.md`

The manager owns user questions and approval gates. Spawn clean-context subagents only
where a stage explicitly requests them. If subagents are unavailable, execute that
stage in isolation and avoid unrelated context.

After Stage 1, use the confirmed outer workspace as the working directory and project
root for every remaining stage. Continue reading routed prompts from the staging clone.

## Completion

Setup is complete when:

- one outer workspace root is confirmed;
- missing skeleton files exist without replacing prior work;
- a missing `AGENTS.md` was created from the template, or an existing file was replaced
  only after the user approved a complete fused proposal;
- user onboarding completed or was explicitly declined;
- a reviewed root `USER.md` exists or onboarding was explicitly declined;
- `wiki/` has an index, schema, log, raw-source area, and interlinked pages;
- approved existing projects have sourced wiki entries;
- memory routing is present or was explicitly declined;
- the outer workspace is a Git repository;
- project profiles match final live Git paths, remotes, and connection modes;
- the user has reviewed all changes;
- a fresh session can retrieve user context and sourced knowledge through `USER.md` and
  `wiki/index.md`;
- the optional inner-project memory-bridge prompt was delivered without editing child
  projects;
- the agent-created temporary setup clone was removed after verification and the final
  handoff.

Installing another harness is outside this setup. It can be added to the completed
workspace later without changing the workspace structure.
