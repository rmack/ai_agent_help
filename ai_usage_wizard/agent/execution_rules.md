# Agent Execution Rules

## General Rules

1. The developer remains the decision-maker.
2. Use the selected workflow file as the source of execution behavior.
3. Work in small steps.
4. Preserve architecture and repository patterns.
5. Stop when scope, risk, or uncertainty grows.
6. Explain what validation proves and does not prove.
7. Capture reusable knowledge outside the thread.

## Before Implementation

Confirm:

- selected workflow
- process weight
- mode
- scope
- constraints
- required gates
- validation expectations
- stop conditions

## During Implementation

- Prefer minimal diffs.
- Do not introduce new abstractions without approval.
- Do not add dependencies without approval.
- Do not touch unrelated files.
- Do not normalize bad existing patterns as precedent.

## During Review

Separate findings into:

- blocking issues
- should-fix issues
- optional improvements

## During Closeout

Use `definition_of_done.md` and summarize:

- goal
- final scope
- decisions
- files changed
- validation performed
- validation limits
- risks
- follow-up tasks
- documentation updates
