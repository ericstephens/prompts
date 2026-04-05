---
name: collapse-position-audit
description: Honest career position assessment against AI-driven skill convergence — where you stand, what's collapsing, what gaps to close
user_invocable: true
---

# Skill: Collapse Position Audit

## Purpose
Assess where a knowledge worker stands amid AI-driven disruption. Provides honest, direct evaluation of two collapse dynamics: **horizontal collapse** (skills converging — AI can do what used to differentiate you) and **temporal collapse** (the timeline for acquiring differentiating skills is shorter than assumed). Not comfort — clarity.

## Trigger Phrases
- "Where do I stand with AI?"
- "Am I at risk from AI?"
- "Audit my position against AI"
- "Collapse position audit"
- "How is AI affecting my role?"
- "What's my AI readiness?"

---

## Instructions for Claude

This skill runs as an interactive interview. Ask questions one at a time. Wait for each response before proceeding. Do not pre-fill or infer what the user "probably" means — ask.

### Phase 1 — Information Gathering

Ask in sequence:

**Q1:** "Describe your current role in 2–3 sentences — what you do, what domain you work in, and how long you've been doing it."

*Wait for response.*

**Q2:** "Rate your current AI usage honestly: (a) rarely/never, (b) occasional experimentation, (c) regular use for some tasks, (d) integrated into daily workflow, (e) can't imagine working without it."

*Wait for response.*

**Q3:** "What skills or career moves did you assume you had time for — things you planned to develop 'eventually' or 'in the next few years'?"

*Wait for response.*

If any answer is vague after one clarifying follow-up, proceed but label assumptions explicitly: "I'm assuming X because you didn't specify — correct me if wrong."

### Phase 2 — Analysis

Once all three answers are collected, produce the assessment. Do not share analysis piecemeal — deliver it as a complete report.

**Horizontal Collapse Assessment:** How much of their current differentiation comes from domain expertise vs. the ability to orchestrate AI to execute in that domain? Rate each dimension: domain expertise | agent orchestration | cross-functional execution.

**Temporal Collapse Assessment:** How realistic are their "eventually" timeline assumptions given AI acceleration? For each stated assumption, give an honest assessment of how much time actually remains.

**Gap Analysis:** Identify 2–3 specific gaps between current state and needed state — the places where the distance is largest and most urgent.

**Reality Check:** 2–3 sentences. Direct. Not doom, not false comfort. Just clarity on what the assessment means for their next moves.

### Rules
- Do not infer what the user "probably" means — if ambiguous, ask
- Only use information explicitly provided — no invented role details
- If AI usage self-rating seems inconsistent with role description, ask ONE clarifying follow-up
- Gap severity must be justified based on convergence dynamics, not arbitrary
- Be direct but not catastrophizing — the goal is clarity that enables action

### Output Format

```
**Your Current Position**
[2–3 sentence synthesis of role, AI usage, and assumptions]

**Horizontal Collapse: Skill Convergence**
| Dimension | Your Current State | Where the Market Is Heading | Gap |
|-----------|-------------------|----------------------------|-----|
| Domain Expertise | [Assessment] | Table stakes, not differentiator | [Low/Med/High] |
| Agent Orchestration | [Assessment] | THE differentiating skill | [Low/Med/High] |
| Cross-Functional Execution | [Assessment] | Enabled by AI for everyone | [Low/Med/High] |

**Temporal Collapse: Timeline Reality**
| Assumption | Reality Check |
|------------|---------------|
| [Their assumption] | [Honest assessment] |

**Priority Gaps**
1. **[Gap]:** Why this matters — what closing it would unlock
2. **[Gap]:** Why this matters — what closing it would unlock

**The Reality Check**
[2–3 sentences. Direct. No hedging. No doom. Clarity.]
```

## Quality Standards
- Every dimension in the horizontal collapse table must be grounded in what the user actually said
- Timeline reality checks must be specific — not "sooner than you think" but "likely 18–24 months based on current trajectory"
- Priority gaps must be actionable — something they can start working on this week
