---
skill_id: 052
name: Actionable SWOT Analysis
version: 1.0
category: strategy
tags: [SWOT, competitive-analysis, strategy, positioning, decision-making]
description: Run a SWOT analysis that produces specific strategic moves — not a box-filling exercise.
compatible_models: [Claude 4/4.5, GPT-4o, Grok-2, Gemini 1.5 Pro]
last_updated: 2026-03-28
change_log:
  - 1.0 (2026-03-28) — Initial version
---

# Skill: Actionable SWOT Analysis
**Version:** 1.0
**Short Description:** Produce a SWOT analysis designed to drive decisions — with moat-focused strengths, honest weaknesses, a cross-impact action matrix, and a single prioritized recommendation.

## Parameters
- `{company}`       : Company or business unit to analyze (required)
- `{industry}`      : Industry or market context (required)
- `{competitors}`   : Top 2–4 direct competitors (required)
- `{time_horizon}`  : Planning horizon — e.g. "next quarter", "12 months", "3 years" (optional, default: 12 months)
- `{context}`       : Additional context — e.g. "preparing for fundraise", "entering new market", "post-acquisition integration" (optional)

## Core Prompt

You are a competitive strategist advising a leadership team. Your job is to produce a SWOT analysis that is specific enough to change what the company does next week — not a generic matrix that could apply to any company in the industry.

**Company:** {company}
**Industry:** {industry}
**Competitors:** {competitors}
**Time Horizon:** {time_horizon}
**Additional Context:** {context}

For each quadrant, apply these sharpened definitions:

1. **Strengths:** What does {company} do that {competitors} literally cannot replicate within {time_horizon}? Focus on structural moats (proprietary data, network effects, regulatory advantages, unique talent, switching costs) — not vague claims like "great team" or "innovative culture."

2. **Weaknesses:** What is the honest, specific reason a customer chooses a competitor over {company}? Name the competitor and the reason. If there's an internal dysfunction that competitors would exploit if they knew about it, name that too.

3. **Opportunities:** What market shift, technology change, regulatory development, or competitor misstep is happening right now that {company} is not yet exploiting? Be specific — cite the trend and explain the window of opportunity.

4. **Threats:** What specific, plausible scenario could seriously damage {company} within {time_horizon}? Not generic "competition increases" — name the competitor, the move, and the mechanism of harm. Include at least one non-obvious threat.

Then produce the cross-impact action matrix:

5. **Strengths × Opportunities → Attack moves:** How can existing advantages be used to capture the identified opportunities? Name 2–3 concrete initiatives.

6. **Weaknesses × Threats → Survival moves:** What must be done to prevent the worst-case scenarios from exploiting known vulnerabilities? Name 2–3 concrete initiatives.

7. **Priority call:** "If {company} could only do ONE thing this quarter, it should be ___." Defend the recommendation in 2–3 sentences.

Rules:
- Every bullet must be specific to {company} — if you could swap in a competitor's name and the statement still works, it's too generic. Rewrite it.
- Name competitors by name. Name customers by segment. Name trends by name or date.
- If you lack information to make a quadrant specific, say what information you would need rather than filling it with generics.

Output in this exact format:

## SWOT: {company}

### Strengths (Defensible Moats)
- [Specific, non-replicable advantage] — *why it's hard to copy*
- ...

### Weaknesses (Honest Gaps)
- [Specific reason customers choose {competitor}] — *evidence or mechanism*
- ...

### Opportunities (Time-Sensitive)
- [Specific shift] — *window and why now*
- ...

### Threats (Named Scenarios)
- [Competitor + move + mechanism of harm] — *timeline*
- ...

## Action Matrix

### Attack Moves (Strengths × Opportunities)
1. ...
2. ...

### Survival Moves (Weaknesses × Threats)
1. ...
2. ...

## The One Thing
> If {company} could only do ONE thing this quarter, it should be: **[recommendation]**
>
> [2–3 sentence defense]

---

## Notes / Tips / Variations
- The specificity test ("could you swap in a competitor's name?") is the key quality control. Without it, models default to generic strategy-speak.
- For startups with limited competitive data, add: "If you cannot identify specific competitor moves, state the most likely competitive response to {company}'s current trajectory."
- For internal-facing use, add a fifth quadrant: "**Internal Friction:** What process, cultural, or organizational issue is silently slowing execution?"
- Pair with **053** (Market Entry Feasibility) if one of the opportunities involves entering a new market.
