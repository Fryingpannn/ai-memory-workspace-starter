# Projects

Use this folder to discover and connect active projects.

- `index.md` is the tracked project registry.
- `<project-id>.md` is a tracked project profile.
- `local-paths.md` maps project IDs to locations on this machine and is gitignored.
- `local-paths.example.md` is the cross-platform path-map template.
- `project-template.md` is the project-profile template.

Existing repositories do not need to be moved into this folder.

Keep their code where it is. Connect them through the registry and local path map.
Use symlinks only as optional local conveniences, never as the source of truth.

Ordinary new project folders may live here when they do not need independent Git
history. Keep a project as a separate repository when permissions, deployment,
collaborators, or release history require it.
