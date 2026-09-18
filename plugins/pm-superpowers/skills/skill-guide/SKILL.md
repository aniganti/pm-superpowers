---
name: skill-guide
description: >
  Guide to all available PM Superpowers skills, recommended workflows, and how
  to get the most out of the plugin. Trigger phrases: "what can you do",
  "help me with PM", "which skill should I use", "pm superpowers help",
  "list skills", "what skills are available", "skill guide"
argument-hint: ""
---

# Skill Guide

You are the guide to the PM Superpowers plugin. When invoked, help the PM understand what skills are available, how they connect, and which one to use for their current need.

This skill was formerly `using-pm-superpowers`.

## Available Skills

| Skill | What It Does | Best For |
|---|---|---|
| **find-your-moat** | Thin first-pass moat read on the user's real product (4 of 8 types) | **Start here for first value** — just installed, "find my moat", or "where do I start" when they want a real pass not a menu |
| **strategy** | Interactive 6-step product strategy framework (Rumelt's kernel) | Building a comprehensive product strategy from scratch or reviewing an existing one |
| **competitive-landscape** | Competitor profiling, positioning maps, whitespace identification | Understanding your competitive environment and finding opportunities |
| **vrio-analysis** | Assess resources/capabilities for sustained competitive advantage | Evaluating which internal strengths are truly defensible |
| **strategic-moat** | Defensibility assessment across 8 moat types | **Full defensibility** — complete 8-type assessment and how to deepen moats |
| **product-ecosystem** | Value chain mapping, integration opportunities, portfolio coherence | Analyzing your product's position in the broader ecosystem |
| **pre-mortem** | Risk analysis with Tigers/Paper Tigers/Elephants framework | Stress-testing a product launch or major initiative before it ships |
| **prompt-builder** | Guided AI prompt creation through 9 structured questions | Crafting effective prompts for any AI tool |
| **verification** | Quality check on any strategy artifact before sharing | Ensuring your documents are complete, consistent, and ready for stakeholders |
| **stakeholder-alignment** | Tailored briefing docs, FAQs, and workshop agendas per audience | Preparing to present strategy to different stakeholder groups |
| **decision-log** | Structured capture of product decisions with reasoning | Building institutional memory and preventing re-litigation of settled decisions |
| **prioritization** | Framework-driven feature/initiative prioritization (RICE, ICE, weighted scoring) | Ranking a backlog of features or initiatives with evidence-based scoring |

## Recommended Workflows

### First value after install

Use this when they just installed or want value on their product now:

```
find-your-moat → strategic-moat  (or competitive-landscape / vrio-analysis)
```

### Full Strategy Pipeline

Use this when building a product strategy from the ground up:

```
competitive-landscape → vrio-analysis → strategic-moat → strategy → pre-mortem
```

Each skill's output feeds into the next. Start with external landscape, move to internal capabilities, synthesize into strategy, then stress-test.

### Launch Readiness

Use this when preparing to launch a product or major feature:

```
pre-mortem → stakeholder-alignment
```

### Quick Assessments

Use individual skills standalone when you need a focused analysis:
- Just installed / first value on their product? → `find-your-moat`
- Know your competitors? → `competitive-landscape`
- Full defensibility (all 8 moat types)? → `strategic-moat`
- Prioritizing features? → `prioritization`
- Writing a prompt? → `prompt-builder`

### After Any Analysis

Always consider running `verification` before sharing artifacts with stakeholders.

## How to Invoke Skills

Skills are triggered by natural language. Just describe what you need:

- "Find my moat for [product]"
- "I just installed — where do I start?"
- "Help me build a product strategy for [product]"
- "Run a competitive analysis on [company]"
- "Do a VRIO analysis for [product]"
- "How defensible is [product]?" (full 8-type assessment → `strategic-moat`)
- "Run a pre-mortem on this launch plan"
- "Help me prioritize these features"

You can also reference skills directly by name.

## Where Outputs Are Saved

All artifacts are saved to the `docs/` directory:

| Skill | Save Location |
|---|---|
| find-your-moat | `docs/strategic-moat/YYYY-MM-DD-find-moat-<slug>.md` |
| strategy | `docs/strategies/YYYY-MM-DD-<slug>.md` |
| competitive-landscape | `docs/competitive-analyses/YYYY-MM-DD-competitive-landscape-<name>.md` |
| vrio-analysis | `docs/vrio-analyses/YYYY-MM-DD-vrio-<product-name>.md` |
| strategic-moat | `docs/strategic-moat/YYYY-MM-DD-moat-<product-name>.md` |
| product-ecosystem | `docs/ecosystem-strategies/YYYY-MM-DD-ecosystem-strategy-<name>.md` |
| pre-mortem | `docs/pre-mortems/YYYY-MM-DD-pre-mortem-<name>.md` |
| prompt-builder | `docs/prompts/YYYY-MM-DD-<slug>.md` |
| stakeholder-alignment | `docs/stakeholder-alignment/YYYY-MM-DD-alignment-<topic>.md` |
| decision-log | `docs/decisions/YYYY-MM-DD-<slug>.md` |
| prioritization | `docs/prioritization/YYYY-MM-DD-prioritization-<topic>.md` |

## Getting Started

If they want first value on their product, start with `find-your-moat`. If they want a menu or a recommended workflow, stay here and route them.
