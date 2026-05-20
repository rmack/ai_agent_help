# Thread Summary / Markdown Memory Workflow

Use this workflow when the user wants to capture a discussion into a reusable Markdown file.

## Purpose

Turn temporary thread context into durable memory for future work.

## Wizard Questions

```text
Selected workflow: Thread Summary / Markdown Memory
Process weight: Lightweight or Standard.
Mode: Summary

Answer what you can:
1. Should the summary be brief, standard, or detailed?
2. Should it capture decisions, open questions, future thread seeds, or all of these?
3. What filename should the Markdown summary use?
4. Should it be written for humans, future AI context, or both?
```

## Process

1. Identify purpose of the thread.
2. Extract major topics.
3. Capture decisions.
4. Capture open questions.
5. Capture future-thread seeds.
6. Capture architecture notes, patterns, and validation details if relevant.
7. Produce Markdown using `templates/thread_summary.md`.

## Output Rule

The summary should be useful if uploaded into a future AI thread.

## Closeout Prompt

```text
Create a Markdown summary of this thread.

Include:
- purpose
- major topics
- decisions made
- open questions
- architecture notes
- patterns identified
- validation performed
- follow-up tasks
- future thread seeds
```
