# ClaudeCLI

A TypeScript-based command-line interface for Claude Code with rich terminal interaction, session management, plugin support, and advanced tooling for developer workflows.

## Overview

This repository contains the source for a Claude Code CLI application. It is built around a terminal UI powered by a custom Ink implementation and a collection of built-in tools, skills, command handlers, and session features.

The application appears to support both interactive and non-interactive modes, including:

- Interactive Claude sessions in the terminal
- Non-interactive output via `--print`
- Session resume and conversation persistence
- Custom agents, skills, and plugin loading
- Chrome integration and remote session support
- Permission, debug, and environment configuration options

## Key Files & Directories

- `main.tsx` — CLI entrypoint and root command definition
- `commands.ts` — command discovery and helpers
- `cli/` — terminal handler and transport code
- `ink/` — terminal rendering engine and UI primitives
- `services/` — API, analytics, plugin, MCP, voice, and session services
- `tools/` — built-in tools and tool configuration
- `skills/` — bundled command skills and skill loader
- `components/` — UI components used across the terminal experience
- `bridge/` — remote bridge and session integration support

## Features

- `claude` command with interactive session default
- `--print` for plain text or JSON output in CLI pipelines
- `--continue` and `--resume` for conversation recovery
- `--model`, `--agent`, `--settings`, and `--plugin-dir` for session customization
- `--bare` minimal startup mode
- `--debug`, `--debug-file`, and `--verbose` for diagnostics
- Built-in permissions and tool filtering support
- MCP configuration loading and remote-managed server support
- `--chrome` integration for Claude in Chrome support

## Requirements

This repository is written in TypeScript and depends on Node.js/Bun-compatible tooling. The top-level package manifest is not currently present in this directory, so install commands require a `package.json` or equivalent manifest to be created.

## Installation

Once a package manifest exists, an example install flow would be:

```bash
npm install
npm run build
npm start
```

Or, if this repo is intended for Bun:

```bash
bun install
bun run build
bun ./main.tsx
```

> Note: `main.tsx` is the main CLI entrypoint.

## Basic Usage

```bash
# Run interactive session
node ./main.tsx

# Run a one-off prompt and print the response
node ./main.tsx --print "Summarize this code."

# Continue the latest conversation
node ./main.tsx --continue

# Resume a saved session
node ./main.tsx --resume

# Provide a specific model and agent
node ./main.tsx --model claude-sonnet-4-6 --agent reviewer
```

## Recommended Next Steps

1. Add a `package.json` with dependencies and scripts.
2. Add a `tsconfig.json` to define TypeScript compilation settings.
3. Add any build or run scripts needed for your preferred package manager.
4. Update the README with exact commands once the manifest is available.

## Notes

- This repository currently lacks a root-level `package.json`, so dependency installation is not fully defined here.
- The CLI is designed around a feature-rich Claude Code integration and appears to support many advanced command-line options.
- If you want a minimal working experience, start by creating a manifest that includes `@commander-js/extra-typings`, `react`, and any Ink-related packages used by the project.
