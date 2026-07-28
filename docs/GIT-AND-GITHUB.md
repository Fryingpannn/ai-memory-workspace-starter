# Git and GitHub for Beginners

## Git Is Local History

- `git status`: see what changed
- `git add <paths>`: select intended files
- `git diff --cached`: inspect the selected checkpoint
- `git commit -m "message"`: save the local checkpoint

Review paths explicitly. Do not use `git add .` blindly.

## GitHub Is the Optional Remote Copy

GitHub is useful for backup, collaboration, and machine synchronization. Keep a
personalized memory workspace private unless every file is intentionally public.

After reviewing the starter:

```bash
git status
git add README.md AGENTS.md CLAUDE.md memory wiki projects docs skills outputs prompts
git diff --cached
git commit -m "Personalize AI memory workspace"
git push
```

Never show or commit authentication tokens.

