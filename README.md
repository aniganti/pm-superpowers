# PM Superpowers

**Framework grounded tool for PMs who think, not just ship**

---

## The problem

Product managers are expected to think in frameworks — VRIO for competitive advantage, moat analysis for defensibility, pre-mortems for launch risk. But running these frameworks well is slow and inconsistent. You either spend hours on a strategy doc that covers surface-level analysis, or you skip it entirely because the next sprint is breathing down your neck.

Meanwhile, AI coding tools like Claude Code are reshaping how technical PMs work. But most AI-for-PM tools stop at "generate a PRD." They don't help you *think strategically* — they just help you write faster.

**PM Superpowers bridges that gap.** It gives you structured, multi-step AI workflows grounded in real strategy frameworks — not generic prompts, but interactive skill sessions that ask the right questions, pull competitive intelligence, and produce analysis you'd actually put in front of your leadership team.

## Installation
![claude_LuCGhoy9iF](https://github.com/user-attachments/assets/3bc942e5-7677-4412-90b4-b6a20550d5ac)


```bash
# Add the marketplace
claude plugin marketplace add aniganti/pm-superpowers

# Install the plugin
claude plugin install pm-superpowers
```

Then run `/strategy` to kick off a full strategy session, or ask "help me prioritize my backlog" to get started.


## What's inside

### Strategic advisor skills

| Skill | What it does |
|---|---|
| `strategy` | Full 6-step interactive workflow: market analysis → problem space → strategic pillars (VRIO) → design/technical alignment → vision/mission/goals → communicate |
| `competitive-landscape` | Standalone competitor analysis with automated web research via sub-agent |
| `vrio-analysis` | VRIO framework competitive advantage evaluation — Value, Rarity, Imitability, Organization — applied to your specific product |
| `strategic-moat` | Defensibility assessment across 8 moat types including network effects, feedback loops, and ecosystem lock-in |
| `product-ecosystem` | Aggregation theory and value chain analysis for platform/ecosystem strategy |

### Planning & execution skills

| Skill | What it does |
|---|---|
| `pre-mortem` | Launch readiness risk analysis using the Tigers / Paper Tigers / Elephants framework |
| `prioritization` | Framework-driven feature/initiative prioritization using RICE, ICE, or weighted scoring — grounded in strategic pillars |
| `decision-log` | Structured capture of product decisions with reasoning, alternatives, evidence, and trade-offs — builds institutional memory |

### Alignment & communication skills

| Skill | What it does |
|---|---|
| `stakeholder-alignment` | Transforms strategy artifacts into tailored briefing docs, audience-specific FAQs, and workshop agendas for each stakeholder group |
| `verification` | Quality gate that re-reads any artifact against structured checklists and issues a PASS / PASS WITH WARNINGS / FAIL verdict |

### Utility skills

| Skill | What it does |
|---|---|
| `prompt-builder` | Guided AI prompt creation through 9 structured questions — role, audience, outcome, obstacles, tone, task, context, examples, format |
| `using-pm-superpowers` | Interactive guide to all available skills, recommended workflows, and output save locations |

### Sub-agents

| Agent | What it does |
|---|---|
| `competitive-researcher` | Automated competitive intelligence gathering via web research |

## Recommended workflows

### Full Strategy Pipeline

```
competitive-landscape → vrio-analysis → strategic-moat → strategy → pre-mortem
```

Each skill's output feeds into the next. Start with external landscape, move to internal capabilities, synthesize into strategy, then stress-test.

### Launch Readiness

```
pre-mortem → stakeholder-alignment
```

### Decision Capture

```
[any analysis skill] → decision-log → stakeholder-alignment
```

### Prioritization

```
strategy → prioritization → stakeholder-alignment
```

### After Any Analysis

Run `verification` before sharing artifacts with stakeholders.

## Where outputs are saved

All artifacts are saved to the `docs/` directory:

| Skill | Save Location |
|---|---|
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


## Architecture

```
pm-superpowers/
├── .claude-plugin/
│   └── marketplace.json        # Root marketplace manifest
├── plugins/
│   └── pm-superpowers/
│       ├── .claude-plugin/
│       │   └── plugin.json     # Plugin manifest
│       ├── agents/             # Sub-agent definitions
│       ├── skills/             # SKILL.md per skill (the core logic)
│       └── commands/           # Slash command definitions
└── references/                 # Shared framework definitions (VRIO, moats, etc.)
```

Each skill follows a consistent structure: **domain context → instructions → interactive process steps → structured output format**. Skills include stopping conditions, red flags/anti-patterns, completion requirements, and workflow chaining to naturally guide PMs to the next relevant analysis.

## Why this approach

**Plugin marketplace, not a prompt library.** Most PM-for-AI repos are flat collections of markdown templates. PM Superpowers is structured as a proper Claude Code plugin with manifests, sub-agents, and commands — which means it installs cleanly, triggers naturally in your workflow, and composes with other tools. You don't copy-paste prompts; you run `/strategy` and the workflow guides you.

**Framework-grounded, not vibes.** Every skill is built on a named, proven strategy framework (VRIO, aggregation theory, pre-mortem analysis, RICE/ICE scoring). The AI doesn't freestyle — it walks you through the framework step by step, asking targeted questions and structuring the output around the framework's actual dimensions. This produces analysis that's defensible in a strategy review, not just plausible-sounding.

**Interactive, not one-shot.** The `strategy` skill is a 6-step *session*, not a single prompt. It gathers context, asks follow-up questions, runs competitive research via sub-agent, and builds the strategy incrementally. This matches how real strategy work happens — iteratively, with judgment at each step.

**Workflow-chained, not isolated.** Skills connect to each other. A competitive landscape feeds into VRIO, which feeds into moat analysis, which feeds into strategy, which feeds into pre-mortem. Decisions get logged. Stakeholders get tailored briefings. The whole system composes into end-to-end strategic workflows.

## Built by

[Ani Ganti](https://github.com/aniganti) — Principal Product Manager at [Wrapbook](https://www.wrapbook.com), where I ship AI-powered payroll software for the entertainment industry. I built this because I wanted the strategic frameworks I use daily to work *inside* my AI coding workflow, not next to it.

## Contributing

All contributions welcome — new skills, new frameworks, agents, bug fixes, docs. See [CONTRIBUTING.md](CONTRIBUTING.md) for details.

## License

MIT
