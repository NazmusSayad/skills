---
name: cleanup
description: Simplifies code and documentation by removing unnecessary parts, flattening overcomplicated implementations, and pruning artifacts left by deletion.

disable-model-invocation: true
metadata: { opencode/autoinvoke: false }
---

## Scope

Identify the exact target and what must remain. Change only that target. Do not clean up nearby code, files, documentation, or formatting unless the requested cleanup requires it.

Do not add features, abstractions, compatibility layers, configuration, tests, or documentation unless explicitly requested. Ask before proceeding only when unclear scope could cause meaningful data or behavior loss.

## Cleanup

Inspect the target and its references before editing. Separate required behavior from removable code or content. Delete unnecessary parts instead of replacing them with new layers, then simplify what remains using direct, readable logic.

Remove imports, exports, variables, helpers, files, assets, and configuration made unused by the cleanup. When removing a feature, remove its unused supporting code instead of leaving aliases, shims, placeholders, or commented-out code. Preserve public behavior, APIs, stored data, schemas, and routes unless the request includes changing them.

Prefer fewer files, fewer layers, and explicit control flow when they improve readability. Inline one-use wrappers and helpers when that is clearer, but keep shared code when removing it would create substantial repetition. Do not rename, reformat, or refactor unrelated code. Do not add comments to explain code that can be written clearly.

## Code organization

Organize code around distinct responsibilities. Separation of concerns does not mean placing every function, component, or visual element in its own file. Treat separation and reuse as different goals. Do not create shared abstractions or modules merely to make separated code reusable.

Before creating a file, identify its responsibility. Keep related small helpers and subcomponents local to the file that owns their behavior. Extract them when they belong to a different concern, not merely because extraction is possible. Replacing one oversized file with many tiny files moves the organization problem instead of solving it.

Separate data construction and transformation from rendering when those concerns are mixed. Keep pages and entry points focused on wiring the relevant units together. Small sibling helpers can remain beside that wiring. Do not edit another implementation or move code into shared files solely to reuse it when the user asked to organize one specific target.

## Documentation cleanup

Edit documentation only when the user explicitly includes it. Preserve required facts, instructions, examples, links, routes, and audience-relevant details. Remove repetition, false claims, unnecessary implementation details, filler, and sections that do not help the intended reader.

Do not invent features, commands, benchmarks, examples, or product behavior. Do not create a README, report, migration guide, or other documentation unless requested.

## Verification

Confirm that the cleanup preserved required behavior and content and left no live references to removed symbols. Report only what was removed or simplified and any relevant verification result.
