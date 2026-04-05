---
name: promo-email-writer
description: Write a short, high-conversion promotional email for an upcoming course or event given a URL
user_invocable: true
---

# Skill: Promo Email Writer

## Purpose
Write a short, high-conversion promotional email for an upcoming course or event given a URL. Fetches the page, extracts every key selling point, and produces a ready-to-send email in 3-5 sentences with a compelling subject line.

## Trigger Phrases
Use this skill when the user says things like:
- "Write a promo email for [URL]"
- "Draft a prospect email for this course: [URL]"
- "Email copy for [URL]"
- "/promo-email [URL]"

---

## Instructions for Claude

### Step 1 — Fetch & Extract
Use WebFetch on the provided URL and extract **all** of the following (skip any that don't exist):
- Course/event title
- Date, time, duration
- Location (in-person) or platform (online)
- Price
- Key learning outcomes / what attendees will walk away with
- Prerequisites or who it's for
- Class size cap or scarcity signal
- Instructor names and credibility highlights
- Any bonus qualifications (e.g., certifications, permits)
- Registration deadline or early-bird pricing

### Step 2 — Write the Email
Produce the email using this structure:

```
Subject: [Course Name] — [Date] | [Scarcity or benefit hook]

Hi [First Name],

[3-5 sentences that hit, in order:]
1. What & when — name the course, date, and location in one punchy line.
2. Value — the top 2-3 things they'll learn or be able to do afterward.
3. Differentiator — what makes this offering unique (small class, qualified instructors, certification, etc.).
4. Bonus (optional) — any extra qualification, permit eligibility, or time-sensitive incentive.
5. CTA — direct link to register with urgency language.

[Sign-off],
[Your Name]
```

### Step 3 — Copywriting Notes
After the email, include 2-3 bullet points explaining the key copy choices (subject line strategy, structure rationale, persuasion levers used) so the user can learn and iterate.

---

## Quality Standards
- **Brevity is non-negotiable.** The body must be 3-5 sentences — no more. Every word must earn its place.
- **Subject line ≤ 60 characters** to avoid truncation on mobile.
- Lead with benefit or scarcity, not the organization name.
- Use concrete details (dates, numbers, specific skills) — never vague promises.
- Tone: professional, direct, confident. Not salesy or hype-driven.
- Always include the registration link as a hyperlink in the CTA sentence.
- Leave `[First Name]` and `[Your Name]` as merge-tag placeholders.

## Example Output Opener
> Here's a ready-to-send prospect email for **[Course Title]**:
