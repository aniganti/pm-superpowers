# CLAUDE.md

## Repository Purpose

This is a Claude Code plugin marketplace for product management skills. It provides structured AI workflows that help PMs make better product decisions using proven strategic frameworks.

## Architecture

### Marketplace Structure

- **`.claude-plugin/marketplace.json`** — Root marketplace manifest. MUST be updated when adding a new plugin.
- **`plugins/`** — Root directory for all plugin packages.
- **`references/`** — Shared framework definitions referenced by skills.

### Plugin Package Structure

```
plugins/
└── plugin-name/
    ├── .claude-plugin/
    │   └── plugin.json     # Plugin manifest (required)
    ├── agents/             # Sub-agent definitions (.md files)
    ├── skills/             # Skill definitions (SKILL.md per skill)
    └── commands/           # Slash command definitions (.md files)
```

## Development Workflow

### Adding a New Plugin

1. Create the plugin directory structure under `plugins/`
2. Create `plugin.json` in `.claude-plugin/` within the plugin directory
3. Add components (agents, skills, commands)
4. **Update `.claude-plugin/marketplace.json`** at the repo root
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
```

## Key Constraints

- All names must be lowercase with hyphens
- Each plugin must have a `plugin.json` manifest
- Root `marketplace.json` must be updated for any new plugin
- Skills should follow Claude Code documentation standards
