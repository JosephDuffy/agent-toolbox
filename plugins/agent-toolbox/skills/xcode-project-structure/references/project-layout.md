# Xcode Project Layout

## Organization

- Organise the main app target by splitting areas of the app in to different folders, starting with the top-level tabs.
- Use broad type folders only for genuinely shared infrastructure or small projects where feature folders would add ceremony.
- Keep files near the feature, flow, or module that owns them.
- Keep generated code, fixtures, previews, and support files visually separate from hand-written product code.

## Project Structure

Use the existing project style when present. For new projects, or when refactoring an existing project, prefer a shape like:

```text
App/
  A Tab/
  B Tab/
  Resources/
  Root/
Foundation/
  AppFoundation/
  AppUI/
  ServiceA/
Features/
  FeatureA/
    Sources/
      FeatureAFoundation/
      FeatureAUI/
      FeatureATestSupport/
    Tests/
      FeatureATests
```

The Resources folder should contain any files that are not source code, such as the Info.plist file, .entitlements files, localisation files, and .xcassets.

The Root folder should contain the types used to bootstrap the app, include the app delegate, scene delegate, and root view controller (likely a tab bar controller).

Features should be contained within individual packages, which are then tied together by the main app target.

## Xcode Groups

- When moving files, update project references carefully and verify the build.
