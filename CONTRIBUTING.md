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

3. Update the plugin's `plugin.json` files if needed (see [Packaging](#packaging-claude-code-vs-cursor))
4. Update the root marketplace manifests (see below)

## Adding a New Plugin

1. Create directory structure under `plugins/`
2. Add `.claude-plugin/plugin.json` (required for Claude Code)
3. Add `.cursor-plugin/plugin.json` if the plugin should also install in Cursor / Grok Bot
4. Add skills and agents (`commands/` is optional; this repo does not currently ship slash commands)
5. Register in the matching root marketplace manifest(s)

## Packaging (Claude Code vs Cursor)

This repo ships **two marketplace formats** so one GitHub repository can install in Claude Code and in Cursor / Grok Bot without breaking either client:

| Client | Root marketplace | Per-plugin manifest |
|---|---|---|
| Claude Code | `.claude-plugin/marketplace.json` | `plugins/<name>/.claude-plugin/plugin.json` |
| Cursor / Grok Bot | `.cursor-plugin/marketplace.json` | `plugins/<name>/.cursor-plugin/plugin.json` |

Skills live once under `plugins/<name>/skills/*/SKILL.md`. Do not copy skill bodies between formats. Cursor auto-discovers `skills/` (this repo also points `plugin.json` at `./skills/`). Keep YAML frontmatter `name` and `description` on every `SKILL.md`.

`hermes-tweet` is registered only in the Claude marketplace. It is documentation for a Hermes Agent + Xquik runtime and is not useful in Cursor / Grok Bot without live `tweet_*` tools.

When you add a **portable** plugin (skills that work in both clients), update **both** marketplace files and both `plugin.json` files. When you add a **runtime-specific** plugin, register it only where it can actually run.

## Naming Conventions

- Lowercase, hyphen-separated: `my-skill-name`
- Skills use `SKILL.md` filename
- Agents and commands use descriptive `.md` filenames

## Validation

Before submitting your PR, ensure all JSON files are valid:

```bash
cat .claude-plugin/marketplace.json | jq .
cat plugins/PLUGIN_NAME/.claude-plugin/plugin.json | jq .
cat .cursor-plugin/marketplace.json | jq .
cat plugins/PLUGIN_NAME/.cursor-plugin/plugin.json | jq .
node scripts/validate-cursor-plugin.mjs
```

To smoke-test Cursor discovery locally, copy the plugin folder (not the whole repo) into `~/.cursor/plugins/local/` and reload Cursor. Use a real copy, not a symlink to the checkout — Cursor skips symlinks that point outside that folder:

```bash
mkdir -p ~/.cursor/plugins/local
cp -R plugins/pm-superpowers ~/.cursor/plugins/local/pm-superpowers
```

## Review Process

- All PRs will be reviewed by [@aniganti](https://github.com/aniganti)
- Expect feedback within a few days
- Please address review comments and push follow-up commits to the same branch
- Once approved, a maintainer will merge your PR
