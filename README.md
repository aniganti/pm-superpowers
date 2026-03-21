# PM Superpowers

**Turn proven product strategy frameworks into structured AI workflows you can run inside Claude Code.**

---

## The problem

Product managers are expected to think in frameworks — VRIO for competitive advantage, moat analysis for defensibility, pre-mortems for launch risk. But running these frameworks well is slow and inconsistent. You either spend hours on a strategy doc that covers surface-level analysis, or you skip it entirely because the next sprint is breathing down your neck.

Meanwhile, AI coding tools like Claude Code are reshaping how technical PMs work. But most AI-for-PM tools stop at "generate a PRD." They don't help you *think strategically* — they just help you write faster.

**PM Superpowers bridges that gap.** It gives you structured, multi-step AI workflows grounded in real strategy frameworks — not generic prompts, but interactive skill sessions that ask the right questions, pull competitive intelligence, and produce analysis you'd actually put in front of your leadership team.

## What's inside

### Strategic advisor skills

| Skill | What it does |
|---|---|
| `product-strategy` | Full 6-step interactive workflow: market analysis → problem space → strategic pillars (VRIO) → design/technical alignment → vision/mission/goals → communicate |
| `competitive-landscape` | Standalone competitor analysis with automated web research via sub-agent |
| `vrio-analysis` | VRIO framework competitive advantage evaluation — Value, Rarity, Imitability, Organization — applied to your specific product |
| `strategic-moat` | Defensibility assessment across 8 moat types including network effects, feedback loops, and ecosystem lock-in |
| `product-ecosystem` | Aggregation theory and value chain analysis for platform/ecosystem strategy |

### Planning & execution skills

| Skill | What it does |
|---|---|
| `pre-mortem` | Launch readiness risk analysis using the Tigers / Paper Tigers / Elephants framework |

### Slash commands

### Sub-agents

| Agent | What it does |
|---|---|
| `competitive-researcher` | Automated competitive intelligence gathering via web research |

## Installation

```bash
# Add the marketplace
claude plugin marketplace add aniganti/pm-superpowers

# Install the plugin
claude plugin install pm-superpowers
```

Then run `/strategy` to kick off a full strategy session, or `/quick-assess` for a fast competitive check.

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

Each skill follows a consistent structure: **domain context → instructions → interactive process steps → structured output format**. The `references/` directory holds canonical framework definitions that skills can pull from, keeping the strategy knowledge centralized and consistent across workflows.

## Why this approach

**Plugin marketplace, not a prompt library.** Most PM-for-AI repos are flat collections of markdown templates. PM Superpowers is structured as a proper Claude Code plugin with manifests, sub-agents, and commands — which means it installs cleanly, triggers naturally in your workflow, and composes with other tools. You don't copy-paste prompts; you run `/strategy` and the workflow guides you.

**Framework-grounded, not vibes.** Every skill is built on a named, proven strategy framework (VRIO, aggregation theory, pre-mortem analysis). The AI doesn't freestyle — it walks you through the framework step by step, asking targeted questions and structuring the output around the framework's actual dimensions. This produces analysis that's defensible in a strategy review, not just plausible-sounding.

**Interactive, not one-shot.** The `product-strategy` skill is a 6-step *session*, not a single prompt. It gathers context, asks follow-up questions, runs competitive research via sub-agent, and builds the strategy incrementally. This matches how real strategy work happens — iteratively, with judgment at each step.

## Tradeoffs and limitations

- **Claude Code only (for now).** The plugin architecture is built for Claude Code's marketplace. It doesn't work in ChatGPT, Cursor, or other AI tools without adaptation. Expanding to other platforms (Codex, Gemini CLI) would require adding install paths similar to what [obra/superpowers](https://github.com/obra/superpowers) does.
- **Strategy breadth vs. depth.** The current skill set focuses on competitive strategy and launch readiness. It doesn't yet cover discovery (user research synthesis), metrics/analytics, pricing strategy, or go-to-market planning. These are natural next additions.
- **No persistence between sessions.** Each `/strategy` run starts fresh. There's no way to pick up a previous analysis or build on it over time. A future version could write outputs to a local `docs/strategy/` directory for continuity.
- **Dependent on web search quality.** The `competitive-researcher` sub-agent's output is only as good as what it finds online. For niche or pre-launch markets, you'll need to supplement with your own research.

## What I'd improve next

1. **Add a `discovery` skill** — synthesize user research notes, interview transcripts, and support tickets into insight themes and opportunity areas
2. **Persistent strategy docs** — auto-save each strategy session's output to a local directory so you can iterate across sessions
3. **Metrics & goal-setting skill** — generate OKRs from strategy outputs, with leading/lagging indicator suggestions
4. **Cross-platform support** — add install paths for Codex CLI, Gemini CLI, and Cursor
5. **Example outputs** — publish sample strategy analyses so new users can see what the skills produce before installing

## Built by

[Ani Ganti](https://github.com/aniganti) — Principal Product Manager at [Wrapbook](https://www.wrapbook.com), where I ship AI-powered payroll software for the entertainment industry. I built this because I wanted the strategic frameworks I use daily to work *inside* my AI coding workflow, not next to it.

## Contributing

All contributions welcome — new skills, new frameworks, agents, bug fixes, docs. See [CONTRIBUTING.md](CONTRIBUTING.md) for details.

## License

MIT
