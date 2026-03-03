---
skill_id: 042
name: Person Research Profile
version: 1.0
category: research
tags: [research, biography, background, people, profile, public-figures, citations]
description: Research and compile a comprehensive, source-backed profile on any prominent figure — across any domain.
compatible_models: [Claude 4/4.5, GPT-4o, Grok-2, Gemini 1.5 Pro — any model with strong reasoning and web/retrieval access]
last_updated: 2026-03-03
change_log:
  - 1.0 (2026-03-03) — Initial version; generalized from AI-specific researcher prompt
model: opus 4.6
---

# Skill: Person Research Profile
**Version:** 1.0
**Short Description:** Produce a comprehensive, source-backed profile of any prominent figure — researcher, executive, policymaker, artist, athlete, or any public person — with cross-verified facts, structured output, and full citations.

## Parameters (replace these placeholders in your copy)
- `{person_name}`          : Full name of the person to profile (required)
- `{domain}`               : The field or context — e.g. "artificial intelligence", "US politics", "jazz music", "venture capital", "neuroscience", "professional basketball" (required)
- `{current_year}`         : Year to use as the "as of" date for the profile (optional, default: 2026)
- `{depth}`                : One of: "concise" (~800–1,200 words), "standard" (~1,500–2,500 words), "comprehensive" (~2,500–4,000 words) (optional, default: standard)
- `{focus}`                : Optional emphasis — e.g. "technical contributions", "leadership and management style", "policy positions", "artistic evolution", "controversies", "mentorship and influence" (optional, default: balanced coverage across all sections)
- `{num_sources_min}`      : Minimum number of distinct references to include (optional, default: 10)

## Core Prompt (copy-paste this block into any LLM chat)

You are a senior research analyst who combines deep domain knowledge with the meticulous, source-triangulating discipline of an intelligence analyst — but **strictly for educational, academic, and public-interest purposes only**. Your task is to produce a comprehensive, objective profile of a prominent figure.

**Person:** {person_name}
**Domain:** {domain}
**As of:** {current_year}
**Depth:** {depth}
**Focus:** {focus}
**Minimum sources:** {num_sources_min}

Follow these steps exactly:

### Step 1 — Research Protocol (follow in order for best accuracy)

1. **Begin with primary sources:** personal website, institutional profile (university/company/organization page), official CV or bio page, verified social media accounts, author pages (Google Scholar, arXiv, IMDB, Discogs, official league stats — whatever is relevant to {domain}).
2. **Cross-reference with authoritative secondary sources:** Wikipedia (only if it aligns with primaries), official award/honor pages, major news outlets (NYT, Nature, WSJ, BBC, domain-specific trade publications), company/organization announcements.
3. **For publications or body of work:** use the domain-appropriate index — Google Scholar/Semantic Scholar/dblp for academics, IMDB for film, Discography databases for music, patent databases for inventors, legislative records for politicians, etc.
4. **Check for recent updates:** look for {current_year} and the prior year for interviews, announcements, role changes, or new work.
5. **Explicitly flag** any major gaps, conflicting reports, or unverified claims. Never speculate or present uncertain information as fact.

### Step 2 — Compile the Profile

Cover the following sections in order. Adapt the emphasis to what is most relevant for {domain} and {focus}. If a section does not apply (e.g., "Publications" for an athlete), replace it with the domain-appropriate equivalent (e.g., "Career Statistics & Records").

**Required scope:**

1. **Background & Education** — Birth year/country if reliably sourced, formative influences, full educational timeline (degrees, institutions, mentors/advisors, thesis/dissertation if academic).

2. **Career Timeline** — Key positions, organizations, dates. Major transitions, founding roles, promotions, team changes. Current status as of {current_year}.

3. **Major Works & Contributions** — The 5–12 most significant outputs for their domain:
   - For researchers: seminal papers, architectures, algorithms, datasets — with title, year, co-authors, venue, significance, citation impact.
   - For executives/founders: companies built, products launched, deals closed, market impact.
   - For politicians/policymakers: key legislation, policy initiatives, diplomatic achievements.
   - For artists/performers: landmark albums, films, exhibitions, performances, critical reception.
   - For athletes: championships, records, signature performances, statistical milestones.
   - For any domain: use a clean table format where applicable.

4. **Current Role & Active Focus** — What they are doing now. Leadership positions, ongoing projects, recent directions, stated priorities.

5. **Broader Impact & Public Presence** — Awards and honors, notable talks/interviews/media appearances, social media presence (include @handle if prominent), influence on their field, public stances or controversies (only if well-documented), advocacy or policy work.

6. **Key Insights & Assessment** — Educational perspective only: how their background, training, and career arc shaped their contributions. What makes their work distinctive. Their lasting influence on {domain}.

If {focus} is specified, weight the corresponding section(s) more heavily without dropping other sections entirely.

### Step 3 — Format the Output

Rules you must obey:
- **Accuracy over coverage.** If you are uncertain about a fact, omit it or flag it explicitly. Never present a guess as established fact.
- **Real references only.** Every citation must refer to a source that actually exists. Do not fabricate URLs, titles, or publication details. If you cannot identify a real source for a claim, mark it as "[citation needed]".
- **Prefer primary sources.** Cite original documents, official profiles, and first-party records over secondary summaries.
- **Quantify when possible.** Replace vague qualifiers ("very influential", "widely recognized") with concrete numbers, metrics, or specific examples.
- **Be precise about uncertainty.** Distinguish between verified, widely reported, and unconfirmed.
- **No filler.** Every sentence should convey information. Cut hedging, throat-clearing, and restatement.
- **Use timelines, bullets, and tables** for readability.

Output **only** in this exact format — no preamble, no meta-commentary:

# {person_name}: {domain} Profile (as of {current_year})

## Background & Education
[Content]

## Career Timeline
[Content — use a bulleted chronological list]

## Major Works & Contributions
[Content — use a table where applicable]

## Current Role & Active Focus
[Content]

## Broader Impact, Awards & Public Presence
[Content]

## Key Insights & Assessment
[Educational perspective — how their work shaped {domain}]

## Sources
[Bulleted list of all used sources with full URLs and access notes; prioritize primary sources]

---
*Profile generated: [date] | Subject: {person_name} | Domain: {domain} | Depth: {depth} | Sources: {num_sources_min}+*

## Example Usage 1 — AI Researcher (Standard)

**Filled Parameters:**
{person_name}: Amanda Askell
{domain}: artificial intelligence
{current_year}: 2026
{depth}: standard
{focus}: (none — balanced)
{num_sources_min}: 10

**Expected Output (abbreviated):**

# Amanda Askell: Artificial Intelligence Profile (as of 2026)

## Background & Education
Amanda Askell holds a PhD in philosophy from the University of London [...]. Her academic training bridged moral philosophy and decision theory, providing a distinctive lens for her later work in AI alignment and language model behavior.

## Career Timeline
- **2018–2019** — Researcher at the Future of Humanity Institute, University of Oxford
- **2019–present** — Anthropic (Character & RLHF lead; helped define Claude's personality and behavioral guidelines)
- [...]

## Major Works & Contributions

| Year | Work | Significance | Link |
|------|------|-------------|------|
| 2021 | Claude character & system prompt design | Defined Anthropic's approach to LLM personality, honesty, and refusal behavior | [Anthropic blog] |
| 2023 | "The Claude Model Spec" (internal, later published) | Formalized how value alignment translates to model behavior at scale | [...] |
| [...] | [...] | [...] | [...] |

## Current Role & Active Focus
As of 2026, Askell leads character and alignment research at Anthropic, focusing on [...].

## Broader Impact, Awards & Public Presence
Known for her public writing on AI alignment [...]. Active on X (@AmandaAskell) [...].

## Key Insights & Assessment
Askell represents a distinctive archetype in AI: a philosopher embedded in a frontier lab [...].

## Sources
- Personal website: [...]
- Anthropic team page: [...]
- Google Scholar profile: [...]
- [...]

## Example Usage 2 — Business Leader (Concise)

**Filled Parameters:**
{person_name}: Jensen Huang
{domain}: semiconductor industry and AI computing
{current_year}: 2026
{depth}: concise
{focus}: leadership and business strategy
{num_sources_min}: 8

**Expected Output (abbreviated):**

# Jensen Huang: Semiconductor Industry and AI Computing Profile (as of 2026)

## Background & Education
Born in Tainan, Taiwan (1963). Moved to the US as a child. BS in Electrical Engineering, Oregon State University (1984). MS in Electrical Engineering, Stanford University (1992). Worked at LSI Logic and AMD before co-founding NVIDIA.

## Career Timeline
- **1993** — Co-founded NVIDIA Corporation; CEO since inception
- **1999** — Launched GeForce 256, marketed as the first "GPU"
- **2006** — Introduced CUDA, enabling general-purpose GPU computing
- **2012–present** — Pivoted NVIDIA toward AI/deep learning as a core market
- **2024–2026** — Led NVIDIA to become the world's most valuable company by market cap (briefly surpassing $3T in 2024)

## Major Works & Contributions

| Year | Contribution | Significance |
|------|-------------|-------------|
| 1993 | NVIDIA founding | Created the GPU industry category |
| 2006 | CUDA platform | Made GPUs programmable for general computing; became the foundation for modern deep learning infrastructure |
| 2016 | DGX-1 | First purpose-built deep learning supercomputer appliance |
| 2022 | H100 GPU | Became the dominant chip for LLM training worldwide |
| [...] | [...] | [...] |

## Current Role & Active Focus
CEO of NVIDIA. Current priorities include [...].

[...]

## Example Usage 3 — Athlete (Comprehensive, Focused)

**Filled Parameters:**
{person_name}: Simone Biles
{domain}: artistic gymnastics
{current_year}: 2026
{depth}: comprehensive
{focus}: competitive record and athletic innovation
{num_sources_min}: 12

**Expected Output (abbreviated):**

# Simone Biles: Artistic Gymnastics Profile (as of 2026)

## Background & Education
Born March 14, 1997, in Columbus, Ohio. Entered foster care as a young child; adopted at age 6 by grandparents Ron and Nellie Biles. Began gymnastics at age 6 during a daycare field trip. Homeschooled through high school to accommodate training schedule. [...]

## Career Timeline
- **2013** — Senior international debut; won all-around gold at World Championships (age 16)
- **2014–2015** — Consecutive World all-around titles (unprecedented three-peat achieved in 2015)
- **2016** — Rio Olympics: 4 gold medals, 1 bronze
- **2017–2020** — Hiatus from competition
- **2021** — Tokyo Olympics: withdrew from team final and multiple individual finals citing mental health ("the twisties"); returned to win bronze on beam
- **2023** — Comeback: won 6th World all-around title, extending her record
- **2024** — Paris Olympics: 3 gold medals, 1 silver [...]

## Major Works & Contributions

| Element / Achievement | Year | Significance |
|----------------------|------|-------------|
| Biles (floor) — double layout half-out | 2013 | First named skill; redefined difficulty in women's floor exercise |
| Biles II (vault) — Yurchenko double pike | 2021/2023 | First woman to land in competition; considered the most difficult vault ever performed by a woman |
| 37 World/Olympic medals combined | 2013–2024 | Most decorated gymnast in World Championship history |
| [...] | [...] | [...] |

[...]

## Notes / Tips / Variations
- **Strong on:** Claude 4/4.5 (excellent structured output, faithfulness, and hedging on uncertain facts), GPT-4o (strong synthesis), Grok-2 with web search (can retrieve real-time data)
- **Weak on:** Models without retrieval/web access will struggle with current-year facts and accurate source URLs — pair with manual verification. Smaller models may fabricate biographical details.
- **Common tweaks:**
  - Want a one-paragraph bio instead? Change output format to: "Output a single paragraph of ~150 words suitable for a conference program or speaker introduction."
  - Need a comparison? Run this skill for two people in the same domain, then use **022** (Pros/Cons Evaluation) to compare their approaches or contributions.
  - Want structured data? Add: "After the Sources section, output a JSON object: `{\"name\": \"...\", \"domain\": \"...\", \"birth_year\": ..., \"current_role\": \"...\", \"key_works\": [...]}`"
  - Controversial figure? Add to rules: "Present all major perspectives on contested actions or statements with their strongest supporting evidence. Do not adopt an editorial position."
  - Deceased subject? Replace "Current Role & Active Focus" with "Legacy & Posthumous Influence" in the output format.
- **Critical caveat:** LLMs can and do fabricate plausible-sounding biographical details, publication titles, and dates. Always verify key facts against primary sources before relying on this output. The "[citation needed]" instruction mitigates but does not eliminate this failure mode.
- **Chaining:** Pairs well with **001** (summarize the profile into a short bio), **041** (deep-dive on a topic they contributed to), or **002** (brainstorm research questions inspired by their work)
