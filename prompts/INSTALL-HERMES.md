# Hermes Installation and Full Local Setup

Use this when Claude, Codex, or another existing agent is preparing Hermes for the user.

## Goal

Install the official Hermes CLI, configure one model provider, enable the useful local
agent capabilities, verify them, and hand control to Hermes.

The required setup includes:

- File Operations and Terminal;
- web search and browser automation;
- built-in memory capture and session search;
- skills and skill management;
- cron and scheduled-task management.

Messaging platforms, external memory providers, MCP servers, voice, smart-home tools,
and other account integrations are outside this tutorial.

## Safety Rules

- Check whether `hermes` is already installed before changing anything.
- Detect the operating system and shell.
- Read the current official installation page before choosing a command:
  `https://hermes-agent.nousresearch.com/docs/getting-started/installation`
- Show the exact install command and ask for approval before downloading or running it.
- Explain that the official command downloads and executes the Hermes installer.
- Do not ask the user to paste an API key or token into chat.
- Let the Hermes setup interface store provider credentials outside the workspace.
- Do not use administrator privileges unless the official installer reports a required
  prerequisite and the user approves it.

## Step 1: Check for an Existing Install

On macOS, Linux, or WSL:

```text
command -v hermes
hermes --version
```

On Windows PowerShell:

```text
Get-Command hermes -ErrorAction SilentlyContinue
hermes --version
```

If Hermes works, skip only Step 2. Continue with Step 3 so the required capabilities
are inspected, configured, and verified before the handoff.

## Step 2: Install the Official CLI

After checking the official page and receiving approval, use its current command for
the detected platform.

Current macOS, Linux, and WSL shape:

```text
curl -fsSL https://hermes-agent.nousresearch.com/install.sh | bash
```

Current Windows PowerShell shape:

```text
iex (irm https://hermes-agent.nousresearch.com/install.ps1)
```

If the official documentation differs, follow the official documentation and tell the
user what changed.

Reload the shell when instructed, then verify:

```text
hermes --version
hermes doctor
```

## Step 3: Choose Full Setup

In the first-run setup:

1. Choose `Full Setup`.
2. Configure one model provider and one supported model.
3. Keep the local terminal backend unless the user explicitly requests isolation.
4. Enable File Operations, Terminal, web/search, browser, memory, session search,
   skills, and cron for the Hermes CLI.
5. Enable built-in memory capture and user-profile memory.
6. Install the local browser runtime when offered.
7. Skip messaging gateways, external memory providers, MCP servers, voice, and other
   account integrations.

Use `hermes tools` after setup to confirm the CLI toolsets. Do not manually edit global
Hermes configuration when the setup interface can make the change safely.

## Step 4: Verify the Full Local Agent

Run:

```text
hermes tools
hermes cron status
```

Start Hermes:

```text
hermes
```

Ask Hermes:

```text
Tell me the current working directory, list only its immediate files, and confirm
whether browser, memory, session search, skills, and cron tools are available.
```

The install passes when:

- Hermes responds with the configured model;
- file and terminal access work;
- browser tools are available;
- memory and session search are available;
- skill tools are available;
- cron status can be read.

Do not create a real scheduled job, write a test memory, or install a skill merely to
prove availability.

## Step 5: Hand Off to the Workspace Setup

Stop the installing agent. Open an empty working directory, start `hermes`, and paste:

```text
Set up my AI memory workspace from this repository:
https://github.com/Fryingpannn/ai-memory-workspace-starter

Start with prompts/START-HERE.md and follow the complete setup workflow.
Ask only the questions you cannot answer safely. Do not move or modify my existing
projects without approval.
```

The Hermes session should now follow `prompts/START-HERE.md`.
