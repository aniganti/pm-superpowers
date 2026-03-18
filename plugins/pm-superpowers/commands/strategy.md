---
name: strategy
description: Run the full 6-step product strategy workflow — gathers market context, analyzes competitors, identifies strategic pillars, and produces a comprehensive strategy document.
---

# Full Product Strategy Workflow

Run the complete product strategy analysis using the 6-step framework:

1. **Understand the market and users** — Gather industry context, user segments, and competitive landscape. Spawns a competitive-researcher agent for real-time market intelligence.
2. **Understand the problem space** — Articulate problem statements (WHO/WHAT/WHY) and prioritize the most acute pain.
3. **Identify key pillars of strategy** — Run VRIO analysis on resources and capabilities to uncover sources of sustained competitive advantage.
4. **Seek design and technical alignment** — Surface technical risks, constraints, and design considerations.
5. **Define vision, mission, and goals** — Craft product vision, mission, north-star metric, and KPIs.
6. **Put it all together and communicate** — Synthesize the strategy document with FAQ for stakeholder pushbacks.

## Usage

```
/pm-superpowers:strategy [topic or existing strategy doc path]
```

## What You Get

A comprehensive product strategy document saved to `docs/strategies/YYYY-MM-DD-<slug>.md` covering:
- Market and user analysis
- Problem statements
- Strategic pillars and competitive advantages (VRIO)
- Vision, mission, and goals
- Communication plan with anticipated pushbacks

## Next Steps After Running

- Run `/pm-superpowers:quick-assess` for a focused competitive deep-dive on specific competitors
- Use the `strategic-moat` skill to assess defensibility in detail
- Use the `product-ecosystem` skill to evaluate aggregation and ecosystem opportunities
- Use the `pre-mortem` skill to stress-test launch readiness
