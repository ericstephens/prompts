---
name: agent-approval-arch
description: Design a 70/30 approval architecture for AI agent workflows — 70% human control, 30% agent execution, with tiered gates and audit trails
user_invocable: true
---

# Skill: Agent Approval Architecture (70/30 Model)

## Purpose
Design an approval architecture that implements 70% human control / 30% agent execution. Identifies which agent actions can be autonomous, which need pre-approval, and which should only support human decision-making. Produces a tiered gate system with verification protocol and audit requirements — implementable today, not theoretical.

## Trigger Phrases
- "Design approval gates for my agent"
- "70/30 approval architecture"
- "How should humans stay in control of my agent?"
- "Help me design agent oversight"
- "Agent approval architecture"

---

## Instructions for Claude

This skill runs as an interactive interview. Ask questions one at a time. Wait for responses. If answers are vague, ask up to 2 follow-up questions. If still not concrete, note as an open design question in the final architecture.

### Architecture Questions

**Q1:** "What workflows are you delegating to agents? List them — email triage, calendar management, research synthesis, meeting prep, etc."

*Wait for response.*

**Q2:** "For each workflow: where are the consequential decision points, and what's the cost of getting them wrong? Not every step — just where a wrong decision is expensive. Sending an email to a client? Expensive. Unsubscribing from spam? Cheap."

*Wait for response.*

**Q3:** "For each consequential decision: can you verify correctness quickly? Can you evaluate the agent's proposed action in under 30 seconds? Or does verification take longer than doing it yourself?"

*Wait for response.*

**Q4:** "What's your realistic verification capacity, and where do you need audit trails? How much time per day for reviewing agent actions? What tooling do you have? Which actions require a record of who approved what and when?"

*Wait for response.*

**Q5:** "Which actions are reversible vs. irreversible? Draft email = reversible. Sent email = irreversible. Design approval gates based on reversibility, not just stakes."

*Wait for response.*

### Architecture Generation

After all five questions, produce the architecture.

**Tier assignment logic:**
- Tier 1 (Autonomous): low-stakes, reversible, high-frequency — agent decides and executes
- Tier 2 (Supervised): medium-stakes, fast-to-verify — agent proposes, human approves before execution
- Tier 3 (Collaborative): high-stakes or irreversible — agent does prep, human decides and executes

### Rules
- If the user tries to make everything Tier 1, push back: "The 70/30 model requires meaningful human control — which consequential decisions are you keeping?"
- If Tier 2 verification time exceeds "just doing it myself," move actions to Tier 3 or Tier 1 depending on stakes
- Never skip audit trails on irreversible actions
- Architecture must be implementable with available tooling — flag infrastructure gaps

### Output Format

```
**70/30 APPROVAL ARCHITECTURE**

**Approval Tiers**

**TIER 1: AUTONOMOUS (Agent Decides & Executes)**
- [Action] — Why it qualifies: [low-stakes/reversible/high-frequency]
- [Notification approach: how you're informed after execution]

**TIER 2: SUPERVISED (Agent Proposes, Human Approves)**
- [Action] — Why it qualifies: [medium-stakes, verification <30 sec]
- [Approval process: how you review and approve]

**TIER 3: COLLABORATIVE (Agent Assists, Human Decides)**
- [Action] — Why it qualifies: [high-stakes or irreversible]
- [What agent delivers: research/draft/options for your decision]

**Verification Protocol**
- Tier 1: [spot-check approach, frequency]
- Tier 2: [approval review process, time budget, tooling]
- Tier 3: [how agent deliverables are structured for decision-making]

**Audit Requirements**
- Actions requiring audit trails: [list]
- What gets logged: [action, timestamp, approval/rejection]
- Review cadence: [daily/weekly/as-needed]

**Escalation Rules**
- When Tier 1 escalates to Tier 2: [trigger conditions]
- When Tier 2 escalates to Tier 3: [trigger conditions]
- How agent signals uncertainty: [mechanism]

**Infrastructure Gaps**
[Any tooling or configuration needed to implement this architecture]
```

Under 800 words. Implementable today.

## Quality Standards
- Every workflow mentioned must have at least one action in each tier (or an explanation of why not)
- Tier 2 verification time must be confirmed as realistic for the user's capacity
- Irreversible actions must be in Tier 2 or Tier 3 — never Tier 1
- Infrastructure gaps must be flagged as blocking if they prevent implementation
