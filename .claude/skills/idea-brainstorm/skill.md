---
name: idea-brainstorm
description: Generate original, diverse, and actionable ideas on any topic — quantity first, quality filtered
user_invocable: true
---

# Skill: Idea Brainstorm

## Purpose
Generate a broad, diverse set of ideas on any topic. Prioritizes originality and range — avoids converging too early on the obvious. Ends with a ranked short list and a single "bold bet" recommendation.

## Trigger Phrases
- "Brainstorm ideas for [topic]"
- "Give me ideas on [topic]"
- "What are some ways to [goal]?"
- "Help me think of approaches to [problem]"
- "Generate [N] ideas for [topic]"

---

## Instructions for Claude

### Parameters
Collect if not provided:
- **topic** (required): What to brainstorm — a problem, goal, product, question, scenario
- **count** (optional, default 10): Number of ideas to generate
- **constraints** (optional): Scope limits — e.g. "under $500", "no new hires", "B2B only", "implementable in one week"
- **style** (optional, default "mixed"): conventional | unconventional | mixed

If topic is not provided, ask for it. Default silently on all other parameters.

### Steps
1. Before generating, identify the *unstated* goal behind the topic — what success actually looks like.
2. Generate ideas in three passes:
   - **Obvious:** The standard approaches most people would suggest first
   - **Adjacent:** Slightly outside the norm — borrowing from other domains or flipping assumptions
   - **Wild:** Deliberately unconventional — at least 2 ideas that feel surprising or counterintuitive
3. For each idea: give it a one-line name and a 1–2 sentence explanation of how it works and why it could succeed.
4. Apply any constraints to filter or flag incompatible ideas.
5. Rank the full list by estimated impact × feasibility.
6. Select one "Bold Bet" — the idea with the highest upside that would be dismissed too quickly by most people.

### Rules
- No two ideas should rely on the same core mechanism.
- Avoid vague ideas ("improve communication", "invest in marketing") — every idea must be specific enough to act on.
- If a constraint rules out an otherwise great idea, include it anyway and flag it as "constraint-blocked."
- The bold bet must be genuinely surprising, not just the highest-ranked conventional idea.

### Output Format

```
## Brainstorm: [Topic]

### All Ideas

1. **[Name]** — [How it works and why it could succeed]
2. **[Name]** — [...]
...

### Ranked Short List (Top 3)
1. [Name] — [1-sentence rationale]
2. [Name] — [1-sentence rationale]
3. [Name] — [1-sentence rationale]

### Bold Bet
**[Name]:** [Why this deserves more serious consideration than most would give it]
```

No preamble. Start directly with `## Brainstorm:`.

## Quality Standards
- At least 20% of ideas must come from outside the obvious solution space
- Every idea must be specific enough to hand to someone for execution
- The bold bet must be distinct from all top-3 items
- If count > 10, maintain diversity — no padding with minor variations
