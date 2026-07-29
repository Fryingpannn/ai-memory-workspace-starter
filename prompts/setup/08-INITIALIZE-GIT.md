# Stage 8: Initialize and Review Git

The outer workspace should version the memory skeleton and wiki without absorbing
independent project contents accidentally.

## Inspect

At the outer workspace root, show:

- whether Git is already initialized;
- current root remote, branch, and status when present;
- immediate child project folders that have their own `.git`;
- files that would be tracked;
- likely secrets or machine-local files that must remain ignored.

Never change a child project's Git state.

## Choose How Existing Child Repositories Connect

When immediate child folders have their own Git repositories, show one explicit choice:

1. **Independent and ignored** — simplest for beginners; the outer repository ignores
   each child directory.
2. **Git submodules** — portable parent-to-child repository pointers; each child needs a
   remote and users must understand that submodules are checked out separately.

Recommend independent and ignored for beginners. Do not choose submodules silently.

If the user chooses submodules:

- preserve every child repository and commit;
- inspect its current remote and default branch;
- when a remote is missing, offer to create a private repository and ask once for the
  exact names and publication approval;
- register the child using its remote URL, never a machine-local path;
- do not stage or commit child source files in the outer repository;
- update its project profile after registration.

## If the Outer Workspace Already Uses Git

- Do not reinitialize it.
- Do not replace its remote or `.gitignore`.
- Propose only missing ignore entries and ask before adding them.

## If the Outer Workspace Does Not Use Git

1. Propose exact root-relative ignore entries for independent child project folders.
2. Merge those entries into `.gitignore` without replacing existing rules.
3. Show the files that the new outer repository would track.
4. Ask approval.
5. Run `git init -b main` only after approval.

## Review and Save

1. Show every changed file.
2. Show `git diff --stat` and `git status`.
3. Confirm no child project was modified or staged.
4. Ask before the first commit.
5. Ask before creating repositories or pushing. One question may cover an exact reviewed
   private-repository plan, including names, commits, and destinations.
6. Never push workspace memory to the public starter remote.

## Reconcile Project Metadata

After the final Git choice, refresh each registered project profile from live Git state:

- root-relative local path for projects inside this workspace;
- connection mode: independent or submodule;
- remote URL or confirmed `NONE`;
- remote default branch.

Do not point an in-workspace project at `projects/local-paths.md`. That file is only for
projects outside the outer workspace. Do not leave `UNKNOWN` when Git can answer the
field read-only.

Check current branch, cleanliness, ahead/behind state, divergence, and recursive
submodule status live and report them during final review. Do not store those changing
values as timeless profile facts.

After the target contains every routed prompt and the reviewed Git state is safe,
remove the temporary starter clone only when it was created by this setup. Report the
removed path. Never remove a clone supplied by the user.

Return `READY_FOR_VERIFICATION` after the reviewed local Git state is safe.
