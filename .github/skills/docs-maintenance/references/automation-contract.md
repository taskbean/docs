# Automation contract

## Agent topology

- `Taskbean docs` is the only user-invokable agent and coordinates planning, authoring, evaluation, and one bounded improvement cycle.
- `Taskbean docs maintainer` is the non-user-invokable Actor.
- `Taskbean docs verifier` is the non-user-invokable, read-only Verifier.
- The coordinator and Actor cannot issue the merge-gating verdict.

## Product merge path

Mintlify owns the event trigger:

- Trigger: a push to `main` in `taskbean/taskbean`.
- Action: run a `source-code-agent` automation with `taskbean/taskbean` as context.
- Output: open or update a focused pull request in `taskbean/docs`.
- Update mode: require review. Do not enable Mintlify automerge because it does not satisfy the independent-verifier requirement.

The Wednesday Copilot automation processes pending Mintlify pull requests before starting the broader audit.

## Wednesday audit

- Schedule: Wednesday at 09:00 Pacific.
- Working-hours boundary: start only between 09:00 and 16:30 Pacific.
- Scope: product accuracy, missing coverage, broken internal and external links, accessibility, SEO, GEO, and AI/agent readiness.
- Product source: `taskbean/taskbean`.
- Maximum repair cycles: one per pull request or audit change.
- Maximum child sessions: one Actor and one fresh Verifier at a time.
- Stop conditions: all scoped work passes, source access is unavailable, checks cannot run, the second verdict fails, or a tool requests new credentials or permissions.

## Pending Mintlify pull requests

For each open pull request authored by Mintlify automation:

1. Confirm it targets `main` and only changes documentation-related files.
2. Run `npm ci`, `npm run check`, and the relevant source-evidence comparison.
3. Invoke `Taskbean docs verifier`.
4. Merge on `VERDICT: PASS`.
5. On failure, invoke `Taskbean docs maintainer` for one focused repair, then invoke a fresh verifier.
6. Leave the pull request open after a second failure and report the blocking evidence.

## Weekly audit flow

1. Compare changes in `taskbean/taskbean` since the latest product commit already represented in the docs.
2. Audit existing pages for stale claims and missing user journeys.
3. Run `npm run check` and `npm run check:external-links`.
4. Review page titles, descriptions, navigation, canonical URLs, contextual AI options, and published MCP/LLM discoverability.
5. Check `https://docs.taskbean.ai/llms.txt`, `https://docs.taskbean.ai/skill.md`, and the Taskbean search MCP when agent-facing guidance changes.
6. If no changes are needed, report an evidence-backed no-op.
7. If changes are needed, create one focused pull request and use the Actor/Verifier flow.

## Merge authority

The user has authorized unattended merge only after deterministic checks and an independent `VERDICT: PASS`. This authorization does not cover force-pushes, history rewrites, deleting content without a replacement, changing credentials, installing unreviewed packages, or expanding repository access.
