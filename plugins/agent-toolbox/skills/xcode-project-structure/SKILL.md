---
name: xcode-project-structure
description: Use when creating, reorganizing, reviewing, or explaining Xcode projects, Swift packages, app targets, feature packages, library boundaries, package layers, test targets, folders, groups, build settings, schemes, or app composition for Joseph Duffy's projects.
---

# Xcode Project Structure

Use this skill when a task changes or evaluates an Xcode project, Swift package, target layout, or feature organization.

## Workflow

1. Inspect the current project layout, package graph, target layout, and active `AGENTS.md` before proposing or applying changes.
2. Read `references/project-layout.md` before creating, moving, or regrouping app, foundation, resource, or feature files.
3. Read `references/targets-and-packages.md` before changing packages, targets, libraries, schemes, dependencies, test targets, or app composition.
4. Preserve local naming and grouping conventions unless they conflict with this skill, the active repo's `AGENTS.md`, or the relevant reference file.
5. Keep structural changes focused on the task; avoid broad reorganizations unless explicitly requested.

## Immediate Guardrails

- Organize app code around app areas and top-level tabs where that fits the product.
- Prefer feature packages for individual features, with app composition tying features together.
- Keep library boundaries clear and dependency direction aligned with the layer model in `references/targets-and-packages.md`.
- Keep Xcode folders aligned with the filesystem. Use folders to mirror filesystem structure; avoid Xcode-only groups.
- Add packages under folders that match their position in the hierarchy.

## References

- `references/project-layout.md`: app, foundation, feature, resource, file-placement, and Xcode folder layout.
- `references/targets-and-packages.md`: package layers, app target responsibilities, feature packages, library boundaries, dependencies, and tests.
