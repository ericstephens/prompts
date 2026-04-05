---
name: top-resources
description: Identify and rank the 5 highest-value resources for learning any topic
user_invocable: true
---

# Skill: Top 5 Learning Resources Finder

## Purpose
Identify and rank the 5 highest-value resources (books, videos, courses, people, or communities) for learning any topic quickly. Each recommendation must include a clear justification for why it's worth the learner's time — not just what it is.

## Trigger Phrases
Use this skill when the user says things like:
- "List the best resources for learning [topic]"
- "What should I read/watch/take to learn [topic] fast?"
- "Top books/courses/videos for [topic]"
- "Who should I follow to learn [topic]?"
- "What's worth my time for [topic]?"

---

## Instructions for Claude

### Step 1 — Assess the Learner's Context
Before listing resources, briefly consider (and ask if not clear):
- Is the learner a complete beginner, or do they have some background?
- Are they learning for practical application, career advancement, or curiosity?
- Do they prefer reading, watching, or doing?

If unclear, make a reasonable assumption and state it explicitly at the top of the response.

### Step 2 — Select 5 Resources Across Diverse Formats

Aim for variety across these categories (don't use 5 books or 5 YouTube channels):
- 📘 **Book or long-form text** — foundational, deep understanding
- 🎥 **Video or course** — structured, visual, interactive
- 🎙️ **Podcast or interview** — passive learning, real-world context
- 👤 **Person to follow** — practitioner with ongoing insights
- 🛠️ **Project, tool, or community** — learn by doing or with others

Adjust categories based on what exists for the specific topic.

### Step 3 — Format Each Resource

```
#[N] — [Resource Title / Name]
Type: [Book / Course / YouTube Channel / Podcast / Person / Community / Tool]
Where to find it: [URL, platform, or publisher]

WHY IT'S WORTH YOUR TIME:
[2–4 sentences explaining the unique value of this resource. What does it do 
that others don't? Who specifically benefits most from it? What will the 
learner be able to do after engaging with it?]

BEST FOR: [Beginner / Intermediate / Advanced — and why]

HOW TO USE IT:
[Specific advice — e.g., "Read chapters 1–4 first, skip Part 3 unless you 
need depth on X", or "Watch the first 3 videos, then pause and practice"]

TIME INVESTMENT: [Realistic estimate — e.g., "6–8 hours for the core content"]
```

---

### Step 4 — Add a Quick-Start Recommendation

After the 5 resources, add:

```
━━━━━━━━━━━━━━━━━━━━━━━━━
🚀 WHERE TO START RIGHT NOW
━━━━━━━━━━━━━━━━━━━━━━━━━
If you only have 2 hours today, start with [Resource #X] because [one-sentence reason].
Your goal for today: [specific, completable micro-task]
```

---

## Quality Standards
- Never recommend a resource you're uncertain about — note if something may be outdated
- Justify each pick based on **unique value**, not just popularity
- "Why it's worth your time" must go beyond a summary — it must speak to the learner's outcome
- Avoid recommending paywalled resources without flagging the cost
- If a topic is niche or fast-moving, note that resources may be limited and suggest communities or primary sources instead

## Example Output Opener
> Here are the 5 resources I'd recommend for learning [topic] fast — selected for variety of format and maximum practical impact...
