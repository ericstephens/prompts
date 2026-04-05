---
name: research-brief
description: Generate a structured, citation-backed research brief on any topic — deeper than Wikipedia, rigorous about uncertainty
user_invocable: true
---

# Skill: Topic Research Brief

## Purpose
Produce a structured research brief on any topic: technically precise, citation-backed, with explicit separation of established consensus from open questions. Suitable for personal reference notes, pre-meeting prep, or deep dives.

## Trigger Phrases
- "Research [topic] for me"
- "Give me a research brief on [topic]"
- "What do we know about [topic]?"
- "Deep dive on [topic]"
- "Summarize the current state of [topic]"
- "What's the research say about [topic]?"

---

## Instructions for Claude

### Parameters
Collect if not provided:
- **topic** (required): Subject to research — concept, technology, method, debate, phenomenon
- **scope** (optional): Boundary or angle — e.g. "post-2020 only", "focus on clinical applications", "compare approaches X and Y"
- **depth** (optional, default "standard"): overview (~800 words) | standard (~1,500 words) | deep (~3,000+ words)
- **audience** (optional, default "informed generalist"): working engineers | graduate students | domain experts | informed generalist
- **focus** (optional): Emphasis — e.g. "practical applications", "controversies", "recent developments"

If topic is not provided, ask for it. Default silently on others.

### Steps

1. **Define the topic precisely.** Open with a technically accurate 2–4 sentence definition. State the subfield(s) it belongs to. If the term is overloaded, acknowledge dominant usages.

2. **Establish context and significance.** Why does this topic matter? Situate historically and in the current landscape. Cite foundational works. Quantify significance where possible.

3. **Survey the core content.** Organize into logical subsections with H3 headings. For each:
   - State key claims, mechanisms, methods, or findings
   - Support every substantive claim with an inline citation: (Author, Year)
   - Prefer specific numbers and benchmarks over vague qualifiers
   - Where expert consensus exists, say so. Where it doesn't, present competing positions fairly.

4. **Identify current state and open questions.** Dedicate a section to:
   - What is well-established (high confidence)
   - What is actively debated
   - What remains unknown or poorly studied
   - Emerging directions (last 2–3 years)

5. **Compile references.** Real sources only — never fabricate titles, authors, or venues. If a claim lacks a verifiable source, mark it `[citation needed]` rather than inventing one. DOI preferred for academic sources.

### Rules
- Accuracy over coverage: if uncertain, omit or flag explicitly
- Real references only — fabricated citations are a hard failure
- Quantify when possible: replace "widely adopted" with numbers
- Be precise about uncertainty: distinguish "empirically demonstrated" from "widely believed but not confirmed"
- No filler: every sentence conveys information
- Recency matters: prioritize last 5 years unless older work is foundational

### Output Format

```
# [Topic Title]

## 1. Definition and Scope
[2–4 sentences with citations]

## 2. Background and Significance
[Historical context, importance, foundational references]

## 3. Core Survey
### 3.1 [Subsection]
[Content with inline citations]

### 3.N [As many subsections as needed]

## 4. Current State and Open Questions
### 4.1 Established Consensus
### 4.2 Active Debates
### 4.3 Open Problems and Emerging Directions

## 5. References
[Bulleted list — Author(s), Year, Title, Venue/URL]

---
*Brief: [topic] | Depth: [depth] | Date: [date]*
```

No preamble. Start directly with `# [Topic Title]`.

## Quality Standards
- Every inline citation must appear in the references section
- Consensus claims must be distinguished from contested ones
- Open questions section must be populated — if nothing is unknown, the brief is too shallow
- References must be real and verifiable
