<h1 align="center">PM Superpowers 🧭</h1>

<p align="center">
  <strong>Turn proven product strategy frameworks into structured AI workflows you can run inside Claude Code.</strong>
</p>

<p align="center">
  <a href="#whats-inside">Skills</a> ·
  <a href="#getting-started">Getting started</a> ·
  <a href="references/strategy-frameworks.md">Frameworks</a> ·
  <a href="CONTRIBUTING.md">Contributing</a> ·
  <a href="LICENSE">MIT</a>
</p>

<p align="center">
  <img width="2808" height="1280" alt="pm-superpowers-grid" src="https://github.com/user-attachments/assets/1168879e-0b0d-485a-841a-dce2fdefa47d">
</p>
<p align="center"><sub><em>Eleven skills, one sub-agent, zero prompt engineering.</em></sub></p>

[![GitHub stars](https://img.shields.io/github/stars/aniganti/pm-superpowers?style=social)](https://github.com/aniganti/pm-superpowers/stargazers)

---

## What is this, really?

It's a Claude Code plugin: a set of skills, one sub-agent, and a shared library of framework definitions, packaged so they trigger naturally in conversation instead of living in a doc you have to remember to open.

In practice it feels like having a strategy-minded chief of staff who's read VRIO, aggregation theory, and every pre-mortem post-mortem, and asks the right follow-up question instead of just generating a wall of text. You don't copy-paste a prompt — you run `/strategy` or say "help me prioritize my backlog," and the skill walks you through the framework step by step.

Most AI-for-PM tools stop at "generate a PRD." They help you write faster, not think straighter. PM Superpowers is grounded in named, proven strategy frameworks — the AI doesn't freestyle; it interviews you the way a sharp analyst would, then structures the output around the framework's actual dimensions.

---

## Stuff you do with it

- **Get a VRIO read on your differentiation** before it becomes a slide in the board deck — Value, Rarity, Imitability, Organization, applied to your actual product.
- **Stress-test a launch with a pre-mortem** before the launch stress-tests you — Tigers, Paper Tigers, and Elephants, named and owned.
- **Run competitive research without opening fifteen tabs** — a sub-agent gathers the intelligence, you review the synthesis.
- **Turn a strategy doc into a briefing your VP will actually read** — audience-specific FAQs and workshop agendas generated from the artifacts you already built.
- **Log a decision the moment you make it** — reasoning, alternatives, and trade-offs captured while you still remember why, not reconstructed from Slack three months later.

## Getting started

### I just want to try a skill

<p align="center">
  <img src="https://github.com/user-attachments/assets/3bc942e5-7677-4412-90b4-b6a20550d5ac" alt="Installing the pm-superpowers plugin in Claude Code" width="100%">
</p>

```bash
# Add the marketplace
claude plugin marketplace add aniganti/pm-superpowers

# Install the plugin
claude plugin install pm-superpowers
```

Then run `/strategy` to kick off a full strategy session, or just ask "help me prioritize my backlog."

### I want to add a skill or framework

See [CONTRIBUTING.md](CONTRIBUTING.md) — new skills, new frameworks, agents, and bug fixes are all welcome. Direct pushes to `main` aren't accepted; everything goes through review.

---

## What's inside

### Companion product intelligence plugins

| Plugin | What it does |
|---|---|
| `hermes-tweet` | Documentation-only product signal workflows. Live research requires a separate Hermes Tweet runtime. |

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

---

## Available today · Being sharpened · Under consideration

| ✅ Available today | 🚧 Being sharpened | 💭 Under consideration |
|---|---|---|
| 11 skills across strategy, planning, and alignment | Deeper workflow chaining between skills (auto-suggest next step) | Skills for OKR authoring and quarterly planning |
| 1 sub-agent for competitive research | Richer verification checklists per artifact type | Multi-product / portfolio-level strategy rollups |
| Marketplace install via `claude plugin` | More worked examples in `references/` | Native integrations with roadmap tools (Jira, Linear) |

<sub>The 💭 column is intent, not a promise — see <a href="CONTRIBUTING.md">CONTRIBUTING.md</a> if you want to help build it.</sub>

---

## Two little stories

**The QBR nobody dreaded.** A PM runs `competitive-landscape`, then `vrio-analysis` on the same product. Twenty minutes later they have a defensibility argument built on named advantages, not adjectives. `strategic-moat` adds the eight-moat check. By the time `strategy` synthesizes it into pillars, the QBR deck writes itself — and survives the first hard question.

**The launch that didn't blow up.** Two weeks before ship, a PM runs `pre-mortem`. The skill surfaces three Tigers (real risks), two Paper Tigers (looked scary, aren't), and one Elephant nobody wanted to name out loud — a dependency on a team that hasn't confirmed capacity. It gets named. `stakeholder-alignment` turns the findings into a one-pager for the exec review. The launch ships on time, because the risk got caught in week two instead of week six.

---

## Recommended workflows

<details>
<summary><strong>Full Strategy Pipeline</strong></summary>

```
competitive-landscape → vrio-analysis → strategic-moat → strategy → pre-mortem
```

Each skill's output feeds into the next. Start with external landscape, move to internal capabilities, synthesize into strategy, then stress-test.

</details>

<details>
<summary><strong>Launch Readiness</strong></summary>

```
pre-mortem → stakeholder-alignment
```

</details>

<details>
<summary><strong>Decision Capture</strong></summary>

```
[any analysis skill] → decision-log → stakeholder-alignment
```

</details>

<details>
<summary><strong>Prioritization</strong></summary>

```
strategy → prioritization → stakeholder-alignment
```

</details>

Run `verification` after any of these before sharing artifacts with stakeholders.

<details>
<summary><strong>Where outputs are saved</strong></summary>

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

</details>

---

## Architecture

```
pm-superpowers/
├── .claude-plugin/
│   └── marketplace.json        # Root marketplace manifest
├── plugins/
│   ├── hermes-tweet/           # X/Twitter product signal workflows
│   └── pm-superpowers/
│       ├── .claude-plugin/
│       │   └── plugin.json     # Plugin manifest
│       ├── agents/             # Sub-agent definitions
│       ├── skills/             # SKILL.md per skill (the core logic)
│       └── commands/           # Slash command definitions
└── references/                 # Shared framework definitions (VRIO, moats, etc.)
```

Each skill follows a consistent structure: **domain context → instructions → interactive process steps → structured output format**. Skills include stopping conditions, red flags/anti-patterns, completion requirements, and workflow chaining to naturally guide PMs to the next relevant analysis.

**Plugin marketplace, not a prompt library.** Most PM-for-AI repos are flat collections of markdown templates. This is a proper Claude Code plugin with manifests, a sub-agent, and commands — it installs cleanly, triggers naturally, and composes with other tools.

---

## What this is not

- **Not a PRD generator.** Plenty of tools already do that well. This one exists for the thinking that has to happen *before* the PRD.
- **Not a replacement for your judgment.** The frameworks structure the analysis and ask the questions you'd otherwise forget to ask. You still own the call.
- **Not gospel.** VRIO, RICE, the Tigers/Paper Tigers/Elephants framework — these are starting points with decades of use behind them, not the only lens worth applying.
- **Not finished.** New skills and sharper frameworks are still landing — see the table above.

---

<p align="center">
  <sub>PM Superpowers 🧭</sub><br>
  <sub>MIT · Built by <a href="https://github.com/aniganti">Ani Ganti</a>, Principal PM at <a href="https://www.wrapbook.com">Wrapbook</a></sub>
</p>
