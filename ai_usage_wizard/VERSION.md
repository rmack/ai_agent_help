# ai_usage_wizard Version 2

## What Changed from v1

Version 2 adds:

- separate human and agent documentation surfaces
- explicit text-based wizard behavior
- agent execution rules
- phase control for multi-phase workflows
- phased architecture workflow:
  - CONOPS
  - Conceptual Architecture
  - Logical Architecture
  - Physical Architecture
  - Architecture Decision Summary
- phased workflows for enhancement, bug fix, and technical debt
- stronger pause/continue checkpoints between phases

## Design Goal

The user should be able to say:

```text
read ai_usage_wizard
```

Then the agent should guide the user like a text-based wizard.
