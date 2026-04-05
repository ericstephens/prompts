---
name: progression-map
description: Break any topic into 5 mastery levels from beginner to advanced with concrete milestones
user_invocable: true
---

# Skill: 5-Level Difficulty Progression Map

## Purpose
Break any topic into 5 clearly defined levels of mastery — from complete beginner (Level 1) to advanced practitioner (Level 5) — with concrete milestones at each step. Gives learners a roadmap so they always know where they are and what's next.

## Trigger Phrases
Use this skill when the user says things like:
- "Break [topic] into levels"
- "Show me how to go from beginner to advanced in [topic]"
- "What are the stages of learning [topic]?"
- "Level up my understanding of [topic]"
- "Progression map", "difficulty levels", "beginner to advanced"

---

## Instructions for Claude

When this skill is triggered, build a 5-level progression map using the structure below.

### Level Framework

Each level must include:
1. **Level Name & Label** — A descriptive title beyond just "beginner/intermediate/advanced"
2. **What You Know** — The knowledge and mental models at this stage
3. **What You Can Do** — Concrete, observable skills and outputs
4. **Milestone Check** — A specific test or project that confirms you've reached this level
5. **Common Mistakes** — What people at this level typically get wrong
6. **Time to Reach** — Rough honest estimate (ranges are fine)
7. **Next Step** — The one thing to focus on to move to the next level

---

### Output Template

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
LEVEL 1 — [Name] (Beginner)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
WHAT YOU KNOW:
[Core mental model / foundational understanding at this stage]

WHAT YOU CAN DO:
- [Skill 1]
- [Skill 2]
- [Skill 3]

✅ MILESTONE: [Specific achievable task that proves Level 1 mastery]
Example: "You can [do X] without looking anything up."

⚠️ COMMON MISTAKES: [2–3 traps beginners fall into]

⏱ TIME TO REACH: [Estimate — e.g., "5–10 hours of focused practice"]

➡️ TO REACH LEVEL 2: [The single most important next focus]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
LEVEL 2 — [Name] (Developing)
...
[Repeat for all 5 levels]
```

---

### Level Calibration Guide

| Level | Label | Rough Descriptor |
|-------|-------|-----------------|
| 1 | Beginner | No prior knowledge; needs hand-holding |
| 2 | Developing | Understands basics; makes frequent mistakes |
| 3 | Competent | Can work independently on standard tasks |
| 4 | Proficient | Handles edge cases; developing intuition |
| 5 | Advanced | Can teach others; innovates within the field |

---

## Quality Standards
- Milestones must be **verifiable** — not "understand X" but "build/produce/explain X"
- Time estimates should be honest, not flattering
- Common mistakes should be specific to that level, not generic advice
- The "To Reach Next Level" pointer should be singular and actionable — one thing, not a list
- Level 5 should note that mastery is an ongoing process, not a finish line

## Example Output Opener
> Here's your complete 5-level progression map for [topic]. Use the milestones to self-assess exactly where you are right now...
