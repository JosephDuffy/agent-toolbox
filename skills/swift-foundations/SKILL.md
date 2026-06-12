---
name: swift-foundations
description: Use when writing, editing, reviewing, or explaining Swift code for Joseph Duffy projects, including Swift style, API design, optionals, trailing commas, file and type organization, extensions, protocols, concurrency, persistence, dependency injection, preferred packages, macro testing, and Swift Testing preferences.
---

# Swift Foundations

Use this skill when a task involves Swift source code or Swift code review in Joseph Duffy's projects.

## Workflow

1. Inspect the local project's existing Swift style and active `AGENTS.md` before editing.
2. Read `references/conventions.md` before making style-sensitive Swift or API changes.
3. Read `references/testing.md` before adding or changing tests, test support, or macro tests.
4. Read `references/common-packages.md` before adding a dependency or choosing between package options.
5. Prefer the project's established patterns unless they conflict with this skill, the active repo's `AGENTS.md`, or the relevant reference file.
6. Call out intentional deviations in the final response.

## Immediate Guardrails

- Do not introduce explicitly unwrapped optionals, `@unchecked Sendable`, or `nonisolated(unsafe)`.
- Do not introduce protocols solely for tests.
- Prefer Swift Testing for new tests.
- Prefer the packages listed in `references/common-packages.md` when they fit the task.

## References

- `references/conventions.md`: Swift style, API design, file naming, extensions, protocols, concurrency, persistence, and dependency injection.
- `references/testing.md`: Swift Testing, macro testing, deterministic tests, and testability guidance.
- `references/common-packages.md`: preferred packages and package-selection guidance.
