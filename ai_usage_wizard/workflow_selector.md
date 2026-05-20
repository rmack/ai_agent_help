# Workflow Selector

Use this file to classify the user's intent.

## Selection Rules

### New Project / Major Design

Use `workflows/architecture/README.md` when the user is starting a new project, designing a major system, or needs architecture-first planning.

### Enhancement

Use `workflows/enhancement/README.md` when adding behavior to an existing project.

### Bug Fix

Use `workflows/bug_fix/README.md` when behavior is incorrect, output is wrong, tests fail, or users report a defect.

### Technical Debt

Use `workflows/technical_debt/README.md` when improving structure without intended behavior change.

### Architecture Review

Use `workflows/review/architecture_review.md` when reviewing an existing design or proposed architecture.

### Code Review

Use `workflows/review/code_review.md` when reviewing a diff, PR, branch, files, or pasted code.

### CI/CD Review

Use `workflows/review/cicd_review.md` when reviewing build, test, release, deployment, secrets, permissions, or pipeline reliability.

### Ideation

Use `workflows/ideation/README.md` when exploring ideas, brainstorming, comparing options, or capturing tangents.

### Thread Summary

Use `workflows/thread_summary/README.md` when creating durable Markdown memory from a thread.

## If Unsure

Ask:

```text
Which best describes the work?

1. Create/design something new
2. Add behavior to existing code
3. Fix incorrect behavior
4. Improve structure without behavior change
5. Review something
6. Explore an idea
7. Summarize this discussion
```

Then route based on the answer.
