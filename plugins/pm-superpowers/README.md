# pm-superpowers

Product strategy skills for PMs, grounded in structured frameworks for competitive analysis, defensibility assessment, and strategic planning.

## Skills

### product-strategy (Main Orchestrator)

The flagship skill. Guides PMs through a 6-step interactive framework to develop a comprehensive product strategy:

1. **Understand the market and users** — Industry analysis, user personas, competitive landscape (with automated research agent)
2. **Understand the problem space** — Problem statements in WHO/WHAT/WHY format
3. **Identify key pillars** — VRIO analysis for competitive advantages
4. **Seek design and technical alignment** — Surface risks and constraints
5. **Define vision, mission, and goals** — North-star metric, KPIs
6. **Put it all together and communicate** — Strategy document with stakeholder FAQ

### vrio-analysis

Standalone VRIO framework for evaluating resources and capabilities. Walks through the Value → Rarity → Imitability → Organization decision tree to classify each capability as Competitive Disadvantage, Parity, Temporary Advantage, or Sustained Advantage.

### competitive-landscape

Focused competitor analysis. Spawns the competitive-researcher agent to gather real-time market intelligence, then synthesizes findings into competitor profiles, value chain mapping, and positioning analysis.

### strategic-moat

Defensibility assessment across 8 moat types: self-reinforcing feedback loops (Fogg B=MAP), network effects, switching costs, data advantages, ecosystem lock-in, economies of scale, brand/trust, and regulatory barriers.

### product-ecosystem

Aggregation theory analysis for ecosystem strategy. Maps value chains, evaluates forward/backward integration opportunities, assesses product portfolio coherence, and identifies closed-loop feedback opportunities.

### pre-mortem

Launch readiness risk analysis. Imagines launch failure and works backward to categorize risks as Tigers (real), Paper Tigers (overblown), or Elephants (unspoken). Creates action plans for launch-blocking risks.

## Commands

- `/strategy` — Full 6-step product strategy workflow
- `/quick-assess` — Lightweight competitive landscape check

## Sub-Agents

- **competitive-researcher** — Automated competitive intelligence gathering via web search. Spawned by the product-strategy and competitive-landscape skills.
