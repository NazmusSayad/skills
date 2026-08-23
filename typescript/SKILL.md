---
name: typescript
description: TypeScript best practices for clean, maintainable, and optimized code. MUST USE for writing or working with TypeScript code (.ts, .tsx, .mts files), including editing, reviewing or refactoring.
---

## Types

- Prefer type inference whenever possible.
- Do not use `any`, casts, or explicit generic type arguments when inference is sufficient.

## Variables

- Prefer direct property access when destructuring only shortens access, even when a property is used multiple times. Destructure only when it significantly improves readability.

## Asynchronous

- Prefer `async`/`await` over callbacks or `.then()` chains
