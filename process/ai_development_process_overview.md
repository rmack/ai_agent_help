# AI-Assisted Development Process Flow v3

## Version Notes

This version extends v2 by adding two practical operating sections:

- intent-based AI workflow modes
- tangent capture and Markdown memory files

The goal is to move the process from a general AI-assisted development overview into a more usable operating model. Different kinds of work require different AI workflows. Starting a new project, enhancing an existing project, fixing a bug, reviewing architecture, and capturing broad ideation should not all use the same process.

This version keeps the same core principles from v2:

- human judgment remains central
- architecture comes before implementation
- AI work should be scoped, reviewed, validated, and documented
- durable knowledge should live outside the chat thread
- security, dependency, data handling, and stop-condition gates should not be bypassed

---

## 0. Core Operating Principle

The developer drives the work.
AI assists, accelerates, challenges, summarizes, implements, and reviews — but it does not own the architecture, requirements, or final decisions.

The mindset should be:

> Human = architect, reviewer, decision-maker  
> AI = fast junior engineer / assistant / workflow orchestrator

This matters because AI can increase code volume quickly. Without discipline, that leads to inconsistent patterns, harder reviews, architecture drift, and code the developer does not fully understand.

---

# 1. Start with Architecture Before Implementation

Before asking AI to write code, use AI to help think.

This phase is about shaping the solution, not generating files.

## 1.1 CONOPS / Concept of Operations

Use AI to define the operating intent before discussing software structure.

CONOPS answers how the system should work in the real world:

- What problem are we solving?
- Who uses the system?
- What are the major workflows?
- What are the operating assumptions?
- What are the failure scenarios?
- What does success look like?
- What constraints or non-goals shape the design?

Example prompt:

```text
I want to explore the concept of operations for this feature before implementation.

Goal:
[Describe the business or technical goal]

Context:
[Describe the current system]

Users / actors:
[List people, systems, services, or jobs involved]

Please help me identify:
- primary workflows
- system boundaries
- assumptions
- risks
- unclear requirements
- decisions I need to make before design
Do not propose code yet.
```

---

## 1.2 Conceptual Architecture

Use AI to turn the CONOPS into major system concepts without choosing implementation details yet.

Conceptual architecture answers what major capabilities, components, responsibilities, boundaries, and flows exist. It should avoid specific files, frameworks, cloud services, or deployment choices unless those are fixed constraints.

Ask:

- What major capabilities are required?
- What are the major conceptual components?
- What responsibilities does each component own?
- What data moves through the system?
- What are the boundaries?
- What external systems or actors interact with the system?
- What should not be coupled?
- What major risks or tradeoffs are already visible?

Example prompt:

```text
Based on the CONOPS, help me define a conceptual architecture.

Focus on:
- major capabilities
- major components
- responsibilities
- data flow
- boundaries
- external dependencies
- risks

Do not move into implementation details yet.
```

---

## 1.3 Logical Architecture

Now move from concepts into software structure.

Logical architecture answers how the conceptual design becomes software responsibilities and contracts. It defines the system's internal organization without yet deciding where the pieces run or which infrastructure hosts them.

Ask:

- What modules, services, jobs, classes, functions, or packages are likely needed?
- What responsibility does each unit own?
- What contracts exist between them?
- What schemas or data structures are involved?
- What state is owned, read, written, or transformed?
- What validation rules are needed?
- What should be deterministic?
- What should fail loudly?
- What test strategy is appropriate?

Example prompt:

```text
Now help me convert the conceptual architecture into a logical architecture.

Include:
- proposed modules
- responsibilities per module
- data contracts
- interfaces
- data ownership and state transitions
- validation rules
- error handling expectations
- test strategy

Call out any ambiguity instead of resolving it silently.
```

---

## 1.4 Physical Architecture

Only after the above should AI map the logical architecture to the real execution environment.

Physical architecture answers where and how the logical architecture actually runs. This includes the runtime topology, infrastructure, cloud or on-prem services, deployment units, databases, queues, streams, containers, networking, identity, secrets, observability, scaling, and operational controls that make the logical design executable.

Repository files, folders, dependencies, commands, and implementation sequencing are still important, but they come after the runtime and deployment model are clear.

Ask:

- Where will this run: local, on-prem, cloud, edge, or a hybrid environment?
- What compute model is used: containers, VMs, serverless functions, managed jobs, Kubernetes, scheduled tasks, or another runtime?
- What deployment units exist, and how are they built, configured, released, and rolled back?
- What data stores are required: relational database, object storage, cache, search index, warehouse, or another service?
- How does data move at runtime: APIs, events, queues, streams, files, ETL, pub/sub, or direct database access?
- What networking, identity, access, secrets, and data-boundary controls are required?
- What observability, logging, monitoring, alerting, backup, recovery, and scaling expectations apply?
- What tools, services, dependencies, and environment configuration are required?
- What repository files, folders, infrastructure definitions, or configuration files need to exist or change?
- What files or areas should not change?
- What commands, tests, smoke checks, deployment checks, or operational checks should validate the design?

Example prompt:

```text
Now map the logical architecture to the physical architecture.

Include:
- target runtime environment
- deployment units
- compute, storage, messaging, and network choices
- data movement at runtime
- identity, secrets, access, and data-boundary controls
- observability, scaling, backup, and recovery expectations
- infrastructure, service, and tool dependencies
- repository structure, configuration, and implementation boundaries
- validation commands, deployment checks, and operational checks

If there is an existing repository, inspect it before proposing file changes. Identify existing patterns and explain the minimal reviewable change path.

Do not edit files until I approve the plan.
```

---

# 2. Establish the Work Mode: Exploration vs Execution

A key part of the process is separating **exploration mode** from **execution mode**.

## 2.1 Exploration Mode

Use this when requirements, architecture, or tradeoffs are unclear.

AI can help:

- explore options
- challenge assumptions
- compare patterns
- identify risks
- ask clarifying questions
- summarize decisions

But AI should not silently decide ambiguous requirements.

Good exploration instruction:

```text
We are in exploration mode. Do not write implementation code. Help me reason through options, risks, assumptions, and tradeoffs.
```

---

## 2.2 Execution Mode

Use this only when the scope is clear.

Execution requires:

- defined goal
- defined scope
- known constraints
- known acceptance criteria
- architecture alignment
- validation plan

Good execution instruction:

```text
We are now in execution mode.

Goal:
[goal]

Scope:
[allowed files / modules]

Constraints:
[patterns, architecture, things not to change]

Acceptance Criteria:
[tests, behavior, output, review expectations]

Work in small steps. Propose a plan before editing.
```

---
# 3. Intent-Based AI Workflow Modes

The overall AI-assisted development process should not be applied as a single rigid workflow. The correct workflow depends on the intent of the session.

A new project, enhancement, bug fix, technical debt cleanup, architecture review, code review, CI/CD review, and general ideation session all require different levels of architecture analysis, implementation discipline, validation, and documentation.

The shared principles remain the same:

- the human drives the work
- AI assists but does not own judgment
- ambiguity should be surfaced, not silently resolved
- architecture and patterns should guide implementation
- changes should be scoped, reviewed, and validated
- durable knowledge should be captured outside the thread

However, the workflow should change based on the task.

## 3.1 Session Intent Declaration

Every significant AI thread should begin by declaring the session intent.

Example session start template:

```text
Session Intent:
[New Project / Enhancement / Bug Fix / Technical Debt / Architecture Review / Code Review / CI/CD Review / Ideation]

Mode:
[Exploration / Execution / Review / Summary]

Goal:
[What are we trying to accomplish?]

Scope:
[What files, systems, features, or topics are in scope?]

Constraints:
[Architecture, patterns, standards, dependencies, security, data handling, or time constraints]

Expected Output:
[Plan, architecture, code change, review findings, summary, Markdown file, etc.]

Stop Conditions:
[When should AI stop and ask for human direction?]
```

Declaring intent helps prevent the AI from using the wrong workflow. For example:

- architecture review mode should not jump into implementation
- bug fix mode should not become broad refactoring
- technical debt mode should not silently change behavior
- ideation mode should not force premature decisions
- enhancement mode should preserve existing architecture and patterns

## 3.2 Intent Decision Tree

Use this decision tree at the start of a thread.

```text
What am I doing?

Starting a new project?
→ Use New Project Mode

Adding capability to an existing project?
→ Use Existing Project Enhancement Mode

Fixing incorrect behavior?
→ Use Defect / Bug Fix Mode

Improving structure without intended behavior change?
→ Use Technical Debt Mode

Evaluating design or system structure?
→ Use Architecture Review Mode

Reviewing implementation?
→ Use Code Review Mode

Reviewing build, release, or deployment automation?
→ Use CI/CD Review Mode

Exploring ideas, tradeoffs, or broader topics?
→ Use Ideation / Tangent Capture Mode
```

## 3.3 New Project Mode

Use this mode when starting something from zero or near-zero.

Primary focus:

```text
Understand the problem before creating structure.
```

Recommended flow:

```text
Problem framing
↓
CONOPS
↓
Requirements and assumptions
↓
Conceptual architecture
↓
Logical architecture
↓
Physical architecture
↓
Repository/project structure
↓
Initial patterns
↓
Initial AGENTS.md
↓
Initial tests
↓
Implementation slices
```

Important gates:

```text
Do not generate project structure too early.
Do not pick frameworks before requirements are understood.
Do not allow AI to create unnecessary abstractions.
Define patterns early, but keep them lightweight.
Create an initial AGENTS.md, but expect it to evolve.
```

Example prompt:

```text
We are in new project mode.

Start in exploration mode. Do not create files or write code yet.

Goal:
[Describe the project]

Context:
[Describe the problem, users, constraints, and known assumptions]

Help me work through:
1. CONOPS
2. requirements and assumptions
3. conceptual architecture
4. logical architecture
5. physical architecture
6. initial project structure
7. initial patterns
8. initial validation strategy
9. initial AGENTS.md guidance

Call out unclear requirements and tradeoffs before suggesting implementation.
```

## 3.4 Existing Project Enhancement Mode

Use this mode when adding capability to an existing system.

Primary focus:

```text
Preserve existing architecture and patterns while adding behavior.
```

Recommended flow:

```text
Understand requested enhancement
↓
Inspect current architecture
↓
Identify existing patterns
↓
Identify affected files/modules
↓
Confirm whether enhancement fits current design
↓
Plan minimal change
↓
Implement small slice
↓
Validate behavior
↓
Update docs/patterns if needed
```

Important gates:

```text
Does this follow an existing pattern?
Are we changing behavior outside the requested enhancement?
Are we introducing a new abstraction unnecessarily?
Does AGENTS.md need to be updated?
Does this require new validation or regression coverage?
```

Example prompt:

```text
We are in existing project enhancement mode.

Goal:
[Describe the enhancement]

Before implementation:
1. Inspect the existing architecture and relevant files.
2. Identify the existing patterns this should follow.
3. Identify the smallest safe change path.
4. Identify tests that should be added or updated.
5. Identify any security, dependency, or data handling gates.

Do not refactor unrelated code.
Do not introduce new abstractions unless justified and approved.
```

## 3.5 Defect / Bug Fix Mode

Use this mode when behavior is incorrect or unexpected.

Primary focus:

```text
Reproduce, isolate, fix, prove.
```

Recommended flow:

```text
Describe observed behavior
↓
Describe expected behavior
↓
Find reproduction path
↓
Identify failing test or create one
↓
Inspect likely code path
↓
Determine root cause
↓
Make minimal fix
↓
Run targeted test
↓
Run regression validation if needed
↓
Document root cause
```

Important gates:

```text
Do not fix symptoms before identifying cause.
Do not make broad refactors during bug fixes.
Do not change unrelated behavior.
Add or update a test that would have caught the bug.
Document the root cause and validation.
```

Example prompt:

```text
We are in defect-fix mode.

Observed behavior:
[What happened?]

Expected behavior:
[What should have happened?]

Known reproduction steps:
[Steps, inputs, logs, or failing test]

Before proposing a fix:
1. Identify the likely code path.
2. Explain the suspected root cause.
3. Identify or propose a failing test.
4. Propose the smallest safe fix.
5. Explain what validation will prove the bug is fixed.

Do not refactor unrelated code.
```

## 3.6 Technical Debt Mode

Use this mode when improving structure, maintainability, naming, organization, or patterns without intending to change behavior.

Primary focus:

```text
Improve structure without changing behavior.
```

Recommended flow:

```text
Define debt item
↓
Explain why it is debt
↓
Identify current behavior that must not change
↓
Identify affected area
↓
Choose narrow refactor boundary
↓
Add characterization/regression tests if needed
↓
Make small refactor
↓
Validate no behavior change
↓
Document improved pattern
```

Important gates:

```text
What behavior must remain identical?
How will we prove behavior did not change?
Is this cleanup or architecture change?
Is this small enough to review?
If the refactor grows, should this become architecture review mode?
```

Example prompt:

```text
We are in technical debt mode.

Debt item:
[Describe the issue]

Goal:
Improve maintainability without changing behavior.

Before making changes:
1. Identify the behavior that must remain unchanged.
2. Identify the smallest safe refactor boundary.
3. Identify tests or characterization checks needed before refactoring.
4. Explain how we will validate no behavior changed.

Stop if the work expands into architecture redesign.
```

## 3.7 Architecture Review Mode

Use this mode when evaluating design, structure, boundaries, coupling, data flow, or long-term maintainability.

Primary focus:

```text
Understand structure, risks, tradeoffs, and improvement options.
```

Recommended flow:

```text
Define review scope
↓
Inspect architecture/docs/code
↓
Summarize current architecture
↓
Identify strengths
↓
Identify risks
↓
Identify inconsistencies
↓
Compare options
↓
Recommend improvements
↓
Separate quick fixes from larger redesigns
```

Important gates:

```text
Do not rewrite architecture during review.
Separate observations from recommendations.
Separate must-fix issues from preferences.
Identify unknowns clearly.
Separate quick improvements from larger redesigns.
```

Example prompt:

```text
We are in architecture review mode.

Scope:
[System, module, repo, feature, pipeline, or workflow]

Review for:
- architecture consistency
- coupling
- boundaries
- data flow
- failure handling
- testability
- maintainability
- security implications
- CI/CD impact

Do not propose code changes yet.
First summarize the current architecture, then identify risks and recommendations.
Separate observations, concerns, and recommendations.
```

## 3.8 Code Review Mode

Use this mode when reviewing a diff, pull request, implementation, or generated code.

Primary focus:

```text
Find correctness, maintainability, security, and pattern issues.
```

Recommended flow:

```text
Define review scope
↓
Review diff or files
↓
Check against architecture
↓
Check against patterns
↓
Check tests
↓
Check security/data handling
↓
Identify required changes
↓
Identify optional suggestions
```

Important gates:

```text
Separate blocking issues from suggestions.
Do not rewrite code unless asked.
Explain why each concern matters.
Check whether the implementation follows existing patterns.
Check whether validation proves the right behavior.
```

Example prompt:

```text
We are in code review mode.

Review this change for:
- correctness
- architecture alignment
- repository pattern consistency
- test coverage
- security/data handling
- maintainability
- unnecessary complexity

Separate findings into:
1. Blocking issues
2. Should-fix issues
3. Optional improvements

Do not rewrite the code unless I ask.
```

## 3.9 CI/CD Review Mode

Use this mode when reviewing build, test, release, deployment, automation, or workflow configuration.

Primary focus:

```text
Validate that build, test, release, and deployment workflows are safe and understandable.
```

Recommended flow:

```text
Inventory workflows
↓
Identify triggers
↓
Identify permissions/secrets
↓
Identify build/test/deploy stages
↓
Check failure behavior
↓
Check environment assumptions
↓
Check security boundaries
↓
Recommend improvements
```

Important gates:

```text
Are secrets protected?
Are permissions least-privilege?
Are failures loud?
Are deployment steps gated correctly?
Can the workflow be reproduced locally?
Are CI checks aligned with the repository's validation strategy?
```

Example prompt:

```text
We are in CI/CD review mode.

Scope:
[Workflow files, pipeline, deployment process, release process]

Review for:
- triggers
- permissions
- secrets handling
- build steps
- test steps
- deployment gates
- failure behavior
- reproducibility
- security risks
- maintainability

Separate findings into:
1. Critical risks
2. Recommended improvements
3. Optional cleanup

Do not modify workflow files until I approve a plan.
```

---

# 4. Tangent Capture and Markdown Memory Files

Tangents are a normal and valuable part of technical thinking. Humans often explore side topics, jump between levels of abstraction, compare alternatives, or discover related concerns while discussing a problem.

This is not necessarily a problem. It becomes a problem only when useful decisions, assumptions, or ideas remain trapped in a long chat thread and are later forgotten.

The AI-assisted development process should explicitly support tangent capture and memory backup.

## 4.1 Why Tangent Capture Matters

During ideation, the discussion may branch into:

- architecture alternatives
- testing philosophy
- coding patterns
- team workflow
- documentation strategy
- security concerns
- CI/CD concerns
- future features
- policy or governance
- developer experience
- risks or tradeoffs

Some tangents should return to the main thread. Others may become future workstreams.

The goal is not to prevent tangents. The goal is to capture them before they are lost.

## 4.2 Ideation / Tangent Capture Mode

Use this mode when the thread is primarily exploratory, conceptual, or wide-ranging.

Primary focus:

```text
Allow exploration without losing durable knowledge.
```

Recommended flow:

```text
Discuss topic freely
↓
Notice branching or tangent topics
↓
Ask AI to summarize main topics
↓
Separate current-thread topics from future-thread topics
↓
Identify decisions, open questions, and assumptions
↓
Create Markdown memory file if the discussion has durable value
↓
Use that file later as context for a new thread
```

## 4.3 When to Trigger Tangent Capture

Ask for a topic summary when:

- the discussion has covered several major themes
- you feel the thread is getting hard to mentally track
- a side topic may deserve its own future thread
- decisions or assumptions were made during discussion
- the thread is becoming long
- the AI starts losing context
- you want to preserve the discussion before switching topics

## 4.4 Topic Summary Prompt

Use this prompt during a discussion:

```text
Summarize the main topics we have discussed so far.

For each topic include:
- topic name
- why it came up
- key points
- decisions made
- open questions
- whether this belongs in the current thread or should become a separate thread
- recommended next action
```

## 4.5 Markdown Memory File Prompt

Use this prompt when the discussion should be preserved:

```text
Create a Markdown summary file for this discussion.

Include:
- purpose of the discussion
- major topics covered
- decisions made
- open questions
- future threads this could become
- important terminology
- reusable prompts or patterns
- recommended next steps

Write it so I can upload it into a future thread as memory/context.
```

## 4.6 Suggested Markdown Memory File Structure

```markdown
# [Topic Name] Discussion Summary

## Purpose

[Why this discussion happened and what we were trying to understand.]

## Main Topics Discussed

### 1. [Topic]

- Why it came up:
- Key points:
- Decisions:
- Open questions:
- Future thread candidate: Yes / No

### 2. [Topic]

- Why it came up:
- Key points:
- Decisions:
- Open questions:
- Future thread candidate: Yes / No

## Decisions Made

- [Decision]
- [Decision]

## Open Questions

- [Question]
- [Question]

## Assumptions

- [Assumption]
- [Assumption]

## Future Thread Candidates

- [Topic that may deserve its own thread]
- [Topic that may deserve its own thread]

## Reusable Prompts / Patterns

```text
[Prompt or pattern]
```

## Recommended Next Steps

1. [Next step]
2. [Next step]
```

## 4.7 Memory File Operating Rules

Use these rules when creating Markdown memory files:

- capture what matters, not every word
- separate facts, decisions, assumptions, and opinions
- identify what is unresolved
- identify what should become its own thread
- write for future reuse, not just current readability
- keep the file focused enough to be useful as context later
- do not treat the memory file as final truth if decisions later change

## 4.8 Relationship to Thread Discipline

Tangent capture supports thread discipline.

A thread can be allowed to explore broadly, but durable conclusions should be moved into a Markdown file when the discussion becomes valuable.

This creates a practical memory loop:

```text
Discussion
↓
Topic summary
↓
Markdown memory file
↓
Future thread context
↓
Updated docs / AGENTS.md / architecture notes if needed
```

The rule is:

> Do not let important thinking live only inside a chat thread.

---

# 5. Build and Enforce Patterns Over Time

This is one of the most important parts of the process.

AI performs much better when the repository has clear patterns. If every feature is implemented differently, AI will imitate inconsistency. If the repo has strong patterns, AI can extend them.

## 5.1 Pattern Categories to Build

Gradually document patterns for:

- project structure
- naming conventions
- error handling
- logging
- configuration
- validation
- dependency injection
- data access
- API boundaries
- test structure
- fixture usage
- command execution
- generated artifacts
- deterministic output handling

---

## 5.2 Pattern Creation Flow

When adding something new, use this sequence:

1. Ask AI to identify existing patterns.
2. Ask AI whether the new change fits an existing pattern.
3. If not, discuss whether a new pattern is justified.
4. Create the smallest useful pattern.
5. Document the pattern.
6. Add or update tests.
7. Add the pattern rule to `AGENTS.md` if AI should follow it in the future.

Example prompt:

```text
Before implementing this, inspect the repository and identify any existing patterns that apply.

Tell me:
- what pattern exists
- where it appears
- whether this change should follow it
- whether a new pattern is needed
- what rule should be added to AGENTS.md after the change
```

---

# 6. Use `AGENTS.md` as the Repository AI Contract

`AGENTS.md` should start simple and become stronger over time.

It should not be a massive policy document. It should be a practical operating contract for AI working inside the repo.

`AGENTS.md` should define architecture expectations, coding standards, validation requirements, workflow rules, and change discipline.

## 6.1 Initial `AGENTS.md` Sections

Start with:

```markdown
# AGENTS.md

## Purpose

This file defines how AI agents should work in this repository.

AI may assist with implementation, analysis, testing, refactoring, and documentation, but the developer remains responsible for architecture, correctness, validation, and final approval.

## Core Rules

- Follow existing repository patterns.
- Prefer minimal, focused diffs.
- Do not introduce new abstractions without approval.
- Do not silently resolve ambiguity.
- Fail loudly rather than hiding invalid states.
- Preserve deterministic behavior where expected.
- Add or update tests for behavior changes.
- Explain validation performed.
- Do not treat existing bad patterns as precedent.
- Do not add new dependencies without approval.
- Do not expose secrets, credentials, regulated data, or confidential data.
- Stop and ask when scope, risk, or architecture impact grows beyond the approved plan.

## Planning Required Before Changes

AI must propose a plan before:
- schema changes
- cross-module changes
- architecture changes
- behavior-affecting refactors
- pipeline changes
- generated artifact changes
- dependency changes
- permission or security-sensitive changes
- data model or data handling changes

## Validation Expectations

Before declaring work complete:
- run relevant unit tests
- run smoke tests if workflow execution changed
- run regression tests if deterministic outputs changed
- perform security/risk review when relevant
- confirm no unauthorized dependencies were added
- confirm no secrets or sensitive data were exposed
- summarize what was validated
- summarize what was not validated

## Thread Discipline

- One thread should focus on one task or one commit.
- Long or degraded threads should be summarized and restarted.
- Durable knowledge belongs in repo docs, tests, architecture docs, and AGENTS.md.
```

Then build it up as patterns emerge.

---

# 7. Thread Execution Process

Threads should be treated as temporary workspaces, not permanent memory.

Threads degrade over time. Durable sources of truth should be the repository, documentation, `AGENTS.md`, tests, and architecture docs.

## 7.1 Thread Start Checklist

Every new development thread should begin with something like:

```text
We are working in this repository.

Before making changes:
1. Read AGENTS.md.
2. Inspect the relevant files.
3. Identify existing patterns.
4. Confirm the likely scope.
5. Propose a plan.
6. Do not edit files until I approve.

Task:
[describe task]
```

---

## 7.2 Thread Execution Loop

Use this loop:

```text
1. Define the goal.
2. Establish scope.
3. Ask AI to inspect relevant context.
4. Ask AI to propose a plan.
5. Human reviews and adjusts the plan.
6. AI makes a small change.
7. Human reviews the diff.
8. AI runs targeted validation.
9. Human decides whether to continue.
10. Repeat until complete.
```

---

## 7.3 Thread End Checklist

At the end of the thread, ask AI for a compressed summary:

```text
Create a compressed Markdown summary of this thread.

Include:
- goal
- decisions made
- architecture assumptions
- files changed
- patterns introduced or followed
- tests run
- validation results
- unresolved issues
- follow-up tasks
- any AGENTS.md updates recommended

Write this so it can be used as context in a future AI thread.
```

This becomes a reusable handoff document for future threads.

---

# 8. Human Thinking Gates

Deliberately insert human decision points into the process.

Do not let AI smoothly carry the work from idea to implementation without stopping.

## 8.1 Required Human Gates

### Gate 1: Problem Understanding

Before architecture:

```text
Do I understand the actual problem?
```

### Gate 2: Architecture Approval

Before code:

```text
Do I agree with the design direction?
```

### Gate 3: Pattern Approval

Before implementation:

```text
Is this following an existing pattern, or am I intentionally creating a new one?
```

### Gate 4: Scope Approval

Before file edits:

```text
Are these the only files that should change?
```

### Gate 5: Diff Review

After AI changes code:

```text
Do I understand every meaningful change?
```

### Gate 6: Validation Review

After tests:

```text
Do the tests prove the right things?
```

### Gate 7: Documentation Capture

Before closing thread:

```text
What needs to become durable knowledge?
```

This is where the developer stays in control.

---

---

# 9. Security and Risk Review Gates

AI-assisted development should not bypass security, privacy, licensing, or operational risk review.

Not every small change needs a heavyweight review. However, the process should always ask whether the change introduces risk. If the answer is yes, the risk needs to be reviewed before implementation continues.

## 9.1 Security Review Gate

Use this gate when a change touches:

- authentication
- authorization
- permissions
- secrets
- credentials
- tokens
- user data
- file access
- network access
- external APIs
- deployment configuration
- CI/CD
- logging of sensitive information
- agent tools or automation permissions

Security review prompt:

```text
Before implementing or finalizing this change, perform a security review.

Identify whether this change affects:
- authentication
- authorization
- permissions
- secrets or credentials
- sensitive data
- external APIs
- logging
- file or network access
- CI/CD or deployment behavior

For each risk, explain:
- what could go wrong
- how the implementation should prevent it
- what validation should be performed
- whether human review is required before proceeding
```

## 9.2 Dependency Change Gate

AI should not casually add new packages, frameworks, services, or external APIs. Dependencies create maintenance, security, licensing, compatibility, and supply-chain risk.

Before adding a dependency, require AI to justify it.

Dependency review prompt:

```text
This task may require a new dependency. Do not add one yet.

First explain:
- why the dependency is needed
- whether the existing codebase already has a solution
- whether the standard library or current dependencies are sufficient
- what maintenance risk this adds
- what security or licensing concerns may exist
- what files would change
- how this dependency would be validated

Recommend whether to proceed without the dependency, use an existing dependency, or request approval for a new one.
```

Recommended rule:

```text
No new dependency should be added unless the developer explicitly approves it.
```

## 9.3 Data Handling and Intellectual Property Gate

AI usage must respect data boundaries. The developer should avoid giving AI secrets, credentials, regulated data, confidential business information, proprietary customer data, or source material that is not approved for the tool being used.

This applies both to what the developer gives the AI and what the AI produces.

Data handling prompt:

```text
Before proceeding, review the data handling implications of this task.

Identify whether the work involves:
- secrets
- credentials
- regulated data
- customer data
- confidential business data
- proprietary source material
- third-party licensed content
- generated code or text with possible licensing concerns

Tell me what should not be pasted into the AI thread, what should be redacted, and what should be handled only through approved local files or approved tools.
```

## 9.4 Risk Classification

For each task, classify the change before execution.

```text
Risk level:
Low / Medium / High

Reason:
[Explain why]

Risk areas:
- architecture
- security
- data handling
- dependencies
- behavior change
- test coverage
- operational impact

Required gates before implementation:
[List gates]
```

Simple changes may remain lightweight. High-risk changes should slow down and require more human review.

---

# 10. Stop Conditions

A strong AI process should define when to stop. This is important because AI can continue confidently even when the task has become unclear, risky, or too broad.

Stop conditions protect the developer from drifting into unreviewable changes.

## 10.1 When AI Should Stop

AI should stop and ask for direction when:

- requirements are unclear
- the requested change conflicts with existing architecture
- the diff grows beyond the approved scope
- more files need changes than expected
- a new dependency appears necessary
- tests fail for unclear reasons
- validation results are ambiguous
- implementation requires security-sensitive changes
- data handling risk appears
- existing patterns are inconsistent or poor
- the AI finds itself guessing

Stop condition prompt:

```text
If any stop condition occurs, stop work and summarize:

- what changed
- what triggered the stop
- what decision is needed
- what options exist
- what you recommend

Do not continue implementation until I approve the next step.
```

## 10.2 Diff Size Stop Rule

AI-generated changes should remain reviewable. If the diff gets too large, pause and split the work.

Example rule:

```text
If the change expands beyond the approved files, or if the diff becomes too large to review comfortably, stop and propose a smaller sequence of changes.
```

---

# 11. Definition of Done

A task is not done just because AI made changes or tests passed. A task is done when the developer can understand, review, validate, and preserve the work.

## 11.1 Definition of Done Checklist

Use this checklist before closing a thread, commit, or PR.

```text
Definition of Done:

Goal and scope:
- The original goal is satisfied.
- The final scope matches the approved scope.
- Any scope changes were explicitly approved.

Architecture and patterns:
- The change follows existing architecture.
- Existing patterns were followed or a new pattern was intentionally approved.
- No unnecessary abstraction was introduced.
- Existing bad code was not treated as precedent.

Code review:
- The developer reviewed the diff.
- The developer understands the meaningful changes.
- The change is small enough to review.

Validation:
- Relevant unit tests were run.
- Smoke tests were run if workflow execution changed.
- Regression tests were run if deterministic output changed.
- Manual validation was performed where needed.
- The limits of validation are known.

Risk controls:
- Security review was performed if relevant.
- No unauthorized dependency was added.
- No secrets or sensitive data were exposed.
- Data handling and licensing concerns were considered.

Documentation:
- AGENTS.md was updated if a durable AI rule was discovered.
- Architecture or pattern docs were updated if needed.
- Thread summary was created if the discussion contains reusable context.

Final state:
- Known limitations are documented.
- Follow-up tasks are captured.
- The work is ready for commit, PR, or handoff.
```

## 11.2 Final Review Prompt

```text
Before we close this task, evaluate whether the Definition of Done is satisfied.

Report:
- completed items
- incomplete items
- risks or limitations
- tests and validation performed
- recommended documentation updates
- recommended follow-up tasks

Do not simply say the task is complete. Be specific.
```

# 12. Validation Process

The process should treat validation as more than “tests passed.”

Unit, smoke, and regression testing serve different purposes.

## 12.1 Unit Tests

Use when logic changes.

They answer:

```text
Does this isolated logic behave correctly?
```

---

## 12.2 Smoke Tests

Use when workflow or integration execution changes.

They answer:

```text
Does the system still run?
```

---

## 12.3 Regression Tests

Use when deterministic outputs, generated artifacts, pipelines, transformations, or expected behavior may change.

They answer:

```text
Did we accidentally change something?
```

---

## 12.4 AI Validation Prompt

```text
Run the appropriate validation for this change.

Classify validation into:
- unit tests
- smoke tests
- regression tests
- manual review

For each one, explain:
- what command was run
- what it proves
- what it does not prove
- whether additional validation is needed
```

This prevents the lazy “all tests pass” trap.

---

# 13. Documentation Capture Process

Capture durable knowledge after meaningful work.

## 13.1 What Should Be Captured

Capture:

- architecture decisions
- rejected options
- new patterns
- testing strategy
- commands
- setup issues
- known pitfalls
- assumptions
- validation expectations
- thread summaries

---

## 13.2 Where It Should Go

Use different documents for different purposes:

```text
AGENTS.md
Repository-local AI operating rules.

Architecture docs
System design, CONOPS, conceptual/logical/physical architecture.

Pattern docs
Reusable implementation patterns.

Thread summaries
Compressed historical context for future AI sessions.

Tests
Executable truth.

README / developer docs
Human onboarding and common workflows.
```

The rule should be:

> If future AI or future you needs to know it, do not leave it trapped in a chat thread.

---

# 14. Recommended End-to-End Flow

Here is the clean process flow.

```text
Idea / Problem
   ↓
AI Exploration Mode
   ↓
CONOPS
   ↓
Conceptual Architecture
   ↓
Logical Architecture
   ↓
Physical Architecture
   ↓
Pattern Review
   ↓
Security / Risk Classification
   ↓
Dependency / Data Handling Gate if Needed
   ↓
AGENTS.md / Docs Check
   ↓
Execution Thread Starts
   ↓
AI Inspects Repo
   ↓
AI Proposes Plan
   ↓
Human Approves / Adjusts
   ↓
Small Implementation Step
   ↓
Diff Review
   ↓
Stop Condition Check
   ↓
Unit / Smoke / Regression Validation
   ↓
Definition of Done Check
   ↓
Repeat Small Steps
   ↓
Final Human Review
   ↓
Update Docs / AGENTS.md / Patterns
   ↓
Create Compressed Markdown Thread Summary
   ↓
Commit / PR / Archive Thread
```

---

# 15. Practical Starting Template

When starting a new AI-assisted development task, use this:

```text
We are using an architecture-first AI-assisted development process.

Session Intent:
[New Project / Enhancement / Bug Fix / Technical Debt / Architecture Review / Code Review / CI/CD Review / Ideation]

Mode:
Start in exploration mode unless the session intent requires review or summary mode. Do not write code yet.

Goal:
[Describe the task]

Context:
[Describe the system/repo/component]

Current known constraints:
[List constraints]

I want to proceed in this order:
1. CONOPS
2. Conceptual architecture
3. Logical architecture
4. Physical architecture
5. Pattern identification
6. Security/risk classification
7. Dependency and data handling gates if needed
8. Implementation plan
9. Small scoped execution
10. Stop condition checks
11. Validation
12. Definition of Done
13. Documentation/thread summary
14. Tangent capture / Markdown memory file if the discussion creates reusable context

First, help me clarify the problem and identify missing requirements.
Do not move to implementation until I explicitly say so.
```

---

# 16. The Process in One Sentence

The AI development process should be:

> Use AI first to reason about architecture, then to identify patterns and risks, then to execute small scoped changes, then to validate aggressively, then to capture durable knowledge outside the thread.

The biggest thing to avoid is letting AI become the driver. The process should make AI powerful, but boxed in.
