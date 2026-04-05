---
name: fast-learning
description: Generate a focused 20-hour learning plan for any topic using the Pareto principle
user_invocable: true
---

# Skill: Fast Learning Plan (20-Hour Pareto Method)

## Purpose
Generate a focused, high-efficiency 20-hour learning plan for any topic using the Pareto principle — identifying the 20% of concepts that drive 80% of real-world results. Breaks learning into 10 structured two-hour sessions, each with curated resources and a built-in 15-minute review block.

## Trigger Phrases
Use this skill when the user says things like:
- "I need to learn [topic] fast"
- "Build me a learning plan for [topic]"
- "20-hour plan", "Pareto learning", "focused study plan"
- "What should I study first to get results quickly in [topic]?"

---

## Instructions for Claude

When this skill is triggered, do the following:

### Step 1 — Identify the Core 20%
Before building sessions, identify the highest-leverage concepts in the topic:
- What knowledge unlocks everything else?
- What do practitioners actually use day-to-day vs. what is theoretical overhead?
- What misconceptions or rabbit holes should be avoided early on?

### Step 2 — Build 10 Two-Hour Sessions

Structure each session as follows:

```
SESSION [N]: [Session Title]
Duration: 2 hours (1h 45m learning + 15m review)

FOCUS: [One clear learning objective]

CORE CONCEPTS:
- [Concept 1]
- [Concept 2]
- [Concept 3]

BEST RESOURCES:
- [Primary resource — book chapter / video / article with specific link or title]
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
After all 10 sessions, include a simple tracker table:

| Session | Topic | Completed? | Confidence (1–5) |
|---------|-------|------------|------------------|
| 1 | ... | ☐ | |
| 2 | ... | ☐ | |
...

### Step 4 — End with a "What's Next" Note
After completing all 20 hours, tell the learner:
- What they should now be capable of doing
- What the next logical 20 hours would cover if they want to go deeper

---

## Quality Standards
- Sessions must build on each other — no random ordering
- Resources must be specific (no vague "search YouTube for videos on this")
- Each session should be completable in exactly 2 hours by a motivated beginner
- Avoid jargon in session titles — keep them outcome-oriented
- The 15-minute review must be actionable, not just "review your notes"

## Example Output Opener
> Here's your 20-hour accelerated learning plan for [topic], built around the 20% of concepts that deliver 80% of practical results...
