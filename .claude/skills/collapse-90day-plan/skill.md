---
name: collapse-90day-plan
description: 90-day AI skill-building plan that compounds — fully detailed Phase 1, directional Phases 2–3, designed for knowledge workers closing the AI gap
user_invocable: true
---

# Skill: 90-Day AI Engagement Accelerator

## Purpose
Design a phased, compounding 90-day plan for building AI skills. Phase 1 is fully specific (tools, tasks, time blocks). Phases 2–3 are directional themes with checkpoint criteria — the user re-runs the skill at each checkpoint to generate the next phase's specifics. Momentum matters more than perfection.

## Trigger Phrases
- "Build me a 90-day AI plan"
- "90-day engagement accelerator"
- "How do I build AI skills in 90 days?"
- "Create an AI learning plan for me"
- "Help me get better at AI in the next 3 months"

---

## Instructions for Claude

This skill runs as an interactive interview before generating the plan. Ask questions one at a time. Wait for each response. Do not generate the plan until all three inputs are collected.

### Phase 1 — Information Gathering

**Q1:** "What's your current AI usage baseline? If you've done the Collapse Position Audit, share that output. Otherwise, describe your current AI usage level and biggest gaps in 3–4 sentences."

*Wait for response.*

**Q2:** "How many hours per week can you realistically dedicate to AI skill-building? Not aspirational — realistic."

*Wait for response.*

**Q3:** "What do you most want to be able to do with AI in 90 days? What would make this investment feel worth it?"

*Wait for response.*

If any answer is vague after one clarifying follow-up, proceed but label assumptions explicitly.

### Phase 2 — Plan Generation

Once all three inputs are collected:

1. If the 90-day target seems unrealistic given baseline and available time, say so directly and propose an adjusted target.
2. Design Phase 1 (weeks 1–4) with full specificity: specific tools, specific tasks, specific time blocks.
3. Design Phases 2 and 3 as directional themes with checkpoint criteria — NOT detailed weekly plans.
4. Include a recovery plan.

**Phase 1 design rules:**
- Time allocations must fit within stated availability — no 10-hour/week plan for someone with 3 hours
- Experiments must be specific enough to execute without further research — name the tool, name the task, describe the expected output
- Each week builds on the previous — no random hops between unrelated tools

**Phases 2–3 rules:**
- Directional, not detailed — the user re-runs this skill at weeks 5 and 9 to generate specifics
- Checkpoint criteria must be yes/no questions, not subjective assessments

### Rules
- Do not infer what the user "probably" means — ask
- Only use information explicitly provided — no invented tools, budget assumptions, or workplace constraints
- If the target is unrealistic, say so with a specific reason before proposing an adjustment
- Phase 1 experiments must be immediately executable

### Output Format

```
**Starting Point**
[2–3 sentence summary of their baseline and constraints]

**90-Day Target**
[1–2 sentences: what they'll be able to do at the end. If adjusted, explain why in one sentence.]

---

**Phase 1: Foundation (Weeks 1–4)**

*Theme:* [Core focus]

| Week | Focus | Experiment to Run | Time |
|------|-------|------------------|------|
| 1 | [Focus] | [Specific tool + specific task] | [X hrs] |
| 2 | [Focus] | [Specific tool + specific task] | [X hrs] |
| 3 | [Focus] | [Specific tool + specific task] | [X hrs] |
| 4 | [Focus] | [Specific tool + specific task] | [X hrs] |

**Week 4 Checkpoint:** [3–4 yes/no questions. If you answer "no" to more than one, repeat the relevant week before proceeding.]

---

**Phase 2: Expansion (Weeks 5–8)**

*Theme:* [What this phase builds toward]

*Direction:* [2–3 sentences — building on Phase 1, expanding to new workflows]

*Checkpoint criteria:* [3–4 yes/no questions. Re-run this skill at week 8 to generate Phase 3's specific plan.]

---

**Phase 3: Integration (Weeks 9–12)**

*Theme:* [What this phase builds toward]

*Direction:* [2–3 sentences — AI as default workflow, not separate activity]

*Final checkpoint:* [3–4 yes/no questions that tell you whether you hit the 90-day target]

---

**If You Fall Behind**
[2–3 sentences: which weeks are non-negotiable vs. which can compress. What to do if you miss a full week.]
```

## Quality Standards
- Phase 1 must have a specific tool and task for every week
- Time budget must match stated availability — no phantom hours
- Checkpoint criteria must be binary (yes/no), not subjective
- Recovery plan must be specific, not "just pick back up where you left off"
