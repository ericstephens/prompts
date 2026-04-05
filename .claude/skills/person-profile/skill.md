---
name: person-profile
description: Research and compile a comprehensive, source-backed profile on any prominent figure — across any domain
user_invocable: true
---

# Skill: Person Research Profile

## Purpose
Produce a comprehensive, objective profile of any prominent figure: researcher, executive, policymaker, artist, athlete, or other public person. Cross-verified facts, structured output, real citations. Directly useful for creating zk people notes.

## Trigger Phrases
- "Research [person] for me"
- "Profile on [person]"
- "Who is [person]?"
- "Build a profile on [person name]"
- "Background on [person] in [domain]"
- "Create a person note for [name]"

---

## Instructions for Claude

### Parameters
Collect if not provided:
- **person_name** (required): Full name of the person to profile
- **domain** (required): Field or context — e.g. "artificial intelligence", "US politics", "jazz music", "venture capital"
- **depth** (optional, default "standard"): concise (~800 words) | standard (~1,500 words) | comprehensive (~3,000 words)
- **focus** (optional): Emphasis — e.g. "technical contributions", "leadership style", "policy positions", "controversies"
- **current_year** (optional, default: current year): Year to use as the "as of" date

If person_name and domain are not provided, ask for them.

### Steps

**Step 1 — Research Protocol**
1. Begin with primary sources: personal website, institutional profile, official CV, verified social accounts
2. Cross-reference with authoritative secondary sources: major news outlets, award pages, official organizational announcements
3. For body of work: use the domain-appropriate index — Google Scholar for academics, IMDB for film, legislative records for politicians, etc.
4. Check for recent updates from the current and prior year
5. Explicitly flag major gaps, conflicting reports, or unverified claims — never speculate

**Step 2 — Compile the Profile**

Cover these sections, adapting to what's most relevant for the domain:

1. **Background & Education** — birth year/country if reliably sourced, formative influences, full educational timeline
2. **Career Timeline** — key positions, organizations, dates, major transitions; bulleted chronological list
3. **Major Works & Contributions** — 5–12 most significant outputs for the domain; use a table where applicable
4. **Current Role & Active Focus** — what they are doing now, stated priorities
5. **Broader Impact & Public Presence** — awards, notable talks, media presence, influence on field, well-documented controversies
6. **Key Insights & Assessment** — educational perspective on how their background shaped their contributions; what makes their work distinctive

If `focus` is specified, weight the corresponding section(s) more heavily without dropping others.

### Rules
- **Accuracy over coverage**: if uncertain about a fact, omit or flag it explicitly — never present a guess as fact
- **Real references only**: every citation must refer to a source that actually exists; mark unverifiable claims as `[citation needed]`
- **Quantify**: replace "widely recognized" with specific numbers, metrics, or named examples
- **No filler**: every sentence conveys information
- **Flag uncertainty**: distinguish "verified", "widely reported", and "unconfirmed"

**Critical caveat**: LLMs can fabricate plausible-sounding biographical details, dates, and publication titles. Always verify key facts before relying on this output. The `[citation needed]` instruction reduces but does not eliminate this risk.

### Output Format

```
# [Person Name]: [Domain] Profile (as of [Year])

## Background & Education
[Content]

## Career Timeline
- [Year] — [Role/Event]
- ...

## Major Works & Contributions
| Year | Work | Significance |
|------|------|-------------|
| ...  | ...  | ...         |

## Current Role & Active Focus
[Content]

## Broader Impact & Public Presence
[Content]

## Key Insights & Assessment
[Educational perspective only]

## Sources
- [Primary source — URL]
- [Secondary source — URL]
- ...

---
*Profile: [person_name] | Domain: [domain] | Depth: [depth] | Date: [date]*
```

No preamble. Start directly with `# [Person Name]:`.

## Quality Standards
- Career timeline must be chronological and specific — no gaps without explanation
- Major works table must include significance column, not just titles
- Sources section must list real, verifiable URLs — no fabricated links
- Any section without verifiable information must say so explicitly rather than fill with plausible-sounding content
