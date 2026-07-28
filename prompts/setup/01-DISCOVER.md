# Stage 1: Discover the Existing Layout

This stage is read-only. Do not edit anything yet.

## Confirm the Starting Point

1. Print the current working directory.
2. Confirm it contains `README.md`, `AGENTS.md`, and `prompts/HERMES-SETUP.md`.
3. Show whether the current folder is a Git repository.
4. List only the immediate files and folders in the current directory.
5. Do not recursively scan other directories.

Stop if this is not the starter workspace root.

## Ask Only What Discovery Cannot Answer

Ask these questions together:

1. Is this memory workspace for one project or multiple projects?
2. Do the existing projects already share an outer folder, or are they scattered?
3. Should the projects remain where they are? Recommend yes.
4. Which one to three projects should be connected first?
5. May setup inspect high-signal documentation in those projects read-only?

Ask for exact project paths only after the user chooses existing-project setup.

## Classify the Scenario

Choose one:

- `NEW`: no existing projects need to be connected.
- `SINGLE`: one existing repository is the whole workspace.
- `OUTER_PLAIN`: an ordinary outer folder contains several project folders.
- `OUTER_GIT`: the outer folder is itself a Git repository.
- `SCATTERED`: projects live in unrelated locations.
- `MIXED`: both new and existing projects will be managed.

## Recommend a Setup Mode

### NEW

Use this starter as the workspace. Put ordinary new project folders under
`projects/`. A project that needs its own Git history can remain a separate repository
and be connected later.

### SINGLE

If memory is only for this project, recommend installing the workspace files into that
repository root. If memory will span multiple projects, keep this starter as a sidecar
workspace and connect the repository by path.

### OUTER_PLAIN

Recommend keeping the starter as one folder inside the existing outer folder. Register
the sibling project folders using relative paths. Do not move them.

Example:

```text
Client-Work/
├── memory-workspace/
├── website/
└── automations/
```

### OUTER_GIT

Ask whether the outer repository should own the shared memory.

- If yes, the workspace files may be deliberately merged into its root in a separate
  reviewed migration.
- If no, keep the memory workspace beside the outer repository and connect it by path.

Do not create a nested memory repository inside another tracked repository by default.

### SCATTERED

Keep the starter as a sidecar workspace. Register each project in
`projects/local-paths.md`. Do not symlink or move it.

### MIXED

Keep existing projects in place. Register them first. Add new projects according to
whether they need independent Git history.

## Confirmation Gate

Show:

- detected scenario;
- recommended mode;
- project paths that would be inspected;
- files that setup may create or edit;
- confirmation that no existing project will be changed.

Wait for explicit confirmation before reading Stage 2 or editing files.
