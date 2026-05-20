# Agent Instruction Templates

This directory contains reusable templates for adding AI agent operating instructions to another repository.

## Files

| File | Purpose |
| --- | --- |
| `AGENTS.md` | Defines general rules for how AI agents should work in a repository. |
| `CLAUDE.md` | Points Claude-compatible tools to the shared `AGENTS.md` instructions. |

## How To Use

Copy the templates into the root of another repository:

```text
AGENTS.md
CLAUDE.md
```

Then edit `AGENTS.md` so it reflects the target repository's actual architecture, commands, coding standards, validation expectations, and stop conditions.

## Intended Role

These templates are a starting point, not a finished policy.

They are meant to give AI tools a simple repository-level operating contract:

- understand before editing
- keep changes minimal
- preserve architecture and contracts
- require planning for risky changes
- validate work before closeout
- report changes clearly
