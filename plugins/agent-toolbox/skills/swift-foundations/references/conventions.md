# Swift Code Style and Conventions

## Optionals

- Never use explicitly unwrapped optionals.
- Prefer modeling unavailable or delayed values with plain optionals, initialization flow, dependency injection, or small helper methods.
- Do not justify an explicitly unwrapped optional by saying it is "known to be safe." Always unwrap the optional by assigning it to a variable.

## Trailing Commas

- Add trailing commas wherever Swift allows them, including modern positions enabled by SE-0439.
- Apply this consistently to multiline literals, argument lists, generic constraints, cases, and declarations where accepted by the compiler.

## Extensions

- Do not add narrow formatting or domain-specific APIs to standard library or system framework types.
- Instead of adding something like `String.formattedAsProjectName`, put the formatting function on the type that owns the concept.
- Extensions on external types are acceptable for generic utilities that are plausibly reusable across domains.

## Types and Files

- Aim for one top-level type per file.
- Exceptions are fine for tightly coupled types and private helper types that only exist to support the main type.
- Prefer file names that match the primary type.

## File Names

- Prefer file names that match the primary type being declared.
- Files that add extentions to a type should be in the format `Type+Feature`.

## Protocols

- Do not create protocols solely to enable mocks, stubs, or tests.
- Use protocols when they model a real substitutable abstraction, replace a class hierarchy, or already have multiple production implementations.
- For dependency injection in view models and services, prefer UseCaseMacro-produced use cases.

## Persistence

- Use JosephDuffy/Persist for stored or saved values.
- Avoid ad hoc wrappers over `UserDefaults`, files, or keychain unless the project already has a specific abstraction for that storage.

## Concurrency

- Avoid `@unchecked Sendable`.
- Only consider `@unchecked Sendable` for types protected by internal locks where a safer concurrency design does not work.
- Do not use `nonisolated(unsafe)` in a final implementation. During a refactor, any temporary `nonisolated(unsafe)` must be removed before delivery.

## API

- Always follow the [Swift API Design Guidelines](https://www.swift.org/documentation/api-design-guidelines/)
- Opt for the smallest surface area when designing API. Only expose a symbol if it's actually needed.

## Dependency Injection

- Prefer UseCaseMacro to produce injectable use cases for view models and services.
- Keep injected dependencies explicit at the boundary where behavior is coordinated.
- Do not hide dependencies behind global state or broad service locator APIs.
