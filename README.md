# PM Superpowers

Claude Code plugin marketplace with skills and tools for product managers. Built on proven product strategy frameworks.

## Installation

```bash
claude plugin marketplace add aniganti/pm-superpowers
```

Then install individual plugins:

```bash
claude plugin install pm-product-strategy
```

## Plugins

### pm-product-strategy

Product strategy skills grounded in structured frameworks for competitive analysis, defensibility assessment, and strategic planning.

**Skills:**

| Skill | Description |
|-------|-------------|
| `product-strategy` | 6-step interactive framework: market analysis → problem space → strategic pillars (VRIO) → design/technical alignment → vision/mission/goals → communicate |
| `competitive-landscape` | Standalone competitor analysis with automated web research |
| `vrio-analysis` | VRIO framework for evaluating competitive advantages (Value, Rarity, Imitability, Organization) |
| `strategic-moat` | Defensibility assessment across 8 moat types including feedback loops and ecosystem lock-in |
| `product-ecosystem` | Aggregation theory and value chain analysis for ecosystem strategy |
| `pre-mortem` | Launch readiness risk analysis using Tigers/Paper Tigers/Elephants framework |

**Commands:**

| Command | Description |
|---------|-------------|
| `/strategy` | Run the full 6-step product strategy workflow |
| `/quick-assess` | Lightweight competitive landscape check |

**Sub-Agents:**

| Agent | Description |
|-------|-------------|
| `competitive-researcher` | Automated competitive intelligence gathering via web research |

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for how to add new skills or plugins.

## License

MIT
