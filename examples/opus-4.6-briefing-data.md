# Opus 4.6 Briefing — Reference Data

Example reference material for use with skill **007** (Personalized Briefing).
Feed this as the `{reference_material}` parameter.

---

```yaml
model: Claude Opus 4.6
family: Claude 4.5
release_date: 2026-03-25

categories:

  - name: Model Identity and Basics
    points:
      - id: naming
        text: >
          Claude Opus 4.6 is the newest and most advanced model in Anthropic's lineup.
          It belongs to the Claude 4.5 model family. The full family currently consists of
          Claude Opus 4.6 and 4.5, Claude Sonnet 4.5, and Claude Haiku 4.5. Opus 4.6 is
          positioned as the most intelligent model Anthropic offers.
      - id: model_string
        text: >
          The API model string is "claude-opus-4-6". This replaces
          "claude-opus-4-5-20250929" as the top-tier model string.
      - id: availability
        text: >
          Available on claude.ai, the Anthropic API, AWS Bedrock, Google Cloud Vertex AI,
          and other major cloud platforms as of launch day.
      - id: context_window
        text: >
          Features a 1 million token context window, currently in beta. Previous Opus models
          had a 200k token context window. Roughly equivalent to several full-length novels,
          thousands of pages of documentation, or an entire midsized codebase at once.
      - id: output_length
        text: >
          Supports output lengths of up to 128,000 tokens, allowing large-output tasks in a
          single response.

  - name: Core Intelligence Improvements
    points:
      - id: deeper_thinking
        text: >
          Thinks more deeply and revisits its reasoning before settling on an answer. Catches
          errors in its own reasoning more often. Produces better results on harder problems
          but can add cost and latency on simpler tasks.
      - id: focus_allocation
        text: >
          Dynamically allocates attention based on difficulty — more focus on challenging parts,
          faster through straightforward parts — without being told to.
      - id: ambiguity_handling
        text: >
          Handles ambiguous problems with better judgment. When instructions are unclear or
          requirements conflict, it makes smarter decisions about how to proceed.
      - id: sustained_productivity
        text: >
          Stays productive over longer sessions with less degradation in performance as
          interactions lengthen.
      - id: planning
        text: >
          Plans more carefully before executing. Constructs better strategies for multi-step
          tasks, breaking work into logical phases.
      - id: self_correction
        text: >
          Improved at catching its own mistakes. More likely to review its own output and fix
          errors without being prompted.

  - name: Long-Context Capabilities
    points:
      - id: retrieval_from_large_documents
        text: >
          Significantly better at retrieving relevant information from large document sets.
          More accurately finds specific pieces of information across hundreds of pages.
      - id: context_rot_resistance
        text: >
          Performs markedly better at maintaining quality over long conversations. Holds and
          tracks information over hundreds of thousands of tokens with less drift.
      - id: buried_detail_detection
        text: >
          Picks up buried details that even Opus 4.5 would miss.
      - id: mrcr_benchmark
        text: >
          On MRCR v2 (8-needle 1M variant), Opus 4.6 scores 76% versus Sonnet 4.5's 18.5%.
          Anthropic's system card reports 93% at 256k tokens. Described as a qualitative shift
          in long-context usability.
      - id: reasoning_after_absorption
        text: >
          Better at reasoning after absorbing large volumes of material. Can synthesize,
          analyze, and draw conclusions from large contexts more effectively.

  - name: Benchmark Performance
    points:
      - id: terminal_bench
        text: >
          Achieves the top reported score on Terminal-Bench 2.0, an agentic coding evaluation
          testing autonomous coding in terminal environments.
      - id: humanitys_last_exam
        text: >
          Leads all frontier models on Humanity's Last Exam (HLE), a complex multidisciplinary
          reasoning test.
      - id: gdpval
        text: >
          On GDPval-AA (economically valuable knowledge work in finance, legal, and professional
          domains), outperforms GPT-5.2 by ~144 Elo points and its own predecessor by 190 Elo
          points.
      - id: browsecomp
        text: >
          Best performance on BrowseComp, measuring ability to locate hard-to-find information
          online. Multi-agent harness increased scores to 86.8%.
      - id: swe_bench
        text: >
          On SWE-bench Verified (software engineering), achieved 81.42% averaged over 25 trials.
      - id: arc_agi
        text: >
          ARC-AGI-2 scores jumped from 37.6% to 68.8% in third-party evaluations.
      - id: multilingual_coding
        text: >
          Improved multilingual coding ability across multiple programming languages.
      - id: life_sciences
        text: >
          Improved life sciences knowledge in biology, medicine, and related fields.

  - name: Knowledge Work and Everyday Tasks
    points:
      - id: professional_domains
        text: >
          State-of-the-art on real-world work tasks across financial analysis, research,
          legal work, and general knowledge work.
      - id: document_creation
        text: >
          Creates and works with documents, spreadsheets, and presentations more effectively —
          including structure, formatting, and document-type constraints.
      - id: financial_analysis
        text: >
          Can run financial analyses including processing data, performing calculations, and
          generating insights.
      - id: research_capability
        text: >
          Improved research capabilities including searching, gathering, synthesizing, and
          presenting information from multiple sources.
      - id: cowork_integration
        text: >
          Within Cowork, can apply all improved skills to handle multiple work streams
          simultaneously.

  - name: Coding and Software Engineering
    points:
      - id: coding_improvement
        text: >
          Improves on predecessor's coding across the board — writes better code, debugs more
          effectively, reviews with more insight, handles larger codebases.
      - id: larger_codebases
        text: >
          Operates more reliably in larger codebases, maintaining awareness of full structure
          and component interactions.
      - id: code_review
        text: >
          Better code review skills — identifies bugs, logic errors, performance issues, and
          style problems more accurately.
      - id: debugging
        text: >
          Improved debugging including complex root cause analysis (excels on OpenRCA benchmark).
      - id: agentic_coding
        text: >
          Sustains agentic coding tasks for longer, maintaining quality and direction over
          more cycles.
      - id: cybersecurity_coding
        text: >
          Enhanced cybersecurity abilities. Anthropic is accelerating cyberdefensive uses
          including finding and patching vulnerabilities in open-source software.

  - name: Agentic Behavior and Autonomy
    points:
      - id: longer_agentic_tasks
        text: >
          Sustains agentic tasks for longer periods without degradation. Maintains goals,
          context, and quality over more steps and longer timeframes.
      - id: autonomy_without_handholding
        text: >
          Early access partners noted the model's ability to work autonomously with less
          frequent check-ins, clarifications, and corrections.
      - id: success_where_others_failed
        text: >
          Partners reported Opus 4.6 succeeded on tasks where previous models failed entirely —
          crossing capability thresholds, not just incremental improvement.
      - id: team_workflow_impact
        text: >
          Partners noted the model changed how their teams work, altering established workflows
          and division of labor.

  - name: Safety and Alignment
    points:
      - id: safety_maintained
        text: >
          Intelligence gains do not come at the cost of safety. Low rate of misaligned behaviors
          (deception, sycophancy, encouragement of delusions, cooperation with misuse).
      - id: alignment_parity
        text: >
          Just as well-aligned as Opus 4.5, which was Anthropic's most-aligned frontier model
          to date.
      - id: lowest_over_refusals
        text: >
          Lowest rate of over-refusals of any recent Claude model. More useful and less
          frustrating without being less safe.
      - id: comprehensive_safety_testing
        text: >
          Most comprehensive safety evaluations Anthropic has run, including new evaluations
          for user wellbeing, complex refusal tests, and new interpretability methods.
      - id: cybersecurity_safeguards
        text: >
          Six new cybersecurity probes developed to track potential misuse. Accelerating
          cyberdefensive applications.

  - name: API and Developer Platform Changes
    points:
      - id: adaptive_thinking
        text: >
          Previously binary (thinking on/off). Now Claude decides on its own when deeper
          reasoning helps. Developers can adjust effort level to control this.
      - id: effort_levels
        text: >
          Four effort levels: low, medium, high (default), max. Lower = faster and cheaper
          for simple tasks. Higher = deeper reasoning for hard problems.
      - id: context_compaction
        text: >
          New beta feature. Automatically summarizes and replaces older context when
          approaching limits, allowing longer agentic tasks without hitting the context ceiling.
      - id: one_million_context_api
        text: >
          1M context available via API in beta. Premium pricing for prompts exceeding 200k
          tokens: $10/M input, $37.50/M output (vs standard $5/$25).
      - id: output_128k
        text: >
          128k output token support for large-output tasks in a single API call.
      - id: us_only_inference
        text: >
          US-only inference available at 1.1x standard pricing for compliance and data
          sovereignty needs.

  - name: Product Updates
    points:
      - id: agent_teams_claude_code
        text: >
          Claude Code now supports agent teams (research preview). Multiple agents work in
          parallel and coordinate autonomously. Best for independent, read-heavy work like
          codebase reviews. Users can take over any subagent with Shift+Up/Down or tmux.
      - id: claude_in_excel
        text: >
          Claude in Excel handles harder tasks, plans before acting, ingests unstructured data
          and infers structure, handles multi-step changes in one pass.
      - id: claude_in_powerpoint
        text: >
          Claude in PowerPoint is new (research preview). Creates presentations reading your
          layouts, fonts, and slide masters to stay on brand. Available for Max, Team, and
          Enterprise plans.
      - id: cowork_update
        text: >
          Within Cowork, Opus 4.6 applies all improved capabilities across multiple
          simultaneous tasks.

  - name: Pricing and Availability
    points:
      - id: standard_pricing
        text: Standard API pricing — $5/M input tokens, $25/M output tokens.
      - id: premium_context_pricing
        text: Premium pricing for prompts exceeding 200k tokens — $10/M input, $37.50/M output.
      - id: us_only_pricing
        text: US-only inference — 1.1x standard pricing.
      - id: platform_availability
        text: >
          Available on claude.ai, Anthropic API, AWS Bedrock, Google Cloud Vertex AI, and
          other major cloud platforms.
      - id: plan_availability
        text: >
          Claude in PowerPoint: Max, Team, and Enterprise plans. Claude Code agent teams:
          research preview. 1M context window and context compaction: beta.
```
