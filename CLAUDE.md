# CLAUDE.md

## Repository Purpose

This is a dual-format plugin marketplace for product management skills (Claude Code + Cursor / Grok Bot). It provides structured AI workflows that help PMs make better product decisions using proven strategic frameworks.

## Architecture

### Marketplace Structure

- **`.claude-plugin/marketplace.json`** — Claude Code marketplace. MUST be updated when adding a Claude-installable plugin.
- **`.cursor-plugin/marketplace.json`** — Cursor / Grok Bot marketplace. MUST be updated when adding a Cursor-installable plugin. Currently lists `pm-superpowers` only (`hermes-tweet` is Claude/Hermes-specific).
- **`plugins/`** — Root directory for all plugin packages.
- **`references/`** — Shared framework definitions referenced by skills.

### Plugin Package Structure

```
plugins/
└── plugin-name/
    ├── .claude-plugin/
    │   └── plugin.json     # Claude Code manifest (required for Claude)
    ├── .cursor-plugin/
    │   └── plugin.json     # Cursor / Grok Bot manifest (required for Cursor)
    ├── agents/             # Sub-agent definitions (.md files)
    ├── skills/             # Skill definitions (SKILL.md per skill)
    └── commands/           # Slash command definitions (.md files)
```

## Development Workflow

### Adding a New Plugin

1. Create the plugin directory structure under `plugins/`
2. Create `plugin.json` in `.claude-plugin/` (and `.cursor-plugin/` if the plugin should install in Cursor)
3. Add components (agents, skills, commands)
4. **Update the matching root marketplace.json file(s)**
5. Use lowercase, hyphen-separated names

### Adding a New Skill

1. Create a directory under the plugin's `skills/` folder
2. Add a `SKILL.md` file with YAML frontmatter (`name`, `description`, `argument-hint`)
3. Structure: Domain Context → Instructions → Process Steps → Output Format

### Validation

Before committing, validate JSON:

```bash
cat .claude-plugin/marketplace.json | jq .
cat plugins/PLUGIN_NAME/.claude-plugin/plugin.json | jq .
cat .cursor-plugin/marketplace.json | jq .
cat plugins/PLUGIN_NAME/.cursor-plugin/plugin.json | jq .
node scripts/validate-cursor-plugin.mjs
```

## Key Constraints

- All names must be lowercase with hyphens
- Each Claude-installable plugin must have a `.claude-plugin/plugin.json` manifest
- Each Cursor-installable plugin must have a `.cursor-plugin/plugin.json` manifest
- Root `.claude-plugin/marketplace.json` / `.cursor-plugin/marketplace.json` must be updated for any new plugin in that client
- Skills should follow Claude Code documentation standards (Cursor discovers the same `SKILL.md` files)
