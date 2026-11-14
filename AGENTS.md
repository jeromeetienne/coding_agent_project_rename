# Agent instructions

Use plain international English and preserve established names. Read CONTEXT.md before editing.

## Development

Requires Node.js 24 or later and pnpm. Run `pnpm install --frozen-lockfile`, `pnpm start --help`, `pnpm test`, and `pnpm check`.
Keep tests isolated to synthetic projects and application stores. Preserve backup, verification, restoration, and manual client closure behavior.
Use strict TypeScript with an ES2020 target, tab indentation, named exports, and the existing class structure.

## Documentation

The docs folder uses README.md for people and index.md for navigation. Keep the existing metadata headers and update Last updated and navigation with each change.
Historical evidence describes the original runs; do not rewrite historical paths or measurements as current results.

## Migration

This repository was extracted from coding_agent_plugins for [issue #79](https://github.com/jeromeetienne/coding_agent_plugins/issues/79).
