# Code Review Workflow

Use this workflow when reviewing a diff, branch, PR, file, or pasted code.

## Purpose

Find correctness, maintainability, security, pattern, and test issues.

## Wizard Questions

```text
Selected workflow: Code Review
Process weight: Lightweight, Standard, or Heavyweight depending on diff size and risk.
Mode: Review

Answer what you can:
1. What should I review: diff, branch, PR, file, or pasted code?
2. What should I focus on: correctness, maintainability, security, patterns, tests, performance?
3. Should findings be grouped as blocking / should-fix / optional?
```

## Process

1. Define review scope.
2. Identify expected behavior.
3. Review for correctness.
4. Review for architecture and pattern alignment.
5. Review tests and validation.
6. Review security/data/dependency risk.
7. Separate findings by severity.

## Output Format

```text
Code Review

Scope:
[scope]

Blocking Issues:
- ...

Should-Fix Issues:
- ...

Optional Improvements:
- ...

Test / Validation Gaps:
- ...

Questions:
- ...
```

## Rule

Do not rewrite code unless the user asks.
