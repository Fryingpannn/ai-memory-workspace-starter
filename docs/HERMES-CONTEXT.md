# Hermes Context Files

Hermes can read project context from several supported files. This starter uses
`AGENTS.md` as the canonical project instructions.

`CLAUDE.md` exists only so Claude Code can enter through its native context file and then
follow the same canonical instructions.

Do not add a root `.hermes.md` or `HERMES.md` unless you intentionally want
Hermes-specific instructions to take priority over `AGENTS.md`.

Hermes keeps its global personality file outside this repository, so this starter does
not include a root `SOUL.md`.

Hermes is installed and configured at the user level during setup. The confirmed outer
folder is registered as a Hermes project and set as `terminal.cwd`, but Hermes does not
create this starter's workspace files.

The current Codex or Claude manager copies missing `AGENTS.md`, `USER.md`, wiki, and
other skeleton files into the confirmed outer folder. These are workspace-local files.
The user does not need to switch into a Hermes chat.

Hermes also has a user-level profile memory named `USER.md`. It is separate from the
root workspace `USER.md`. This starter treats the root file as the portable,
workspace-canonical profile and does not silently synchronize global Hermes memory.
