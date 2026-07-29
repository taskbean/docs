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
- `.github/agents/docs-maintainer.agent.md` and `docs-verifier.agent.md` enforce Actor/Verifier separation.

Update the Mintlify skill with:

```bash
gh skill update mintlify
```
