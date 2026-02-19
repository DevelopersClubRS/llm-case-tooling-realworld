# Variant: Cursor + Agent Orchestration

## Harness

**Tool:** Cursor IDE -- agent mode with multi-agent orchestration
**Model:** TBD (e.g. Claude Sonnet 4 for coding, Claude Haiku 3.5 for review subagents)

## Configuration

- `.cursor/rules/` -- Cursor rules files scoped by file pattern
- `.cursor/agents/` -- Multiple specialized agent definitions (planner, coder, reviewer, tester)

## What Makes This Different

This variant uses explicit agent orchestration: a planner agent breaks down the work, specialized coding agents handle implementation, and reviewer/tester agents validate the output. The goal is to see if structured multi-agent workflows produce better results or lower cost than single-agent approaches.

## Reproduction

1. Open this folder as a Cursor workspace
2. Ensure rules and agents are loaded from `.cursor/`
3. Point the agent at `../../realworld-docs/` for the spec
4. Use orchestration workflow: plan -> implement -> review -> test
5. Log each session to `tracking/session-log.jsonl`

## Status

Not started.
