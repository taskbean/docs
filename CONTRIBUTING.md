# Contribute to Taskbean documentation

Use active voice, address the reader as "you," and keep each page focused on a concrete task.

## Make a change

1. Fork and clone this repository.
2. Install dependencies with `npm ci`.
3. Create a branch.
4. Read `AGENTS.md`, `docs.json`, and the related pages.
5. Verify product claims against `taskbean/taskbean`.
6. Run `npm run dev` and inspect the page locally.
7. Run `npm run check`.
8. Open a pull request with source evidence and validation results.

New pages must appear in `docs.json`. Internal links use root-relative paths without file extensions.

## Product language

Use the canonical terms in [`concepts/glossary.mdx`](concepts/glossary.mdx). Do not use Project and Workspace interchangeably.
