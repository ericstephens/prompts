---
name: rewrite-tone
description: Rewrite any text in a different tone, formality level, or length while preserving the original meaning
user_invocable: true
---

# Skill: Rewrite / Tone Shift

## Purpose
Rewrite text in a specified tone, formality, or style without changing the meaning. Useful for adapting drafts for different audiences, making writing more concise, or shifting register from casual to professional (or vice versa).

## Trigger Phrases
- "Rewrite this [more formally / more casually / more concisely]"
- "Make this sound [professional / direct / warmer / shorter]"
- "Tone shift this to [target tone]"
- "Edit this for [audience]"
- "Tighten this up"
- "Make this less [formal / wordy / passive]"

---

## Instructions for Claude

### Parameters
Collect if not provided:
- **text** (required): The content to rewrite
- **target_tone** (required): The desired register — e.g. "professional", "casual", "executive", "empathetic", "direct", "academic", "conversational", "assertive"
- **target_length** (optional): "shorter", "same", "longer" — or a specific word count target (default: same)
- **preserve** (optional): Anything that must not change — e.g. "keep the bullet structure", "don't change the opening line", "preserve all proper nouns"
- **audience** (optional): Who will read it — helps calibrate the rewrite

If text and target_tone are not provided, ask for them. Default silently on other parameters.

### Steps
1. Identify the core message — what the original text is actually trying to communicate.
2. Note structural elements to preserve (if any): headings, lists, paragraph count, key phrases.
3. Rewrite in the target tone, adjusting:
   - Vocabulary (formality, specificity, jargon level)
   - Sentence structure (active vs. passive, sentence length)
   - Opener and closer (tone is set strongest at the edges)
   - Transitions and connectives
4. If length adjustment is requested, apply it without cutting meaning or padding with filler.
5. After the rewrite, note any meaning changes or trade-offs made (only if material).

### Rules
- The rewrite must preserve the original meaning — no added claims, no removed key points.
- Do not silently add a CTA, disclaimer, or framing that wasn't in the original.
- If the original has errors (factual, logical, grammatical), flag them but do not silently fix them in the rewrite — the user may have intended them.
- If "shorter" is requested and cutting would remove a key point, flag the trade-off rather than silently omitting.
- Never explain what you changed unless it's material.

### Output Format

```
[Rewritten text — no label, no intro]
```

If material trade-offs were made:
```
---
Note: [1 sentence describing any meaningful change in emphasis or omission]
```

No "Here is the rewrite:" opener. No closing commentary. Output the rewrite, then stop.

## Quality Standards
- All key points from the original must survive the rewrite
- Tone must be consistent throughout — no register drift mid-piece
- Length target must be within ±10% of requested
- The rewrite must be ready to use without further editing
