# LLM Skills Catalog

This is the master index of all reusable prompt skills in the library.  
Each skill is a self-contained `.md` file in `/skills/` that you can copy-paste directly into any LLM chat (Grok, Claude, GPT, Gemini, etc.).

Last updated: March 2026  
Total skills: 2 (growing…)

## How to Use This Catalog
- **ID** → Unique number + short filename hint
- **Name** → Clickable link to the file (GitHub relative path)
- **Category** → High-level grouping
- **Tags** → For quick filtering
- **Description** → One-line purpose
- **Version** → Current version of the skill

## Core Skills

| ID  | Name                          | Category | Tags                              | Description                                              | Version | File Path                              |
|-----|-------------------------------|----------|-----------------------------------|----------------------------------------------------------|---------|----------------------------------------|
| 001 | [Text Summarizer](./skills/core/001_text_summarize.md)          | core     | summarization, extraction, concise, compression | Condense long text into faithful summary + key points   | 1.1     | skills/core/001_text_summarize.md      |
| 002 | [Idea Brainstorm](./skills/core/002_idea_brainstorm.md)         | core     | ideation, creativity, generation, divergent-thinking | Generate original, diverse, actionable ideas for any topic | 1.0     | skills/core/002_idea_brainstorm.md     |
| 003 | Extract Entities              | core     | extraction, NER, structured-data  | Pull named entities, dates, numbers, products from text | 1.0 (planned) | skills/core/003_extract_entities.md    |
| 004 | Code Review                   | core     | code, debugging, quality          | Analyze code for bugs, style, security, improvements    | —       | skills/core/004_code_review.md         |
| 005 | Chain of Thought              | core     | reasoning, step-by-step           | Force detailed step-by-step reasoning on complex problems | —       | skills/core/005_chain_of_thought.md    |

## Writing Skills

| ID  | Name                          | Category  | Tags                              | Description                                              | Version | File Path                              |
|-----|-------------------------------|-----------|-----------------------------------|----------------------------------------------------------|---------|----------------------------------------|
| 011 | Rewrite / Tone Shift          | writing   | rewriting, style, tone            | Rewrite text in a different tone, formality, length     | —       | skills/writing/011_rewrite_tone.md     |
| 012 | Write Email                   | writing   | email, communication, professional | Craft effective emails (cold, follow-up, complaint…)    | —       | skills/writing/012_write_email.md      |
| 013 | Create User Story             | writing   | agile, product, requirements      | Generate INVEST-compliant user stories + acceptance criteria | —       | skills/writing/013_create_user_story.md |

## Analysis Skills

| ID  | Name                          | Category  | Tags                              | Description                                              | Version | File Path                              |
|-----|-------------------------------|-----------|-----------------------------------|----------------------------------------------------------|---------|----------------------------------------|
| 021 | Sentiment Analysis            | analysis  | sentiment, emotion, opinion       | Detect overall sentiment + key emotional drivers        | —       | skills/analysis/021_sentiment_analysis.md |
| 022 | Pros / Cons Evaluation        | analysis  | decision-making, tradeoffs        | Balanced pros/cons list + weighted recommendation       | —       | skills/analysis/022_pros_cons_evaluation.md |

## Transformation Skills

| ID  | Name                          | Category       | Tags                       | Description                                              | Version | File Path                                 |
|-----|-------------------------------|----------------|----------------------------|----------------------------------------------------------|---------|-------------------------------------------|
| 031 | Natural Language Translate    | transformation | translation, multilingual  | High-quality translation with tone preservation         | —       | skills/transformation/031_translate_natural.md |
| 032 | JSON ↔ Markdown               | transformation | formatting, structured     | Convert between free text/markdown and clean JSON       | —       | skills/transformation/032_json_to_markdown.md  |

## Meta / Utility Skills

| ID  | Name                          | Category | Tags                       | Description                                              | Version | File Path                              |
|-----|-------------------------------|----------|----------------------------|----------------------------------------------------------|---------|----------------------------------------|
| 091 | Combine / Chain Skills        | meta     | orchestration, workflow    | Instructions for chaining 2+ skills in one prompt       | —       | skills/meta/091_combine_skills.md      |
| 092 | Debug LLM Output              | meta     | troubleshooting, critique  | Analyze why an LLM response failed + how to fix prompt  | —       | skills/meta/092_debug_llm_output.md    |

## Status Legend
- **1.x** → Actively maintained, tested across models
- **—**   → Placeholder / planned / in progress
- **experimental** → Early version — use with caution

## Quick Start Examples
- Summarize a long article → Use **001**
- Need fresh ideas for a project → Use **002**
- Want to rewrite an email more professionally → Use **011**
- Chain summarize → brainstorm → Use **001** then **002** (or **091**)

Want to contribute?  
→ Duplicate `_template.md`, fill it out, add a row here, and open a PR!

