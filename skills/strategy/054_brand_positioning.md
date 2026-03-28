---
skill_id: 054
name: Brand Positioning Statement
version: 1.0
category: strategy
tags: [positioning, brand, messaging, differentiation, go-to-market, marketing]
description: Generate differentiated brand positioning statements using a structured framework — with scoring, one-liner variants, and a final recommendation.
compatible_models: [Claude 4/4.5, GPT-4o, Grok-2, Gemini 1.5 Pro]
last_updated: 2026-03-28
change_log:
  - 1.0 (2026-03-28) — Initial version
---

# Skill: Brand Positioning Statement
**Version:** 1.0
**Short Description:** Produce 3 positioning statement options with differentiation scoring, pitfall analysis, and a short-form variant for each — then recommend the strongest.

## Parameters
- `{product}`           : The product or service to position (required)
- `{target_customer}`   : Specific target customer — role, company size, pain point (required)
- `{competitors}`       : Top 2–3 direct competitors (required)
- `{differentiator}`    : The core unfair advantage or unique value (required)
- `{tone}`              : Brand voice — e.g. "professional", "bold", "technical", "approachable" (optional, default: professional)

## Core Prompt

You are a brand strategist specializing in competitive positioning. Your job is to produce positioning statements that pass the substitution test: if you can swap in a competitor's name and the statement still works, it's not positioning — it's filler.

**Product:** {product}
**Target Customer:** {target_customer}
**Competitors:** {competitors}
**Core Differentiator:** {differentiator}
**Brand Tone:** {tone}

Follow these steps:

1. **Analyze the competitive positioning landscape.** In 3–5 sentences: What do {competitors} each claim? Where is there whitespace — a positioning angle that no competitor owns?

2. **Generate 3 positioning statement options** using this framework:

   > For **[target customer]** who **[need or pain point]**, **[product]** is the **[category]** that **[key benefit]**, unlike **[competitor/alternative]**, because **[reason to believe]**.

   Each option should take a different strategic angle on {differentiator} — don't generate three minor variations of the same idea.

3. **Score each option** on three dimensions (1–10):
   - **Clarity:** Can a stranger understand what this product does in one read?
   - **Differentiation:** Does this claim something no competitor can honestly claim?
   - **Believability:** Would a skeptical customer find this credible without further proof?

4. **For each option, provide:**
   - The messaging pitfall it avoids (e.g. "avoids feature-stuffing", "avoids category confusion")
   - A one-liner version (under 10 words) suitable for a homepage headline

5. **Recommend one.** State which you would bet on and why — referencing the scores and the competitive whitespace analysis.

Rules:
- No "we're the leading platform for..." — self-proclaimed leadership is not positioning.
- No "AI-powered" or "next-generation" unless {differentiator} specifically justifies it — these are noise words.
- Every statement must name or clearly imply {competitors} as the alternative. Positioning only exists relative to alternatives.
- Match the {tone} in word choice and register.

Output in this exact format:

## Competitive Landscape
[3–5 sentences on competitor positioning and whitespace]

## Option 1: [Strategic Angle Name]
**Statement:** For [target customer] who [need], [product] is the [category] that [benefit], unlike [competitor], because [reason to believe].

| Clarity | Differentiation | Believability | Avg |
|:---:|:---:|:---:|:---:|
| X | X | X | X.X |

**Avoids:** [pitfall]
**One-liner:** [≤10 words]

## Option 2: [Strategic Angle Name]
[Same structure]

## Option 3: [Strategic Angle Name]
[Same structure]

## Recommendation
**Go with Option X: [name]**
[3–4 sentences: why this wins, referencing scores and competitive whitespace]

---

## Notes / Tips / Variations
- The substitution test ("swap in a competitor's name") is the single most effective quality filter for positioning. Keep it.
- For B2B products, the `{target_customer}` should include a job title and a buying trigger, not just a demographic — e.g. "VP Engineering at a Series B startup whose CI pipeline takes >45 minutes" rather than "engineering leaders."
- To generate taglines rather than positioning statements, change the framework to: "In [X] words or fewer, complete: '[Product] — ...'" and request 10 options ranked by memorability.
- Pair with **055** (Demand Validation) to test whether the positioning resonates with actual buyer intent.
