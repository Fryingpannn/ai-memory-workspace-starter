# Troubleshooting

## Wrong Working Directory

Run `pwd` and confirm you are at the repository root before letting an agent edit files.

## Instructions Were Ignored

Ask the agent which context file it loaded. Confirm root `AGENTS.md` exists and keep
Claude-specific instructions in the short `CLAUDE.md` bridge.

## AGENTS.md Is Growing Too Large

Keep routing, safety, and operating rules in `AGENTS.md`. Move project detail to the
project, durable facts to the wiki, and repeatable procedures to `skills/`.

## An Existing Project Is Somewhere Else

Do not move it just to complete setup. Add a tracked profile under `projects/` and put
its machine-specific location in the gitignored `projects/local-paths.md`.

## A Project Path Broke on Another Machine

Update `projects/local-paths.md` on that machine. Do not commit the local path map.
The tracked project ID and profile should remain the same.

## A Symlink Does Not Work

Remove the optional symlink and use the local path map directly. Symlinks are not
required and are never the canonical connection.

## The Outer Folder Is Already a Git Repository

Do not place another tracked memory repository inside it by default. Either deliberately
merge the workspace files into the outer repository or keep the memory workspace beside
it and connect it by path.

## A Source Is Missing

Do not present an unsupported durable claim as fact. Preserve its origin in `wiki/raw/`
and add provenance to the durable wiki page.

## A Secret Was Committed

Stop sharing or pushing, rotate the secret, and follow GitHub's current history-removal
guidance. Deleting the current file does not remove the secret from Git history.
