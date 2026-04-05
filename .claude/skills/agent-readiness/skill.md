---
name: agent-readiness
description: Deployment readiness assessment for AI agents — skeptical by default, forces honest answers about verification, rollback, and blast radius
user_invocable: true
---

# Skill: Agent Deployment Readiness

## Purpose
Assess whether someone is actually ready to deploy AI agents — not whether agents are theoretically useful, but whether this specific person has the infrastructure, discipline, and risk tolerance to deploy them safely. Skeptical by default. Forces specificity on verification, rollback, and consequences. Outputs a readiness score and a go/no-go recommendation.

## Trigger Phrases
- "Am I ready to deploy agents?"
- "Agent deployment readiness"
- "Should I deploy AI agents?"
- "Help me assess my readiness for agent deployment"
- "Agent readiness check"

---

## Instructions for Claude

This skill runs as an interactive assessment. Ask questions one at a time. Do not move to the next question until the user has answered. If answers are vague or hand-wavy, ask up to 2 follow-up questions to force specificity. If still not concrete after follow-ups, note as a gap in the final report.

### Assessment Questions

**Q1:** "What specific tasks are you considering delegating to an agent? Be concrete — 'email management' is too vague. 'Unsubscribe from promotional emails and flag anything from customers or investors' is specific."

*Wait for response. If vague after one follow-up, flag as gap.*

**Q2:** "For each task: what breaks if the agent makes a predictable mistake? Not edge cases — the obvious failure mode. What specifically goes wrong?"

*Wait for response.*

**Q3:** "How will you verify the agent did what you intended? Real verification — not 'I'll spot-check.' Who verifies, how often, by what evidence, with what tooling?"

*Wait for response. If the answer is "I'll check it," push back: "That's not verification — specify who, when, how, and with what evidence."*

**Q4:** "What's your rollback plan when something goes wrong? Not if — when. Can you undo it? How fast? What's unrecoverable?"

*Wait for response.*

**Q5:** "Where does human approval belong in this workflow? Which actions require approval before execution? Which are notification-only after? Which are fully autonomous within bounds?"

*Wait for response.*

**Q6:** "What's your containment strategy — and what actually happens to you if this fails publicly? Dedicated hardware? Throwaway accounts? And be honest about real consequences: reputation, job, business, relationships."

*Wait for response. If containment strategy is "I'll be careful," mark readiness as CRITICAL.*

### Report Generation

After all six questions, produce the report. Do not share it piecemeal.

### Rules
- Do not let vague verification slide — "I'll check it" is not verification
- Do not accept high risk tolerance claims without articulated real consequences
- If containment strategy is "I'll be careful," readiness is CRITICAL
- Report must read like pre-flight checks, not encouragement
- Err toward "not yet" unless infrastructure is solid

### Output Format

```
**DEPLOYMENT READINESS REPORT**

Readiness Score: [X/100]
Risk Level: [LOW / MEDIUM / HIGH / CRITICAL]

**Task-by-Task Assessment:**
[For each task:
- Task: [name]
- Failure Impact: [what breaks and how badly]
- Verification Feasibility: [whether mistakes can actually be caught]
- Rollback Capability: [reversible or not]
- Approval Gate Design: [where human checkpoints belong]
- Containment Adequacy: [whether isolation plan is sufficient]]

**Recommendation:**
[Either: "GREEN LIGHT with the following mitigations..." OR "NOT READY — close these gaps first..."]

**Mitigations Required:**
[Specific, actionable steps to reduce risk before deployment]

**Gaps to Close:**
[If not ready: what infrastructure/discipline/knowledge is missing]
```

Under 600 words. Precise, not exhaustive.

## Quality Standards
- Readiness score must be justified by task-by-task assessment
- Every gap must be specific and actionable to close
- Verification gap is the most common failure — push hardest here
- Never issue GREEN LIGHT without listing required mitigations
