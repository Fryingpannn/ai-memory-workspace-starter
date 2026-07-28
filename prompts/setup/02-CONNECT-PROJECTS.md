# Stage 2: Connect Existing Projects

Use this stage only after the user confirms the setup mode and project paths.

## Connection Model

Existing projects stay where they are.

- `projects/index.md` is the tracked logical project registry.
- `projects/<project-id>.md` is the tracked profile for one project.
- `projects/local-paths.md` maps project IDs to paths on this machine.
- `projects/local-paths.md` is gitignored because paths differ by machine.

## Validate Each Project

For each approved path:

1. Confirm the path exists.
2. Resolve its project root without changing directories permanently.
3. Detect whether it is a Git repository.
4. Read its remote URL, current branch, and working-tree status read-only.
5. Never stage, commit, checkout, fetch, pull, push, or modify the project.

If a path is missing or ambiguous, stop and ask.

## Read Only High-Signal Files

Read files only when they exist and the user approved inspection:

- `README.md`;
- `AGENTS.md`;
- `CLAUDE.md`;
- `package.json`, `pyproject.toml`, `Cargo.toml`, or `go.mod`;
- a documentation index or clearly named architecture file;
- a small number of files explicitly named by the user.

Do not broadly scan source code during initial setup.

Never read:

- `.env` or secret files;
- credential folders;
- private keys or certificates;
- generated dependency folders;
- build outputs;
- large datasets or media folders.

## Create the Local Path Map

Create `projects/local-paths.md` from `projects/local-paths.example.md`.

Use one stable project ID per project:

```text
- `customer-portal`: `../customer-portal`
- `automation-service`: `C:\Users\Name\code\automation-service`
```

Prefer a relative path when the project and memory workspace share an outer folder.
Otherwise use the local absolute path.

## Create a Project Profile

Copy `projects/project-template.md` to `projects/<project-id>.md`.

Populate only confirmed information:

- project name and stable ID;
- purpose;
- lifecycle status, only when explicitly labeled by a source or confirmed by the user;
- repository remote, if present;
- authoritative files;
- confirmed run or test commands;
- important outputs;
- important people or roles;
- durable facts and decisions with source paths;
- open questions.

Write `Unknown` rather than guessing.

Do not infer lifecycle status from loose wording such as "maintained," "current,"
"legacy," or "in development." Those phrases may describe the work without defining
its status.

Do not put machine-specific absolute paths in the tracked project profile.

## Update the Registry

Add each profile to `projects/index.md`.

For every project, record:

- project ID;
- display name;
- profile link;
- current status;
- local connection status.

## Intake Limit

Connect at most three projects in the initial pass.

If more projects exist:

- list their names in `wiki/inbox.md`;
- mark them as pending intake;
- do not inspect them yet.

## Review Gate

Before Stage 3:

1. Show every source file read.
2. Show every workspace file created or changed.
3. Confirm no connected project was modified.
4. Ask the user to correct uncertain project facts.
