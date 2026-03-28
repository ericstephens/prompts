---
skill_id: 053
name: Market Entry Feasibility
version: 1.0
category: strategy
tags: [market-entry, expansion, feasibility, go-to-market, risk-assessment]
description: Assess whether entering a new market, geography, or segment is worth the investment — with a structured go/no-go framework.
compatible_models: [Claude 4/4.5, GPT-4o, Grok-2, Gemini 1.5 Pro]
last_updated: 2026-03-28
change_log:
  - 1.0 (2026-03-28) — Initial version
---

# Skill: Market Entry Feasibility
**Version:** 1.0
**Short Description:** Run a structured feasibility analysis for entering a new market, geography, or customer segment — with an attractiveness score, right-to-win assessment, break-even timeline, and explicit kill criteria.

## Parameters
- `{target_market}`     : The new market, geography, or segment to evaluate (required)
- `{current_business}`  : Description of the existing business — what it does, current customers, core capabilities (required)
- `{advantages}`        : What the company brings to the new market — assets, brand, technology, relationships (required)
- `{budget}`            : Available investment for the entry (required)
- `{timeline}`          : Expected timeline to evaluate success (optional, default: 18 months)

## Core Prompt

You are a market entry strategist advising a leadership team on whether to commit resources to a new market. Your job is to be rigorously honest — the cost of a bad "go" decision is far higher than the cost of a correct "no-go."

**Target Market:** {target_market}
**Current Business:** {current_business}
**Advantages We Bring:** {advantages}
**Available Budget:** {budget}
**Evaluation Timeline:** {timeline}

Conduct the following analysis:

1. **Market Attractiveness Score (1–10).** Rate each dimension, then compute a weighted average:
   - Market size and growth rate (weight: 25%)
   - Profit margins / unit economics in this market (weight: 25%)
   - Competitive intensity — number of entrenched players, switching costs (weight: 25%)
   - Regulatory / structural barriers to entry (weight: 25%)

2. **Right to Win.** Answer honestly: Why would customers in {target_market} choose this company over incumbents? Be specific. If the answer is "nothing compelling," say so — that is the most valuable finding.

3. **Top 3 Barriers to Entry.** For each: name the barrier, estimate the cost and time to overcome it, and rate difficulty (low / medium / high).

4. **Required Capabilities Gap.** What partnerships, hires, technology, or licenses does the company need but does not currently have? For each, estimate cost and lead time.

5. **Break-Even Analysis.** Using conservative (not best-case) assumptions:
   - Monthly burn rate for the entry
   - Revenue ramp assumptions (state them explicitly)
   - Months to break-even
   - Total capital required to reach break-even
   - Flag if total capital required exceeds {budget}

6. **Kill Criteria.** Define 3–4 specific, measurable signals that should trigger an exit from this market. These must be concrete enough that the team cannot rationalize past them — e.g. "fewer than X paying customers after Y months," not "if things aren't going well."

7. **Verdict.** One of: **GO** / **CONDITIONAL GO** (with conditions) / **NO-GO** (with reasoning).

Rules:
- Be specific to {target_market} and {current_business} — no generic frameworks.
- If the budget is insufficient for a credible entry, say so in the first paragraph.
- Every cost estimate should be a range (low–high), not a single number.
- If this is a bad idea, say so clearly. A well-reasoned "no-go" is more valuable than an optimistic "go."

Output in this exact format:

## Market Entry Feasibility: {target_market}

### Market Attractiveness

| Dimension | Score (1–10) | Weight | Weighted |
|-----------|:---:|:---:|:---:|
| Size & growth | X | 25% | X |
| Margins / unit economics | X | 25% | X |
| Competitive intensity (10 = low) | X | 25% | X |
| Barrier height (10 = low) | X | 25% | X |
| **Weighted Average** | | | **X.X** |

### Right to Win
[Honest assessment — 3–5 sentences]

### Barriers to Entry
| # | Barrier | Cost to Overcome | Time | Difficulty |
|---|---------|:---:|:---:|:---:|
| 1 | ... | $X–$Y | ... | ... |

### Capabilities Gap
[What's missing, cost, lead time]

### Break-Even Analysis
[Conservative projections with explicit assumptions]
**Months to break-even:** X–Y
**Total capital required:** $X–$Y

### Kill Criteria
1. [Measurable signal] → Exit
2. [Measurable signal] → Exit
3. [Measurable signal] → Exit

### Verdict
**[GO / CONDITIONAL GO / NO-GO]**
[2–4 sentence rationale]

---

## Notes / Tips / Variations
- The kill criteria section is the most important output for decision-makers. Without pre-committed exit signals, teams almost always throw good money after bad.
- For geographic expansion specifically, add: "Include a section on regulatory, tax, and employment law differences that affect cost structure."
- For channel or segment expansion (not geographic), simplify by removing barriers to entry and expanding the right-to-win section.
- Pair with **051** (TAM/SAM/SOM) for detailed market sizing of the target market.
