# Hermes Context Files

Hermes can read project context from several supported files. The installed workspace
uses `AGENTS.md` as its canonical project instructions.

`CLAUDE.md` exists only so Claude Code can enter through its native context file and then
follow the same canonical instructions.

Do not add a root `.hermes.md` or `HERMES.md` unless you intentionally want
Hermes-specific instructions to take priority over `AGENTS.md`.

Hermes keeps its global personality file outside the project, so the workspace template
does not include `SOUL.md`.

Hermes contributes three native context layers during setup:

- user-level `SOUL.md` and configuration created by Hermes setup;
- user-profile memory populated through Hermes's consent-gated onboarding;
- workspace-local root `AGENTS.md` created or merge-updated by Hermes `/init`.

The current Codex or Claude manager first adds the supporting skeleton while reserving a
missing `AGENTS.md`. It then supervises one Hermes session for onboarding and `/init`,
and resumes the remaining setup afterward.

When root `AGENTS.md` is missing, Hermes `/init` is intentionally its native source.
Pre-existing files remain approval-gated, and the fallback template is used only when
native initialization is unavailable. It lives at
`templates/workspace/AGENTS.md`; the repository-root `AGENTS.md` governs this installer.

Hermes's user-level profile memory remains separate from the root workspace `USER.md`.
Stage 5 reuses the confirmed onboarding answers to draft the portable root file without
asking twice. It does not silently synchronize the two files later.
