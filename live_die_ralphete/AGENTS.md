# Ralph Loop — Agent Instructions

> This repository uses the [Ralph Loop](https://ghuntley.com/ralph/) pattern for autonomous AI agent development.
> Each iteration spawns a fresh agent with clean context.
> Memory persists via files on disk: `PLAN.md`, `TODO.md`, `PERSISTANCE.md`, and git history.

---

## Your Task (do this in order, every iteration)

### Step 0: Resolve existing TODOs first

Before doing ANY feature work, scan all project files for `TODO`, `FIXME`, and `HACK` comments.
If unresolved TODOs exist that are not yet listed in [TODO.md](TODO.md), add them under **Bootstrap Tasks**.
Work on bootstrap tasks before feature tasks. Only move to feature work when bootstrap tasks are done or explicitly deferred in [PERSISTANCE.md](PERSISTANCE.md).

### Step 1: Read state files

1. Read [PLAN.md](PLAN.md) — understand the current high-level goal
2. Read [TODO.md](TODO.md) — find the next actionable task (highest priority `[ ]` item)
3. Read [PERSISTANCE.md](PERSISTANCE.md) — check for known problems, patterns, and blockers
4. Check git log — understand what previous iterations have done

### Step 2: Pick ONE task

Pick the highest-priority task from [TODO.md](TODO.md) that is marked `[ ]`.
Mark it `[~]` (in progress). **Work on only ONE task per iteration.**

Each task must be small enough to complete in a single context window.
If a task is too large, split it into smaller tasks in [TODO.md](TODO.md) and pick the first sub-task.

### Step 3: Implement

- Write the code / make the changes for the selected task
- Follow existing code patterns and conventions
- Keep changes focused and minimal
- Run quality checks if applicable (typecheck, lint, test)

### Step 4: Record & commit

1. **Update [TODO.md](TODO.md)**: Mark the completed task `[x]` and move it to the Completed section with a short note
2. **Update [PLAN.md](PLAN.md)**: If you learned something that changes the plan, update it
3. **Update [PERSISTANCE.md](PERSISTANCE.md)**: Record any problems, gotchas, patterns, or context that future iterations need
4. **Commit** with message: `feat(<scope>): <description>` (or `fix`, `docs`, etc.)

### Step 5: Check for completion

If ALL tasks in [TODO.md](TODO.md) are `[x]`, reply with:

```
<promise>COMPLETE</promise>
```

If tasks remain, end your response normally. The next iteration will pick up where you left off.

---

## Key Files

| File | Purpose | Who writes it |
|------|---------|---------------|
| [PLAN.md](PLAN.md) | High-level plan and goal for the current session | Orchestrator / agent |
| [TODO.md](TODO.md) | Actionable task list with completion status | Agent (every iteration) |
| [PERSISTANCE.md](PERSISTANCE.md) | Problems, patterns, blockers, and learnings (append-only) | Agent (when discoveries are made) |
| [CONTRIBUTING.md](CONTRIBUTING.md) | Workflow conventions and orchestrator constraints | Human / setup |
| [CLAUDE.md](CLAUDE.md) | Agent-specific entry point | Human / setup |

---

## Rules for the Orchestrator / Plan-Mode Agent

> These constraints are for the **orchestrator** (the outer loop or plan-mode agent that manages iterations).
> They are NOT restrictions on the coding agent within a single iteration.

1. **DO NOT skip the TODO scan.** Every first iteration of a session must scan for TODOs across all files and populate [TODO.md](TODO.md) before doing anything else.
2. **DO NOT work on more than one task per iteration.** One task, one commit, one progress update.
3. **DO NOT discard state.** Always append to [PERSISTANCE.md](PERSISTANCE.md), never replace it. Always update [TODO.md](TODO.md), never start fresh unless explicitly told to.
4. **DO NOT ignore previous learnings.** Read [PERSISTANCE.md](PERSISTANCE.md) before starting work — it contains hard-won context from earlier iterations.
5. **DO NOT leave broken code.** If quality checks fail, fix them before committing. If you can't fix them, document the issue in [PERSISTANCE.md](PERSISTANCE.md) and move on.
6. **DO split large tasks.** If a task can't be completed in one iteration, break it into sub-tasks in [TODO.md](TODO.md).
7. **DO commit after each completed task.** Small, atomic commits preserve progress across iterations.

---

## Coding Guidelines

- Follow existing patterns in the codebase (indentation, naming, structure)
- Prefer readability over cleverness
- When adding new code, consider long-term maintenance cost
- Avoid unnecessary dependencies
- Consider cross-platform compatibility
- Add inline documentation (docstrings, comments) for non-obvious logic

---

## Related Documentation

- [CONTRIBUTING.md](CONTRIBUTING.md) — workflow conventions and orchestrator constraints
- [Build documentation](docs/build.md)
- [Testing documentation](docs/tests.md)
- [Modules & commit format](docs/modules.md)
