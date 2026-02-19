# Evaluation Criteria

How we compare variants after each builds the RealWorld app from spec.

## Cost and Efficiency

| Metric | How measured |
|--------|-------------|
| Total input tokens | Sum from `session-log.jsonl` |
| Total output tokens | Sum from `session-log.jsonl` |
| Total cost (USD) | Calculated via `cost-model.md` rates |
| Session count | Number of entries in session log |
| Total wall-clock time | Sum of `duration_min` |
| Human interventions | Manual edits, restarts, prompt corrections |

## Spec Compliance

| Metric | How measured |
|--------|-------------|
| API endpoints implemented | Count vs. RealWorld spec |
| RealWorld API test suite | Pass / fail / skip counts |
| Frontend routes implemented | Count vs. routing spec |
| Feature parity | Checklist from `realworld-docs/implementation-creation/features.md` |

## Code Quality

| Metric | How measured |
|--------|-------------|
| Linter errors | ESLint / language-specific linter |
| Test coverage | Coverage report (line %) |
| File/module structure | Manual review: modularity, naming, separation of concerns |
| Duplication | Tool-based (e.g. jscpd) or manual assessment |
| Type safety | TypeScript strict mode errors, or equivalent |

## Qualitative

- How much did the developer need to "steer" the agent?
- Did the agent follow the harness rules consistently?
- Where did the agent struggle most?
- What surprised us (positively or negatively)?
