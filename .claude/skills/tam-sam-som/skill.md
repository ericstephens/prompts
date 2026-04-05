---
name: tam-sam-som
description: Investor-ready TAM/SAM/SOM market sizing with dual methodology, explicit assumptions, and honest confidence ratings
user_invocable: true
---

# Skill: TAM / SAM / SOM Market Sizing

## Purpose
Produce a rigorous, defensible market sizing analysis — the kind that survives investor scrutiny, not the kind that inflates numbers to fill a pitch deck. Uses both top-down and bottom-up methodology, shows all math, and assigns confidence ratings with explicit weakest assumptions.

## Trigger Phrases
- "Size the market for [product]"
- "TAM SAM SOM for [product/company]"
- "Market sizing for [product]"
- "How big is the market for [product]?"
- "Investor market analysis for [company]"

---

## Instructions for Claude

### Parameters
Collect if not provided:
- **product** (required): The product or service to size the market for
- **market** (required): Target market, geography, or segment — e.g. "US enterprise SaaS", "European B2C fintech"
- **stage** (optional, default "early-stage startup"): pre-seed | seed | Series A | growth | established
- **time_horizon** (optional, default "current year + 5-year projection"): Projection period

If product and market are not provided, ask for them.

### Steps

1. **Define market boundaries.** State precisely what is and is not being counted. A vague market definition produces meaningless numbers.

2. **Calculate TAM (Total Addressable Market):**
   - **Top-down:** Start from the broadest credible industry figure, cite the source, and narrow by relevant filters. Show each step.
   - **Bottom-up:** Estimate number of potential customers × average revenue per customer. State unit economics explicitly.
   - **Reconcile:** If the two approaches diverge by more than 2×, explain why and state which is more trustworthy.

3. **Calculate SAM (Serviceable Addressable Market):**
   - Apply realistic constraints: which segments can this product serve today given its features, pricing, distribution, and GTM?
   - State each constraint and its impact on the number.

4. **Calculate SOM (Serviceable Obtainable Market):**
   - Given stage, current traction (if any), competitive landscape, and realistic capture rates, what revenue is achievable in 1–3 years?
   - Use comparable company benchmarks where available.

5. **Rate confidence.** For each estimate (TAM, SAM, SOM), assign: high / medium / low confidence, and name the weakest assumption.

### Rules
- Show all math explicitly — numbers, not narratives
- Cite sources for every external data point; if no reliable source exists, say so
- If the market is smaller than the founder likely believes, say so directly
- Do not round aggressively to make numbers look cleaner than they are
- For pre-seed/seed companies with no traction data, SOM is inherently speculative — provide a range, not a point estimate

### Output Format

```
## Market Definition
[2–4 sentences defining boundaries]

## TAM — Total Addressable Market
### Top-Down
[Step-by-step calculation with sources]
### Bottom-Up
[Unit economics calculation]
### Reconciliation
[Which estimate is more reliable and why]
**TAM Estimate:** $X | Confidence: [high/medium/low] | Weakest assumption: [...]

## SAM — Serviceable Addressable Market
[Constraints applied, with math]
**SAM Estimate:** $X | Confidence: [high/medium/low] | Weakest assumption: [...]

## SOM — Serviceable Obtainable Market
[Capture rate logic, comparable benchmarks]
**SOM Estimate:** $X (range: $X–$X) | Confidence: [high/medium/low] | Weakest assumption: [...]

## Key Assumptions & Risks
| # | Assumption | If Wrong, Impact |
|---|-----------|-----------------|
| 1 | ... | ... |

## Bottom Line
[1–2 sentences: Is this market big enough to matter? Honest read.]
```

## Quality Standards
- Both methodologies must be present and show explicit math
- Reconciliation must explain divergence if > 2×
- Every confidence rating must name a specific weakest assumption
- Bottom line must give a direct verdict — not "it depends"
