---
skill_id: 041
name: Topic Research Brief
version: 1.0
category: research
tags: [research, citations, references, literature, survey, academic, technical, synthesis]
description: Produce a structured, citation-backed research brief on any topic — deeper than Wikipedia, lighter than a full paper.
compatible_models: [Claude 4/4.5, GPT-4o, Grok-2, Gemini 1.5 Pro — any model with strong reasoning and web/retrieval access]
last_updated: 2026-03-03
change_log:
  - 1.0 (2026-03-03) — Initial version
model: opus 4.6
---

# Skill: Topic Research Brief
**Version:** 1.0
**Short Description:** Generate a structured, technically precise research brief on a given topic — with inline citations, a formal reference list, and clear separation of established consensus from open questions.

## Parameters (replace these placeholders in your copy)
- `{topic}`               : The subject to research — a concept, technology, phenomenon, method, debate, etc. (required)
- `{scope}`               : Boundary or angle — e.g. "focus on post-2020 developments", "limit to biomedical applications", "compare approaches X and Y" (optional, default: general survey of the topic)
- `{depth}`               : One of: "overview" (~1,500 words), "standard" (~3,000 words), "deep" (~5,000+ words) (optional, default: standard)
- `{audience}`            : Target reader — e.g. "working engineers", "graduate students", "informed generalists", "domain experts" (optional, default: technically literate non-specialist)
- `{citation_style}`      : Reference format — e.g. "APA 7", "IEEE", "Chicago author-date", "numbered" (optional, default: APA 7)
- `{num_sources_min}`     : Minimum number of distinct references to include (optional, default: 12)

## Core Prompt (copy-paste this block into any LLM chat)

You are a senior research analyst with deep expertise across the sciences, engineering, and technology. Your task is to produce a structured research brief on the topic below — something more rigorous and citation-dense than a Wikipedia article, but more accessible and concise than a full academic paper.

**Topic:** {topic}
**Scope:** {scope}
**Depth:** {depth}
**Audience:** {audience}
**Citation style:** {citation_style}
**Minimum sources:** {num_sources_min}

Follow these steps exactly:

1. **Define the topic precisely.** Open with a concise, technically accurate definition or framing (2–4 sentences). State the subfield(s) it belongs to. If the term is overloaded or contested, acknowledge the dominant usages.

2. **Establish context and significance.** Why does this topic matter? Situate it historically and in the current landscape. Cite foundational or seminal works. Quantify significance where possible (market size, adoption rates, mortality impact, performance benchmarks — whatever is appropriate).

3. **Survey the core content.** This is the main body. Organize it into logical subsections with clear H3 headings. For each subsection:
   - State the key claims, mechanisms, methods, or findings.
   - Support every substantive claim with an inline citation: (Author, Year) or [N] depending on {citation_style}.
   - Where data exists, prefer specific numbers, effect sizes, or benchmarks over vague qualifiers.
   - Where expert consensus exists, say so explicitly. Where it does not, present the competing positions fairly.

4. **Identify current state and open questions.** Dedicate a section to:
   - What is well-established (high confidence).
   - What is actively debated or under investigation.
   - What remains unknown or poorly studied.
   - Emerging directions or recent breakthroughs (last 2–3 years).

5. **Compile the reference list.** At the end, provide a formal reference list in {citation_style} format. Every inline citation must appear here; every entry here must be cited in the text. Include:
   - Full author names (not "et al." in the reference list — use et al. only inline for 3+ authors).
   - Publication year.
   - Title.
   - Journal/conference/publisher or a stable URL (DOI preferred for journal articles).
   - For preprints, indicate the repository (e.g. arXiv, bioRxiv) and note "preprint" status.

Rules you must obey:
- **Accuracy over coverage.** If you are uncertain about a fact, either omit it or flag it explicitly as uncertain. Never present a guess as established fact.
- **Real references only.** Every citation must refer to a work that actually exists. Do not fabricate authors, titles, or publication venues. If you cannot identify a real source for a claim, either drop the claim or mark it as "[citation needed]".
- **Prefer primary sources.** Cite original research papers, technical reports, and official specifications over secondary summaries, blog posts, or news articles. Use secondary sources only for historical context or when the primary source is inaccessible.
- **Quantify when possible.** Replace vague language ("significantly improved", "widely adopted") with numbers, percentages, or concrete comparisons wherever the data exists.
- **Be precise about uncertainty.** Distinguish clearly between: empirically demonstrated, theoretically predicted, widely believed but not yet confirmed, and speculative.
- **No filler.** Every sentence should convey information or provide necessary framing. Cut throat on hedging, throat-clearing, and restatement.
- **Recency matters.** Prioritize recent work (last 5 years) unless older work is foundational. Note when findings may have been superseded.

Output **only** in this exact format — no preamble, no meta-commentary:

# {Topic Title}

## 1. Definition and Scope
[Precise definition and framing — 2–4 sentences with citations]

## 2. Background and Significance
[Historical context, importance, foundational references — ~15–20% of total length]

## 3. Core Survey
### 3.1 [Subsection Title]
[Content with inline citations]

### 3.2 [Subsection Title]
[Content with inline citations]

### 3.N [As many subsections as needed]
[Content with inline citations]

## 4. Current State and Open Questions
### 4.1 Established Consensus
[What is well-supported]

### 4.2 Active Debates
[Competing positions with citations for each side]

### 4.3 Open Problems and Emerging Directions
[What is unknown, underexplored, or newly emerging]

## 5. References
[Formatted reference list — {citation_style}]

---
*Brief generated: [date] | Topic: {topic} | Depth: {depth} | Minimum sources: {num_sources_min}*

## Example Usage 1 — Standard Technical Topic

**Filled Parameters:**
{topic}: Retrieval-Augmented Generation (RAG) for large language models
{scope}: focus on architectural patterns and evaluation methods
{depth}: standard
{audience}: working engineers
{citation_style}: APA 7
{num_sources_min}: 12

**Expected Output (abbreviated):**

# Retrieval-Augmented Generation (RAG) for Large Language Models

## 1. Definition and Scope
Retrieval-Augmented Generation (RAG) is a hybrid architecture that augments a parametric language model with a non-parametric retrieval component, enabling the model to condition its outputs on documents fetched from an external corpus at inference time (Lewis et al., 2020). The approach addresses well-known LLM failure modes — hallucination, knowledge staleness, and lack of source attribution — by grounding generation in retrieved evidence. RAG sits at the intersection of information retrieval and natural language generation, with applications spanning open-domain question answering, enterprise search, and knowledge-intensive dialogue.

## 2. Background and Significance
The foundational RAG architecture was introduced by Lewis et al. (2020) at Facebook AI Research, combining a DPR retriever (Karpukhin et al., 2020) with a BART generator. [...]

## 3. Core Survey
### 3.1 Retrieval Mechanisms
Modern RAG systems typically employ dense passage retrieval using bi-encoder architectures. DPR (Karpukhin et al., 2020) demonstrated that learned dense representations outperform BM25 on open-domain QA by 9–19% top-20 retrieval accuracy. Subsequent work introduced ColBERT (Khattab & Zaharia, 2020) for late-interaction scoring, reducing latency while preserving effectiveness. [...]

### 3.2 Generation Architectures
[...]

### 3.3 Evaluation Frameworks
Evaluation of RAG systems remains fragmented. RAGAS (Es et al., 2024) proposed metrics for faithfulness, answer relevance, and context precision. RGB (Chen et al., 2024) introduced a benchmark testing noise robustness, negative rejection, information integration, and counterfactual resilience. [...]

## 4. Current State and Open Questions
### 4.1 Established Consensus
- RAG reduces hallucination rates by 30–70% compared to closed-book generation across most benchmarks (Shuster et al., 2021).
- Chunk size, overlap, and retrieval top-k are high-sensitivity hyperparameters (Wang et al., 2024).

### 4.2 Active Debates
- **Sparse vs. dense vs. hybrid retrieval:** Hybrid approaches (BM25 + dense) often outperform either alone (Ma et al., 2024), but the margin is task-dependent. [...]

### 4.3 Open Problems and Emerging Directions
- Multi-hop reasoning across retrieved passages remains unreliable. [...]
- Agentic RAG — where the model iteratively decides what to retrieve — shows promise but lacks standardized evaluation. [...]

## 5. References
Es, S., James, J., Espinosa-Anke, L., & Schockaert, S. (2024). RAGAS: Automated evaluation of retrieval augmented generation. *Proceedings of the 18th Conference of the European Chapter of the ACL*, 150–163.
Karpukhin, V., Oguz, B., Min, S., Lewis, P., Wu, L., Edunov, S., Chen, D., & Yih, W. (2020). Dense passage retrieval for open-domain question answering. *Proceedings of EMNLP 2020*, 6769–6781.
Lewis, P., Perez, E., Piktus, A., Petroni, F., Karpukhin, V., Goyal, N., Küttler, H., Lewis, M., Yih, W., Rocktäschel, T., Riedel, S., & Kiela, D. (2020). Retrieval-augmented generation for knowledge-intensive NLP tasks. *Advances in Neural Information Processing Systems*, 33, 9459–9474.
[...]

## Example Usage 2 — Deep Dive with Narrow Scope

**Filled Parameters:**
{topic}: CRISPR off-target effects
{scope}: focus on detection methods and mitigation strategies, limit to mammalian systems
{depth}: deep
{audience}: graduate students in molecular biology
{citation_style}: numbered
{num_sources_min}: 20

**Expected Output (abbreviated):**

# CRISPR Off-Target Effects: Detection and Mitigation in Mammalian Systems

## 1. Definition and Scope
Off-target effects in CRISPR-Cas systems refer to unintended cleavage or modification at genomic loci sharing partial sequence complementarity with the guide RNA (gRNA) [1]. In mammalian systems, these events are a primary safety concern for both research and therapeutic applications, as they can introduce deleterious mutations, activate oncogenes, or disrupt essential genes [2]. This brief surveys methods for detecting off-target activity and strategies for reducing it, limited to mammalian (primarily human and mouse) contexts.

## 2. Background and Significance
The original demonstration of SpCas9 genome editing in human cells [3] was followed rapidly by reports of off-target cleavage at sites with up to 5 mismatches to the gRNA [4]. Whole-genome sequencing of edited cells revealed off-target mutation rates ranging from <0.1% to >50% depending on gRNA design and delivery method [5]. For clinical translation — particularly in ex vivo gene therapies now in trials — off-target profiling is required by FDA guidance [6]. [...]

## 3. Core Survey
### 3.1 Unbiased Detection Methods
GUIDE-seq [7] remains the most widely used unbiased detection method, integrating short double-stranded oligodeoxynucleotides at cleavage sites for subsequent identification. Tsai et al. [7] reported detection sensitivity down to 0.1% indel frequency in human cells. DISCOVER-Seq [8] exploits endogenous DNA repair factor MRE11 binding as a real-time marker of Cas9 activity, avoiding exogenous DNA integration. [...]

### 3.2 In Silico Prediction
[...]

### 3.3 Mitigation Strategies
High-fidelity Cas9 variants — including eSpCas9(1.1) [12], SpCas9-HF1 [13], HypaCas9 [14], and evoCas9 [15] — reduce off-target cleavage by 10- to 10,000-fold while retaining >70% on-target activity in most tested loci. [...]

[...]

## 5. References
[1] Hsu, P. D., Scott, D. A., Weinstein, J. A., Ran, F. A., Konermann, S., Agarwala, V., Li, Y., Fine, E. J., Wu, X., Shalem, O., Cradick, T. J., Marraffini, L. A., Bao, G., & Zhang, F. (2013). DNA targeting specificity of RNA-guided Cas9 nucleases. *Nature Biotechnology*, 31(9), 827–832.
[2] Fu, Y., Foden, J. A., Khayter, C., Maeder, M. L., Reyon, D., Joung, J. K., & Sander, J. D. (2013). High-frequency off-target mutagenesis induced by CRISPR-Cas nucleases in human cells. *Nature Biotechnology*, 31(9), 822–826.
[...]

## Notes / Tips / Variations
- **Strong on:** Claude 4/4.5 (excellent at structured output and citation discipline), GPT-4o (strong synthesis), Grok-2 with web search enabled (can retrieve real-time sources)
- **Weak on:** Models without retrieval/web access will have a harder time producing verifiable citations — pair with manual reference checking. Smaller models may fabricate references.
- **Common tweaks:**
  - Want a slide-ready version? Add to rules: "After the references section, include a 'Key Takeaways' section with 5–7 bullet points suitable for a presentation slide."
  - Need only the reference list? Change output instructions to: "Output only the reference list with one-sentence annotation per entry (annotated bibliography format)."
  - Controversial or politicized topic? Add to rules: "Present all major perspectives with their strongest supporting evidence. Do not adopt an editorial position."
  - Want structured data? Add: "After the references, output a JSON array of all citations: `[{"id": 1, "authors": "...", "year": 2024, "title": "...", "venue": "...", "doi": "..."}]`"
- **Critical caveat:** LLMs can and do fabricate plausible-sounding references. Always verify the reference list against a real database (Google Scholar, Semantic Scholar, PubMed) before relying on it. The "[citation needed]" instruction mitigates but does not eliminate this failure mode.
- **Chaining:** Pairs well with **001** (summarize the brief into an executive summary), **002** (brainstorm research directions from open questions), or **022** (pros/cons evaluation of competing approaches identified in the survey)
