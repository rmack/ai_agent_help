# AGENTS.md

## Purpose
Defines how AI agents should work in this repository.

## Operating Rules
- Understand before editing
- Prefer minimal changes
- Do not infer new architecture
- Preserve contracts
- Report changes clearly

## Decision Hierarchy
1. correctness
2. explicit user request
3. architecture / contracts
4. security / fail-loud behavior
5. minimal diff
6. formatting conventions

## Plan-First Triggers
Require a plan before:
- schema changes
- cross-module changes
- architecture changes
- pipeline/stage changes
- behavior changes

## Coding Standards
- follow repo style
- preserve formatting
- avoid clever abstractions
- no unrelated cleanup

## Testing and Validation
- unit tests for isolated logic
- smoke tests for system/stage execution
- regression tests for output stability
- run relevant commands when practical

## Change Report
After non-trivial changes, report:
- files changed
- purpose
- behavior impact
- tests run
- risks
