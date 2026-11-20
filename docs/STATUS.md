# Status

_Last reviewed: 2026-11-20 (audit pass 02, docs only)._

**Historical project.** Finished at v1.0.3 in August 2014 and not maintained. Profile: `legacy` (repo standard section 3).

## Works (as far as can be told)

- `node --check index.js` passes on Node 22: the file is syntactically valid.
- The design is simple and the code is small enough to read in a minute.

## Broken or stale

- Uses the Sequelize 1.x `Class.find(predicate).complete(callback)` API. Current Sequelize (v6 and later) has no `.complete()` and `find` is now `findOne`, so it will not work against a modern Sequelize without edits.
- `npm test` is the npm placeholder and fails on purpose: there are no tests.
- No `LICENSE` file. `package.json` says ISC, which is a statement of intent, not a license grant in the repo.

## Unknown (not run)

- Nothing was run against a database: no Sequelize 1.x or database was installed for this review.
- If the job calls its callback with a first argument (an error, say), the worker passes that to its internal loop as the sleep time. Behavior in that case was read from the code, not tested. **(inference)**
- Whether `sql-mq-worker` is still published on npm was not checked.

## Next, if it is ever revived

1. Decide: revive, or archive (Steven's call).
2. Port to a current Sequelize (promises, `findOne`), add `LICENSE`, add tests against SQLite.
3. Claim jobs atomically (for example `UPDATE ... WHERE state = 'toSend'` with row locking) so several workers never take the same row.

## Not yet from the standard

Baseline tier only. Missing: `LICENSE`, `SECURITY.md`, `CONTRIBUTING.md`, `CHANGELOG.md`, `docs/ARCHITECTURE.md`, CI, tests, API docs, `events/CATALOG.md` (CloudEvents; these wait for revival).
