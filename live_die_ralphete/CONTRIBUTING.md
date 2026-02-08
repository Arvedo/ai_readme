# Contributing

This repository is a **base template** for the [Ralph Loop](https://ghuntley.com/ralph/) pattern — an autonomous AI agent development workflow where each iteration spawns a fresh agent, works on one task, commits, and exits.

## How the Ralph Loop Works

```
Orchestrator spawns agent
       |
       v
Agent reads PLAN.md, TODO.md, PERSISTANCE.md
       |
       v
Agent scans for TODOs in project files (Step 0)
       |
       v
Agent picks ONE task from TODO.md
       |
       v
Agent implements, tests, commits
       |
       v
Agent updates TODO.md + PERSISTANCE.md
       |
       v
Agent exits -> Orchestrator spawns next iteration
```

Each iteration is **stateless** — the agent has no memory of previous runs except what is written to disk.

---

## File Responsibilities

| File | Purpose | Mutability |
|------|---------|------------|
| `PLAN.md` | High-level plan for the session | Updated when the plan changes |
| `TODO.md` | Task list with `[ ]`, `[~]`, `[x]` status markers | Updated every iteration |
| `PERSISTANCE.md` | Accumulated learnings, gotchas, patterns | Append-only (never delete entries) |
| `AGENTS.md` | Instructions the agent reads every iteration | Rarely changed |
| `CLAUDE.md` | Agent-specific entry point (for Claude Code) | Rarely changed |
| `CODEOWNERS.txt` | Ownership of files for review routing | Human-maintained |

---

## Conventions

### Commit Messages

Follow the format documented in [docs/modules.md](docs/modules.md):

```
<type>(<scope>): <description>
```

**Types**: `feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `test`, `build`, `ops`, `chore`

### One Task Per Iteration

The agent MUST work on exactly one task per iteration. This ensures:
- Small, reviewable commits
- Clean git history
- Progress is never lost if an iteration fails

### Bootstrap Before Features

On the first iteration of a session, the agent scans all files for `TODO`, `FIXME`, and `HACK` comments and adds them to `TODO.md` under **Bootstrap Tasks**. These are resolved before any feature work begins.

---

## Rules for the Orchestrator / Plan-Mode Agent

> **These rules govern the outer loop** — the system that spawns and manages agent iterations.
> They are NOT restrictions on what the coding agent can do within a single iteration.

1. **Scan for TODOs first.** The first iteration must populate `TODO.md` with any unresolved TODOs found across the codebase.
2. **One task per iteration.** Never assign multiple tasks to a single agent invocation.
3. **Preserve state.** Never reset `PERSISTANCE.md` or `TODO.md` — only append or update in-place.
4. **Read before writing.** The agent must read `PERSISTANCE.md` before starting work to avoid repeating past mistakes.
5. **Commit after each task.** Every completed task gets its own atomic commit.
6. **Split large tasks.** If a task is too big for one context window, break it into sub-tasks in `TODO.md`.
7. **Don't leave broken code.** Fix quality issues before committing. If unfixable, document in `PERSISTANCE.md`.

---

## Coding Guidelines

- Follow existing patterns in the codebase (indentation, naming, structure)
- Prefer readability over cleverness
- When adding new code, consider long-term maintenance cost
- Avoid unnecessary dependencies
- Consider cross-platform compatibility
- Add inline documentation (docstrings, comments) for non-obvious logic
- Vertical alignment makes things more readable and easier to batch edit

---

## For Humans Using This Template

This repo is meant to be **forked or copied** as a starting point for your own Ralph Loop project. To adapt it:

1. Update `PLAN.md` with your project's goal
2. Add your project-specific tasks to `TODO.md`
3. Customize `AGENTS.md` with project-specific coding guidelines
4. Fill in `docs/build.md` and `docs/tests.md` with your build/test instructions
5. Update `CODEOWNERS.txt` with your team

The orchestrator rules in this file and `AGENTS.md` stay the same — they define the loop's behavior, not your project's.

---

## Related Documentation

- [AGENTS.md](AGENTS.md) — full agent instructions (read every iteration)
- [Build documentation](docs/build.md)
- [Testing documentation](docs/tests.md)
- [Modules & commit format](docs/modules.md)
