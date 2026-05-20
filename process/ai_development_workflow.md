# AI Development Workflow

## The Whole Process in One Simple Flow

```text
Discussion thread
   ↓
Define purpose
   ↓
Clarify the work
   ↓
Create Markdown handoff for Codex/Claude/Agent
   ↓
Codex/Claude/Agent reads and explains understanding
   ↓
Human confirms or corrects
   ↓
Codex/Claude/Agent executes small step
   ↓
Human reviews diff
   ↓
Run unit / smoke / regression tests / code reviews
   ↓
Commit locally
   ↓
Create summary if useful
   ↓
Repeat
```

---

# Simple AI Development Workflow

## 1. Start with a Discussion Thread

Use a normal AI chat to think through the work before touching code.

Purpose:

```text
Understand the problem before asking Codex/Claude/Agent or an agent to implement anything.
```

This is where you discuss:

```text
What are we trying to do?
Why does it matter?
What are the risks?
What are the options?
What is the likely approach?
```

---

## 2. Track the Purpose of the Thread

At the beginning, define why the thread exists.

Example:

```text
The purpose of this thread is to explore how to add CSV export to the reporting screen.
We are not implementing yet.
We are trying to define the work clearly enough for Codex/Claude/Agent to execute later.
```

This prevents the conversation from drifting too far without knowing what it is for.

---

## 3. Define the Work

Use the discussion thread to clarify the work.

Capture:

```text
Goal
Scope
Out of scope
Assumptions
Requirements
Acceptance criteria
Risks
Architecture notes
Testing expectations
```

The point is to turn a vague idea into executable instructions.

---

## 4. Create a Codex/Claude/Agent Handoff Markdown File

Once the work is understood, ask the discussion thread to create a Markdown artifact for Codex/Claude/Agent.

This file should include:

```text
Purpose
Context
Goal
Scope
Constraints
Relevant architecture
Expected behavior
Files or areas likely involved
Implementation guidance
Validation expectations
Stop conditions
Definition of done
```

Simple wording:

```text
Create a Markdown handoff file that I can give to Codex/Claude/Agent.
It should contain enough context for Codex/Claude/Agent to discuss and then execute this work safely.
```

---

## 5. Give the Markdown File to Codex/Claude/Agent

Start a Codex/Claude/Agent/agent thread and provide the Markdown artifact.

Initial intent should be discussion, not execution.

Example:

```text
Read this Markdown handoff.
Do not implement yet.
First explain your understanding of the work, the likely approach, risks, and any questions.
```

This makes Codex/Claude/Agent prove it understands before it changes code.

---

## 6. Confirm or Correct Codex/Claude/Agent’s Understanding

Review what Codex/Claude/Agent says.

Ask yourself:

```text
Does it understand the goal?
Did it miss any constraints?
Is the scope correct?
Is the approach reasonable?
Is it following the intended architecture?
```

If not, correct it before execution.

---

## 7. Ask Codex/Claude/Agent to Execute in Small Steps

Once the plan is correct, tell Codex/Claude/Agent to begin.

But not as one giant change.

Example:

```text
Proceed with the first implementation step only.
Keep the diff small.
Stop after the first meaningful change and summarize what changed.
```

This keeps the work reviewable.

---

## 8. Review the Work

After Codex/Claude/Agent makes changes, review the diff.

Check:

```text
Do I understand the change?
Is it within scope?
Does it follow existing patterns?
Did it introduce unnecessary complexity?
Did it change unrelated behavior?
```

The human still owns the code.

---

## 9. Validate the Work

Run the right level of testing.

Use:

```text
Unit tests
Validate isolated logic.

Smoke tests
Validate that the workflow/system still runs.

Regression tests
Validate that existing expected behavior did not unintentionally change.

Code Reviews
Perform 1..n code reviews depending on the work completed.
```

Also ask:

```text
What did the tests prove?
What did they not prove?
What still needs manual review?
```

---

## 10. Check It In Locally

Once reviewed and validated:

```text
Stage the changes.
Commit locally.
Use a clear commit message.
Capture follow-up work if needed.
```

Do not let the AI-generated work sit as a vague pile of changes.

---

## 11. Create a Thread Summary If Useful

At the end, ask the AI to summarize the work.

Capture:

```text
What was done
Why it was done
Files changed
Patterns followed
Tests run
Validation results
Open questions
Follow-up tasks
Create the PR context as a PR.md file locally
Review the PR markdown
```

This becomes memory for the future.

---

## 12. Repeat the Process

For the next task, start again.

```text
Discuss
Define
Create handoff
Give to Codex/Claude/Agent
Confirm understanding
Execute
Review
Validate
Commit
Summarize
Repeat
```

---

# Simple Explanation

The discussion thread is for **thinking**.

The Markdown handoff is for **transferring clear intent**.

Codex/Claude/Agent/Claude/Agent is for **executing scoped work**.

The developer is responsible for **reviewing, validating, and committing**.
