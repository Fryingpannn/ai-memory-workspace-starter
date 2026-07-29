# Wiki Index

This wiki stores durable facts, decisions, and relationships.

For reads, start here and follow only the links relevant to the current task.

For writes, use a focused clean-context subagent when supported so the main task does
not load the full wiki. Give it the new evidence, its source paths, and the requested
update. The subagent must read `SCHEMA.md`, update the narrowest relevant page, add any
needed index link, preserve provenance, and append the change to `log.md`. The main
agent reviews the proposed diff before it is accepted.

- [User Profile](../USER.md)
- [Wiki Schema](SCHEMA.md)
- [Workspace Profile](pages/workspace-profile.md)
- [Decisions](pages/decisions.md)
