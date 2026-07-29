# Git and GitHub for Beginners

## Git Is Local History

- `git status`: see what changed
- `git add <paths>`: select intended files
- `git diff --cached`: inspect the selected checkpoint
- `git commit -m "message"`: save the local checkpoint

Review paths explicitly. Do not use `git add .` blindly.

`projects/local-paths.md` is intentionally ignored and is only for projects outside the
outer workspace. Immediate child projects use stable root-relative paths in their
tracked profiles.

When child projects have their own repositories, choose explicitly:

- keep them independent and ignored for the simplest beginner setup; or
- register them as submodules when portable parent-to-child pointers justify the extra
  Git workflow.

Before work that needs current code, fetch and fast-forward the outer repository from
its tracked remote default branch when a remote exists. If it is local-only, report
that and continue from verified local state. Then sync submodule URLs and update
recursively to the commits pinned by the parent. Do not independently advance a
submodule beyond its pinned commit. Stop on local changes or divergence.

## GitHub Is the Optional Remote Copy

GitHub is useful for backup, collaboration, and machine synchronization. Keep a
personalized memory workspace private unless every file is intentionally public.

After reviewing the outer workspace:

```bash
git status
git add .gitignore README.md AGENTS.md CLAUDE.md USER.md memory wiki projects skills outputs
git diff --cached
git commit -m "Personalize AI memory workspace"
git push
```

Never show or commit authentication tokens.
