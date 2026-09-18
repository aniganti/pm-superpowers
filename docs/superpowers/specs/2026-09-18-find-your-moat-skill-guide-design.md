# find-your-moat + skill-guide — Design Spec

## Status

Approved for implementation planning after user reviews this file.

Locked with product owner Ani Ganti on 2026-09-18. This document is the source of truth for the follow-on implementation plan. Do not implement skills in the same PR as this spec.

## Context

PM Superpowers is a **moat machine**, not a PRD generator. After marketplace packaging, P0 is plugin activation: a front-door skill that runs a short **real** moat pass on the user’s product. Avoid “demo/tour” framing.

Existing skill `using-pm-superpowers` is a catalog/router (lists skills, workflows, save paths). It is **not** a moat run. Design is rename + split: new front door + renamed router.

| Item | Value |
|---|---|
| Repo | https://github.com/aniganti/pm-superpowers |
| Cursor marketplace listing | `51593709` (already resubmitted once after logo; needs another refresh after this ships) |
| Plugin | `plugins/pm-superpowers/` |
| Current skill count | 12 `SKILL.md` files under `plugins/pm-superpowers/skills/` |
| Dual packaging | Claude (`.claude-plugin`) + Cursor (`.cursor-plugin`); skill bodies live once |

### Current state (repo, 2026-09-18)

- Front-door gap: post-install copy in the root README leads with `/strategy` or “help me prioritize my backlog.” Neither is a thin moat pass on the user’s product.
- Catalog skill: `plugins/pm-superpowers/skills/using-pm-superpowers/SKILL.md` (`name: using-pm-superpowers`). Job is help/router, not first value.
- Deep moat skill: `strategic-moat` already exists. It asks a 6-question intake and scores all **8** moat types. That remains the full defensibility assessment.
- Validator: `scripts/validate-cursor-plugin.mjs` discovers `SKILL.md` files and logs `pm-superpowers: discovered N skill(s).` Today that is **12**. It does not hard-assert 12; post-implementation expected log is **13**.

## Goals

1. First valuable loop after install: real thin moat read on the user’s product → short saved artifact → handoff into the depth chain.
2. Clear separation: help/catalog vs first-value moat work.
3. Naming reinforces moat-machine positioning; **no demo/tour/playground language** in skill names or descriptions.

## Non-goals

- Moat machine v2 (evidence prompts, one-pager export, win/loss skill) — P1
- Changing deep `strategic-moat` internals beyond an optional one-line cross-link
- Builder writing/scheduling social posts (Marketing Bot owns)
- Becoming a PRD generator

## Skill map

### `find-your-moat` (NEW — front door)

- **Job:** first valuable loop after install — real thin moat read on the user’s product (not sample data, not a catalog).
- **Depth:** deliberately shallower than `strategic-moat`; never claims “complete defensibility assessment.”
- **Triggers (examples):** “find my moat”, “how defensible is this”, “just installed / where do I start” when they want value not a menu.
- **Path:** `plugins/pm-superpowers/skills/find-your-moat/SKILL.md`
- **Frontmatter:** `name: find-your-moat`. Description must sell a real pass on *their* product. Forbidden in name and description: demo, tour, playground, sample, walkthrough-as-the-product.

#### Flow

1. **Context:** max 2–3 questions (product, audience, top 1–2 competitors). No 6-question intake.
2. **Thin scorecard:** 4 of 8 moat types only — feedback loops, switching costs, network effects, unique data/tech. Each: **None | Emerging | Moderate | Strong** + one evidence line + one deepen idea. Other types **“not assessed.”**
3. **So-what:** 3–5 bullets (strongest, weakest, competitor-copy risk, one do-this-week move).
4. **Save:** `docs/strategic-moat/YYYY-MM-DD-find-moat-<slug>.md`
5. **Handoff:** offer deepen with `strategic-moat`, or start the pipeline at `competitive-landscape` / `vrio-analysis`.

#### Scorecard mapping to existing 8 types

Use the same rating scale and type names as `strategic-moat` so a later deep pass can pick up the file. Assess only these four:

| Assess in `find-your-moat` | Maps to `strategic-moat` |
|---|---|
| Feedback loops | Moat 1 — Self-reinforcing feedback loops |
| Network effects | Moat 2 — Network effects |
| Switching costs | Moat 3 — Switching costs |
| Unique data/tech | Moat 4 — Data advantages |

Leave these four as **not assessed** (do not score, do not invent evidence):

- Ecosystem lock-in
- Economies of scale
- Brand and trust
- Regulatory barriers

#### Relationship to `strategic-moat`

Sits **beside** `strategic-moat` as quick pass → deep pass.

| | `find-your-moat` | `strategic-moat` |
|---|---|---|
| Role | Front door / thin read | Full defensibility assessment |
| Intake | 2–3 questions | 6-question intake (unchanged) |
| Coverage | 4 types; 4 marked not assessed | All 8 types |
| Claim | Never “complete” | Complete 8-type assessment |
| Artifact | `…-find-moat-<slug>.md` | `…-moat-<product-name>.md` (unchanged) |

**Trigger overlap (locked):** `strategic-moat` already triggers on phrases like “how defensible is my product.” Keep those triggers. Do not rewrite `strategic-moat` internals. Optional one-line cross-link only (e.g. if the user wants a *quick* first read, point at `find-your-moat`). First-install / “where do I start” / “find my moat” language belongs to `find-your-moat`.

**Inputs:** the user’s real product. If they have not named one, ask. Do not substitute a sample product, fictional company, or canned walkthrough.

### `skill-guide` (RENAME of `using-pm-superpowers`)

- **Job:** unchanged — catalog, recommended workflows, which skill, save paths.
- **Implementation:** move `skills/using-pm-superpowers/` → `skills/skill-guide/`; frontmatter `name: skill-guide`.
- **Triggers:** keep old help phrases (“what can you do”, “which skill”, “list skills”, “pm superpowers help”, etc.) plus “skill guide”.
- **Body:** same tables/workflows; add `find-your-moat` as **start here for first value**; “full defensibility” → `strategic-moat`; one-line note that this skill was formerly `using-pm-superpowers`.

Do not leave a duplicate `using-pm-superpowers` directory or `SKILL.md`. After the move, discovery should see `skill-guide` and not the old name.

Update catalog tables and save-path tables to include `find-your-moat` → `docs/strategic-moat/YYYY-MM-DD-find-moat-<slug>.md`.

## Docs & packaging

- Root README “What’s inside” + getting started: lead with `find-your-moat`; list `skill-guide` under utility (replace `using-pm-superpowers`).
- Plugin README (`plugins/pm-superpowers/README.md`) currently documents `using-pm-superpowers`; keep it consistent with the root README (same rename + front-door lead).
- `scripts/validate-cursor-plugin.mjs` must discover **13** skills (was 12). Expected log after implementation: `pm-superpowers: discovered 13 skill(s).` No skill-body change to the validator is required unless a later plan adds a hard assertion.
- Claude + Cursor dual packaging preserved; **no skill body duplication**. One `SKILL.md` per skill under `plugins/pm-superpowers/skills/` is discovered by both manifests via `skills: "./skills/"`.
- Manifest `plugin.json` descriptions/keywords may mention the new front door; that is packaging copy, not a second skill body.

## Marketplace (in scope for P0 done)

After skills merge to **main**: update/resubmit Cursor marketplace listing **51593709** for `aniganti/pm-superpowers` so discovery includes `find-your-moat` + `skill-guide` and drops stale `using-pm-superpowers`.

This marketplace refresh is **not** part of the design-doc PR. It is part of P0 completion after the implementation PR lands on main.

## Marketing handoff

Marketing Bot informed 2026-09-18:

- Lead with “find your moat in minutes on your product,” not demo.
- Stay moat-machine.
- Don’t hard-market the rename.

Builder pings Marketing with the **implementation PR** URL when that PR opens (not this design-doc PR).

## Success criteria

- Both skills validate; README consistent (root + plugin README).
- First-run path = moat value (`find-your-moat`); help path = `skill-guide`.
- No “demo” wording in skill names/descriptions (also no tour/playground).
- Listing **51593709** refreshed after merge to main.
- Marketing Bot has the implementation PR URL for messaging.

## Implementation notes (for later plan — not this PR)

Implementation will be a **separate PR**: add `find-your-moat` `SKILL.md`, rename to `skill-guide`, update READMEs, run the validator. This PR is design doc only.

Suggested later-plan file (when Ani approves this spec): `docs/superpowers/plans/2026-09-18-find-your-moat-skill-guide.md`.

Out of that later PR, still: marketplace resubmit (after merge) and Marketing ping (when the implementation PR opens).
