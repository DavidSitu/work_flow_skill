# Subsystem Doc Template

Use this template for `ARCHITECTURE/current/subsystems/<name>.md`.

Use `references/subsystem-planning-rules.md` when deciding whether a subsystem is large enough to deserve a doc and how its code/test boundaries should work.

## Naming Guidance

- Name the file by bounded behavior, not by a vague system bucket.
- Prefer names like `auth-session-and-timezone.md` or `companion-lifecycle-and-reveal.md`.
- Avoid names like `login-system.md` or `pet-system.md` unless the area is truly cohesive at that level.
- Do not create subsystem docs for every function, hook, widget, UI page, or tiny helper area.
- A page or device capability becomes a subsystem only when it owns meaningful workflow, lifecycle, state, data, dependencies, or tests.

```md
# <Subsystem Name>

## Purpose

Describe what this subsystem is responsible for.

## Scope

- In scope:
- Out of scope:

## Boundary Contract

- Owns:
- Does not own:
- Public entrypoints:
- Internal files:

## Data Ownership

- Owns:
- Reads from:
- Writes to:
- Storage / tables / keys:

## Key Flows

- Flow 1:
- Flow 2:

## States And Rules

- Important states:
- Transition rules:
- Validation or business rules:

## Interfaces And Dependencies

- UI surfaces:
- Services / providers / controllers:
- RPCs / APIs / jobs:
- Data models / tables / storage:

## Import Rules

- Allowed imports:
- Forbidden imports:
- Shared utilities allowed:

## Code Map

- Primary paths:
- Key entrypoints:
- Important symbols:

## Test Strategy

- Unit tests:
- Contract tests:
- Integration tests:
- Manual verification:

## Known Gaps

- Missing behavior:
- Technical debt:
- Operational risks:

## Safe Extension Points

- Where new behavior should be added:
- What should not be coupled or duplicated:

## Refactor Notes

- Current mixed-ownership areas:
- Files to move later:
- Compatibility constraints:
```
