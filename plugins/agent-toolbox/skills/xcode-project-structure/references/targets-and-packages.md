# Targets and Packages

## Naming

-

## App Target

- The app target should facilitate the communication between features, but should not include feature implementations.
- The app target should create an app-wide dependencies, which can then be injected in to individual features.

## Heirachy

Projects are built using layers. These should be treated as hard boundries and have different requirements when looking at test coverage, API, and flexibility. Each layer may depend on any packages from the layers below, but some may not rely on those within the same layer.

// TODO: Flip to have App at the top so it's more of a "built on top of"
   Utilities
       ↓
Core Technologies
       ↓
   Foundations
       ↓
    Services
       ↓
    Features
       ↓
      App

## Utilities

- Utility package must be project-agnostic.
- Most utility packages will be added as external dependencies.
- May depend on other packages in this layer, although rarely.
- Should have high code coverage.
- Examples:
  - JosephDuffy/Persist
  - JosephDuffy/HashableMacro
  - apple/swift-algorithms

## Core Technologies

- Should not include any code specific to the app.
- Might be open-source, or may be made open-source in the future.
- May be added as external dependencies, excluding where they wrap system functionality and tests would mostly test the system functionality.
- May depend on other packages in this layer, although rarely.
- May contain multiple libraries.
- Examples:
  - JosephDuffy/GatheredKit

## Foundations

- Contain code that would be shared across multiple features, such as shared UI compontents, wrappers around services, and shared models.
- Most apps will include:
  - AppUI: Generic or shared UI components. Does not include unit tests.
  - AppFoundation: Foundational types, shared extensions, and any constants that are required from multiple features. Should include unit tests.
- Should contain a single library.
- May depend on other packages in this layer.

## Services

- Contain individual services that by themselves are not features, such as access to an API or a capability required by multiple feature.
- Should have high code coverage, except when wrapping external sources, such as a 3rd party API.
- May contain multiple libraries.
- May depend on other packages in this layer.

## Feature Packages

- Feature packages are focussed on a single feature.
- Should split UI and business logic between 2 libraries: FeatureUI and FeatureFoundation.
- May not depend on other packages in this layer.

## Library Boundaries

- Keep the boundaries between libraries clear.
- Use `package`-scoped symbols where it would reduce the public API of the package while allowing the other libraries in the package to function.

## Tests

- Keep test targets parallel to the source they validate.
- Prefer focused package or feature tests over large app-target tests when practical.
- Do not create protocol layers solely to make package or target tests easier.
- Create a PackageTestSupport library when test-specific types or symbols are needed outside of the package that declares. For example, mocks, stubs, or the ability to create an instance of something without an otherwise public initialiser.
