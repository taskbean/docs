---
name: taskbean
description: Explains how to install, use, troubleshoot, and integrate Taskbean, a local-first task manager for developers and coding agents. Use for bean CLI workflows, Projects and Workspaces, Agent Sessions, Chronicle reconciliation, reports, the desktop app, or Taskbean Agent Skill installation.
license: MIT
metadata:
  source: "https://github.com/taskbean/taskbean"
  documentation: "https://docs.taskbean.ai"
---

# Taskbean

Taskbean captures developer work so tasks, agent sessions, and review evidence can be reported at the right level. The `bean` CLI records and reports work. The desktop app provides local review, planning, reminders, Chronicle reconciliation, and telemetry views.

## Use this skill

Use this documentation skill when you need to:

- Install, update, or troubleshoot the Taskbean CLI.
- Create, start, block, edit, complete, list, or report Tasks.
- Understand Projects, Project Keys, Project Selectors, and Workspaces.
- Attribute work to Agent Sessions or reconcile Chronicle evidence.
- Install or update the Taskbean Agent Skill for a coding agent.
- Configure or troubleshoot the desktop app and its local API.

## Source order

1. Use [`taskbean/taskbean`](https://github.com/taskbean/taskbean) as the only source of truth for product behavior.
2. Read [`CONTEXT.md`](https://github.com/taskbean/taskbean/blob/main/CONTEXT.md) for canonical terms and [`PRODUCT.md`](https://github.com/taskbean/taskbean/blob/main/PRODUCT.md) for audience and boundaries.
3. Use [`llms.txt`](https://docs.taskbean.ai/llms.txt) to find the relevant documentation page.
4. Verify exact commands, flags, defaults, and UI behavior against current source and tests.

## Documentation workflow

1. Identify whether the request concerns the cross-platform CLI, the Windows-specific desktop app, or both.
2. Find the smallest relevant page through `llms.txt` or the Taskbean documentation search MCP at `https://docs.taskbean.ai/mcp`.
3. Use canonical terms exactly: Project, Project Key, Project Selector, Workspace, Tracked Project, Tracked Workspace, Discovered Workspace, Primary Workspace, Agent Session, Copilot Fork, Task, and Unassigned Work.
4. Prefer JSON output when another process needs to consume `bean` command results.
5. Treat Chronicle suggestions as review evidence until the user approves or links them.
6. Use the installed Taskbean Agent Skill when the user wants an agent to record coding work. This documentation skill explains Taskbean; it does not replace the installed action skill.

## Guardrails

- Do not use `taskbean.ai` or legacy documentation as product evidence.
- Do not infer that Windows-specific desktop features apply to the cross-platform CLI.
- Do not invent commands, flags, defaults, UI labels, compatibility, or product behavior.
- Do not present pending Chronicle suggestions as canonical Tasks or completed work.
- Do not claim Taskbean imports raw prompts, responses, tool outputs, or command output by default.

## Resources

- [Documentation index](https://docs.taskbean.ai/llms.txt)
- [Quickstart](https://docs.taskbean.ai/quickstart)
- [Task lifecycle](https://docs.taskbean.ai/cli/lifecycle)
- [Projects and Workspaces](https://docs.taskbean.ai/cli/projects-workspaces)
- [Reports and packages](https://docs.taskbean.ai/cli/reporting)
- [Chronicle overview](https://docs.taskbean.ai/chronicle/overview)
- [Taskbean Agent Skill](https://docs.taskbean.ai/cli/agent-skill)
- [Glossary](https://docs.taskbean.ai/concepts/glossary)
