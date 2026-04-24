# Planning Rules

Use these rules when `$WF` is handling planning, review, or scoped implementation work.

## Task Slicing

- Prefer session-sized tasks that affect one subsystem or one clear behavior.
- Each session should be small enough to complete in one focused pass.
- Each session should have an obvious verification step.
- If a task spans multiple systems or sittings, split it into sequenced sessions whenever possible.
- Keep only the current and near-next sessions in `TODO.md`. Remove stale or merged items.

## TODO Discipline

Use `TODO.md` as a clean session tracker, not a backlog.

Format it with:

- a date heading using `YYYY-MM-DD`
- session sections such as `S1`, `S2`, `S3`
- a short title for each session
- a small checkbox list for that session only

Keep in `TODO.md`:

- the current session
- the next few planned sessions
- blockers only when they affect an active or near-next session

Do not keep a long master task list in `TODO.md`.

If a request is too large, split it into additional sessions instead of extending one session indefinitely.

## LOG Discipline

Use `LOG.md` as the dated record of completed sessions that matches the session structure in `TODO.md`.

Format it with:

- the same date heading used for the work
- the same session IDs such as `S1`, `S2`, `S3`
- a brief session title when helpful

Each log entry should record only useful outcomes, such as:

- what was completed
- the key result or decision
- the verification outcome when it mattered
- a blocker or handoff only if it affects the next session

Do not log every prompt, every edit, or in-progress work that has not reached a useful stopping point.

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
- split the work into the smallest useful session-sized slices
- define how each session will be verified
- keep the `TODO.md` output clean enough to execute session by session
