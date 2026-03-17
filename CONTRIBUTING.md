# Contributing

Thank you for your interest in contributing to pm-superpowers! All contributions are welcome — new skills, agents, commands, bug fixes, and documentation improvements.

## How to Contribute

1. **Fork** this repository
2. **Create a feature branch** from `main` (`git checkout -b my-new-skill`)
3. Make your changes (see guidelines below)
4. **Validate** your JSON files before pushing (see [Validation](#validation))
5. **Open a Pull Request** against `main`
6. **Wait for review** — all PRs require approval from a maintainer before merging. Do not merge your own PR.

> **Note:** Direct pushes to `main` are not accepted. All changes must go through the PR review process.

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

Before submitting your PR, ensure all JSON files are valid:

```bash
cat .claude-plugin/marketplace.json | jq .
cat plugins/PLUGIN_NAME/.claude-plugin/plugin.json | jq .
```

## Review Process

- All PRs will be reviewed by [@aniganti](https://github.com/aniganti)
- Expect feedback within a few days
- Please address review comments and push follow-up commits to the same branch
- Once approved, a maintainer will merge your PR
