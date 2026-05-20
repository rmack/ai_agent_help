# Prompt Cards

These are reusable prompts. The agent should use them internally when guiding the user, but should not force the user to memorize them.

## Start AI Usage

```text
read ai_usage_wizard
```

## Architecture Phase Continue Prompt

```text
This phase looks good. Continue to the next architecture phase.
```

## Revise Current Phase Prompt

```text
Revise the current phase with these changes:
[changes]
```

## Closeout Prompt

```text
Close out this task using ai_usage_wizard.
Include decisions, validation, risks, open questions, and follow-up tasks.
```

## Thread Memory Prompt

```text
Summarize this thread into a Markdown memory file.
Include major topics, decisions, open questions, future thread seeds, and reusable context.
```
