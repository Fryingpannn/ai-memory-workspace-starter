# Hermes Context Files

Hermes can read project context from several supported files. This starter uses
`AGENTS.md` as the canonical project instructions.

`CLAUDE.md` exists only so Claude Code can enter through its native context file and then
follow the same canonical instructions.

Do not add a root `.hermes.md` or `HERMES.md` unless you intentionally want
Hermes-specific instructions to take priority over `AGENTS.md`.

Hermes keeps its global personality file outside this repository, so this starter does
not include a root `SOUL.md`.

Hermes is installed and configured at the system level during setup. Codex or Claude
remains the setup manager; the user does not need to switch into a Hermes chat.
