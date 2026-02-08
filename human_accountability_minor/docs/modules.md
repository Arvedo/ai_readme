# Commit messages & modules — Simple guide


## Commit message format

A short, plain guide to help new projects write clear commit messages and use a small set of module scopes.

## Modules
Use short scopes to indicate the area of change. Pick a few that make sense for your project and keep the list small.

- backend 
- example (main, ...)
- build
- ci
- docs
- examples
- logging
- tests

(TODO:You can add or remove scopes to match your project.)

---

Use a short, consistent subject line and an optional body and footer:

```
<type>(<scope>): <description>
```

- Keep the subject 50–72 characters and use the imperative, present tense (e.g., "add", "fix").
- Use lowercase for the type and description; no trailing period.
- Scope is optional and should be a short module name (e.g., `docs`, `api`).

### Common types
- feat — a new feature
- fix — a bug fix
- docs — documentation only changes
- style — formatting, whitespace, linter changes (no code logic)
- refactor — code changes that do not add features or fix bugs
- perf — changes that improve performance
- test — adding or fixing tests
- build — build system or dependency changes
- ops — operational changes (infrastructure, deployment, backups, etc.)
- merge — merge commits
- chore — other maintenance tasks

### Breaking changes
- Mark breaking changes in the subject with a `!` before the `:` (example: `feat(api)!: remove v1 endpoints`) and add a `BREAKING CHANGE:` note in the footer with details.

### Changelog & tooling
- Group changelog entries by commit types used for releases: `feat` → Features, `fix` → Bug Fixes, `perf` → Performance Improvements, `merge` → Merges.
- Ignore commits that start with `WIP ` when generating changelogs (regex: `^WIP `).
- The changelog config has `includeInvalidCommits: true` — tools may include commits that don't match the commit regex; set to `false` to exclude them from generated changelogs.
- Release tags should follow `vMAJOR.MINOR.PATCH` (pattern: `v[0-9]*.[0-9]*.[0-9]*`).
- Parsing regex for commit headers: `^(?<type>\w+)(?:\((?<scope>[^()]+)\))?(?<breaking>!)?:\s*(?<description>.+)`.
- If using a changelog generator, set `commitUrl`/`commitRangeUrl` templates to enable links to commits and compare pages (example: GitHub URLs).
- Note: your config lists `ops` and `merge` as commit types and contains a duplicate `docs` entry; ensure configuration and docs stay aligned.

### Examples
- `feat: add user settings page`
- `fix(auth): handle missing token`
- `docs: update contributing guide`
- `refactor(db): simplify query builder`
- `perf: reduce memory usage in cache`
- `chore: bump dependency versions`


---

## References
- https://www.conventionalcommits.org/ — specification and examples
- https://github.com/qoomon/git-conventional-commits — CLI validator and helpers
