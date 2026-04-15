# Stock Skills

Reusable stock-analysis skills extracted from the `stockyy` workflow and packaged as a self-contained repo.

This repo is designed for:

- Research-support workflows (not financial advice).
- Repeatable outputs with explicit sourcing and “Fact vs Inference” discipline.
- Optional on-box data pulls and technical indicators (AkShare).

## What’s Included

Primary skills:

- `skills/company-deep-research`: single-company deep research memo/report (risk-first, valuation discipline, citations).
- `skills/sector-cycle-analysis`: sector/industry cycle stage judgment (supply/demand/prices/inventory/capacity/policy + invalidation).
- `skills/kline-trend-analysis`: K-line trend judgment across short/medium/long horizons (structure + MA + volume + invalidation).

Vendored helper skills:

- `skills/deep-research`: multi-source research pipeline templates and validation scripts.
- `skills/akshare-stock`: A-share market data + basic analysis routing (requires Python deps).

## Repository Layout

```text
skills/<skill-name>/SKILL.md
skills/<skill-name>/references/*.md
harness/<skill-name>/*.md
docs/plans/*.md
```

Harness cases are pressure scenarios: prompt, required behaviors, failure modes, and expected output skeletons.

## Environment Setup

### Minimum (works everywhere)

No dependencies are required for reading and using the workflows as plain Markdown.

For “research-grade” reports, you still need a way to browse/search and access filings (CNINFO PDFs, exchange announcements, company IR pages).

### Optional: Python for market data (recommended)

If you want “latest completed trading-day close” and K-line indicators computed locally, install Python deps:

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -U pip
python -m pip install akshare pandas numpy
```

Quick check:

```bash
python -c "import akshare, pandas, numpy; print('ok')"
```

Notes:

- Some environments (e.g., very new Python versions) may not be compatible with `akshare`. If import fails, follow `skills/company-deep-research/references/data-playbook.md` fallback ladder.
- `skills/akshare-stock/SKILL.md` documents its intended runtime and module requirements.

## How to Use

These are “skills” in the agent sense: load the relevant `SKILL.md`, follow the workflow, and produce the output in the requested format.

### 1) Company Deep Research (000157 example)

Open and follow:

- `skills/company-deep-research/SKILL.md`
- `skills/company-deep-research/references/report-template.md`

Suggested prompt (for an agent runtime):

```text
Use company-deep-research to research 000157.SZ Zoomlion.
Output a full report in Chinese.
Include latest completed trading-day close with date + source + method.
Label major statements as Fact or Inference.
```

### 2) Sector Cycle Analysis

Open and follow:

- `skills/sector-cycle-analysis/SKILL.md`
- `skills/sector-cycle-analysis/references/indicator-map.md`

Suggested prompt:

```text
Use sector-cycle-analysis to judge China construction machinery sector cycle.
Give primary stage + alternate stage, evidence table, disconfirming signals, and next-week watchlist.
```

### 3) K-Line Trend Analysis

Open and follow:

- `skills/kline-trend-analysis/SKILL.md`
- `skills/kline-trend-analysis/references/horizon-framework.md`

Suggested prompt:

```text
Use kline-trend-analysis on 600519.SH using completed daily and weekly bars.
Return short/medium/long calls with key levels and invalidation.
Avoid deterministic targets.
```

## Tips and Known Pitfalls

- Latest close must be a completed trading-day close. If you cannot verify it, explicitly state “latest verified close” and mark the true latest close as “pending verification”.
- Do not output valuation action bands if the valuation anchor is unstable or missing; explain what data is needed.
- Technical analysis should be multi-timeframe and must include invalidation levels.
