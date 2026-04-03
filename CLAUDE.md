# LLM Skills Library — Project Guide

## What This Repo Is
A collection of reusable, parameterized prompt "skills" for LLMs. Each skill is a self-contained `.md` file with frontmatter, parameters, a core prompt, output format, and notes. Think of them as prompt functions — write once, reuse across any model.

## Repo Structure
```
skills/
├── core/            (001–006)  General-purpose skills (summarize, brainstorm, extract, etc.)
├── writing/         (011–013)  Email, tone rewriting, user stories
├── analysis/        (021–022)  Sentiment, pros/cons
├── transformation/  (031–032)  Translation, format conversion
├── research/        (041–042)  Topic briefs, person profiles
├── strategy/        (051–055)  TAM/SAM/SOM, SWOT, market entry, positioning, demand validation
├── learning/        (061–065)  Feynman technique, fast learning plans, quizzes, resources, progression maps
├── meta/            (091–092)  Skill chaining, LLM output debugging
inbox/                          Raw/unrefined prompts before they become skills
research/                       Output from research skill executions
examples/                       Example outputs
_template.md                    Canonical skill file template
SKILLS-CATALOG.md               Master index of all skills
```

## Skill File Conventions
- **Filename:** `{NNN}_{snake_case_name}.md` — number is the skill_id
- **ID ranges:** core 001–009, writing 011–019, analysis 021–029, transformation 031–039, research 041–049, strategy 051–059, learning 061–069, meta 091–099
- **Frontmatter:** YAML between `---` fences — must include skill_id, name, version, category, tags, description, compatible_models, last_updated, change_log
- **Sections (in order):** Parameters → Core Prompt → Output format → Examples (optional) → Notes / Tips / Variations
- **Placeholders:** Use `{snake_case}` syntax (e.g. `{target_market}`, `{price}`) — never `[YOUR X]` or `<X>`
- **Template:** Always start new skills from `_template.md`

## When Creating or Editing Skills
- Read `_template.md` first to match the canonical structure
- Assign the next available ID within the category range
- Every skill must have: a role line, numbered steps, explicit rules, and a locked output format
- Include at least one example for any skill at version 1.0+
- Update `SKILLS-CATALOG.md` when adding a new skill
- Cross-reference related skills by ID in the Notes section (e.g. "Pair with **051**")

## Slash Commands
Slash commands in `.claude/commands/` invoke skills directly. They read the skill file, substitute `$ARGUMENTS` into parameters, and execute. When creating new slash commands, follow the pattern in `research-topic.md`.

## Quality Standards
- Prompts must be model-agnostic where possible (note model-specific behavior in Notes)
- No fabricated citations — research skills must use web search for real sources
- Every substantive claim in a skill's output format should demand evidence or specificity
- Prefer sharp, opinionated analytical framing over generic templates
- Skills should produce outputs that are actionable, not just informative

## Style
- Concise, direct language — no filler or throat-clearing
- Em dashes for asides, not parentheses
- Use tables for structured comparisons
- Markdown throughout — skills are designed to render well in any markdown viewer
