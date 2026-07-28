# Troubleshooting

## Wrong Working Directory

Run `pwd` and confirm you are at the repository root before letting an agent edit files.

## Instructions Were Ignored

Ask the agent which context file it loaded. Confirm root `AGENTS.md` exists and keep
Claude-specific instructions in the short `CLAUDE.md` bridge.

## AGENTS.md Is Growing Too Large

Keep routing, safety, and operating rules in `AGENTS.md`. Move project detail to the
project, durable facts to the wiki, and repeatable procedures to `skills/`.

## A Source Is Missing

Do not present an unsupported durable claim as fact. Preserve its origin in `wiki/raw/`
and add provenance to the durable wiki page.

## A Secret Was Committed

Stop sharing or pushing, rotate the secret, and follow GitHub's current history-removal
guidance. Deleting the current file does not remove the secret from Git history.

