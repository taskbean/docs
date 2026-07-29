# Taskbean documentation

This repository contains the canonical Taskbean documentation published at [docs.taskbean.ai](https://docs.taskbean.ai).

Product behavior comes from [`taskbean/taskbean`](https://github.com/taskbean/taskbean). The legacy `taskbean/taskbean.ai/docs` tree is migration history, not product truth.

## Local development

```bash
npm ci
npm run dev
```

Open `http://localhost:3000`.

## Validation

```bash
npm run check
npm run check:external-links
```

`npm run check` validates the Mintlify build, internal links, anchors, snippets, and accessibility.

## Agent guidance

- `AGENTS.md` is the canonical repository instruction file.
- `.mintlify/AGENTS.md` carries the subset that Mintlify's agent reads.
- `.github/skills/mintlify` is the upstream Mintlify authoring skill.
- `.github/skills/docs-maintenance` defines Taskbean synchronization and verification.
- `.github/agents/taskbean-docs.agent.md` is the only user-invokable coordinator.
- `.github/agents/docs-maintainer.agent.md` and `docs-verifier.agent.md` are non-user-invokable Actor and Verifier roles.
- `skill.md` overrides Mintlify's generated product skill with source-backed Taskbean guidance.
- Mintlify generates [llms.txt](https://docs.taskbean.ai/llms.txt) from current page descriptions; do not commit a duplicate while the generated file remains accurate.

Set **Taskbean docs** as your default agent in the Copilot session settings after the agent profile reaches the repository's default branch.

## MCP servers

`.vscode/mcp.json` exposes three distinct surfaces:

- `mintlify-docs` searches current Mintlify product documentation.
- `taskbean-docs` searches the published Taskbean documentation and exposes its skill resources.
- `Mintlify` provides OAuth-protected admin tools for trusted interactive clients.

Clients that use the `mcpServers` schema can connect to the Mintlify admin MCP with:

```json
{
  "mcpServers": {
    "Mintlify": {
      "url": "https://mcp.mintlify.com"
    }
  }
}
```

The Mintlify admin MCP requires interactive OAuth. Copilot cloud agent does not support remote OAuth MCP servers, so cloud authoring continues through repository edits and pull requests. The read-only Mintlify and Taskbean search MCP servers remain available to cloud agents.

Update the Mintlify skill with:

```bash
gh skill update mintlify
```
