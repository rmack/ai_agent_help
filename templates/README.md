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

## How Codex And Claude Use These Files

Codex and Claude Code load repository instructions differently:

- Codex reads `AGENTS.md` files directly.
- Claude Code reads `CLAUDE.md` files.
- Claude Code imports additional files only when `CLAUDE.md` uses `@path`
  syntax, such as `@AGENTS.md`.
- A Markdown link such as `[AGENTS.md](./AGENTS.md)` is documentation text,
  not a Claude import.

The recommended strategy is:

```text
AGENTS.md  = canonical shared instructions
CLAUDE.md  = adapter that imports the adjacent AGENTS.md
```

This avoids maintaining separate Codex and Claude rule systems.

## Codex Size And Loading Notes

Codex builds an instruction chain when it starts. It reads global instructions
from the Codex home directory, then walks from the project root down to the
current working directory and includes matching `AGENTS.md` files along that
path.

Important size behavior:

- Codex has a combined project-document size limit controlled by
  `project_doc_max_bytes`.
- The documented default is 32 KiB.
- Once the combined instruction content reaches that limit, Codex stops adding
  more instruction files.
- If root `AGENTS.md` is too large, more specific local instructions may not be
  loaded.
- Remedies are to keep root concise, split scoped guidance into nested
  `AGENTS.md` files, or intentionally raise `project_doc_max_bytes` in Codex
  config.

This is why the root template should stay compact and why detailed rules should
move closer to the files they govern.

## Claude Memory Notes

Claude Code has two related mechanisms:

- `CLAUDE.md` files: instructions written by humans for project, user, or
  organization behavior.
- Auto memory: notes Claude writes itself from corrections and preferences.

For repository instructions, prefer checked-in `CLAUDE.md` adapter files that
import `AGENTS.md`. Auto memory is useful for personal or learned preferences,
but it is not a replacement for durable repository rules.

Important Claude behavior:

- Claude reads `CLAUDE.md`, not `AGENTS.md`, unless `CLAUDE.md` imports it.
- `@path` imports are expanded into context; Markdown links are not imports.
- Imported files still consume context.
- Long instruction files consume more context and can reduce adherence.
- Claude's docs recommend keeping `CLAUDE.md` files concise; if instructions
  grow large, split or scope them.
- `/memory` can be used to inspect or edit Claude memory/instruction files, but
  behavior may vary by Claude Code version and UI mode.

## Scoped Context Strategy

Keep the root `AGENTS.md` focused on rules that apply to most work:

- source of truth
- operating model
- stop conditions
- decision hierarchy
- plan-first triggers
- common commands
- security and dependency rules
- closeout expectations

Move detailed or area-specific rules closer to the files they govern:

```text
src/domain/AGENTS.md
src/plugins/AGENTS.md
tests/integration/AGENTS.md
tools/AGENTS.md
```

This gives agents more relevant context when they work in those paths without
forcing every task to load all detailed rules at the repository root.

For Claude Code, add an adjacent bridge file beside each local `AGENTS.md` that
should be loaded:

```text
src/domain/
  AGENTS.md
  CLAUDE.md
```

with:

```md
# CLAUDE.md

@AGENTS.md
```

## Focused Reference Docs

Some guidance is important but too detailed to keep in root or too broad for a
single code subtree. Put that guidance in focused reference docs, for example:

```text
docs/agent_rules/python_style.md
docs/agent_rules/yaml_records.md
docs/agent_rules/artifact_uri_policy.md
docs/agent_rules/golden_artifacts.md
docs/agent_rules/new_stage_checklist.md
```

Then document those references explicitly in root `AGENTS.md`:

```md
## Must-Read References

Before editing an area below, read the matching reference first:

- Python formatting and docstrings: `docs/agent_rules/python_style.md`
- YAML flat-record tables: `docs/agent_rules/yaml_records.md`
- Artifact URI policy: `docs/agent_rules/artifact_uri_policy.md`
- Golden artifacts: `docs/agent_rules/golden_artifacts.md`
- New stage checklist: `docs/agent_rules/new_stage_checklist.md`
```

Use this pattern when a rule is durable and reusable, but loading it for every
task would make the root instruction file noisy.

## Risks If You Do Not Follow This Pattern

Common failure modes:

- `CLAUDE.md` contains only a Markdown link to `AGENTS.md`, so Claude may not
  import the actual instructions.
- Codex and Claude drift because teams maintain separate rule files with
  different content.
- Root `AGENTS.md` grows too large, causing Codex to hit its instruction size
  limit before local rules load.
- All tasks load every detailed rule, which wastes context and makes agents
  less likely to follow the rule that actually matters.
- Local teams or subtrees lose important guidance because their rules are buried
  in a large root document instead of placed near the relevant code.
- Conflicting instructions across root and local files make behavior
  unpredictable.
- Durable decisions stay only in chat history or auto memory instead of the
  repository, so future sessions and other tools do not reliably see them.

The goal is not to create many files for their own sake. The goal is to keep
root instructions small, shared instructions canonical, and detailed guidance
loaded only where it is relevant.

## Official Documentation

Use official documentation for the latest behavior:

- OpenAI Codex `AGENTS.md` guide:
  <https://developers.openai.com/codex/guides/agents-md>
- Claude Code memory and `CLAUDE.md` guide:
  <https://code.claude.com/docs/en/memory>
- Claude documentation index:
  <https://code.claude.com/docs/llms.txt>

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
file.

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
