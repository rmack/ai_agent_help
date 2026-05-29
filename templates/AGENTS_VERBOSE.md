# AGENTS.md

## Purpose

Define how AI agents should work in this repository.

This file is the repository-level operating contract for AI-assisted work. Agents must follow it unless the user explicitly provides a higher-priority instruction.

## Project Context

- Project purpose: `[describe what this repository does]`
- Primary users: `[describe users, operators, systems, or teams]`
- Runtime environment: `[local, cloud, on-prem, edge, hybrid, etc.]`
- Production criticality: `[prototype, internal tool, production, regulated, safety-critical, etc.]`
- Important constraints: `[security, compliance, performance, compatibility, cost, platform, etc.]`

## Source of Truth

- Repository code is the source of truth for current behavior.
- Tests describe expected behavior where coverage exists.
- Architecture docs describe intended structure and constraints.
- Schemas, migrations, API specs, and generated artifacts must be treated as contracts.
- Chat threads are temporary working context, not durable project memory.

Fill in repo-specific sources of truth:

- Architecture docs: `[path]`
- API contracts / schemas: `[path]`
- Database migrations: `[path]`
- Deployment / infrastructure config: `[path]`
- Test suites: `[path]`
- Generated files: `[path or "none"]`

## Agent Operating Model

- The developer remains the decision-maker.
- Understand the request and relevant code before editing.
- Prefer small, reviewable changes.
- Preserve existing architecture, contracts, and style.
- Do not infer new architecture silently.
- Do not expand scope without approval.
- Explain assumptions when they affect implementation.
- Stop when requirements, risks, or validation expectations are unclear.

## Work Modes

Use the appropriate mode for the task:

- Exploration: clarify requirements, architecture, options, risks, or tradeoffs. Do not edit implementation files.
- Execution: make scoped changes after goal, scope, constraints, and validation expectations are clear.
- Review: inspect code, diffs, architecture, tests, or CI/CD and report findings before summaries.
- Summary: capture durable context, decisions, open questions, and follow-up tasks.

Before switching from exploration to execution, confirm the change is ready to implement.

## Before Implementation

Confirm or infer safely:

- goal
- scope
- out of scope
- affected files or modules
- constraints
- expected behavior
- validation plan
- stop conditions

If any item is unclear and could change the implementation, ask before editing.

## Decision Hierarchy

When instructions conflict, prioritize:

1. correctness
2. explicit user request
3. architecture and contracts
4. security and data protection
5. fail-loud behavior
6. minimal, reviewable diff
7. repository style and formatting conventions

## Plan-First Triggers

Create a plan before changing:

- schemas or data contracts
- public APIs
- authentication, authorization, or secrets handling
- cross-module behavior
- architecture boundaries
- pipeline, stage, workflow, or job orchestration
- deployment, infrastructure, or CI/CD config
- database migrations or data backfills
- dependency versions or package manager configuration
- performance-critical paths
- behavior that lacks test coverage

## Stop Conditions

Stop and ask for direction if:

- requirements are ambiguous
- the task grows beyond the requested scope
- architecture impact is larger than expected
- a new dependency seems necessary
- a contract, schema, migration, or API change is needed
- sensitive data, credentials, or regulated data may be involved
- tests fail for unclear reasons
- validation cannot be performed
- implementation would require guessing

## Repository Map

Fill in the important repository areas:

```text
[path] - [purpose]
[path] - [purpose]
[path] - [purpose]
```

Areas agents should avoid unless explicitly requested:

```text
[path] - [reason]
[path] - [reason]
```

## Common Commands

Fill in commands for this repository:

```text
Install dependencies:
[command]

Run unit tests:
[command]

Run smoke tests:
[command]

Run regression tests:
[command]

Run lint:
[command]

Run typecheck:
[command]

Run build:
[command]

Run formatter:
[command]
```

If a command is unavailable or too expensive to run routinely, document that here.

## Coding Standards

- Follow existing repository style.
- Prefer existing helpers, patterns, and abstractions.
- Avoid clever abstractions.
- Avoid unrelated cleanup.
- Preserve formatting unless formatting is the task.
- Keep error handling explicit.
- Prefer fail-loud behavior when silent failure would hide data or correctness issues.
- Add comments only when they clarify non-obvious logic.

Repo-specific standards:

- Language/runtime: `[fill in]`
- Frameworks: `[fill in]`
- Formatting rules: `[fill in]`
- Naming conventions: `[fill in]`

## Architecture and Contract Rules

- Preserve module boundaries.
- Preserve public APIs unless an API change is explicitly approved.
- Preserve schema compatibility unless a migration plan is approved.
- Do not introduce new architectural layers without approval.
- Do not bypass validation, authorization, or data access boundaries.
- Treat generated files, lockfiles, migrations, and snapshots as high-impact changes.

Repo-specific architecture constraints:

- `[constraint]`
- `[constraint]`

## Dependencies and Tooling

- Do not add dependencies without approval.
- Do not change package managers without approval.
- Do not update lockfiles unless dependency changes are intentional.
- Prefer standard library or existing dependencies when appropriate.
- Explain why a new dependency is needed and what alternatives were considered.

## Testing and Validation

Use the right level of validation for the risk:

- Unit tests for isolated logic.
- Integration tests for cross-module behavior.
- Smoke tests for major workflows.
- Regression tests for behavior that must remain stable.
- Golden artifact comparison for deterministic generated outputs.
- Manual review when tests cannot prove correctness.

When reporting validation, explain:

- what was run
- what passed or failed
- what the validation proves
- what it does not prove
- what remains untested

Review tests and artifact diffs for correctness. Do not treat successful
execution, regenerated outputs, or passing tests as sufficient evidence by
themselves.

## Security and Data Handling

- Do not expose secrets, tokens, keys, credentials, or sensitive data.
- Do not log sensitive data.
- Do not weaken authentication, authorization, encryption, or validation.
- Do not use production data unless explicitly approved.
- Do not send sensitive repository, customer, regulated, or proprietary data to external services unless approved.

Repo-specific sensitive areas:

- `[path or system]`
- `[path or system]`

## Generated Files

Generated files:

```text
[path] - generated by [command/tool]
```

Rules:

- Do not edit generated files by hand unless explicitly instructed.
- Regenerate artifacts using the documented command.
- Include source changes and generated output together when required.

## Git and Change Discipline

- Do not revert user changes unless explicitly requested.
- Do not modify unrelated files.
- Keep diffs small and reviewable.
- Separate refactors from behavior changes.
- Avoid formatting-only churn unless formatting is the task.
- Do not create commits, branches, tags, or pull requests unless asked.

## Documentation Expectations

Update documentation when changes affect:

- user-visible behavior
- setup or commands
- architecture or contracts
- operational procedures
- validation expectations
- known limitations

Durable decisions should be captured in repository docs, not only in chat.

## Change Report / Closeout

After non-trivial work, report:

- goal
- files changed
- behavior impact
- architecture or contract impact
- tests and commands run
- validation result
- validation limits
- risks or follow-up tasks
- documentation updates

If no tests were run, explain why.
