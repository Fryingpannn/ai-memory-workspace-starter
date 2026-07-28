# Minimal Hermes Installation

Use this only when `hermes` is not already installed.

## Goal

Install the official Hermes CLI, configure one model provider, keep only the file and
terminal tools needed for workspace setup, verify one working chat, and hand control to
Hermes.

Do not configure messaging, gateways, browser automation, web tools, voice, TTS, image
generation, cron, skills, plugins, MCP servers, or other integrations.

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

If Hermes works, skip installation and continue to the handoff.

## Step 2: Install the Official CLI

After checking the official page and receiving approval, use its current command for
the detected platform.

Current macOS, Linux, and WSL shape:

```text
curl -fsSL https://hermes-agent.nousresearch.com/install.sh | bash -s -- --skip-browser
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

## Step 3: Choose Minimal Setup

In the first-run setup:

1. Choose `Blank Slate`, not the integration-focused quick setup.
2. Configure one model provider and one supported model.
3. Keep the File Operations and Terminal toolsets enabled.
4. Leave every optional integration and advanced tool disabled.
5. Keep the local terminal backend unless the user explicitly requests isolation.

The model provider is required for Hermes to respond. It is the only account or
credential setup required in this tutorial.

## Step 4: Verify One Chat

Start Hermes:

```text
hermes
```

Ask:

```text
Tell me the current working directory and list only its immediate files.
```

The install passes when Hermes responds and can use local file and terminal tools.

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
