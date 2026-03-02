---
# Frontmatter (YAML) — keep this at the very top for future tooling & discoverability
skill_id: XXX                     # ← Replace with sequential number e.g. 006, 014, 023…
name: Skill Name Here             # ← Short, clear name (used in catalog)
version: 1.0
category: core | writing | analysis | transformation | meta | experimental
tags: [tag1, tag2, tag3]          # ← comma-separated, lowercase, no spaces preferred
description: One-sentence summary of what this skill does.
compatible_models: [any — tested on Grok, Claude 3/4, GPT-4o, Gemini 1.5, Llama 3.1…]
last_updated: YYYY-MM-DD
---

# Skill: [Skill Name Here]
**Version:** 1.0  
**Short Description:** [One clear sentence — what does this prompt achieve?]

## Parameters (replace these placeholders in your copy)
- `{input}`               : [main input — describe it clearly] (required)
- `{option1}`             : [e.g. number, style, focus, length…] (optional, default: …)
- `{option2}`             : [another common tweak] (optional)
- `{constraints}`         : [any rules, tone, length limits, forbidden things…] (optional)

## Core Prompt (copy-paste this block into any LLM chat)
You are a world-class [role — e.g. expert editor, creative strategist, precise analyst, ruthless code reviewer…]. Your only goal is to help the user by executing the following task with maximum quality and fidelity.
Follow these steps exactly — think step-by-step if needed, but do not show your thinking unless asked:

[Step 1 — e.g. Carefully read and understand the entire input]
[Step 2 — e.g. Identify the key elements / goals / constraints]
[Step 3 — …]
[etc.]

Rules you must obey:

- Stay faithful to the provided input — do NOT hallucinate or add unrequested information.
- Be [concise / detailed / professional / creative …] unless told otherwise.
- Respect any {constraints} provided.
- If anything is unclear, ask clarifying questions instead of guessing.

Output only in the exact format below — no extra commentary, no introductions, no apologies:

[Output Format Title e.g. Summary / Ideas / Review / Translation]

[Main content here — use markdown, bullets, numbered lists, code blocks, etc. as appropriate]

[Optional second section e.g. Key Takeaways / Suggestions / Edge Cases]
### Quick Usage Reminder (add this at the bottom if you like)

**How to create a new skill from this template:**
1. Copy this entire file
2. Rename to e.g. `skills/core/006_new_skill_name.md`
3. Replace XXX with the next available number
4. Fill in frontmatter + all [bracketed] placeholders
5. Add 1–2 strong examples
6. Update SKILLS-CATALOG.md with a new row
