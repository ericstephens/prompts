---
skill_id: 062
name: Fast Learning Plan (20-Hour Pareto)
version: 1.0
category: learning
tags: [learning, study-plan, pareto, accelerated-learning, curriculum, structured]
description: Generate a focused 20-hour learning plan using the Pareto principle — 10 structured sessions targeting the 20% of concepts that drive 80% of results.
compatible_models: [Claude 4/4.5, GPT-4o, Grok-2, Gemini 1.5 Pro — any model with strong reasoning and web/retrieval access]
last_updated: 2026-04-03
change_log:
  - 1.0 (2026-04-03) — Initial version; adapted from inbox draft
---

# Skill: Fast Learning Plan (20-Hour Pareto)
**Version:** 1.0
**Short Description:** Generate a focused, high-efficiency 20-hour learning plan for any topic using the Pareto principle — identifying the 20% of concepts that drive 80% of real-world results. Breaks learning into 10 structured two-hour sessions with curated resources and built-in review blocks.

## Parameters (replace these placeholders in your copy)
- `{topic}`               : The subject to build a learning plan for (required)
- `{learner_level}`       : Current knowledge level — e.g. "complete beginner", "some basics", "intermediate refresher" (optional, default: complete beginner)
- `{learning_goal}`       : What the learner wants to be able to do after 20 hours — e.g. "build a basic web app", "hold a conversation in Spanish", "understand financial statements" (optional, default: practical working competence)
- `{preferred_formats}`   : Preferred learning formats — e.g. "books and articles", "video courses", "hands-on projects", "mixed" (optional, default: mixed)
- `{time_per_session}`    : Hours per session (optional, default: 2)

## Core Prompt (copy-paste this block into any LLM chat)

You are an expert learning designer who specializes in accelerated skill acquisition. Your task is to create a focused learning plan that maximizes results in minimal time by applying the Pareto principle — identify the 20% of concepts that deliver 80% of practical results, and structure learning around those.

**Topic:** {topic}
**Learner level:** {learner_level}
**Learning goal:** {learning_goal}
**Preferred formats:** {preferred_formats}
**Session length:** {time_per_session} hours

Follow these steps exactly:

### Step 1 — Identify the Core 20%

Before building sessions, identify the highest-leverage concepts in {topic}:
- What knowledge unlocks everything else?
- What do practitioners actually use day-to-day vs. what is theoretical overhead?
- What misconceptions or rabbit holes should be avoided early on?

Present this as a brief "Pareto Analysis" section (5–8 bullet points).

### Step 2 — Build 10 Sessions

Structure each session as follows:

```
SESSION [N]: [Session Title]
Duration: {time_per_session} hours ([time minus 15min] learning + 15m review)

FOCUS: [One clear learning objective]

CORE CONCEPTS:
- [Concept 1]
- [Concept 2]
- [Concept 3]

BEST RESOURCES:
- [Primary resource — book chapter / video / article with specific title and author]
- [Secondary resource — alternative format]
- [Optional stretch resource for depth]

HANDS-ON TASK:
[A concrete 15–20 minute activity to apply what was learned]

15-MINUTE REVIEW:
- Summarize the session in 3 bullet points from memory
- Answer: What was the single most important thing I learned?
- Flag: What am I still confused about? (carry to next session)
```

### Step 3 — Add a Progress Tracker

After all 10 sessions, include a tracker table:

| Session | Topic | Completed? | Confidence (1–5) |
|---------|-------|------------|-------------------|
| 1       | ...   |            |                   |
| ...     | ...   |            |                   |
| 10      | ...   |            |                   |

### Step 4 — End with "What's Next"

After the plan, include:
- What the learner should be capable of doing after all 10 sessions
- What the next logical 20 hours would cover for deeper mastery

Rules you must obey:
- Sessions must build on each other — no random ordering
- Resources must be specific — include titles, authors, chapter numbers, or URLs. No vague "search YouTube for videos on this."
- Each session should be completable in exactly {time_per_session} hours by a motivated learner at {learner_level}
- Avoid jargon in session titles — keep them outcome-oriented
- The 15-minute review must be actionable, not just "review your notes"
- If recommending paid resources, flag the cost
- Prioritize free and widely accessible resources where quality is comparable

Output **only** in the format above — no preamble, no meta-commentary.

## Notes / Tips / Variations
- **Strong on:** Claude 4/4.5 (excellent at structuring curricula and identifying high-leverage concepts), GPT-4o with web access (can find specific resources)
- **Weak on:** Models without web access may recommend outdated or non-existent resources — verify links manually
- **Common tweaks:**
  - Want a shorter plan? Change to 5 sessions of {time_per_session} hours for a 10-hour sprint
  - Want daily structure? Add: "Label each session as Day 1, Day 2, etc. and note that sessions should be spaced at least 24 hours apart for retention."
  - Career-focused? Add: "For each session, note which skills are most valued by employers and which are portfolio-worthy."
- **Chaining:** Pairs well with **064** (find the best resources before building the plan), **065** (map progression levels to calibrate session difficulty), or **063** (quiz after completing a session block)
