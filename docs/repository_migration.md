# Repository migration

- Created: 14 November 2026
- Last updated: 14 November 2026
- Status: Migration evidence
- Related framing: [Agent instructions](../AGENTS.md)
- Related issue: [Issue #79](https://github.com/jeromeetienne/coding_agent_plugins/issues/79)

For maintainers reviewing the extraction: the package moved to the repository root, and the current tool documentation moved to docs. Git history was filtered to the package, its current and earlier documentation paths, and LICENSE. Nine relevant commits retain their authors, dates, and messages, with rewritten identifiers because file paths changed.

Every current package file is retained. Implementation and test code changes only rename the command and its test invocation. Package metadata, current commands, context headings, and relative documentation links were adapted for independent use. Historical verification evidence and recovery behavior are preserved.

The original pnpm lockfile was retained with the package importer moved to the repository root; dependency versions did not change.

## Commit mapping

| Original history | Extracted history |
| --- | --- |
| [Original commit](https://github.com/jeromeetienne/coding_agent_plugins/commit/02ca3e41bf0340d0a18207ea75109c0217d089c7) | [Extracted commit](https://github.com/jeromeetienne/coding_agent_project_rename/commit/56a377ad0d2c065a0765479aa74a74920a919627) |
| [Original commit](https://github.com/jeromeetienne/coding_agent_plugins/commit/521cb21ccc9bab9d563c2ed3ad2104f4e16fa069) | [Extracted commit](https://github.com/jeromeetienne/coding_agent_project_rename/commit/597256c11bf2ad7afedefb290e1a6aed44bc8fb9) |
| [Original commit](https://github.com/jeromeetienne/coding_agent_plugins/commit/6d4bb294c625b389d3f83984f145b901e3fe1cbe) | [Extracted commit](https://github.com/jeromeetienne/coding_agent_project_rename/commit/aaaac60d1f25081d06c3bdcd46aacad550c08555) |
| [Original commit](https://github.com/jeromeetienne/coding_agent_plugins/commit/8f7a49beac3b973a10eeaa2d73be3fd6af7d5be8) | [Extracted commit](https://github.com/jeromeetienne/coding_agent_project_rename/commit/16dcfe5561ffd1b6e2156a53ead74351f4c964bd) |
| [Original commit](https://github.com/jeromeetienne/coding_agent_plugins/commit/94ea0b7a7267b6fe9fbf2e2176c42d55bc4a3295) | [Extracted commit](https://github.com/jeromeetienne/coding_agent_project_rename/commit/f9a6bf61ae15ee29efffd1b3397a5c924f66f0ec) |
| [Original commit](https://github.com/jeromeetienne/coding_agent_plugins/commit/aaab8aee882f8f398e5298145040d4aee5a414ed) | [Extracted commit](https://github.com/jeromeetienne/coding_agent_project_rename/commit/5b2cf14ac1474e39d0193a698af989e845ac519e) |
| [Original commit](https://github.com/jeromeetienne/coding_agent_plugins/commit/c9f73a16685a9a1bae1354881c309cbdb5a56f38) | [Extracted commit](https://github.com/jeromeetienne/coding_agent_project_rename/commit/55ac9ce6641761206a4736ce36eb73caf1991cb7) |
| [Original commit](https://github.com/jeromeetienne/coding_agent_plugins/commit/eeddfb45beadf1e3eb29bd6bebcf9c457d762495) | [Extracted commit](https://github.com/jeromeetienne/coding_agent_project_rename/commit/19efb28a5e8135d0de934472d3c930c7a6efd0fb) |
| [Original commit](https://github.com/jeromeetienne/coding_agent_plugins/commit/eff797118be7a8f450ec12cd5379b42779f4e021) | [Extracted commit](https://github.com/jeromeetienne/coding_agent_project_rename/commit/635b27d1a408656e974f41fe9df1c875a931f6ae) |
## Open work

- [Issue #75: preserve nested directory permissions](https://github.com/jeromeetienne/coding_agent_plugins/issues/75).
- [Issue #86: generated artifacts and operation storage](https://github.com/jeromeetienne/coding_agent_plugins/issues/86).

These issues remain in their original repository to preserve their discussion. Continue implementation in coding_agent_project_rename.

## Extraction verification

On 14 November 2026, Node.js 24.14.0 and pnpm 10.33.2 installed the standalone package with the frozen lockfile. Command help reported coding_agent_project_rename and TypeScript checking passed.

The complete test run passed 48 of 49 tests in 117.206 seconds. One test stopped at the existing 4 GiB free-space reserve while other test fixtures consumed disk space. The isolated retry passed in 8.938 seconds and rejected all six corruption classes and formatting-only restoration corruption. All 49 tests therefore passed across the full run and the isolated retry; the full run did not pass in one attempt.

The full run exercised synthetic rename, backup, verification, worker execution, and restoration. This extraction adds no new live application verification. See [verification history](verification_history.md) and [synthetic results](synthetic_results.md) for earlier results and their limits.
