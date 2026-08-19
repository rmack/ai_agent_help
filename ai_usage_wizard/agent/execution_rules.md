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

When a WBS Work Package is used, also confirm:

- repository and supporting-document claims were verified
- prerequisites and blockers are current
- execution approval is not Pending
- the agent explained its understanding, approach, risks, validation plan, and stop
  conditions before editing

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

When executing a WBS Work Package, update its task checkboxes and Closeout Record with
the same evidence. Do not silently change package scope; stop for revision and renewed
approval when material scope or architecture changes.
