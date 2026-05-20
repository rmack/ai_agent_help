# Agent Instruction Templates

This directory contains reusable templates for adding AI agent operating instructions to another repository.

## Files

| File | Purpose |
| --- | --- |
| `AGENTS.md` | Lightweight starter template for basic repository-level AI agent instructions. |
| `AGENTS_VERBOSE.md` | Fuller template for larger, production, regulated, or higher-risk repositories. |
| `CLAUDE.md` | Points Claude-compatible tools to the shared `AGENTS.md` instructions. |

## How To Use

Copy the templates into the root of another repository:

```text
AGENTS.md
CLAUDE.md
```

For a small or low-risk repository, start with `AGENTS.md`.

For a larger or higher-risk repository, copy `AGENTS_VERBOSE.md` as `AGENTS.md`.

Then edit the selected `AGENTS.md` so it reflects the target repository's actual architecture, commands, coding standards, validation expectations, and stop conditions.

## Intended Role

These templates are starting points, not finished policy.

They are meant to give AI tools a simple repository-level operating contract:

- understand before editing
- keep changes minimal
- preserve architecture and contracts
- require planning for risky changes
- validate work before closeout
- report changes clearly
