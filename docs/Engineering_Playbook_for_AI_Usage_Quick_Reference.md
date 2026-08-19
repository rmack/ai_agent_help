# Engineering Playbook for AI Usage (Quick Reference)

Use this as the quick reminder. Use
`docs/Engineering_Playbook_for_AI_Usage.md` for the full standard.

## Core Mindset

- You = architect + reviewer + decision-maker
- AI = assistant for exploration + implementation
- Never outsource judgment
- Clarity over speed
- Consistency and control over cleverness

## Source of Truth

- Repo = truth
- `AGENTS.md` / tool rules = constraints
- Docs = durable knowledge
- Threads = scratchpad

## Workflow

- Define goal
- Pick the mode
- Clarify scope + constraints
- Ask for a plan when non-trivial
- Execute in small steps
- Review diffs
- Run validation
- Accept, iterate, summarize, or stop

## Modes

- Architecture / new project
- Enhancement
- Bug fix
- Technical debt / refactor
- Architecture review
- Code review
- CI/CD, build, release, deployment review
- Ideation / option comparison
- Thread summary / handoff

## Exploration vs Execution

Exploration:

- reason
- compare options
- challenge assumptions
- do not edit files

Execution:

- use the handoff structure from `process/ai_development_workflow.md`
- WBS Work Package = one bounded outcome with 1..n tasks
- WBS Stream = multiple related Work Packages for a larger objective
- supporting docs provide context; they do not expand Work Package scope
- pending WBS execution approval means do not implement
- verify non-trivial handoffs against as-built repo before execution
- require expected behavior, validation expectations, correctness evidence,
  stop conditions, and definition of done
- do not proceed when the inputs are ambiguous for the task risk

## Plan-First Triggers

Always request a plan before:

- schema or contract changes
- cross-module logic
- pipelines or stages
- performance-critical code
- architecture changes
- security, deployment, dependency, or data-handling changes

## Risk and Gates

Match gate depth to risk:

- Trivial = scope + diff + validation review
- Normal = standard gates
- High-risk = stronger gates
- Regulated / sensitive = strongest gates

Remember the gates:

- problem understanding
- architecture approval
- pattern approval
- scope approval
- diff review
- validation review
- documentation or handoff capture

## Agent Controls

Before edits:

- read repo instructions
- inspect relevant code + tests
- explain handoff understanding before execution
- check worktree state when possible
- confirm scope, validation, and stop conditions

During edits:

- follow existing patterns
- keep diffs minimal
- avoid unrelated cleanup
- do not add dependencies or change contracts without approval
- stop before destructive, privileged, network, production, or credential actions

Closeout:

- files changed
- commands run
- what validation proved
- what validation did not prove
- risks + follow-ups

## Validation

Goal:

- build multi-dimensional confidence
- prove intended behavior
- preserve required existing behavior
- detect unintended changes
- validate outputs, not just execution

Always:

- review diffs
- run relevant tests/checks
- understand what passing results actually prove

Never:

- trust green output blindly
- accept generated tests without reviewing assertions

## Testing Layers

Common:

- unit = isolated logic
- smoke = workflow still runs
- regression / golden = stable outputs did not drift

Conditional:

- integration = boundaries
- contract = schemas and interfaces
- security = auth, input, secrets, dependencies
- performance = hot paths and scale
- migration / rollback = deploy and data change safety
- manual / exploratory = UI, workflow, operator, or human-observed behavior

## Review Loop

- Human reviews first
- Use secondary agent review for non-trivial or risky AI changes
- Ask for specific issues, not "is this good?"
- Check correctness, behavior, architecture, tests, contracts, security,
  performance, maintainability, and scope
- Treat agent findings as inputs, not truth
- Fix valid findings and review again

## Security and Data

Do not expose:

- secrets, credentials, keys, tokens, cookies
- customer, personal, regulated, financial, health, or confidential data
- unapproved proprietary code, logs, incidents, designs, or datasets
- production data or production access details

Use sanitized, minimized, or synthetic examples.

## Stop Conditions

Stop when:

- requirements are unclear
- scope expands
- architecture impact grows
- new dependency appears necessary
- security, permissions, deployment, or data risk appears
- tests fail for unclear reasons
- validation is ambiguous
- existing patterns are inconsistent or poor
- the AI is guessing

When stopping:

- summarize what changed
- explain what triggered the stop
- state the decision needed
- list available options

## Context

- One thread = one task / feature / defect / review / handoff
- Threads are not memory
- Summarize long or resumed work
- Reconfirm assumptions after interruptions
- Restart if the thread gets weird
- Promote durable rules into `AGENTS.md`
- Capture decisions in docs

## Accountability

- You own correctness
- You own behavior changes
- You own performance impact
- You own downstream effects
- "The AI generated it" is not a justification

## Cost Awareness

- Use AI intentionally
- Keep prompts scoped
- Avoid unnecessary churn
- Use the right tool/model for the task

## Common Mistakes

- One large thread for everything
- Broad "fix everything" prompts
- Exploration drifting into execution
- Accepting changes without review
- Trusting tests without understanding them
- Treating local code as the standard
- Relying on AI context instead of docs
