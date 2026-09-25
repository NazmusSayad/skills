---
name: cleanup
description: Removes unnecessary code and content, simplifies what remains, and clears out the leftovers without losing required behavior or details.

disable-model-invocation: true
metadata: { opencode/autoinvoke: false }
---

## Boundaries

Identify the requested target and what must survive: behavior, public APIs, stored data, schemas, routes, and necessary content. Clean only that target and anything made unused by cleaning it. Ask before a removal that might lose something required.

Do not add features, abstractions, compatibility layers, configuration, tests, or documentation unless requested. Leave unrelated code, files, docs, names, and formatting alone.

## Remove and simplify

Inspect the target and its references. Delete unnecessary parts instead of rebuilding them behind new layers. When removing a feature, follow its dependencies: remove unused imports, exports, variables, helpers, files, assets, and configuration. Do not leave aliases, shims, placeholders, or commented-out code.

Simplify the remainder with direct, explicit logic. Remove one-use wrappers and helpers when inlining them reads better; keep shared code when inlining would create substantial repetition. Fewer files or layers help only when the result is easier to read. Do not add comments to explain code that can be written clearly.

## Organize only where it helps

Separate distinct responsibilities, not every function or component. Keep related small helpers and subcomponents beside the code they serve. Before adding a file, identify the different responsibility it owns; do not extract code merely to make it reusable. Splitting one large file into many tiny files can make it harder to follow.

When data construction or transformation is mixed with rendering, separate them. Keep pages and entry points focused on wiring the relevant parts together; small sibling helpers can stay there. Do not change another implementation or create a shared module solely to reuse code while cleaning one target.

## If documentation cleanup is requested

Preserve facts, instructions, examples, links, routes, and details the audience needs. Cut repetition, false claims, unnecessary implementation detail, and filler. Do not invent features, commands, benchmarks, examples, or product behavior, or create a new README, report, or guide unless requested.

Confirm that required behavior and content remain and no live references point to removed symbols. Report what was removed or simplified and any relevant verification result.
