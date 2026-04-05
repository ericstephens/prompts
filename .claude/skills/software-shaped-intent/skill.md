---
name: software-shaped-intent
description: Map your domain expertise as agent-directable patterns — inputs, transformations, outputs — to identify high-leverage AI orchestration opportunities
user_invocable: true
---

# Skill: Software-Shaped Intent Builder

## Purpose
Help domain experts translate their work into patterns that AI agents can execute. Think in systems: inputs, transformations, outputs, data flows. Identify where AI could handle 60–80% of execution if properly directed, and surface the "direction gaps" — where the user would need to think differently to effectively orchestrate agents.

## Trigger Phrases
- "Help me figure out what to delegate to AI"
- "Map my work for agent orchestration"
- "Software-shaped intent"
- "How can I use AI agents in my workflow?"
- "What in my work can AI do?"
- "Help me think about AI delegation"

---

## Instructions for Claude

This skill runs as an interactive interview. Ask questions one at a time. Wait for responses. Do not generate the analysis until all inputs are collected.

### Phase 1 — Information Gathering

**Q1:** "What domain or function do you work in — not your job title, but what kind of work you actually do day-to-day?"

*Wait for response.*

**Q2:** "List 3 tasks you do regularly that take significant time — things you do weekly or more often."

*Wait for response.*

If the user lists more than 3 tasks, identify the 3 highest-leverage ones and proceed with those. Explain briefly why you're narrowing.

**Q3:** "For each task you listed, what do you currently delegate (to anyone — assistant, team member, contractor, AI) vs. do entirely yourself?"

*Wait for response.*

If any answer is vague after one clarifying follow-up, proceed but label assumptions explicitly.

### Phase 2 — Analysis

Once all inputs are collected, produce the full analysis.

For each task:
1. Map the software-shaped structure: What data does it need as input? What transformation happens? What's the output? Where does that output go?
2. Identify which tasks are high-leverage for agent orchestration — where AI could handle 60–80% of execution
3. Identify the "direction gaps" — where they'd need to think differently to effectively orchestrate agents
4. Provide 2–3 concrete starter patterns they can use immediately

**Total output: under 600 words.** Go deepest on the #1 opportunity. Lighter touch on the others.

### Rules
- Do not infer what the user "probably" means — ask if ambiguous
- Only use explicitly provided information — no assumed tools or workflows
- If a task description is too vague to decompose, ask ONE clarifying follow-up
- Starter patterns must be specific and immediately usable — not abstract principles
- Focus on highest-leverage opportunities, not comprehensive coverage

### Output Format

```
**Your Domain in Software Terms**
[2–3 sentences describing their work as a system — what inputs flow in, what transformations they apply, what outputs they produce]

**Task Decomposition**

**Task: [Name]**
| Component | Current State | Agent-Directable Version |
|-----------|--------------|-------------------------|
| Input | [Where data comes from now] | [How an agent could gather it] |
| Transformation | [What they do to it] | [How to direct an agent to do this] |
| Output | [What they produce] | [Where agent output would go] |
| Bottleneck | [What makes this slow/hard] | [What agent orchestration solves] |

[Repeat for each of the 3 tasks]

**High-Leverage Opportunities**
Ranked by potential time savings:
1. **[Task]:** [Why high-leverage] — Estimated effort shift: ~X% agent-handled
2. **[Task]:** [Why high-leverage] — Estimated effort shift: ~X%

**Direction Gaps to Close**
- [Gap]: [What they'd need to think about differently]
- [Gap]: [What they'd need to think about differently]

**Starter Patterns — Try This Week**
1. **[Pattern name]:** [Specific prompt or workflow for their highest-leverage task]
2. **[Pattern name]:** [Specific prompt or workflow]
```

## Quality Standards
- Every table row must be grounded in what the user actually said
- Effort shift estimates must be justified, not arbitrary
- Starter patterns must be copy-paste ready — no "figure out the details yourself"
- Total output must stay under 600 words to maintain focus
