# CI/CD Review Workflow

Use this workflow when reviewing build, test, release, deployment, secrets, permissions, or automation reliability.

## Purpose

Validate that automation is safe, understandable, reproducible, and appropriately gated.

## Wizard Questions

```text
Selected workflow: CI/CD Review
Process weight: Heavyweight if deployment, secrets, or permissions are involved.
Mode: Review

Answer what you can:
1. What workflow or pipeline should I review?
2. Is the concern build, test, deploy, release, secrets, permissions, or reliability?
3. Should I focus on correctness, security, speed, reproducibility, or maintainability?
```

## Process

1. Inventory workflows.
2. Identify triggers.
3. Identify permissions and secrets usage.
4. Identify build/test/deploy stages.
5. Check failure behavior.
6. Check environment assumptions.
7. Check reproducibility.
8. Recommend improvements.

## Risk Checks

- Are secrets protected?
- Are permissions least-privilege?
- Are deployments gated?
- Are failures loud?
- Can key commands be run locally?
- Are artifacts traceable?

## Output Format

```text
CI/CD Review

Scope:
[scope]

Workflow Summary:
[summary]

Risks:
- ...

Findings:
1. Blocking
2. Should-fix
3. Optional

Recommendations:
- ...
```
