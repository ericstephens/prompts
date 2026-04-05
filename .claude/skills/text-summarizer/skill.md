---
name: text-summarizer
description: Condense any text into a faithful summary paragraph plus key points — no hallucinations, no editorializing
user_invocable: true
---

# Skill: Text Summarizer

## Purpose
Produce a concise, accurate summary of any input text while preserving meaning, structure, and the most important facts. Structured output: a summary paragraph followed by bulleted key points.

## Trigger Phrases
- "Summarize this: [text]"
- "Give me a summary of [text/article]"
- "TL;DR this"
- "What are the key points from [text]?"
- "Condense this into [N] words"
- "Summarize in [style] format"

---

## Instructions for Claude

### Parameters
Collect if not provided inline:
- **text** (required): Content to summarize — article, transcript, email, doc, etc.
- **max_words** (optional, default 120): Target word count for the summary paragraph
- **style** (optional, default "neutral"): neutral | bullet-heavy | executive | academic | casual
- **focus** (optional): Emphasis angle — e.g. "action items", "risks", "business impact", "key arguments"

If text is not provided, ask for it. All other parameters can default silently.

### Steps
1. Read the entire text carefully.
2. Identify:
   - Core topic / main thesis
   - 4–8 most important points, facts, arguments, or findings
   - Any conclusions, recommendations, or calls to action
3. Remove fluff, repetition, minor examples, and low-value details unless central to the thesis.
4. Write a coherent summary paragraph of at most ~max_words words.
5. If focus is specified, weight that aspect above others.
6. Adapt tone to the requested style.

### Rules
- Never invent information not present in the input.
- Do not editorialize or add opinions.
- If the text is very short, do not artificially pad the output.
- If anything essential is ambiguous, note it briefly in the key points.
- Bullet points must be specific — no generic observations that could apply to any text.

### Output Format

```
Summary (~N words):
[One coherent paragraph]

Key Points:
- [Most important fact/idea]
- [Second point]
- [Continue 4–8 bullets as warranted]
```

No preamble. No "Here is your summary:" opener. Start directly with `Summary (~N words):`.

## Quality Standards
- Every sentence in the summary must be traceable to source content
- Key points must be specific to this text, not generic
- Word count must be close to target (within ±15%)
- If the source contains a clear call to action or recommendation, it must appear in the output
