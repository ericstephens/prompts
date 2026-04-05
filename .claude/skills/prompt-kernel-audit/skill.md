---
name: prompt-kernel-audit
description: Audit any prompt or skill against the KERNEL framework for reproducibility, clarity, and business value — identifies weaknesses and suggests concrete fixes
user_invocable: true
---

# Skill: Prompt KERNEL Framework Audit (Metaskill)

## Purpose
Validate any prompt, skill, or instruction set against the KERNEL framework — six core principles derived from 1,000 hours of prompt engineering. Produces a detailed audit report with a reproducibility score, identified gaps, and concrete revision suggestions. Use this to harden existing prompts before shipping them or to validate new skills before integration.

## Trigger Phrases
- "Audit this prompt against KERNEL"
- "Validate this skill / prompt"
- "KERNEL framework audit"
- "Score this prompt"
- "Is this prompt solid?"
- "What's wrong with this prompt?"

---

## Instructions for Claude

### Parameters
Collect if not provided:
- **prompt_or_skill** (required): The full text of the prompt, skill, or instruction set to audit
- **context** (optional): What this prompt/skill is used for — e.g. "email triage", "research synthesis", "market analysis"
- **current_usage** (optional): How it's currently being used and any known problems — e.g. "outputs are inconsistent", "takes too long to verify", "users confused by the format"

If the prompt/skill text is not provided, ask for it.

### The KERNEL Framework

**K — Keep it Simple:** One task per prompt. Eliminate side tasks, optional branches, or multi-step workflows that belong in separate prompts.

**E — Easy to Verify:** Outputs are testable and measurable. Clear format (numbered lists, specific lengths, structured data), not narrative prose. You can assess quality in <30 seconds without re-reading.

**R — Reproducible Results:** Same prompt + same input → consistent quality (not identical output, but reliable quality). The output doesn't drift or degrade on repeated use.

**N — Narrow Scope:** Constraints improve outputs more than open-ended requests. Explicit boundaries on what the task is NOT, who the audience is, what domain it covers. Narrow > comprehensive.

**E — Explicit Constraints:** All requirements stated directly: tone, length, format, audience, terminology to avoid, prohibited actions, reversibility concerns. Zero unstated assumptions.

**L — Logical Structure:** Prompts organized systematically: [Context] → [Task] → [Constraints] → [Output Format]. Numbered sections, clear hierarchy, easy to scan and modify.

### Audit Steps

1. **Read the prompt/skill end-to-end** to understand the intended task and current structure.

2. **Score each of the six principles:**
   - Read the definition of each principle
   - Assess whether the prompt embodies that principle
   - Rate as: ✓ (strong), ◐ (partial), ✗ (missing/weak)
   - Cite the specific text or structure that justifies the rating
   - If ✗ or ◐, identify the exact gap

3. **Reproducibility assessment:** 
   - Would this prompt produce consistent quality across 3 runs with different inputs?
   - Or would output quality drift based on input complexity, context, or how it's phrased?

4. **Business impact analysis:**
   - What breaks if the output is inconsistent?
   - How much time is wasted verifying / fixing outputs?
   - What's the blast radius of a bad output?

5. **Revision recommendations:**
   - For each ✗ or ◐, propose specific, concrete rewrites
   - Show before/after examples where helpful
   - Prioritize by impact (what fix improves reproducibility most?)

### Rules
- Every rating (✓/◐/✗) must cite text from the prompt
- Critique the prompt as-is, not what it "could be" — if it doesn't say it, it doesn't exist
- Revision suggestions must be specific enough to copy-paste, not abstract principles
- If a principle is strong, say so explicitly — don't just list weaknesses
- Highlight any mutual contradictions in the prompt (e.g., "be concise" + "comprehensive coverage")

### Output Format

```
## KERNEL Audit: [Prompt/Skill Name]

**Context:** [What this prompt does]
**Current Issues (if provided):** [Known problems the user mentioned]

---

### Audit Results

**K — Keep it Simple**
Rating: ✓ / ◐ / ✗
Evidence: [Cite text or structure from the prompt]
Assessment: [1–2 sentences on whether the prompt focuses on one clear task]

**E — Easy to Verify**
Rating: ✓ / ◐ / ✗
Evidence: [Cite text or structure]
Assessment: [Can the user assess quality in <30 seconds? Is the output format testable?]

**R — Reproducible Results**
Rating: ✓ / ◐ / ✗
Evidence: [Cite text or structure]
Assessment: [Would this prompt produce consistent quality across multiple runs?]

**N — Narrow Scope**
Rating: ✓ / ◐ / ✗
Evidence: [Cite text or structure]
Assessment: [Are constraints explicit? Boundaries clear?]

**E — Explicit Constraints**
Rating: ✓ / ◐ / ✗
Evidence: [Cite text or structure]
Assessment: [Are tone, length, format, audience, and forbidden terms stated clearly?]

**L — Logical Structure**
Rating: ✓ / ◐ / ✗
Evidence: [Cite text or structure]
Assessment: [Is the prompt organized: Context → Task → Constraints → Output Format?]

---

### Reproducibility Score
[Overall assessment: Will this prompt produce consistent quality? What factors could cause drift?]

### Business Impact
[What breaks if output is inconsistent? Time wasted? Blast radius?]

---

### Priority Revisions

**[Priority 1 — Highest Impact]**
Principle: [K/E/R/N/E/L]
Current: [Quote the problematic text]
Revised: [Concrete rewrite]
Why this matters: [How does this fix improve reproducibility?]

**[Priority 2]**
[Same format]

**[Priority 3 (if needed)]**
[Same format]

---

### Strengths
[1–2 principles where the prompt is strong — be specific]

### Overall Assessment
[1 paragraph: Is this prompt ready to ship? If not, what blocks it? If yes, what makes it solid?]
```

## Quality Standards
- Every K/E/R/N/E/L rating must include a direct quote from the prompt being audited
- At least one revision suggestion must be a complete before/after rewrite
- If the prompt scores ✓ on all six, explicitly state that
- Business impact must be specific to the actual use case (not generic)
- Reproducibility assessment must identify the specific factors that could cause drift
