# Agent Instruction Templates

This directory contains reusable templates for adding AI agent operating instructions to another repository.

## Files

| File | Purpose |
| --- | --- |
| `AGENTS.md` | Lightweight starter template for basic repository-level AI agent instructions. Use this as the canonical shared rule source. |
| `AGENTS_VERBOSE.md` | Fuller template for larger, production, regulated, or higher-risk repositories. Copy it as `AGENTS.md` when the starter is too small. |
| `CLAUDE.md` | Claude Code adapter template. It imports the adjacent `AGENTS.md` with `@AGENTS.md`. |

## Recommended Instruction Layout

Use one shared rule system:

```text
repo/
  AGENTS.md      # canonical shared agent instructions
  CLAUDE.md      # Claude adapter only; imports @AGENTS.md
```

For larger repositories, add scoped instructions near the code they govern:

```text
repo/
  AGENTS.md
  CLAUDE.md
  src/some_area/
    AGENTS.md
    CLAUDE.md
```

Local `CLAUDE.md` files should import only the adjacent local `AGENTS.md`.
Do not make local `CLAUDE.md` files re-import the root `AGENTS.md`; root
loading should handle root instructions.

## How To Use

Copy the templates into the root of another repository:

```text
AGENTS.md
CLAUDE.md
```

For a small or low-risk repository, start with `AGENTS.md`.

For a larger or higher-risk repository, copy `AGENTS_VERBOSE.md` as `AGENTS.md`.

Then edit the selected `AGENTS.md` so it reflects the target repository's actual architecture, commands, coding standards, validation expectations, and stop conditions.

Keep `CLAUDE.md` small. It should normally be an adapter, not a second policy
file. Claude Code imports files with `@path` syntax. A normal Markdown link
such as `[AGENTS.md](./AGENTS.md)` is documentation text, not an import.

If the root `AGENTS.md` becomes large, split detailed rules into local
`AGENTS.md` files or focused reference docs and leave root as the concise
repository-wide operating contract. This keeps Codex startup context smaller
and makes Claude's imported context easier to follow.

When adding a local `AGENTS.md` that Claude Code should see, add an adjacent
`CLAUDE.md` containing:

```md
# CLAUDE.md

@AGENTS.md
```

## Intended Role

These templates are starting points, not finished policy.

They are meant to give AI tools a simple repository-level operating contract:

- understand before editing
- keep changes minimal
- preserve architecture and contracts
- require planning for risky changes
- validate work before closeout
- report changes clearly

They are also meant to keep repository instructions durable. Chat threads are
temporary working context; lasting rules belong in `AGENTS.md`, local
`AGENTS.md` files, tests, architecture docs, and other repository documentation.
