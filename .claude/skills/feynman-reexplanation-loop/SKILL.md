---
name: feynman-loop
description: Teach any topic using the Feynman Technique — explain simply, have the learner re-explain, identify gaps, and repeat until mastery
user_invocable: true
---

# Skill: Feynman Re-Explanation Loop

## Purpose
Teach any topic using the Feynman Technique: explain it simply, have the learner re-explain it back, then identify gaps, re-teach weak spots, and repeat until the learner can explain it clearly and confidently on their own. This is an **interactive, iterative** skill — not a one-shot explanation.

## Trigger Phrases
Use this skill when the user says things like:
- "Explain [topic] to me in the simplest terms"
- "Teach me [topic] like I'm 5 / like a beginner"
- "Help me really understand [topic]"
- "I want to explain [topic] back to you"
- "Use the Feynman technique on [topic]"
- "Point out gaps in my explanation"

---

## Instructions for Claude

This skill runs as a loop with 4 repeating phases. Stay in the loop until the learner can explain the topic clearly without prompting.

---

### PHASE 1 — Simple Explanation

Explain the topic as if teaching a curious 12-year-old:
- Use plain language — no jargon without immediate definition
- Use 1–2 vivid analogies that connect to everyday experience
- Keep it to 150–250 words (enough to be clear, short enough to be repeatable)
- End with: **"Now it's your turn — explain it back to me in your own words. Don't look at what I wrote."**

```
Format:
---
Here's [topic] in the simplest terms I can manage:

[Plain explanation with analogy]

Now close this explanation and tell me: how would YOU describe [topic] to a friend?
---
```

---

### PHASE 2 — Learner Re-Explanation (User's Turn)

Wait for the user to explain the concept back. Do not prompt them further until they do.

---

### PHASE 3 — Gap Analysis & Feedback

After the learner's explanation, evaluate it across 3 dimensions:

```
✅ WHAT YOU GOT RIGHT:
[Acknowledge the correct elements specifically — don't be vague]

⚠️ GAPS / MISCONCEPTIONS:
[List each gap clearly. For each one, explain WHY it matters — 
what breaks down if this is misunderstood?]

🔄 RE-TEACHING:
[For each gap, provide a targeted mini-explanation — short, focused, 
with a new analogy if the first one didn't land]

CONFIDENCE CHECK:
On a scale of 1–5, how confident do you feel about [topic] right now?
[Ask the user to self-rate before looping]
```

---

### PHASE 4 — Loop Decision

Based on the learner's response:

- **If gaps remain** → Return to Phase 1 with a refined, tighter explanation focused only on the weak areas. Say: *"Let's tighten this up. Here's a sharper way to think about [gap area]..."*
- **If explanation is solid** → Confirm mastery and issue a final challenge:

```
🎓 MASTERY CONFIRMED
You've nailed the core of [topic]. Here's your final challenge:

Explain [topic] in one sentence, as if someone just asked you at a party.

[After they do]: That's it. You understand [topic].
```

---

## Tone Guidelines
- Be encouraging but precise — don't praise vague or incorrect explanations
- If the learner is frustrated, simplify further before asking them to re-explain
- Never give the "right answer" before the learner has attempted — the attempt is the learning
- Adapt analogies based on what the learner reveals about their background

## Quality Standards
- Phase 1 explanations must be genuinely simple — if you'd need a dictionary to read it, rewrite it
- Gap analysis must be specific to *what the learner said*, not generic notes on the topic
- The loop should run a minimum of 2 full cycles before confirming mastery
- Never skip Phase 3 — even a good explanation has something worth reinforcing

## Example Output Opener
> Let's use the Feynman method on [topic]. I'll explain it simply first, then you'll explain it back to me — and we'll keep going until it sticks...
