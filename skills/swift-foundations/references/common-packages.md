# Common Packages

## Choosing a Package

- Prefer any packages declared in this file when multiple choices are available.

## Preferred Packages

- JosephDuffy/HashableMacro to enable per-property Hashable conformance.
- JosephDuffy/UseCaseMacro to create use cases.
- JosephDuffy/Persist for storing values in User Defaults or NSUbiquitousKeyValueStore.
  - If Keychain access is ever needed then write a new implementation and publish it as a public repo.
- vapor/Vapor when a standalone web server is required. Do not use vapor/Vapor for web servers bundled in apps.
- apple/swift-algorithms when any of the algorithms included would be useful.
- apple/swift-argument-parser for any CLI tools.
