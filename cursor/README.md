# Variant: Cursor (Standard Agent Mode)

## Harness

**Tool:** Cursor IDE -- agent mode
**Model:** TBD (e.g. Claude Sonnet 4, GPT-4.1, Gemini 2.5 Pro)

## Configuration

- `.cursor/rules/` -- Cursor rules files scoped by file pattern
- `.cursor/agents/` -- Agent definitions for delegation

## Reproduction

1. Open this folder as a Cursor workspace
2. Ensure rules and agents are loaded from `.cursor/`
3. Point the agent at `../../realworld-docs/` for the spec
4. Run sessions, log each to `tracking/session-log.jsonl`

## Status

Not started.
