# Optional: Reorganize Existing Projects

Read this file only when the user explicitly asks to reorganize repositories.

Reorganization is not required for memory setup.

## Default Recommendation

Keep projects where they are and use:

- tracked project profiles;
- a gitignored local path map;
- relative paths when projects share an outer folder.

## Moving a Repository

Moving a repository can preserve its `.git` history, but may break:

- scripts with absolute paths;
- IDE workspaces;
- deployment configuration;
- scheduled jobs;
- local environment files;
- external integrations.

Before proposing a move:

1. Confirm the exact source and destination.
2. Check Git status and active worktrees.
3. Identify known absolute-path dependencies.
4. Show the proposed final folder tree.
5. Explain rollback.
6. Ask for explicit approval.

After an approved move:

1. Confirm `.git` history and remotes still exist.
2. Run only the project's documented validation commands.
3. Update `projects/local-paths.md`.
4. Update the project profile if its logical structure changed.
5. Do not rewrite Git history.

## Nested Repositories and Submodules

Do not introduce them during beginner setup.

Use a submodule only when the user already understands:

- independent repository history;
- pinned commits;
- clone and update commands;
- cross-machine synchronization.

Treat consolidation into one monorepo as a separate migration project.
