# AGENTS.md

## Purpose

This file defines how AI agents should work in this repository.

AI may assist with exploration, implementation, testing, refactoring,
documentation, review, and summarization. The developer remains responsible for
requirements, architecture, correctness, validation, security, and final
approval.

## Operating Rules

- Understand the request and relevant files before editing.
- Prefer minimal, focused, reviewable changes.
- Preserve existing architecture, contracts, public behavior, and style.
- Do not infer new architecture silently.
- Do not expand scope without approval.
- Do not treat existing bad patterns as precedent.
- Avoid clever abstractions that hide control flow or domain boundaries.
- Do not add dependencies without approval.
- Do not expose secrets, credentials, regulated data, or confidential data.
- Stop and ask when requirements, scope, validation, risk, or architecture impact is unclear.
- Report changes clearly.

## Decision Hierarchy

When instructions conflict, prioritize:

1. correctness
2. explicit user request
3. architecture / contracts
4. security / data protection
5. fail-loud behavior
6. minimal diff
7. formatting conventions

## Plan-First Triggers

Create a plan before changing:

- schema changes
- public APIs or data contracts
- authentication, authorization, secrets handling, or sensitive data flows
- architecture changes
- pipeline/stage changes
- cross-module behavior
- dependency or package-manager configuration
- generated artifacts, migrations, snapshots, or lockfiles
- behavior that lacks test coverage

The plan should identify impacted files, expected behavior, validation steps,
risks, and stop conditions.

## Coding Standards

- Follow existing repository style.
- Prefer existing helpers, patterns, and abstractions.
- Preserve formatting unless formatting is the task.
- Avoid unrelated cleanup.
- Keep error handling explicit.
- Prefer fail-loud behavior when silent failure would hide data or correctness issues.
- Add comments only when they clarify non-obvious logic.

Fill in repository-specific standards:

```text
Language/runtime:
Frameworks:
Formatting rules:
Naming conventions:
Generated files:
```

## Testing and Validation

Use the right level of validation for the risk:

- unit tests for isolated logic
- integration tests for cross-module behavior
- smoke tests for major workflows or stage execution
- regression tests for output stability
- manual review when tests cannot prove correctness

When reporting validation, explain what was run, what passed or failed, what
the validation proves, what it does not prove, and what remains untested.

Fill in common commands:

```text
Install dependencies:
Run unit tests:
Run smoke tests:
Run regression tests:
Run lint:
Run typecheck:
Run build:
```

If a command is unavailable, expensive, or unsafe to run routinely, document
that here.

## Change Report

After non-trivial changes, report:

- files changed
- purpose
- behavior impact
- architecture or contract impact
- tests run
- validation limits
- risks or follow-up tasks
- documentation updates

## Durable Context

Chat threads are temporary working context, not durable project memory.
Reusable decisions, architecture notes, conventions, and AI operating rules
belong in repository docs, tests, architecture records, or `AGENTS.md`.
