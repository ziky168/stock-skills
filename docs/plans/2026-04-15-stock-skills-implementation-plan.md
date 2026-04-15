# Stock Skills Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Build three reusable English-language stock-analysis skills plus harness scenarios.

**Architecture:** Each skill is a standalone folder with `SKILL.md` as the triggerable guide and one reference file for heavier checklists. Harness files live outside skills so they can test behavior without bloating skill context.

**Tech Stack:** Markdown skills, YAML frontmatter, shell-based verification.

---

### Task 1: Repository Skeleton

**Files:**
- Create: `README.md`
- Create: `docs/plans/2026-04-15-stock-skills-design.md`
- Create: `docs/plans/2026-04-15-stock-skills-implementation-plan.md`

**Step 1: Write the failing check**

Run:

```bash
test -f README.md
```

Expected: fail before repository docs exist.

**Step 2: Implement**

Create the README and plan/design docs.

**Step 3: Verify**

Run:

```bash
test -f README.md && test -f docs/plans/2026-04-15-stock-skills-design.md
```

Expected: pass.

### Task 2: Skill Documents

**Files:**
- Create: `skills/company-deep-research/SKILL.md`
- Create: `skills/company-deep-research/references/report-template.md`
- Create: `skills/sector-cycle-analysis/SKILL.md`
- Create: `skills/sector-cycle-analysis/references/indicator-map.md`
- Create: `skills/kline-trend-analysis/SKILL.md`
- Create: `skills/kline-trend-analysis/references/horizon-framework.md`

**Step 1: Write the failing check**

Run:

```bash
find skills -name SKILL.md | wc -l
```

Expected: not equal to `3` before skill docs exist.

**Step 2: Implement**

Write the three skills with concise frontmatter and executable workflows.

**Step 3: Verify**

Run:

```bash
find skills -name SKILL.md | wc -l
```

Expected: `3`.

### Task 3: Harness Scenarios

**Files:**
- Create: `harness/company-deep-research/case-01.md`
- Create: `harness/sector-cycle-analysis/case-01.md`
- Create: `harness/kline-trend-analysis/case-01.md`

**Step 1: Write the failing check**

Run:

```bash
find harness -name 'case-*.md' | wc -l
```

Expected: not equal to `3` before harness cases exist.

**Step 2: Implement**

Write one pressure scenario per skill, including prompt, required behaviors, failure modes, and output skeleton.

**Step 3: Verify**

Run:

```bash
find harness -name 'case-*.md' | wc -l
```

Expected: `3`.

### Task 4: Final Verification

Run:

```bash
git status --short
find skills -name SKILL.md -print
rg -n '^name:|^description:' skills
rg -n 'Fact|Inference|Disconfirm|latest completed trading-day close|not financial advice' skills
```

Expected: all skill docs exist, frontmatter is present, and required workflow guardrails are discoverable.

