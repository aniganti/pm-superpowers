# pm-superpowers

Product strategy skills for PMs, grounded in structured frameworks for competitive analysis, defensibility assessment, strategic planning, and cross-functional alignment.

## Skills

### strategy (Main Orchestrator)

The flagship skill. Guides PMs through a 6-step interactive framework to develop a comprehensive product strategy:

1. **Understand the market and users** — Industry analysis, user personas, competitive landscape (with automated research agent)
2. **Understand the problem space** — Problem statements in WHO/WHAT/WHY format
3. **Identify key pillars** — VRIO analysis for competitive advantages
4. **Seek design and technical alignment** — Surface risks and constraints
5. **Define vision, mission, and goals** — North-star metric, KPIs
6. **Put it all together and communicate** — Strategy document with stakeholder FAQ

### competitive-landscape

Focused competitor analysis. Spawns the competitive-researcher agent to gather real-time market intelligence, then synthesizes findings into competitor profiles, value chain mapping, and positioning analysis.

### vrio-analysis

Standalone VRIO framework for evaluating resources and capabilities. Walks through the Value → Rarity → Imitability → Organization decision tree to classify each capability as Competitive Disadvantage, Parity, Temporary Advantage, Unused Advantage, or Sustained Advantage. Includes strategic recommendations and stakeholder engagement guidance.

### strategic-moat

Defensibility assessment across 8 moat types: self-reinforcing feedback loops (Fogg B=MAP), network effects, switching costs, data advantages, ecosystem lock-in, economies of scale, brand/trust, and regulatory barriers. Includes an ethical check to balance engagement with user well-being.

### product-ecosystem

Aggregation theory analysis for ecosystem strategy. Maps value chains, evaluates forward/backward integration opportunities, assesses product portfolio coherence, and identifies closed-loop feedback opportunities.

### pre-mortem

Launch readiness risk analysis. Imagines launch failure and works backward to categorize risks as Tigers (real), Paper Tigers (overblown), or Elephants (unspoken). Creates action plans for launch-blocking risks.

### stakeholder-alignment

Transforms strategy artifacts into tailored communications for different stakeholder audiences. Produces audience-specific briefing documents, FAQs (5-8 questions per audience), and cross-functional workshop agendas. Supports executive leadership, engineering, sales, marketing, and customer success audiences.

### decision-log

Captures product decisions with structured reasoning, alternatives considered, evidence, and trade-offs. Builds institutional memory and prevents re-litigation of settled decisions. Links decisions back to source artifacts and flags when new decisions supersede existing ones.

### prioritization

Framework-driven feature and initiative prioritization using RICE, ICE, or weighted scoring. Grounds every priority in strategic pillars and demands evidence-based scoring. Produces ranked lists with dependency checks, cut lines, and key assumptions.

### verification

Quality gate for any PM strategy artifact. Re-reads completed documents against structured checklists (universal + artifact-specific) and issues a PASS / PASS WITH WARNINGS / FAIL verdict. Covers strategy, competitive landscape, VRIO, strategic moat, product ecosystem, and pre-mortem artifact types.

### prompt-builder

Guided AI prompt creation for PMs. Walks through 9 structured questions (role, audience, outcome, obstacles, tone, task, context, examples, format) to craft effective prompts for any AI tool.

### using-pm-superpowers

Interactive guide to all available skills, recommended workflows, invocation examples, and output save locations.

## Recommended Workflows

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

## Output Locations

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

## Sub-Agents

- **competitive-researcher** — Automated competitive intelligence gathering via web search. Spawned by the strategy and competitive-landscape skills.
