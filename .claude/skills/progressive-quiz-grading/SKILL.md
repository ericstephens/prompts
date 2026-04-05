---
name: quiz
description: Test understanding of any topic with 10 progressively harder questions, graded with real-time feedback
user_invocable: true
---

# Skill: Progressive Quiz & Grading

## Purpose
Test a learner's understanding of any topic they've just studied using 10 progressively harder questions. After each answer, grade it immediately, explain what was missed, and build toward deeper understanding. Simulates the experience of a knowledgeable tutor giving real-time feedback.

## Trigger Phrases
Use this skill when the user says things like:
- "I just studied [topic] — quiz me"
- "Test my understanding of [topic]"
- "Give me progressively harder questions on [topic]"
- "Grade my answers on [topic]"
- "Quiz me and tell me what I missed"

---

## Instructions for Claude

### Setup

Before starting, confirm the topic and briefly acknowledge what the learner studied (ask if not stated). Then set expectations:

```
Great — let's test your understanding of [topic] with 10 questions that get 
progressively harder. Answer each one before I move to the next. 
I'll grade you and explain anything you miss. Ready? Here's Question 1:
```

---

### Question Difficulty Progression

| Q# | Level | Type |
|----|-------|------|
| 1–2 | Recall | Define or identify a core term/concept |
| 3–4 | Comprehension | Explain in your own words / describe how X works |
| 5–6 | Application | Apply the concept to a specific scenario |
| 7–8 | Analysis | Compare, contrast, or identify cause/effect |
| 9 | Synthesis | Combine multiple concepts to solve a novel problem |
| 10 | Evaluation | Critique, defend a position, or identify limitations |

---

### Per-Question Flow

**Ask one question at a time.** Do not reveal the next question until the learner answers.

```
QUESTION [N] of 10 [Difficulty: ⭐ / ⭐⭐ / ⭐⭐⭐ / ⭐⭐⭐⭐ / ⭐⭐⭐⭐⭐]
[The question]
```

After the learner answers:

```
GRADE: [Pass ✅ / Partial ⚠️ / Miss ❌]
SCORE: [X/10 points for this question]

WHAT YOU GOT RIGHT:
[Specific acknowledgment of correct elements]

WHAT YOU MISSED:
[Clear explanation of gaps — not just "wrong" but WHY it matters]

THE FULL ANSWER:
[Concise correct answer for reference]

PRO TIP:
[One insight that deepens understanding beyond just the correct answer]

---
[Move to next question]
```

---

### Grading Rubric

| Grade | Criteria | Points |
|-------|----------|--------|
| ✅ Full Pass | Core answer correct, no major gaps | 10 |
| ⚠️ Partial | Partially correct — right idea, missing key detail | 6 |
| ❌ Miss | Incorrect or fundamentally misunderstood | 2 |

---

### Final Score & Summary

After all 10 questions, deliver a full debrief:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📊 QUIZ COMPLETE — FINAL RESULTS
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
TOTAL SCORE: [X] / 100

PERFORMANCE BREAKDOWN:
✅ Strong areas: [List topics/questions you nailed]
⚠️ Shaky areas: [List topics/questions that were partial]
❌ Knowledge gaps: [List topics/questions you missed]

WHAT TO DO NEXT:
[Specific study recommendations based on missed questions — 
e.g., "Re-study [concept] — your answer on Q7 shows a 
misconception about how X relates to Y"]

OVERALL VERDICT:
[One honest paragraph on where the learner stands and what 
they should focus on next]
```

---

## Quality Standards
- Questions must genuinely escalate in difficulty — Q1 should be answerable by anyone who briefly read about the topic; Q10 should challenge even prepared learners
- Feedback must be specific to the learner's actual answer, not generic notes on the topic
- Never reveal the next question before the learner answers the current one
- The "Pro Tip" should add real value — a nuance, common misconception, or practitioner insight
- Final debrief must be actionable — not just a score, but a study prescription

## Example Output Opener
> Perfect — let's put your knowledge of [topic] to the test. 10 questions, getting harder as we go. Answer each one and I'll grade you in real time...
