# Technical Debt / Refactor Workflow

Use this workflow when improving structure without intended behavior change.

## Purpose

Improve maintainability while preserving behavior.

## Phase Sequence

1. `01_intake.md`
2. `02_characterization.md`
3. `03_refactor_boundary.md`
4. `04_execution_plan.md`
5. `05_validation_closeout.md`

## Agent Rules

- Behavior must remain unchanged unless explicitly approved.
- Add characterization tests if behavior is not already protected.
- Stop if the refactor becomes architecture redesign.
- Keep diffs small and reviewable.

## Initial Wizard Questions

```text
Selected workflow: Technical Debt / Refactor
Process weight: Standard unless the area is broad or risky.

Current phase: Intake

Answer what you can:
1. What area feels like technical debt?
2. What problem does the debt cause?
3. Should behavior stay exactly the same?
4. Are there tests covering current behavior?
5. Is this cleanup, refactor, or architecture change?
```
