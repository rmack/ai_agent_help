# Enhancement Workflow

Use this workflow when adding behavior to an existing project.

## Purpose

Preserve existing architecture and patterns while adding new capability.

## Phase Sequence

1. `01_intake.md`
2. `02_pattern_discovery.md`
3. `03_design_impact.md`
4. `04_execution_plan.md`
5. `05_validation_closeout.md`

## Agent Rules

- Do not implement during intake.
- Identify existing patterns before proposing a design.
- Prefer minimal, reviewable changes.
- Stop if the enhancement becomes architecture redesign.

## Initial Wizard Questions

```text
Selected workflow: Enhancement
Process weight: Standard unless the change is very small or high-risk.

Current phase: Intake

Answer what you can:
1. What behavior or capability are we adding?
2. What existing area may be affected?
3. What should remain unchanged?
4. Are there constraints, deadlines, or compatibility requirements?
5. Should we start in exploration mode or execution planning mode?
```
