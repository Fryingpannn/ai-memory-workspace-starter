# Troubleshooting

## The User Only Has the Public Repository Link

Read `SETUP.md`. Clone the setup package into an agent-created temporary directory, then
use its prompts and `templates/workspace/` scaffold. Do not personalize or push from
that clone.

## The User Does Not Have an Outer Workspace

Follow `prompts/setup/01-CHOOSE-WORKSPACE.md`. Ask where to create one folder, confirm
the exact path, and use it as the project root for the remaining stages.

## The Outer Folder Already Contains Files

That is expected. Add only missing skeleton files. Record collisions and never replace
an existing file silently.

## AGENTS.md or CLAUDE.md Already Exists

Preserve it during scaffolding. Follow `prompts/setup/06-FINALIZE-AGENTS.md` to create
and review `AGENTS.proposed.md`. Replace the old `AGENTS.md` only after the user confirms
the complete fused file. Add a missing `CLAUDE.md` bridge only after review.

## USER.md Already Exists

Preserve it. Follow `prompts/setup/03-ONBOARD-USER.md`, show only compact proposed
additions based on confirmed answers, and do not create a duplicate wiki profile.

## The Outer Folder Is Already a Git Repository

Use the existing repository. Do not reinitialize it, replace its remote, or create a
nested memory repository.

## Existing Projects Have Their Own Git Repositories

Leave their source unchanged. Follow `prompts/setup/07-INITIALIZE-GIT.md` and ask whether
they should remain independent and ignored or become Git submodules. Never choose
submodules silently.

## Projects Are Outside the Outer Workspace

Finish the guided setup without them. Connecting scattered projects is an advanced
manual step and is not part of the one-prompt workflow.

## A Source Is Missing

Do not present an unsupported durable claim as fact. Record uncertainty, preserve
provenance under `wiki/raw/`, and queue unresolved material in `wiki/inbox.md`.

## A Secret Was Committed

Stop sharing or pushing, rotate the secret, and follow GitHub's current history-removal
guidance. Deleting the current file does not remove the secret from Git history.
