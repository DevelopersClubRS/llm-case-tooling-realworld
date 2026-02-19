# Contributing

We welcome contributions of new variants -- different agentic coding harnesses, LLM models, or configuration approaches used to build the RealWorld app from spec.

## What is a contribution?

A contribution is a **complete variant**: you build the RealWorld "Conduit" app using your chosen AI coding tool and model, track your token usage and cost, and submit the results.

## Requirements

Every contribution **must** include token and cost data. This is the core of the project -- we're comparing how different approaches perform on the same task, and cost/efficiency is a first-class metric.

### 1. Create your variant folder

Copy an existing variant (e.g. `claude-code/`) and rename it to describe your approach:

```
llm-case-tooling/
  your-variant-name/
    README.md
    tracking/
      session-log.jsonl
    output/
    results.md
```

Use a descriptive name like `windsurf-sonnet4/`, `cursor-gemini-pro/`, `claude-code-opus4-tdd/`, etc.

### 2. Fill in your README.md

Your variant `README.md` must specify:

| Field | Description |
|-------|-------------|
| **Tool / Harness** | e.g. Claude Code, Cursor, Windsurf, Copilot, Aider, etc. |
| **LLM Model(s)** | Exact model identifiers used (e.g. `claude-sonnet-4-20250514`) |
| **Harness config** | What rules, agents, skills, or other context engineering was used |
| **Reproduction steps** | How someone else could replicate your run |

### 3. Log every session with token data

Each coding session must be logged as a JSON line in `tracking/session-log.jsonl`. See [`common/tracking-template.json`](common/tracking-template.json) for the full schema.

**Required fields per session:**

```json
{
  "session_id": "2026-02-20-001",
  "date": "2026-02-20",
  "model": "claude-sonnet-4-20250514",
  "harness": "your-variant-name",
  "task": "Implement article CRUD endpoints",
  "input_tokens": 52000,
  "output_tokens": 18400,
  "cache_read_tokens": 12000,
  "cache_write_tokens": 3200,
  "cost_usd": 0.58,
  "duration_min": 25,
  "human_interventions": 2,
  "notes": "Had to manually fix DB migration naming"
}
```

**Where to get token counts:**
- **Claude Code**: Check the session summary at the end, or use `/cost`
- **Cursor**: Check the cost tracking panel or `.cursor-cost-tracking/` if available
- **Copilot / other tools**: Check the tool's usage dashboard or billing page
- **API-based tools (Aider, etc.)**: Usually printed in terminal output

If your tool doesn't expose exact token counts, provide your best estimate and note the estimation method.

### 4. Write up results

Fill in `results.md` with:

- **Cost totals** -- sum of all sessions (input tokens, output tokens, total USD)
- **Spec compliance** -- which RealWorld features were implemented, API test pass rate
- **Code quality** -- linter results, test coverage, structural notes
- **Observations** -- what worked, what didn't, where the agent struggled, surprises

### 5. Include your harness configuration

Include the actual rules, agents, skills, or other config files you used:

- **Claude Code**: `CLAUDE.md`, `rules/`, `agents/`, `skills/`, `hooks/`
- **Cursor**: `.cursor/rules/`, `.cursor/agents/`
- **Other tools**: Whatever configuration files your tool uses

This lets others learn from and reproduce your approach.

### 6. Submit a PR

- Branch from `main`
- Add your variant folder with all the above
- PR title format: `Add variant: <tool> + <model>` (e.g. `Add variant: Claude Code + Opus 4`)
- In the PR description, include a brief cost summary:

```
## Cost Summary
- Total input tokens: 1,240,000
- Total output tokens: 380,000
- Total cost: $14.20
- Sessions: 12
- Human interventions: 8
```

## Contribution checklist

- [ ] Variant folder with a descriptive name
- [ ] `README.md` with tool, model, config, and reproduction steps
- [ ] `tracking/session-log.jsonl` with **token counts and cost for every session**
- [ ] `results.md` with cost totals, spec compliance, code quality, and observations
- [ ] Harness config files included (rules, agents, etc.)
- [ ] `output/` contains the generated code or a git ref to it

## Code of conduct

Be honest about your numbers. The value of this project depends on accurate, comparable data. If you had to estimate token counts, say so. If the agent failed and you rewrote something manually, log the intervention.
