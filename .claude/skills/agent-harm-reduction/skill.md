---
name: agent-harm-reduction
description: Implement containment protocols that limit blast radius when agent deployment goes wrong — isolation, monitoring, and incident response
user_invocable: true
---

# Skill: Agent Deployment Harm Reduction

## Purpose
Implement containment protocols for AI agent deployment. Not perfect security — that doesn't exist. Practical harm reduction that limits damage when (not if) something breaks. Covers isolation, access control, monitoring, and incident response. The output is a pre-flight checklist you can actually run through today.

## Trigger Phrases
- "Help me reduce harm from agent deployment"
- "Agent harm reduction protocol"
- "How do I contain my agent if it goes wrong?"
- "Agent safety and containment"
- "Pre-deployment safety check for agents"

---

## Instructions for Claude

This skill runs as an interactive interview. Ask questions one at a time. Wait for responses. If answers are vague, ask up to 2 follow-up questions. If still not concrete, flag as a pre-deployment blocker.

### Protocol Questions

**Q1:** "What infrastructure are you using for agent deployment? Dedicated hardware? Cloud instance? Running on your primary machine? Be specific."

*Wait for response. If "primary machine with full access," flag as CRITICAL RISK and recommend dedicated infrastructure first.*

**Q2:** "What accounts and systems will the agent access? Can you use dedicated or throwaway accounts for each? Email, calendar, file storage, APIs, financial systems — list everything. Dedicated accounts limit blast radius."

*Wait for response.*

**Q3:** "What data are you protecting — not everything, just what you can't afford to lose or expose? Client lists, financial records, credentials, source code?"

*Wait for response. If no backups of protected data exist, flag as a pre-deployment blocker.*

**Q4:** "How will you detect when the agent does something wrong? Specific monitoring — not 'I'll notice.' Log review? Alerts on specific actions? Audit trail review cadence?"

*Wait for response.*

**Q5:** "What's your incident response plan and rollback capability? Step by step: how do you kill the agent, revoke permissions, assess damage, and recover? Which actions are reversible? What's backed up? How fast can you restore?"

*Wait for response. If the plan is "figure it out when it happens," require a step-by-step plan before proceeding.*

### Protocol Generation

After all five questions, produce the protocol.

### Rules
- Running on primary machine with full account access = CRITICAL RISK flag
- No backups of protected data = pre-deployment blocker
- "I'll be careful" as containment strategy = CRITICAL flag
- "I'll figure it out when it happens" as incident response = blocking
- Pre-flight checklist items are blocking — all must be checked before deployment

### Output Format

```
**AGENT DEPLOYMENT HARM REDUCTION PROTOCOL**

**Isolation Layer**
- Infrastructure: [hardware/VM/container — what's isolated and how]
- Network: [what agent can reach, what it can't]
- Storage: [where agent can read/write, what's off-limits, backup strategy]

**Access Control**
- Accounts: [which accounts, whether dedicated/throwaway]
- Permissions: [minimum necessary permissions per system]
- Credential management: [storage, rotation, monitoring approach]

**Monitoring & Detection**
- What I'm monitoring: [specific actions, log entries, system states]
- How I'm monitoring: [tools, scripts, manual review — be specific]
- Alert thresholds: [what triggers immediate attention vs. batch review]
- Review cadence: [daily log review? weekly audit? real-time alerts?]

**Incident Response Plan**
1. STOP: [command/action to kill the agent immediately]
2. REVOKE: [how to revoke agent permissions across all systems]
3. ASSESS: [how to determine what the agent did — log locations]
4. CONTAIN: [how to prevent further damage]
5. RECOVER: [how to restore from backup, undo actions, notify if needed]

**Pre-Flight Checklist**
[ ] Isolation infrastructure configured and tested
[ ] Dedicated accounts created with minimum permissions
[ ] Protected data backed up and out of agent access
[ ] Monitoring and alerting configured
[ ] Incident response plan documented and practiced
[ ] Rollback procedures tested
[ ] Kill switch tested and accessible
```

Under 700 words. Implementable today — no aspirational security theater.

## Quality Standards
- Every checklist item must be testable before deployment
- Incident response must be step-by-step — not narrative
- STOP step must name a specific command or action, not "shut it down"
- Any red flags (primary machine, no backups, no monitoring) must be flagged as blocking before issuing the protocol
