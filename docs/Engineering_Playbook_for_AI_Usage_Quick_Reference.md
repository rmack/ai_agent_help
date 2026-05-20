# Engineering Playbook for AI Usage (Lightweight)

## Core mindset

- You = architect + reviewer
- AI = fast junior engineer
- Never outsource judgment
- Clarity over speed, consistency over cleverness

## Threads

- One thread = one task / one commit
- Keep threads short and focused
- If behavior gets weird → start a new thread
- Threads are not memory or source of truth

## Source of truth

- Repo = truth
- AGENTS.md = rules
- Docs = knowledge
- Threads = scratchpad

## Workflow

- Define goal
- Ask for plan (if non-trivial)
- Execute in small steps
- Review diffs
- Run tests
- Iterate

## Plan-first triggers

Always request a plan before:

- schema or contract changes
- cross-module logic
- pipelines or stages
- performance-critical code
- architectural changes

## Task scoping

- Keep changes small and bounded
- Avoid “do everything” prompts

Break work into:

- ideation
- implementation
- cleanup
- testing

## Validation

Always:

- review diffs
- run tests

Never:

- trust green output blindly

Also:

- understand what tests actually prove

## Testing (two levels)

Unit testing:

- validate isolated logic
- cover edge cases

Smoke testing:

- validate system/stage behavior
- ensure pipeline still works

Goal:

- validate outputs, not just execution
- move toward artifact comparison

## Control and safety

- Prefer minimal diffs
- Do not allow:
  - silent behavior changes
  - schema drift
  - formatting churn
- Enforce rules via AGENTS.md

## Diff discipline

- Changes must be:
  - minimal
  - isolated
  - reviewable

If changes grow too large:

- break them into smaller steps
- or restart with tighter scope

## Environment checks

Before real work:

- verify read access
- verify write access
- verify command execution

If something behaves unexpectedly:

- stop
- isolate the issue
- restart with a clean context

## Accountability

- You own:
  - correctness
  - behavior
  - performance
  - downstream impact
- “The AI generated it” is not a valid justification

## Cost awareness

- Use AI intentionally
- Avoid unnecessary or excessive usage
- Prefer small, scoped prompts
- Reuse context when possible
- Use the appropriate tool/model for the task

## Knowledge capture

- Do not rely on thread history
- Document:
  - decisions
  - architecture
  - current state

Keep documentation lightweight and durable.

## Common mistakes to avoid

- One large thread for everything
- Broad “fix everything” prompts
- Accepting changes without review
- Treating local code as the standard
- Relying on AI context instead of documentation
