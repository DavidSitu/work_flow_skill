# Doc Update Rules

Use this file to decide which architecture doc should change. Use `references/architecture-structure.md` as the source of truth for the standard `ARCHITECTURE/` folder contract and file responsibilities.

## Architecture Shape

Use a two-layer architecture model by default:

- top-level docs for cross-cutting truth
- subsystem docs for bounded behavior areas

Stop at subsystem-level by default. Do not create per-function docs unless a function is unusually critical or complex.

For a medium or large app, prefer a small set of real subsystem docs before creating more. A good starting point is often 4-6 subsystem docs, not dozens of micro-docs.

Avoid too many tiny docs because they increase:

- file chasing
- duplicated facts
- doc drift
- the chance that one focused task requires opening many files

## Top-Level Docs

- Use `ARCHITECTURE/current/01-project-intent.md` for stable project target: goals, users, scope, non-goals, constraints, current phase, and success direction.
- Use `ARCHITECTURE/current/02-milestones.md` for V0, V1, optional V1.x, optional V2+, roadmap direction, milestone direction, phase direction, and final-product direction.
- Use `ARCHITECTURE/current/03-overall-system-design.md` for system boundaries and architecture flow.
- Use `ARCHITECTURE/current/04-overall-ui-design.md` for UI/UX architecture, or mark it `N/A` for projects without a UI.
- Use `ARCHITECTURE/current/05-repo-map.md` for codebase layout and doc-to-code mapping.
- Add an ADR under `ARCHITECTURE/decisions/` only when a decision materially constrains future architecture work.

## Subsystem Docs

Use `references/subsystem-planning-rules.md` when subsystem granularity, code ownership, import direction, or test strategy is part of the decision.

Create or update a subsystem doc when a change affects one specific area's:

- purpose or scope
- boundary contract, public API, or internal ownership
- flows and transitions
- states and rules
- APIs, RPCs, jobs, or data dependencies
- code map
- import rules or test strategy
- known gaps
- safe extension points

Create a subsystem doc only when the area has one or more of these:

- meaningful business logic
- multiple modules or code paths
- important states or transitions
- backend and frontend interaction
- non-obvious constraints or likely future expansion
- independently testable behavior
- owned data, storage, device capability, API contract, or job

Name subsystem docs by bounded behavior, not vague buckets.

Prefer:

- `auth-session-and-timezone`
- `companion-lifecycle-and-reveal`

Avoid vague buckets such as:

- `login-system`
- `pet-system`

The goal is to name the behavior boundary a contributor actually needs to understand. Do not group unrelated behavior into one vague subsystem doc.

Do not create subsystem docs by default for:

- one function
- one hook
- one helper
- one UI component
- one UI page that only renders a view
- a folder that is only an implementation bucket

A UI page can be a subsystem only when it owns a real workflow, state machine, data contract, lifecycle, or cross-layer behavior. Otherwise, document it inside the subsystem that owns the workflow.

Split a subsystem when it has distinct ownership, state, data, dependencies, failure modes, or tests. Merge or avoid splitting when two areas always change together, cannot be tested alone, or would create circular/chattering dependencies.

For a focused task, the ideal documentation read set is usually:

- `01-project-intent.md` only if product intent matters
- `02-milestones.md` only if roadmap, phase, milestone, or session planning depends on it
- one relevant top-level doc
- one relevant subsystem doc
- `05-repo-map.md` only when code location is needed

If a focused task keeps requiring many scattered top-level docs, move the detailed behavior into a subsystem doc instead of fragmenting the top-level set further.

## Archive Rules

- Do not update `ARCHITECTURE/archive/` during normal current-state work.
- Move a document into `archive/` only when it is no longer current but still valuable for history.
- Consult `archive/` only for historical comparison, migration context, or explicit user requests.
- During retrofit, merge still-current facts from old docs into the current docs before archiving useful historical material.
- Do not blindly rename existing numbered architecture files unless the user asked for retrofit or normalization and references can be updated cleanly.

## Drift Handling

If code and current docs disagree:

- treat code as runtime truth for what currently happens
- update `current/` if the runtime behavior is intentional and should become the new documented truth
- otherwise, record the mismatch in the relevant current doc and add a task in `TODO.md`
