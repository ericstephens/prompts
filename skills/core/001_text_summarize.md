---
skill_id: 001
name: Text Summarizer
version: 1.1
category: core
tags: [summarization, extraction, concise, compression]
description: Condense long text into a clear, faithful summary with key points — no added information or hallucinations.
compatible_models: [any — especially strong on Grok, Claude 3/4, GPT-4o, Gemini 1.5, Llama 3.1+]
last_updated: 2026-03-01
change_log:
  - 1.1 (2026-03-01) — Added {style} parameter, improved rules section, more robust examples
  - 1.0 (2025-10-15) — Initial version
---

# Skill: Text Summarizer
**Version:** 1.1  
**Short Description:** Produce a concise, accurate summary of any input text while preserving meaning, structure, and most important facts.

## Parameters (replace these placeholders in your copy)
- `{input_text}`          : The full text, article, transcript, email thread, etc. to summarize (required)
- `{max_words}`           : Target maximum length of the main summary paragraph (optional, default: 120)
- `{style}`               : Tone/style — e.g. "neutral", "bullet-heavy", "executive", "academic", "casual" (optional, default: neutral)
- `{focus}`               : Optional emphasis — e.g. "business impact", "risks and mitigations", "action items", "key arguments" (optional)

## Core Prompt (copy-paste this block into any LLM chat)

You are a world-class professional summarizer — precise, neutral, faithful to the source material. Your only task is to condense the provided text without adding, omitting critical facts, or hallucinating.

Follow these steps exactly:

1. Read the entire {input_text} carefully at least once.
2. Identify:
   - Core topic / main thesis
   - 4–8 most important points, facts, arguments or findings
   - Any conclusions, recommendations, or calls to action
3. Remove fluff, repetition, minor examples, and low-value details unless they are central.
4. Write a coherent summary paragraph of at most ~{max_words} words.
5. If {focus} is specified, emphasize that aspect above others.
6. Adapt tone to {style} (default: neutral and professional).

Rules you must obey:
- Never invent information not present in the input.
- Do not editorialize or add your own opinions.
- If the text is very short, do not artificially lengthen the summary.
- If anything essential is ambiguous, note it briefly in the key points.

Output **only** in this exact format — no extra text, no introductions, no explanations:

Summary (~{actual word count} words):
[One coherent paragraph summary here]

Key Points:
- Bullet 1 — most important fact/idea
- Bullet 2
- Bullet 3

## Example Usage 1 — Basic Article Summary
**Filled Parameters:**
{input_text}: Artificial intelligence is advancing at an unprecedented pace. Recent models such as GPT-4o, Claude 3.5 Sonnet and Grok-2 demonstrate capabilities approaching or exceeding average human performance across many academic benchmarks. However, these systems still struggle with long-term planning, genuine reasoning over novel problems, and maintaining consistency over long contexts. Researchers have identified multiple risks including misalignment, misuse by bad actors, proliferation of deepfakes, and economic displacement. Mitigation strategies under discussion include scalable oversight, constitutional AI, red-teaming, and international coordination on safety standards. Several leading labs have paused or slowed releases pending better safety evaluations.
{max_words}: 100
{style}: neutral
{focus}: (none)
**Expected Output:**
Summary (~94 words):
Large language models are rapidly approaching or surpassing average human performance on many benchmarks, yet continue to struggle with long-horizon planning, novel reasoning, and extended context consistency. Key risks include misalignment, malicious use, deepfakes, and labor market disruption. Proposed mitigations encompass scalable oversight, constitutional approaches, rigorous red-teaming, and global safety coordination. Several major AI labs are currently slowing or pausing frontier model releases to improve safety evaluation processes.
Key Points:
• Frontier models near/exceed human-level on many academic tests
• Persistent weaknesses: long-term planning, novel problems, long contexts
• Major risks: misalignment, misuse, deepfakes, economic displacement
• Mitigation efforts: scalable oversight, constitutional AI, red-teaming, international standards
• Several labs delaying releases for better safety testing
## Example Usage 2 — With Focus & Shorter Style

**Filled Parameters:**
{input_text}: [same long text as above]
{max_words}: 60
{style}: executive
{focus}: action items and recommendations


**Expected Output:**
Summary (~58 words):
Frontier AI models approach human-level performance on many tasks but remain weak in long-term planning and novel reasoning. Risks include misalignment and misuse. Labs are slowing releases to improve safety testing.

Key Points:
• Pause or slow frontier model releases
• Strengthen scalable oversight & red-teaming
• Pursue constitutional AI techniques
• Coordinate international AI safety standards

## Notes / Tips / Variations
- Strong on: Claude (excellent faithfulness), Grok (good at staying concise), GPT-4o
- Weak on: Older/smaller models may hallucinate or pad — add "Be extremely concise and strict" in those cases
- Common tweaks:
  → Want only bullets? Change output instruction to: "Output only the Key Points bullets — no summary paragraph."
  → Need JSON? Replace output format with: `Output valid JSON only: {"summary": "...", "key_points": ["...", ...]}`
  → Very long documents: Add to rules: "Prioritize the most recent or most repeated information if context is extremely long."
- Great chaining partner: Use after 031_translate_natural or before 002_idea_brainstorm