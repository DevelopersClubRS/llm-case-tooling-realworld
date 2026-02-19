# LLM Case Tooling

Building the RealWorld app from spec using different agentic coding harnesses and LLM models, then comparing the results.

## Goal

Evaluate how different AI coding tools and configurations perform on the same well-defined task: implementing the RealWorld "Conduit" app (a Medium clone with user auth, articles, comments, tags, profiles, and favoriting).

## Structure

```
llm-case-tooling/
  common/                            # Shared specs, evaluation criteria, cost tracking schema
  claude-code/                       # Variant: Claude Code terminal agent
  cursor/                            # Variant: Cursor IDE (standard agent mode)
  cursor-agent-orchestration/        # Variant: Cursor with multi-agent orchestration
```

Each variant folder contains:

| Path | Purpose |
|------|---------|
| `README.md` | Harness + model description, reproduction steps |
| `rules/` or `.cursor/rules/` | Rules/guidance files used |
| `agents/` or `.cursor/agents/` | Subagent definitions |
| `tracking/session-log.jsonl` | Per-session token usage and cost log |
| `output/` | Generated RealWorld app code (or git ref) |
| `results.md` | Post-run evaluation notes |

## Contributing

This is an open source project. We welcome new variants -- different tools, models, or harness configurations.

Every contribution **must include token usage and cost data** for each session. This is non-negotiable; the whole point is comparing approaches on a level playing field.

See [CONTRIBUTING.md](CONTRIBUTING.md) for the full guide, including:
- How to structure your variant folder
- Required fields in `tracking/session-log.jsonl`
- Where to find token counts in different tools
- PR format and checklist

## What We Track

- Token usage (input, output, cache) and cost per session
- Total cost to reach feature parity with the RealWorld spec
- Number of sessions / human interventions required
- Code quality: linting, test coverage, structural consistency
- Spec compliance: RealWorld API test suite pass rate

See [common/evaluation-criteria.md](common/evaluation-criteria.md) for the full rubric.
