# Troubleshooting

## The User Only Has the Public Repository Link

Read `SETUP.md`. Clone the starter into an agent-created temporary directory, then use
it as the instruction and skeleton source. Do not personalize or push from that clone.

## The User Does Not Have an Outer Workspace

Follow `prompts/setup/01-CHOOSE-WORKSPACE.md`. Ask where to create one folder, confirm
the exact path, and use it as the project root for the remaining stages.

## The Outer Folder Already Contains Files

That is expected. Add only missing skeleton files. Record collisions and never replace
an existing file silently.

## AGENTS.md or CLAUDE.md Already Exists

Preserve it. Follow `prompts/setup/07-LINK-MEMORY.md`, show the one-line wiki bridge,
and insert only that line after the user approves.

## USER.md Already Exists

Preserve it. Follow `prompts/setup/04-ONBOARD-USER.md`, show only compact proposed
additions based on confirmed answers, and do not create a duplicate wiki profile.

## The Outer Folder Is Already a Git Repository

Use the existing repository. Do not reinitialize it, replace its remote, or create a
nested memory repository.

## Existing Projects Have Their Own Git Repositories

Leave their source unchanged. Follow `prompts/setup/08-INITIALIZE-GIT.md` and ask whether
they should remain independent and ignored or become Git submodules. Never choose
submodules silently.

## Projects Are Outside the Outer Workspace

Finish the guided setup without them. Connecting scattered projects is an advanced
manual step and is not part of the one-prompt workflow.

## Hermes Is Installed but No Hermes Chat Is Running

That is expected. The original Codex or Claude task continues the workspace setup.

## Hermes Was Installed but the Workspace Has No Files

Hermes installation creates user-level profile and configuration state. Registering a
Hermes project points Hermes at the folder but does not create this starter's files.
The original Codex or Claude manager must complete Stage 3 to add the workspace-local
skeleton.

## A Source Is Missing

Do not present an unsupported durable claim as fact. Record uncertainty, preserve
provenance under `wiki/raw/`, and queue unresolved material in `wiki/inbox.md`.

## A Secret Was Committed

Stop sharing or pushing, rotate the secret, and follow GitHub's current history-removal
guidance. Deleting the current file does not remove the secret from Git history.
