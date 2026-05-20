# Architecture Review Workflow

Use this workflow when reviewing an existing architecture, proposed design, or system structure.

## Purpose

Understand current/proposed architecture, identify risks, and recommend improvements without prematurely rewriting the system.

## Wizard Questions

```text
Selected workflow: Architecture Review
Process weight: Standard or Heavyweight depending on scope.
Mode: Review

Answer what you can:
1. What architecture should be reviewed?
2. Are we reviewing current state or a proposed design?
3. What concerns should I focus on? Examples: coupling, data flow, scalability, security, maintainability, CI/CD, testing.
4. Should the output be findings, recommendations, or a decision record?
```

## Process

1. Define review scope.
2. Inspect or summarize available architecture context.
3. Describe the current/proposed architecture.
4. Identify strengths.
5. Identify risks and inconsistencies.
6. Separate blocking issues, should-fix issues, and optional improvements.
7. Recommend next steps.

## Stop Conditions

Stop if:

- scope is unclear
- architecture context is insufficient
- review turns into redesign
- security/data/dependency risk requires deeper analysis

## Output Format

```text
Architecture Review

Scope:
[scope]

Current / Proposed Architecture:
[summary]

Strengths:
- ...

Risks:
- ...

Findings:
1. Blocking
2. Should-fix
3. Optional

Recommendations:
- ...

Open Questions:
- ...
```
