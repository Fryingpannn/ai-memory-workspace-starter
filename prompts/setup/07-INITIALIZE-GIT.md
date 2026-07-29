# Stage 7: Initialize and Review Git

The outer workspace should version the memory skeleton and wiki without absorbing
independent project repositories.

## Inspect

At the outer workspace root, show:

- whether Git is already initialized;
- current root remote, branch, and status when present;
- immediate child project folders that have their own `.git`;
- files that would be tracked;
- likely secrets or machine-local files that must remain ignored.

Never change a child project's Git state.

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
5. Ask separately before creating or pushing to a private GitHub remote.
6. Never push workspace memory to the public starter remote.

After the target contains every routed prompt and the reviewed Git state is safe,
remove the temporary starter clone only when it was created by this setup. Report the
removed path. Never remove a clone supplied by the user.

Return `READY_FOR_VERIFICATION` after the reviewed local Git state is safe.
