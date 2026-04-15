# Stock Skills

Reusable stock-analysis skills extracted from the `stockyy` workflow.

## Skills

- `company-deep-research`: single-company deep research with deep-research, source discipline, valuation, and risk-first output.
- `sector-cycle-analysis`: sector and industry cycle judgment using supply, demand, price, inventory, capacity, policy, and market evidence.
- `kline-trend-analysis`: short-, medium-, and long-term trend judgment from K-line/candlestick data, price structure, volume, and moving averages.

## Layout

```text
skills/<skill-name>/SKILL.md
skills/<skill-name>/references/*.md
harness/<skill-name>/*.md
docs/plans/*.md
```

Each harness case is a pressure scenario: it records a prompt, required behaviors, failure modes, and the expected output skeleton.

