# Variant: Claude Code

## Harness

**Tool:** Claude Code (terminal agent)
**Model:** TBD (e.g. Claude Sonnet 4, Claude Opus 4)

## Configuration

- `CLAUDE.md` -- project-level guidance loaded at session start
- `rules/` -- always-follow conventions (coding style, testing, security)
- `agents/` -- subagent definitions for delegation (planner, reviewer, tdd, etc.)
- `skills/` -- on-demand workflow knowledge (backend patterns, TDD workflow)
- `hooks/` -- trigger-based automations (format on edit, lint checks)

## Reproduction

1. Install Claude Code
2. Copy this folder as the project root (or symlink `CLAUDE.md`, `rules/`, etc. into your project)
3. Point the agent at `../../realworld-docs/` for the spec
4. Run sessions, log each to `tracking/session-log.jsonl`

## Status

Not started.
