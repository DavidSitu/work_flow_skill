# Subsystem Doc Template

Use this template for `ARCHITECTURE/current/subsystems/<name>.md`.

## Naming Guidance

- Name the file by bounded behavior, not by a vague system bucket.
- Prefer names like `auth-session-and-timezone.md` or `companion-lifecycle-and-reveal.md`.
- Avoid names like `login-system.md` or `pet-system.md` unless the area is truly cohesive at that level.
- Do not create subsystem docs for every function or tiny helper area.

```md
# <Subsystem Name>

## Purpose

Describe what this subsystem is responsible for.

## Scope

- In scope:
- Out of scope:

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

## Code Map

- Primary paths:
- Key entrypoints:
- Important symbols:

## Known Gaps

- Missing behavior:
- Technical debt:
- Operational risks:

## Safe Extension Points

- Where new behavior should be added:
- What should not be coupled or duplicated:
```
