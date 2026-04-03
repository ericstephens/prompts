---
skill_id: 065
name: Level Progression Map
version: 1.0
category: learning
tags: [learning, progression, mastery, roadmap, milestones, self-assessment]
description: Break any topic into 5 clearly defined mastery levels — from beginner to advanced — with concrete milestones, common mistakes, and time estimates at each stage.
compatible_models: [Claude 4/4.5, GPT-4o, Grok-2, Gemini 1.5 Pro — any model with strong reasoning]
last_updated: 2026-04-03
change_log:
  - 1.0 (2026-04-03) — Initial version; adapted from inbox draft
---

# Skill: Level Progression Map
**Version:** 1.0
**Short Description:** Break any topic into 5 clearly defined levels of mastery — from complete beginner to advanced practitioner — with concrete milestones, common mistakes, time estimates, and clear next steps at each stage.

## Parameters (replace these placeholders in your copy)
- `{topic}`               : The subject to map progression levels for (required)
- `{num_levels}`          : Number of progression levels (optional, default: 5)
- `{domain_context}`      : Specific application area — e.g. "for web development", "for academic research", "for personal projects" (optional, default: general)
- `{include_resources}`   : Whether to include 1–2 recommended resources per level — "yes" or "no" (optional, default: no)

## Core Prompt (copy-paste this block into any LLM chat)

You are an expert curriculum designer and domain specialist. Your task is to create a clear, honest progression map that shows a learner exactly where they are in their journey and what it takes to reach the next level. This is a self-assessment and planning tool — not a course.

**Topic:** {topic}
**Number of levels:** {num_levels}
**Domain context:** {domain_context}
**Include resources:** {include_resources}

Follow these steps exactly:

### Step 1 — Build the Progression Map

For each of the {num_levels} levels, provide:

```
LEVEL [N] — [Descriptive Name] ([Label])

WHAT YOU KNOW:
[The mental models, concepts, and understanding at this stage — 3–5 bullet points]

WHAT YOU CAN DO:
- [Observable skill 1]
- [Observable skill 2]
- [Observable skill 3]

MILESTONE: [A specific, verifiable task or project that proves this level is reached]
Example: "You can [do X] without looking anything up."

COMMON MISTAKES: [2–3 specific traps people at this level fall into]

TIME TO REACH: [Honest estimate from previous level — e.g., "10–20 hours of focused practice"]

TO REACH LEVEL [N+1]: [The single most important thing to focus on next]
```

If {include_resources} is "yes", add after each level:
```
RECOMMENDED RESOURCES:
- [Resource 1 — title, author/platform, why it's right for this level]
- [Resource 2 — title, author/platform, why it's right for this level]
```

### Step 2 — Level Calibration Summary

After all levels, include a quick-reference table:

| Level | Name | Label | Key Milestone | Time from Zero |
|-------|------|-------|---------------|----------------|
| 1     | ...  | ...   | ...           | ...            |
| ...   | ...  | ...   | ...           | ...            |

### Step 3 — Self-Assessment Prompt

End with:

```
WHERE ARE YOU NOW?
Read the milestones above. The highest level where you can honestly complete
the milestone — that's your current level. Start your next learning session
focused on the "To Reach Level [N+1]" guidance from that level.
```

Use these default labels (adjust if {num_levels} differs from 5):

| Level | Label       | Rough Descriptor                              |
|-------|-------------|-----------------------------------------------|
| 1     | Beginner    | No prior knowledge; needs hand-holding        |
| 2     | Developing  | Understands basics; makes frequent mistakes   |
| 3     | Competent   | Can work independently on standard tasks      |
| 4     | Proficient  | Handles edge cases; developing intuition      |
| 5     | Advanced    | Can teach others; innovates within the field  |

Rules you must obey:
- Milestones must be verifiable — not "understand X" but "build/produce/explain X"
- Time estimates should be honest, not flattering — include ranges
- Common mistakes should be specific to that level, not generic advice
- The "To Reach Next Level" pointer should be singular and actionable — one thing, not a list
- Level {num_levels} should note that mastery is an ongoing process, not a finish line
- Each level must be meaningfully distinct from adjacent levels — no filler levels

Output **only** in the format above — no preamble, no meta-commentary.

## Notes / Tips / Variations
- **Strong on:** Claude 4/4.5 (excellent at calibrating difficulty and being honest about time estimates), GPT-4o (strong at generating specific milestones)
- **Common tweaks:**
  - Want more granularity? Set {num_levels} to 7 or 10 for a more gradual curve
  - Want career alignment? Add: "For each level, note which job titles or roles typically require this level of competence."
  - Want it visual? Add: "After the table, describe a simple ASCII skill tree showing how concepts build on each other."
- **Chaining:** Pairs well with **062** (build a learning plan targeting a specific level transition), **063** (quiz to validate current level), **064** (find resources matched to the learner's current level), or **061** (Feynman loop on concepts needed for the next level)
