# Phase Control

Use this file for multi-phase workflows.

## Core Rule

Do not run all phases in one response unless the user explicitly asks for a complete draft.

For each phase:

1. State the current phase.
2. State the goal of the phase.
3. Ask only the questions required for that phase.
4. Produce the phase output.
5. Summarize open questions.
6. Ask whether to revise or continue.
7. Do not proceed until the user confirms or gives enough direction.

## Phase Response Format

```text
Current phase: [phase name]
Goal: [phase goal]

Questions:
1. ...
2. ...
3. ...

After you answer, I will produce:
- [expected output]

Next phase after approval:
[next phase]
```

## Phase Completion Format

```text
Phase complete: [phase name]

Summary:
[summary]

Open questions:
- [...]

Next phase:
[next phase]

Do you want to revise this phase or continue?
```

## Skipping Phases

Only skip a phase if:

- the user explicitly asks to skip it
- the phase is clearly irrelevant
- the needed information already exists and has been summarized

If skipping, state why.
