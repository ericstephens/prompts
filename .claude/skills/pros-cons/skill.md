---
name: pros-cons
description: Balanced pros/cons analysis with weighted scoring and a direct recommendation — not a fence-sitting exercise
user_invocable: true
---

# Skill: Pros / Cons Evaluation

## Purpose
Produce a rigorous, honest pros/cons analysis for any decision, option, or tradeoff. Outputs weighted scoring and a clear recommendation — not a list that leaves all the work to the reader.

## Trigger Phrases
- "Pros and cons of [option]"
- "Help me decide between [A] and [B]"
- "Evaluate [option] for me"
- "Should I [decision]?"
- "Weigh the tradeoffs of [option]"

---

## Instructions for Claude

### Parameters
Collect if not provided:
- **subject** (required): The option, decision, or tradeoff to evaluate
- **context** (optional): Relevant background — who's deciding, what constraints exist, what goals matter most
- **alternatives** (optional): Other options to compare against; if none given, compare against "not doing it" / status quo
- **criteria** (optional): Specific dimensions to weight — e.g. "cost, speed, risk, reversibility"

If subject is not provided, ask for it. Collect context conversationally if it would materially change the analysis.

### Steps
1. Identify the decision criteria — what factors actually matter for this choice. If not specified, infer from context.
2. Assign weights to each criterion (1–3 scale: 1 = nice to have, 2 = important, 3 = critical). State the weights explicitly.
3. For each pro and con:
   - State it specifically — no vague entries like "saves time" without quantifying or grounding
   - Map it to the relevant criterion
   - Rate its magnitude (low / medium / high)
4. Compute a weighted score: sum pros weighted by criterion × magnitude, subtract cons weighted the same way.
5. Identify the "killer" items — any single pro or con significant enough to override the score.
6. Issue a direct recommendation. Don't hedge. If the analysis is genuinely ambiguous, say what additional information would resolve it.

### Rules
- Every pro and con must be specific to the subject, not generic.
- Weight assignments must be justified — state why each criterion has its weight.
- The recommendation must follow from the analysis — no surprise pivots.
- If context changes the answer materially, say so explicitly.
- Never end with "it depends" without specifying what it depends on.

### Output Format

```
## Evaluation: [Subject]

**Decision Criteria & Weights**
| Criterion | Weight (1–3) | Why |
|-----------|-------------|-----|
| [Criterion] | [Weight] | [Rationale] |

**Pros**
| Pro | Criterion | Magnitude | Weighted Score |
|-----|-----------|-----------|----------------|
| [Specific pro] | [Criterion] | High/Med/Low | [W × M] |

**Cons**
| Con | Criterion | Magnitude | Weighted Score |
|-----|-----------|-----------|----------------|
| [Specific con] | [Criterion] | High/Med/Low | [W × M] |

**Score**
- Pros total: [X]
- Cons total: [X]
- Net: [+/- X]

**Killer Items** (if any)
[Any single factor that overrides the score — explain why]

**Recommendation**
[Direct statement: do it / don't do it / do it with these conditions]
[2–3 sentence defense of the recommendation]
```

## Quality Standards
- No generic pros/cons — every item must be specific to this subject
- Weights must be stated and justified before scoring
- Recommendation must be unambiguous
- If comparing multiple options, run the same framework for each
