# LLM Skills Library

A collection of **reusable, copy-paste prompt skills** for Large Language Models (Grok, Claude, GPT, Gemini, Llama, etc.). I found these in various locations on the interwebs. They are untested. They may crash your machine or create a temporal paradox. You have been advised 😊. 

Each skill is a self-contained `.md` file containing:
- Role & instructions
- Parameterized placeholders (e.g. `{topic}`)
- Strict step-by-step logic
- Locked output format
- Real examples
- Notes on model compatibility & variations

Think of these as **prompt functions** — write once, reuse forever across any LLM chat or tool.

## Why This Exists

Most people rewrite the same good prompts over and over.  
This repo turns high-quality prompt engineering into portable, versioned assets — like code snippets or utility functions.

## Prompt vs Instruction vs Skill

| Term            | What it is                                                   | Lifetime                          | Reusability | Example                                                                |
| --------------- | ------------------------------------------------------------ | --------------------------------- | ----------- | ---------------------------------------------------------------------- |
| **Prompt**      | The full text you send to the LLM right now                  | One conversation turn             | Low         | "Summarize this in 100 words"                                          |
| **Instruction** | The "how to behave / format / think" rules                   | Per prompt or persistent (system) | Medium      | "Think step-by-step. Output only JSON. Be neutral."                    |
| **Skill**       | Packaged, reusable prompt + instructions + format + examples | Permanent, shareable              | High        | The entire `001_text_summarize.md` file — copy, fill parameters, paste |

Skills live in the sweet spot: powerful enough to be reliable, modular enough to chain or tweak.

## Quick Start

1. Browse the **[Skills Catalog](./SKILLS-CATALOG.md)** for what you need
2. Open the desired `.md` file (e.g. [Text Summarizer](./skills/core/001_text_summarize.md))
3. Copy the **Core Prompt** block (everything inside the triple-backticks)
4. Replace the `{placeholders}` with your values
5. Paste the whole thing into any LLM chat
6. Get consistent, high-quality output — every time

### Example: Quick Summarize

Copy from `001_text_summarize.md`:
