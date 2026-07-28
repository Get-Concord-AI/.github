<p align="center">
  <a href="https://getconcord.ai">
    <img src="https://raw.githubusercontent.com/Get-Concord-AI/concord-mcp/main/assets/concord-readme-header.png" alt="Concord AI: shared work-state for coding agents" width="100%">
  </a>
</p>

<h1 align="center">Concord AI</h1>

<p align="center"><strong>Google Workspace for your AI agents.</strong></p>

<p align="center">
  Give Claude Code, Codex, Cursor, and other MCP-capable coding agents one shared
  place to coordinate work, retain decisions, and create clear handoffs.
</p>

<p align="center">
  <a href="https://www.npmjs.com/package/@concord-ai/concord-mcp"><img src="https://img.shields.io/npm/v/@concord-ai/concord-mcp.svg" alt="npm version"></a>
  <a href="https://github.com/Get-Concord-AI/concord-mcp/actions/workflows/ci.yml"><img src="https://github.com/Get-Concord-AI/concord-mcp/actions/workflows/ci.yml/badge.svg" alt="CI"></a>
  <a href="https://github.com/Get-Concord-AI/concord-mcp/blob/main/LICENSE"><img src="https://img.shields.io/badge/License-MIT-blue.svg" alt="MIT License"></a>
</p>

<p align="center">
  <a href="https://github.com/Get-Concord-AI/concord-mcp">Concord MCP</a> ·
  <a href="https://github.com/Get-Concord-AI/concord-mcp#quick-start">Quick start</a> ·
  <a href="https://getconcord.ai">Website</a> ·
  <a href="https://github.com/Get-Concord-AI/concord-mcp/blob/main/CONTRIBUTING.md">Contribute</a>
</p>

## Shared work-state for coding agents

Open several coding agents in one checkout and their chat sessions cannot tell
each other who owns a file, which assumptions guide the work, or whether a task
is ready for review. Concord adds that shared work layer to the repository.

Agents register their presence, claim files and modules before editing, attach
decisions to a task, and hand work off with tests and review evidence. Humans
inspect the same state through the CLI and dashboard.

| Concord records | Your team can inspect |
| --- | --- |
| Agent presence | Who is active, away, blocked, or waiting for review |
| Work claims | Which files and modules each task expects to touch |
| Task memory | Decisions, assumptions, findings, questions, and blockers |
| Handoffs | Changes, tests, risks, provenance, and open review questions |

## Start with Concord MCP

[`concord-mcp`](https://github.com/Get-Concord-AI/concord-mcp) is our open-source,
local-first MCP server. It gives coding agents a shared SQLite work-state inside
the repository they are changing.

```bash
npm install -g @concord-ai/concord-mcp
concord install
```

`concord install` adds the agent instructions for the current repository. Connect
the MCP server using the guide for
[Claude Code](https://github.com/Get-Concord-AI/concord-mcp/blob/main/docs/claude-code.md),
[Codex](https://github.com/Get-Concord-AI/concord-mcp/blob/main/docs/codex.md), or
[Cursor](https://github.com/Get-Concord-AI/concord-mcp/blob/main/docs/cursor.md).

<p>
  <a href="cursor://anysphere.cursor-deeplink/mcp/install?name=concord&config=eyJjb21tYW5kIjoibnB4IiwiYXJncyI6WyIteSIsIkBjb25jb3JkLWFpL2NvbmNvcmQtbWNwQGxhdGVzdCJdfQ==">
    <img src="https://img.shields.io/badge/Install_Concord_MCP-Cursor-7ee787?style=for-the-badge&labelColor=0d1117" alt="Install Concord MCP in Cursor">
  </a>
</p>

Concord is early and under active development.

## A small, inspectable surface

| Tool | Role |
| --- | --- |
| `register_agent` | Add an agent instance to the live roster |
| `get_work_state` | Read agents, active tasks, overlaps, and review state |
| `claim_work` | Record expected files and modules before edits begin |
| `update_task` | Attach progress, decisions, questions, and findings |
| `get_task_context` | Resume a task from its ordered shared context |
| `handoff` | Capture changes, tests, risks, and review evidence |

The CLI exposes the same state to developers:

```bash
concord status
concord dashboard
concord tasks
concord handoff <task-id>
```

## Local by default

Concord keeps its source of truth in `.concord/concord.db` at the repository
root. It also generates readable artifacts for handoff and review:

```text
.concord/
├── concord.db
├── HANDOFF.md
├── REVIEW_PACKET.md
└── WORK_STATE.json
```

The server stays model-agnostic and works with MCP clients that can run a local
process. Your code and task content stay in the checkout.

## Build with us

Concord MCP uses the MIT license. The codebase enables TypeScript strict mode,
keeps modules focused, and requires each pull request to stay under 600 lines.

- Browse [good first issues](https://github.com/Get-Concord-AI/concord-mcp/labels/good%20first%20issue)
- Read the [contribution guide](https://github.com/Get-Concord-AI/concord-mcp/blob/main/CONTRIBUTING.md)
- Open or follow [issues](https://github.com/Get-Concord-AI/concord-mcp/issues)
- Explore the [source](https://github.com/Get-Concord-AI/concord-mcp)

<p align="center">
  <a href="https://getconcord.ai">getconcord.ai</a> ·
  <a href="https://www.npmjs.com/package/@concord-ai/concord-mcp">npm</a> ·
  <a href="https://github.com/Get-Concord-AI/concord-mcp">GitHub</a>
</p>
