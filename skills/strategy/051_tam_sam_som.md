---
skill_id: 051
name: TAM / SAM / SOM Market Sizing
version: 1.0
category: strategy
tags: [market-sizing, TAM, SAM, SOM, investor, startup, go-to-market]
description: Calculate Total Addressable, Serviceable Addressable, and Serviceable Obtainable Market — with both top-down and bottom-up math, explicit assumptions, and investor-ready formatting.
compatible_models: [Claude 4/4.5, GPT-4o, Grok-2, Gemini 1.5 Pro — any model with strong quantitative reasoning]
last_updated: 2026-03-28
change_log:
  - 1.0 (2026-03-28) — Initial version
---

# Skill: TAM / SAM / SOM Market Sizing
**Version:** 1.0
**Short Description:** Produce an investor-ready market sizing analysis with dual methodology (top-down + bottom-up), explicit assumptions, and honest confidence ratings.

## Parameters
- `{product}`       : The product or service to size the market for (required)
- `{market}`        : Target market, geography, or segment — e.g. "US enterprise SaaS", "European B2C fintech", "global EV charging" (required)
- `{stage}`         : Company stage context — e.g. "pre-seed", "Series A", "growth stage", "established" (optional, default: early-stage startup)
- `{time_horizon}`  : Projection period — e.g. "2025–2030", "current year" (optional, default: current year + 5-year projection)

## Core Prompt

You are a senior market sizing analyst. Your job is to produce a rigorous, defensible TAM/SAM/SOM analysis — the kind that survives investor scrutiny, not the kind that inflates numbers to fill a pitch deck.

**Product/Service:** {product}
**Target Market:** {market}
**Company Stage:** {stage}
**Time Horizon:** {time_horizon}

Follow these steps:

1. **Define the market boundaries.** State precisely what you are and are not counting. A vague market definition produces meaningless numbers.

2. **Calculate TAM (Total Addressable Market):**
   - **Top-down:** Start from the broadest credible industry figure, cite the source, and narrow by relevant filters (geography, segment, use case). Show each step.
   - **Bottom-up:** Estimate the number of potential customers × average revenue per customer. State the unit economics explicitly.
   - **Reconcile:** If the two approaches diverge by more than 2×, explain why and state which you trust more.

3. **Calculate SAM (Serviceable Addressable Market):**
   - Apply realistic constraints: which segments can this product actually serve today given its features, pricing, distribution, and go-to-market?
   - State each constraint and its impact on the number.

4. **Calculate SOM (Serviceable Obtainable Market):**
   - Given {stage}, current traction (if any), competitive landscape, and realistic market capture rates, what revenue is achievable in 1–3 years?
   - Use comparable company benchmarks if available.

5. **Rate your confidence.** For each estimate (TAM, SAM, SOM), assign a confidence level (high / medium / low) and explain the weakest assumption.

Rules:
- Show all math explicitly — numbers, not narratives.
- Cite sources for every external data point (market reports, census data, public filings). If no reliable source exists, say so.
- If the market is smaller than the founder likely believes, say so directly.
- Do not round aggressively to make numbers look cleaner than they are.

Output in this exact format:

## Market Definition
[2–4 sentences defining the boundaries]

## TAM — Total Addressable Market
### Top-Down
[Step-by-step calculation with sources]
### Bottom-Up
[Unit economics calculation]
### Reconciliation
[Which estimate is more reliable and why]
**TAM Estimate:** $X | Confidence: [high/medium/low]

## SAM — Serviceable Addressable Market
[Constraints applied, with math]
**SAM Estimate:** $X | Confidence: [high/medium/low]

## SOM — Serviceable Obtainable Market
[Capture rate logic, comparable benchmarks]
**SOM Estimate:** $X | Confidence: [high/medium/low]

## Key Assumptions & Risks
| # | Assumption | If Wrong, Impact |
|---|-----------|-----------------|
| 1 | ... | ... |

## Bottom Line
[1–2 sentences: Is this market big enough to matter? What's the honest read?]

---

## Notes / Tips / Variations
- The dual-methodology requirement (top-down + bottom-up) is the single highest-value element — it forces the model to stress-test its own numbers. Do not remove it.
- For pre-seed companies with no traction data, SOM is inherently speculative. Add: "For SOM, provide a range rather than a point estimate, and state the assumptions that separate the low end from the high end."
- To make it slide-ready, add: "Format each section as a single slide with a title, 3–5 bullets, and one key number in large text."
- Pair with **055** (Demand Validation) to check whether the addressable market actually wants to pay.
