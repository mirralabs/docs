# mirra docs

Mintlify documentation for Mirra. Served at `docs.mirra.run` when deployed.

## Local preview

```bash
npm i -g mint
mint dev
```

Opens `http://localhost:3000` with hot reload.

## Content layout

- `index.mdx` — what Mirra is, landing for first-time readers
- `quickstart.mdx` — install + first mirror in two minutes
- `concepts/` — mirrors, sessions, scenarios, fidelity
- `cli/` — per-command reference for the `mirra` CLI
- `guides/` — task-shaped walkthroughs (first scenario, CI, Vitest, MCP)
- `mirrors/` — per-vendor mirror documentation
- `reference/` — scenario format, evaluation system, HTTP API

## Writing rules

See [`AGENTS.md`](./AGENTS.md) for terminology, voice, and content boundaries.

## Source of truth

Content derives from `../project_docs/` (product description, whitepaper, thesis, technical spec). Keep these in sync when those files change.

## Publishing

Auto-deployed by Mintlify from `main`. Open a PR, get it merged, production updates within a minute.
