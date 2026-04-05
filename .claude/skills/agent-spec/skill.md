---
name: agent-spec
description: Turn vague agent delegation intentions into a precise, executable task specification — ruthless about ambiguity in boundaries, approval gates, and failure modes
user_invocable: true
---

# Skill: Agent Task Specification

## Purpose
Turn vague delegation intentions into a precise, copy-paste-ready agent task specification. Forces clarity on objectives, boundaries, approval requirements, success criteria, and failure modes. A finished spec should be something you can hand to an agent deployment (or review yourself before granting permissions) — no "fill this in later."

## Trigger Phrases
- "Write an agent spec for [task]"
- "Help me spec out an agent task"
- "Agent task specification"
- "Define what my agent should do for [task]"
- "Create an agent brief for [task]"

---

## Instructions for Claude

This skill runs as an interactive interview. Ask questions one at a time. Do not move to the next question until the user has answered. If answers are vague, ask up to 2 follow-up questions to force specificity. If still vague, flag as a blocker in the final spec.

### Specification Questions

**Q1:** "What is the task you're delegating? Specific and bounded — not 'manage my calendar' but 'identify scheduling conflicts and propose resolution options for my approval.'"

*Wait for response. If too vague after one follow-up, flag as blocker.*

**Q2:** "What is the objective — not what the agent does, but what outcome you care about? 'Free up 5 hours/week by automating email triage' is an objective. 'Process emails' is not."

*Wait for response.*

**Q3:** "What tools does the agent need access to, and what is it explicitly NOT allowed to do? Be specific: read-only vs. write access, which accounts, which systems, which APIs. The 'must not' list matters more than the 'can do' list."

*Wait for response. If the user says 'whatever it needs,' reject that: "Define boundaries explicitly — what can it NOT do?"*

**Q4:** "What are the approval gates? Which actions require human approval before execution? Which are notification-only after? Which are fully autonomous within bounds?"

*Wait for response.*

**Q5:** "What does success look like — measurable criteria? Not 'does a good job' but '90% of emails correctly triaged, zero false positives on urgent messages, drafts ready within 2 hours.'"

*Wait for response. If success criteria are subjective, push back: "Operationalize that into measurable terms."*

**Q6:** "What are the predictable failure modes and the mitigation for each? Not edge cases — the obvious ways this fails. For each: how do you detect it, how do you recover, what's the rollback procedure?"

*Wait for response. If no mitigation exists for a predictable failure, flag as blocker.*

### Spec Generation

After all six questions, produce the spec. Do not share it piecemeal.

### Rules
- If user says agent can do "whatever it needs," reject and force explicit boundary definition
- Success criteria must be operationalized — no subjective standards
- Every predictable failure mode without a mitigation is a blocker
- Output must be copy-paste ready — no placeholders, no "fill this in later"

### Output Format

```
**AGENT TASK SPECIFICATION**

**Task Name:** [concise identifier]

**Objective:** [the outcome, measurable]

**Scope:**
- Authorized actions: [what the agent can do]
- Tools/permissions: [each system with permission level]
- Time/frequency: [schedule or trigger]

**Boundaries (MUST NOT):**
- [Prohibited action]
- [System/account off-limits]
- [Data it cannot access or expose]

**Approval Gate Architecture:**
- Tier 1 — Autonomous: [actions agent can take without approval]
- Tier 2 — Notification: [actions agent takes, notifies after]
- Tier 3 — Approval Required: [actions requiring pre-approval]

**Success Criteria:**
- [Measurable criterion]
- [Measurable criterion]

**Failure Modes & Mitigations:**
| Failure | Detection | Recovery | Prevention |
|---------|-----------|----------|-----------|
| [Failure] | [How detected] | [How recovered] | [Prevention] |

**Verification Protocol:**
[Who checks, how often, by what method, using what evidence]
```

Under 500 words. Precise and immediately usable.

## Quality Standards
- Boundaries section must be non-empty — no spec without explicit "must not" list
- Every tier in the approval architecture must have at least one example action
- Failure modes table must cover the most obvious failure, not just edge cases
- No placeholders in the final output
