---
name: cleanup
description: Simplifies code and documentation by removing unnecessary parts, flattening overcomplicated implementations, and pruning artifacts left by deletion. MUST USE when the user asks to clean up, simplify, reduce, prune, remove slop, delete dead code, or strip a project to essentials.
---

## Scope

- Identify the exact target and the behavior or content that must remain.
- Change only that target. Do not clean up nearby code, files, documentation, or formatting unless required by the requested cleanup.
- Do not add features, abstractions, compatibility layers, configuration, tests, or documentation as part of cleanup unless explicitly requested.
- Ask before proceeding only when unclear scope could cause meaningful data or behavior loss.

## Process

1. Inspect the target and its references before editing.
2. Separate required behavior from removable code or content.
3. Delete unnecessary parts instead of replacing them with new layers.
4. Simplify the remaining implementation using direct, readable logic.
5. Remove imports, exports, variables, helpers, files, assets, and configuration made unused by the cleanup.
6. Check that the requested behavior and content remain and that removed symbols have no live references.

## Code cleanup

- Prefer fewer files, fewer layers, and explicit control flow when they make the code easier to read.
- Remove a requested feature completely, including its now-unused supporting code. Do not leave aliases, shims, placeholders, or commented-out code unless the user asks for compatibility.
- Inline one-use wrappers and helpers when doing so is clearer. Keep shared code when removing it would create substantial repetition or make behavior harder to understand.
- Preserve public behavior, APIs, stored data, schemas, and routes unless changing them is part of the request.
- Do not rename, reformat, or refactor unrelated code.
- Do not add comments to explain code that can be written clearly.

## Code organization

- Organize around distinct responsibilities. Separation of concerns does not mean putting every function, component, or visual element in its own file.
- Treat separation and reuse as different goals. Do not create shared abstractions or modules merely to make separated code reusable.
- Before creating files, name the single responsibility of each proposed file. Keep related small parts together when they serve the same responsibility.
- Keep small helpers and subcomponents local to the file that owns their behavior. Extract them only when they belong to a different concern, not because they can be extracted.
- Avoid replacing one oversized file with many tiny files. That moves the organization problem instead of solving it.
- Separate data construction and transformation from rendering when both concerns are mixed together.
- Keep pages and entry points focused on wiring focused units together. Small sibling helpers may remain in the same file when they only support that wiring.
- Do not move code into shared files or edit another implementation just to reuse it when the user asked to organize one specific target.

## Documentation cleanup

- Edit documentation only when the user explicitly includes it in the task.
- Preserve required facts, instructions, examples, links, routes, and audience-relevant details.
- Remove repetition, false claims, internal implementation details, filler, and sections that do not help the intended reader.
- Do not invent features, commands, benchmarks, examples, or product behavior.
- Do not create a README, report, migration guide, or other documentation unless requested.
- Apply the `unslop` skill when rewriting substantive prose.

## Verification

- Search for references to every removed symbol or file.
- Confirm that cleanup did not remove required behavior or content.
- Run only the checks needed to verify the change. Do not claim success without evidence.
- Report only what was removed or simplified and any relevant verification result.
