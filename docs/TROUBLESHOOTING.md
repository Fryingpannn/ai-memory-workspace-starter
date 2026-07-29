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

Preserve it. Before Hermes `/init` merge-updates an existing `AGENTS.md`, follow
`prompts/setup/04-INITIALIZE-WITH-HERMES.md` and get approval. Later follow
`prompts/setup/08-LINK-MEMORY.md` for the shared-routing block and Claude bridge.

## USER.md Already Exists

Preserve it. Follow `prompts/setup/05-ONBOARD-USER.md`, show only compact proposed
additions based on confirmed answers, and do not create a duplicate wiki profile.

## The Outer Folder Is Already a Git Repository

Use the existing repository. Do not reinitialize it, replace its remote, or create a
nested memory repository.

## Existing Projects Have Their Own Git Repositories

Leave their source unchanged. Follow `prompts/setup/09-INITIALIZE-GIT.md` and ask whether
they should remain independent and ignored or become Git submodules. Never choose
submodules silently.

## Projects Are Outside the Outer Workspace

Finish the guided setup without them. Connecting scattered projects is an advanced
manual step and is not part of the one-prompt workflow.

## Hermes Is Installed but `/init` Has Not Run

The original Codex or Claude manager must supervise one Hermes session in Stage 4.
Complete or decline onboarding, run `/init`, verify root `AGENTS.md`, then return to the
original setup task.

## Hermes Was Installed but the Workspace Has No Files

Hermes installation creates user-level profile and configuration state. Registering a
Hermes project points Hermes at the folder but does not itself write `AGENTS.md`. The
manager must complete Stage 3, then run Hermes `/init` in Stage 4.

## Hermes `/init` Fails

Retry once after checking Hermes authentication, active project, `terminal.cwd`, and
file tools. If it still fails, copy the starter `AGENTS.md` only when the root file is
missing, report the fallback, and continue. Never replace an existing file.

## A Source Is Missing

Do not present an unsupported durable claim as fact. Record uncertainty, preserve
provenance under `wiki/raw/`, and queue unresolved material in `wiki/inbox.md`.

## A Secret Was Committed

Stop sharing or pushing, rotate the secret, and follow GitHub's current history-removal
guidance. Deleting the current file does not remove the secret from Git history.
