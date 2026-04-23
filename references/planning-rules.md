# Planning Rules

Use these rules when `$WF` is handling planning, review, or scoped implementation work.

## Task Slicing

- Prefer small tasks that affect one subsystem or one clear behavior.
- Each task should have an obvious verification step.
- If a task spans multiple systems, split it into sequenced slices whenever possible.
- Keep only the current and near-next work in `TODO.md`. Remove stale or merged items.

## TODO Discipline

Use `TODO.md` for:

- active tasks
- next steps
- blockers
- short acceptance checks

Avoid turning `TODO.md` into a long backlog dump.

## LOG Discipline

Use `LOG.md` only for:

- completed milestones
- important decisions
- resolved blockers
- session handoff notes

Do not log every prompt, every edit, or obvious git-level changes.

## Review Flow

For review requests:

1. Identify the intended behavior from current docs and code.
2. Inspect the changed or affected code paths.
3. Return findings first, ordered by severity.
4. Note open questions or assumptions.
5. Add summaries only after findings.

## Planning Output

A good plan should:

- state the goal clearly
- identify the touched subsystem or code area
- list the smallest useful implementation steps
- define how each step will be verified
