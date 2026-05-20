# Bug Fix Workflow

Use this workflow when fixing incorrect behavior, failed tests, bad output, regressions, or user-reported defects.

## Purpose

Reproduce, isolate, fix, prove.

## Phase Sequence

1. `01_intake.md`
2. `02_reproduction.md`
3. `03_root_cause.md`
4. `04_fix_plan.md`
5. `05_validation_closeout.md`

## Agent Rules

- Do not fix symptoms before identifying likely cause.
- Do not refactor unrelated code.
- Prefer a failing test or characterization before the fix.
- Stop if the fix requires broad architecture change.

## Initial Wizard Questions

```text
Selected workflow: Bug Fix
Process weight: Standard unless the issue is trivial or high-risk.

Current phase: Intake

Answer what you can:
1. What is the observed behavior?
2. What is the expected behavior?
3. Can you reproduce it?
4. Are there logs, errors, screenshots, or failing tests?
5. What area of the project might be involved?
```
