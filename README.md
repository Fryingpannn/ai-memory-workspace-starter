# AI Memory Workspace Starter

A Hermes-friendly, files-first workspace that keeps useful context across fresh chats.

The workspace belongs to you, not to one model or app. Hermes, Codex, Claude Code, and
other file-aware agents can all use the same durable Markdown files.

## Start With Hermes

1. Complete the official Hermes install and `hermes setup`.
2. Use this repository as a GitHub template to create your own private repository.
3. Clone your new repository and open its folder in a terminal.
4. Run `hermes`.
5. Tell Hermes:

   `Read prompts/HERMES-SETUP.md and personalize this workspace for me.`

6. Inspect every changed file.
7. Create the first local Git checkpoint, then push to your private GitHub repository.
8. Open a fresh session and run `prompts/VERIFY-WORKSPACE.md`.

Hermes does not own the resulting memory. It helps create and maintain ordinary files
inside your Git repository.

## Workspace Map

```text
.
├── AGENTS.md                  canonical operating instructions
├── CLAUDE.md                  Claude Code compatibility bridge
├── memory/                    recent dated working context
├── wiki/
│   ├── index.md               durable knowledge map
│   ├── inbox.md               unsynthesized material
│   ├── log.md                 durable change history
│   ├── pages/                 durable facts and decisions
│   └── raw/                   auditable source records
├── projects/                  active work
├── docs/                      operating references
├── skills/                    reusable procedures
├── outputs/                   reviewable deliverables
└── prompts/                   setup and verification prompts
```

## Memory Model

- Current chat is temporary.
- `memory/YYYY-MM-DD.md` holds recent working context.
- `wiki/pages/` holds durable facts and decisions.
- `wiki/raw/` preserves source records and provenance.
- `projects/` holds current project state.
- `outputs/` holds deliverables, not memory.

Vector search, RAG, databases, knowledge graphs, and automations are intentionally
excluded from this beginner starter.

## Definition of Done

The workspace is ready when a fresh session can:

1. Explain what the workspace is for.
2. Identify the important project and people or roles.
3. Follow the operating rules in `AGENTS.md`.
4. Retrieve one durable decision and name its source file.
5. Write one new dated memory to the correct file.

## Safety

Keep passwords, API keys, tokens, credentials, and secret environment files out of Git.
Use safe or fictional data while learning.

