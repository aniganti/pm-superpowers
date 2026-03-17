# Contributing

## Adding a New Skill

1. Create a directory under the appropriate plugin's `skills/` folder
2. Add a `SKILL.md` file with this structure:

```markdown
---
name: skill-name
description: >-
  What the skill does and when to use it.
  Include trigger phrases.
argument-hint: "<what-to-pass>"
---

# Skill Title

## Purpose
What this skill helps PMs accomplish.

## Instructions
Step-by-step process the skill follows.

## Output Format
What the skill produces.
```

3. Update the plugin's `plugin.json` if needed
4. Update `.claude-plugin/marketplace.json` at the repo root

## Adding a New Plugin

1. Create directory structure under `plugins/`
2. Add `.claude-plugin/plugin.json` manifest
3. Add skills, agents, or commands
4. Register in root `.claude-plugin/marketplace.json`

## Naming Conventions

- Lowercase, hyphen-separated: `my-skill-name`
- Skills use `SKILL.md` filename
- Agents and commands use descriptive `.md` filenames

## Validation

```bash
cat .claude-plugin/marketplace.json | jq .
cat plugins/PLUGIN_NAME/.claude-plugin/plugin.json | jq .
```
