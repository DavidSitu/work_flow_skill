# Retrofit Rules

Use these rules when `$WF` is asked to adopt or restore the workflow in an existing repository, especially via `$wf retrofit`.

## Goal

Bring an existing repository into the standard WF structure without treating it like a brand-new project and without overwriting useful existing material.

## First Pass Inspection

- Inspect the repo shape, entrypoints, and key folders first.
- Read the project README and any existing project docs that explain intent or structure.
- Inspect `TODO.md`, `LOG.md`, and `ARCHITECTURE/` if they already exist.
- Determine what already exists, what is missing, and what is nonstandard.
- Identify behavior-based subsystem candidates and obvious mixed-ownership areas without moving code on the first pass unless requested.

## Preservation Rules

- Preserve useful user content by default.
- Do not overwrite existing files unless the user clearly wants normalization or replacement.
- Prefer migrating or reshaping existing tracking and docs over deleting and recreating them.
- If old structure is unclear or mixed-quality, preserve it conservatively and summarize the tradeoffs.

## Standard WF Structure

Ensure these exist when needed:

- `TODO.md`
- `LOG.md`
- the standard `ARCHITECTURE/` skeleton from `references/architecture-structure.md`

Use `references/session-tracking.md` as the format contract for `TODO.md` and `LOG.md`.

Create the standard current architecture docs when reconstructing architecture. Use `02-milestones.md` for accepted milestone direction, or keep it thin when milestone direction is not yet known. Mark `04-overall-ui-design.md` as `N/A` with a short reason for backend-only, CLI-only, or library projects. Create `ARCHITECTURE/decisions/` only when recording actual ADRs.

## TODO Migration Rules

- Convert active work into the standard session-based structure from `references/session-tracking.md`.
- Keep only the current and near-next sessions in `TODO.md`.
- Do not copy a long stale backlog into the new `TODO.md`.
- If an old `TODO.md` contains mixed backlog and active work, preserve the useful active items and summarize any dropped backlog in the handoff.

## LOG Migration Rules

- Preserve useful history.
- Normalize only enough to make future entries consistent.
- Do not rewrite a large historical log unless the user asks for a full cleanup.
- New entries should follow `references/session-tracking.md` and use the same date and session IDs used in `TODO.md`.

## Architecture Recovery Rules

- Use `references/architecture-structure.md` as the folder and file contract.
- Use `references/subsystem-planning-rules.md` when reconstructing subsystem boundaries from existing code.
- Create or normalize the top-level current docs first.
- If old milestone content exists in `01-project-intent.md`, move only accepted milestone direction into `02-milestones.md`; keep stable project target content in `01-project-intent.md`.
- If existing `02-overall-system-design.md`, `03-overall-ui-design.md`, or `04-repo-map.md` exist, plan a safe rename to `03`, `04`, and `05` only when links and references can be updated cleanly.
- If renaming would create churn, preserve existing filenames and document the local structure in `ARCHITECTURE/README.md`.
- Merge still-current facts from old docs into the current docs before archiving useful historical material.
- Create subsystem docs only for clearly justified bounded areas.
- Prefer a thin but correct first-pass architecture set over speculative detail.
- Use actual code and project docs as the source of truth when reconstructing missing architecture.
- Map existing folders/files to proposed subsystem owners before planning moves.
- Document temporary mixed ownership rather than forcing a large refactor during retrofit.

## Completion Criteria

A successful retrofit should leave the repo with:

- standard WF tracking files or clearly normalized equivalents
- a usable current architecture skeleton
- a first-pass subsystem ownership map when the repo has meaningful behavior areas
- a clean session-based `TODO.md`
- a `LOG.md` structure that can record future sessions consistently
- a brief summary of what was created, what was preserved, and what still needs follow-up
