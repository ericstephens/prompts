---
name: swot-analysis
description: Run a SWOT analysis that produces specific strategic moves — not a box-filling exercise
user_invocable: true
---

# Skill: Actionable SWOT Analysis

## Purpose
Produce a SWOT analysis specific enough to change what a company or project does next week. Uses sharpened definitions focused on defensible moats, honest gaps, and named competitive threats. Ends with a cross-impact action matrix and a single prioritized recommendation.

## Trigger Phrases
- "SWOT analysis for [company/project]"
- "Run a SWOT on [subject]"
- "Help me think through the competitive position of [company]"
- "What are the strengths and weaknesses of [company]?"
- "Strategic analysis of [company]"

---

## Instructions for Claude

### Parameters
Collect if not provided:
- **company** (required): Company, business unit, product, or project to analyze
- **industry** (required): Industry or market context
- **competitors** (required): Top 2–4 direct competitors — if not provided, ask
- **time_horizon** (optional, default "12 months"): Planning horizon
- **context** (optional): Additional context — e.g. "preparing for fundraise", "entering new market", "post-acquisition"

If company, industry, or competitors are not provided, ask for them.

### Steps

Apply these sharpened definitions to each quadrant:

1. **Strengths — Defensible Moats:** What does this company do that competitors literally cannot replicate within the time horizon? Focus on structural moats: proprietary data, network effects, regulatory advantages, unique talent, switching costs. Reject vague claims like "great team" or "innovative culture" — name the specific mechanism.

2. **Weaknesses — Honest Gaps:** What is the specific reason a customer chooses a competitor over this company? Name the competitor and the reason. If there's an internal dysfunction competitors would exploit if they knew about it, name it.

3. **Opportunities — Time-Sensitive:** What market shift, technology change, regulatory development, or competitor misstep is happening right now that the company is not yet exploiting? Cite the trend and explain the window.

4. **Threats — Named Scenarios:** What specific, plausible scenario could seriously damage the company within the time horizon? Name the competitor, the move, and the mechanism of harm. Include at least one non-obvious threat.

**Specificity test:** For every bullet, ask "could I swap in a competitor's name and have this still apply?" If yes, it's too generic — rewrite it.

5. **Cross-Impact Action Matrix:**
   - **Strengths × Opportunities → Attack moves:** How can existing advantages capture identified opportunities? Name 2–3 concrete initiatives.
   - **Weaknesses × Threats → Survival moves:** What must be done to prevent worst-case scenarios from exploiting known vulnerabilities? Name 2–3 concrete initiatives.

6. **Priority call:** "If this company could only do ONE thing this quarter, it should be ___." Defend in 2–3 sentences.

### Rules
- Every bullet must be specific to this company — if a competitor's name could replace it unchanged, rewrite it
- Name competitors by name, customers by segment, trends by name or date
- If you lack information to make a quadrant specific, state what information would be needed rather than filling with generics
- No vague strategic language ("leverage synergies", "drive growth") — name the mechanism

### Output Format

```
## SWOT: [Company]

### Strengths (Defensible Moats)
- [Specific advantage] — *why it's hard to copy within [time_horizon]*

### Weaknesses (Honest Gaps)
- [Specific reason customers choose [competitor]] — *evidence or mechanism*

### Opportunities (Time-Sensitive)
- [Specific shift] — *window and why now*

### Threats (Named Scenarios)
- [Competitor] + [move] + [mechanism of harm] — *timeline*

## Action Matrix

### Attack Moves (Strengths × Opportunities)
1. [Concrete initiative]
2. [Concrete initiative]

### Survival Moves (Weaknesses × Threats)
1. [Concrete initiative]
2. [Concrete initiative]

## The One Thing
> If [company] could only do ONE thing this quarter, it should be: **[recommendation]**
>
> [2–3 sentence defense]
```

## Quality Standards
- Each quadrant must have at least 3 items
- No item should survive the specificity test unchallenged
- Action matrix must connect to specific SWOT items, not be generic advice
- The One Thing must be defended — not just stated
