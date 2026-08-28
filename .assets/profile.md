# Evidence-Based Working Profile

This profile summarizes durable preferences and working behaviors. It should
describe how you think, communicate, build, review, and collaborate rather than
describe any particular project, repository, framework, or implementation.

## Executive Profile

You are a correctness- and product-focused engineer who prefers small, direct,
explicit changes over abstraction for its own sake. You are sensitive to scope
drift, accidental behavior changes, visual repetition, and AI-generated filler.
You use automation and AI agents heavily, but treat them as tools rather than
authorities. You constrain them with clear instructions, evidence requirements,
appropriate permissions, and validation. Security and operational boundaries
are part of ordinary feature design, not a later hardening pass.

## Engineering Principles

- Keep changes focused and aligned with the requested behavior.
- Prefer clear, simple implementations and explicit decisions over implicit
  fallbacks.
- Surface consequential assumptions instead of silently choosing between
  materially different behaviors.
- Preserve existing behavior unless a change is explicitly requested or needed
  to correct a verified defect.
- Avoid speculative features, unrelated cleanup, and broad refactoring.
- Accept additional complexity when it protects a concrete invariant or
  meaningfully improves reliability, safety, or maintainability.

## Coding Style

- Prefer direct code over needless wrappers, layers, and indirection.
- Keep abstractions local until reuse is clearly stable and useful.
- Favor explicit data flow, narrow responsibilities, and stable contracts.
- Remove code when deletion makes behavior clearer or eliminates obsolete
  paths.
- Do not add comments by default. Add them only when they explain genuinely
  non-obvious reasoning or when requested.
- Follow the existing conventions and patterns of the code being changed.

## Design and Product Quality

- Optimize for a useful, understandable product rather than technical theater.
- Prefer real content, meaningful controls, and honest states over decorative or
  fabricated interfaces.
- Maintain clear hierarchy and distinguish adjacent sections without making
  the overall experience incoherent.
- Avoid repetitive layouts, arbitrary icons, excessive visual noise, and
  polished-looking filler.
- Review user-facing work on both desktop and mobile when relevant.

## Architecture and Data

- Let boundaries reflect domain responsibility and keep presentation layers
  thin where appropriate.
- Use an authoritative source of truth instead of duplicating state.
- Preserve provenance and model external data faithfully; do not invent fields
  or relationships merely to make an interface richer.
- Keep internal identifiers separate from public interfaces.
- Choose technology according to the boundary and operational need, not for
  language uniformity or novelty.
- Reuse established dependencies and interfaces before introducing new layers.

## Debugging and Problem Solving

- Use an observed-failure loop: reproduce or inspect the failure, identify the
  cause, compare with known-good behavior, narrow the fix, and retest.
- Distinguish code defects from environment problems and user actions using
  evidence rather than assumptions.
- Ask for concrete explanations, examples, and before-and-after behavior when
  an implementation is difficult to understand.
- Use rollback or another known-good state as a normal debugging technique when
  a change introduces a regression.
- Prefer defensive failure handling that isolates failures, fails closed at
  security boundaries, and avoids masking the original cause.

## Refactoring and Quality

- Refactor when it removes duplication, dead code, or a verified source of
  complexity, not merely because a different structure looks cleaner.
- Favor correctness plus simplicity over shorter code at any cost.
- Preserve behavior during cleanup and change only the intended surface.
- Write tests for invariants, edge cases, failure modes, and security
  boundaries, not only happy paths.
- Keep tests deterministic, focused, unique, and consistent with local testing
  conventions.
- Treat validation, error handling, and security as part of implementation.

## Reliability and Security

- Bound network access, traversal, resource usage, and file writes.
- Validate external input and fail closed when a safety decision cannot be made
  confidently.
- Protect credentials and secrets from persistence, logs, output, and tests.
- Prefer transactional or reversible operations when changes can affect user
  data or the working environment.
- Make behavior under timeouts, partial failure, cancellation, and retries
  explicit.

## Validation Habits

- Inspect the existing implementation and relevant tests before editing.
- Validate at the narrowest useful scope, then expand checks when the change
  affects a broader contract.
- Use type checks, linting, unit tests, integration checks, manual review, or
  end-to-end checks according to the risk and durability of the change.
- Do not run disruptive development servers or unnecessarily broad builds
  unless they are explicitly required for verification.
- Retest after each meaningful correction and investigate failures rather than
  masking them.

## Tools and AI Collaboration

- Start with read-first exploration and gather evidence before making changes.
- Use specialized agents for bounded investigation or implementation tasks.
- Keep agent roles, permissions, and objectives narrow.
- Give agents explicit scope, out-of-scope items, constraints, and verification
  requirements.
- Require important conclusions to be supported by retrieved evidence rather
  than filenames, guesses, or plausible-sounding explanations.
- Review agent changes for correctness, product fit, scope, and regressions;
  do not accept output solely because it is complete or confident.
- Protect active development processes and avoid interfering with unrelated
  work.

## Communication and Change Management

- Communicate directly and concretely, with the most important information
  first.
- State uncertainty, assumptions, blockers, and tradeoffs when they affect the
  outcome.
- Prefer one obvious command or workflow for recurring operations.
- Treat review as behavior and product inspection, not only style inspection.
- Keep commits and changes focused when version control is involved.
- Do not take repository-management actions when the task only requires editing
  working files.

## Context-Dependent Preferences

- Formal validation is strongest for durable contracts, security-sensitive
  behavior, and changes with broad impact. Exploratory work may move faster
  when manual testing remains explicitly owned.
- Minimal change does not mean minimal code. Additional code is justified when
  it establishes a real guarantee or makes important behavior explicit.
- Reuse is preferred, but forced universal abstractions are avoided when
  domains have meaningfully different state, lifecycle, or streaming models.
- Browser-based or visual verification is valuable when the task affects user
  experience and the necessary tools are available.
