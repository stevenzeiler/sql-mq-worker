# AGENTS.md

Notes for AI agents and contributors.

## What this is

`sql-mq-worker` is a tiny 2014 npm library: a polling worker that treats a Sequelize-backed SQL table as a message queue. It is a **historical repo on the `legacy` profile** of the repo standard. Status and known problems: [docs/STATUS.md](docs/STATUS.md).

## Stack

- JavaScript (ES5, CommonJS), Node.js 0.10 era.
- Sequelize 1.x API (not declared in `package.json`; the host app supplies it).
- No build step, no dependencies, no lockfile.

## Layout

- `index.js`: the whole library (the `Poller` class).
- `package.json`: metadata, v1.0.3.
- `docs/`: `STATUS.md` and `docs/readme/banner.svg`.

## Commands

- `npm test`: placeholder from 2014, exits with an error (no tests exist).
- Syntax check: `node --check index.js`.

## Rules

- Docs-only changes unless the repo is explicitly revived (a decision for Steven, recorded in `docs/STATUS.md`).
- Never commit secrets, credentials, or database URLs.
- Use Conventional Commits (`docs:`, `fix:`, `chore:`).
- Update `docs/STATUS.md` whenever you learn something about what works.
- Do not add a `LICENSE` file; the license choice is Steven's.
