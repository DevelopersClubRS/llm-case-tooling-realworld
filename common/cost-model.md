# Cost Model

Reference pricing for token cost calculations across variants. Update as pricing changes.

> Prices as of February 2026. All prices per 1M tokens.

## Anthropic

| Model | Input | Output | Cache Read | Cache Write |
|-------|-------|--------|------------|-------------|
| Claude Opus 4 | $15.00 | $75.00 | $1.50 | $18.75 |
| Claude Sonnet 4 | $3.00 | $15.00 | $0.30 | $3.75 |
| Claude Haiku 3.5 | $0.80 | $4.00 | $0.08 | $1.00 |

## OpenAI

| Model | Input | Output | Cache Read | Cache Write |
|-------|-------|--------|------------|-------------|
| GPT-4.1 | $2.00 | $8.00 | $0.50 | -- |
| GPT-4.1 mini | $0.40 | $1.60 | $0.10 | -- |
| o3 | $2.00 | $8.00 | -- | -- |
| o4-mini | $1.10 | $4.40 | $0.275 | -- |

## Google

| Model | Input | Output |
|-------|-------|--------|
| Gemini 2.5 Pro | $1.25 - $2.50 | $10.00 - $15.00 |
| Gemini 2.5 Flash | $0.15 - $0.30 | $0.60 - $3.50 |

## Cost Calculation

For each session log entry:

```
cost_usd = (input_tokens * input_rate / 1M)
          + (output_tokens * output_rate / 1M)
          + (cache_read_tokens * cache_read_rate / 1M)
          + (cache_write_tokens * cache_write_rate / 1M)
```
