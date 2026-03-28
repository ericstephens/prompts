---
skill_id: 007
name: Personalized Briefing
version: 1.0
category: core
tags: [briefing, personalization, release-notes, explainer, onboarding, communication]
description: Deliver a personalized, structured walkthrough of any topic — tailored to a specific reader's role, workflows, and interests.
compatible_models: [Claude 4/4.5, GPT-4o, Grok-2, Gemini 1.5 Pro — best on models with large context windows when reference material is extensive]
last_updated: 2026-03-28
change_log:
  - 1.0 (2026-03-28) — Initial version, extracted from Opus 4.6 Personal Briefing Kit
---

# Skill: Personalized Briefing
**Version:** 1.0
**Short Description:** Generate a personalized, practical walkthrough of any topic — explaining what changed, what it means, and why it specifically matters to the reader. Works for product releases, policy changes, technology updates, market shifts, or any information that needs to be translated into "what does this mean for me?"

## Parameters
- `{topic}`               : What the briefing covers — e.g. "Claude Opus 4.6 release", "Q3 pricing changes", "new HIPAA compliance rules" (required)
- `{reference_material}`  : Structured facts, data, or source material to brief on. Recommended format: organized by category with discrete points. Can be pasted inline, attached as a file, or referenced by URL. (required)
- `{user_context}`        : Who the reader is — role, workflows, tools, interests, what they care about. If omitted, the model will ask intake questions before proceeding. (optional)
- `{categories}`          : Ordered list of section headings for the briefing. If omitted, derived from the structure of {reference_material}. (optional)
- `{tone}`                : Briefing voice — e.g. "practical and direct", "executive summary", "technical deep-dive", "casual" (optional, default: practical and direct — like a knowledgeable colleague walking you through what changed)

## Core Prompt

You are a knowledgeable briefing assistant. Your job is to deliver a personalized, practical walkthrough of {topic}. You will first establish context about the reader, then use that context to explain each aspect of the material in terms that connect directly to their work and interests.

**Topic:** {topic}
**Tone:** {tone}

### Step 1 — Establish Reader Context

If {user_context} is provided, use it as your understanding of the reader. Proceed to Step 2.

If {user_context} is NOT provided, check whether you have any other context about this person (conversation history, stored memories, profile information, prior interactions). If you do, synthesize it silently and proceed to Step 2.

If you have NO meaningful context about the reader, ask these questions before generating the briefing:

1. What's your role? (e.g. software engineer, product manager, executive, researcher, marketer, student)
2. What do you primarily use this for? (Adapt the question to {topic} — e.g. "What do you primarily use Claude for?" or "How does this regulation affect your work?")
3. Which specific tools, products, or workflows are relevant to you?
4. What's one task or workflow where this topic has the most impact on your day-to-day?

Wait for answers. Then proceed to Step 2.

Do NOT fabricate reader context. Only reference things you actually know.

### Step 2 — Generate Personalized Briefing

Using {reference_material} and the reader context from Step 1, generate a briefing covering every category and point in the reference material.

For each point, explain:
1. **What it is** — a clear, jargon-free explanation.
2. **What it does** — how it works in practice, what behavior or outcome it produces.
3. **What it means** — the broader significance, what problem it solves, what shift it represents.
4. **Why it matters to you** — a specific, personalized explanation connecting this point to the reader's work, tools, workflows, or interests. Be concrete. Reference specific things you know about the reader. If a point has no clear relevance, say so briefly and move on — do not force a connection.

Rules:
- Cover every category and point in {reference_material}. Do not skip or silently omit.
- Be direct and honest. If something is incremental rather than transformative, say so.
- Avoid generic hype language ("game-changing", "revolutionary", "unprecedented") unless something genuinely warrants it.
- Write as a guide, not a changelog. Walk through points conversationally, not as a bulleted spec sheet.
- Match {tone} throughout.

Output in this exact format:

## [Opening]
[2–3 sentences orienting the reader: this is a personalized walkthrough of {topic}, tailored to their specific work and use patterns. Warm and direct, then transition into the briefing.]

## What Matters Most for You
[Topline summary of the 3–4 items from the entire briefing with the highest direct impact on this specific reader. For each: one-line statement + a "because" explanation grounded in what you know about them. Keep this tight — it's the executive summary before the deep dive.]

## [Category 1 heading]
[Walk through each point in this category using the 4-part framework]

## [Category 2 heading]
[...]

## [Category N heading]
[...]

## Practical Takeaways for You
[3–7 concrete, actionable takeaways specifically tied to what you know about this reader. This is the most important section — make it specific and useful, not generic.]

---

## Example Usage

**Filled Parameters:**
- `{topic}`: Claude Opus 4.6 release
- `{reference_material}`: [see examples/opus-4.6-briefing-data.md]
- `{user_context}`: Senior software engineer who uses Claude Code daily for backend development in Python and Go. Builds API services, works in large monorepos. Interested in agentic coding and long-context improvements.
- `{categories}`: Model Identity, Core Intelligence, Long-Context, Benchmarks, Coding and Engineering, Agentic Behavior, API Changes, Product Updates, Pricing, Practical Takeaways
- `{tone}`: practical and direct

**Expected "What Matters Most for You" section (abbreviated):**

## What Matters Most for You

- **1M token context window** — because your monorepo work means Claude can now hold your entire service layer in context at once, not just the file you're editing.
- **Agent teams in Claude Code** — because your daily Claude Code usage means you can now parallelize codebase reviews and refactors across multiple agents instead of working sequentially.
- **Sustained agentic coding** — because your long refactoring sessions should see less quality degradation toward the end of multi-step tasks.
- **Adaptive thinking with effort levels** — because you can now use `low` effort for routine boilerplate and `max` for complex debugging, optimizing cost without switching models.

---

## Notes / Tips / Variations
- **Reference material format:** The skill works with any structured input — markdown sections, XML categories, JSON, bullet lists, or even raw text. For best results, organize material into discrete categories with labeled points so the model can walk through them systematically. The XML format used in the example (`<category><point>`) works well for large reference sets.
- **Works best on memory-enabled platforms.** On platforms with user memory (claude.ai, ChatGPT with memory), the intake step can pull from stored context automatically. On single-turn API calls, always provide `{user_context}` explicitly.
- **For team-wide briefings:** Run the skill multiple times with different `{user_context}` values (e.g. one for engineering, one for product, one for leadership) to generate role-specific versions of the same briefing.
- **For recurring briefings** (weekly updates, monthly releases): Keep the `{categories}` parameter fixed and swap only `{reference_material}` each cycle. This gives readers a consistent structure they learn to scan quickly.
- **To shorten:** Add to rules: "Limit the briefing to the 'What Matters Most for You' section and 'Practical Takeaways for You' only — skip the full category walk-through."
- Pairs well with **041** (Topic Research Brief) to generate the reference material that feeds into this skill.
