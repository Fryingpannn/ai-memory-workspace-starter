# Projects

Use this folder for project metadata and discovery.

- `index.md` is the tracked project registry.
- `<project-id>.md` is a tracked project profile.
- `local-paths.md` maps only projects outside this workspace to machine-specific
  locations and is gitignored.
- `local-paths.example.md` is the cross-platform path-map template.
- `project-template.md` is the project-profile template.

Do not move project source code into this metadata folder during guided setup. Existing
project repositories stay as immediate child folders of the outer workspace and use
root-relative paths in their profiles. The path map is for later external connections.
