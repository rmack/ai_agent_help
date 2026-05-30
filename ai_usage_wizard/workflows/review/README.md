# Review Workflows

Use these workflows when the user wants evaluation, findings, or recommendations rather than immediate implementation.

## Available Review Modes

| Workflow | Use When | File |
| --- | --- | --- |
| Architecture Review | Reviewing an existing architecture, proposed design, system structure, boundaries, coupling, data flow, scalability, security, maintainability, or testing strategy. | `architecture_review.md` |
| Code Review | Reviewing a diff, branch, PR, file, or pasted code for correctness, maintainability, security, repository patterns, tests, or performance. | `code_review.md` |
| CI/CD Review | Reviewing build, test, release, deployment, automation, secrets, permissions, or pipeline reliability. | `cicd_review.md` |

## Routing Guidance

- Use `architecture_review.md` when the concern is system shape, design quality, responsibility boundaries, or long-term maintainability.
- Use `code_review.md` when the concern is implementation quality, correctness, tests, or whether a change follows the requested scope.
- Use `cicd_review.md` when the concern is automation safety, reproducibility, release controls, secrets, permissions, or deployment behavior.

If the review scope includes more than one area, start with the highest-risk area and call out the remaining review scopes as follow-up work.

## Review Rules

- Stay in review mode unless the user explicitly asks for changes.
- Define review scope before findings.
- Separate blocking issues, should-fix issues, and optional improvements.
- Identify validation gaps and open questions.
- Stop if review turns into redesign, implementation, or high-risk security/data analysis.
