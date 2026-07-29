# Stage 7: Analyze Existing Projects

Use only for project folders already inside the confirmed outer workspace.

## Select Scope

List immediate child folders only. If the user already approved all detected projects
during Stage 1, do not ask again. Otherwise ask which one to three project folders to
analyze first.

Exclude workspace control folders such as `wiki`, `memory`, `projects`, `prompts`,
`docs`, `skills`, `outputs`, and `.git` from project candidates.

`projects/` is the metadata registry, not a guided source-project location. Guided
project folders are immediate children of the outer workspace root.

Do not inspect:

- projects outside the outer workspace;
- `.env`, secrets, credentials, or keys;
- dependency, build, cache, dataset, or media directories;
- broad source trees without separate approval.

## Spawn Read-Only Project Workers

When supported, spawn one clean-context subagent per approved project. Each worker gets:

- one exact project path;
- read-only instructions;
- `wiki/SCHEMA.md`;
- the structured output below.

Each worker may inspect:

- immediate project structure;
- Git remote, branch, and status read-only;
- `README.md`, `AGENTS.md`, and `CLAUDE.md`;
- package or language manifests;
- a documentation index and a few clearly relevant architecture or decision files.

Workers never edit the project or the workspace.

Each worker returns a sourced brief:

```text
Project name and purpose
Major components
Important workflows and outputs
People or roles
Confirmed decisions
Dependencies and relationships
Authoritative source paths
Uncertainty and open questions
```

## Spawn One Wiki Integrator

After the user reviews the briefs, show the proposed integration plan. Ask another
question only when the briefs contain uncertainty, a collision, or a material choice.
Otherwise integrate the reversible wiki-only changes and show the exact result.

Spawn one separate clean-context wiki integrator. Give it only the reviewed briefs,
source paths, the workspace root, and `wiki/SCHEMA.md`.

The integrator:

- creates or updates linked pages under `wiki/pages/`;
- updates `wiki/index.md`;
- appends one dated entry to `wiki/log.md`;
- updates `projects/index.md` and project profiles when present;
- cites project-relative source paths;
- never edits a project folder.

Show all wiki changes and confirm no project file changed.
