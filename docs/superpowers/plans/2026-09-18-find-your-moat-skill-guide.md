# find-your-moat + skill-guide Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Add a thin real-product front-door skill (`find-your-moat`) and rename the catalog router to `skill-guide`, so first value after install is a moat pass rather than a menu.

**Architecture:** Dual Claude + Cursor packaging is unchanged. Skill bodies live once under `plugins/pm-superpowers/skills/*/SKILL.md`. `find-your-moat` sits beside `strategic-moat` (quick 4-type pass → full 8-type assessment). `using-pm-superpowers` is moved, not duplicated. READMEs and the router tables point first-value traffic at `find-your-moat`.

**Tech Stack:** Markdown `SKILL.md` files with YAML frontmatter; existing Node validator `scripts/validate-cursor-plugin.mjs` (discovers `SKILL.md` under the Cursor plugin `skills/` path).

## Global Constraints

- Source of truth: `docs/superpowers/specs/2026-09-18-find-your-moat-skill-guide-design.md` (locked 2026-09-18).
- Dual packaging: Claude (`.claude-plugin`) + Cursor (`.cursor-plugin`); **no skill body duplication**.
- Moat machine positioning; **not a PRD generator**.
- No P1 features (one-pager, win/loss, evidence-prompt machine).
- Do not touch marketplace publish UI. Listing **51593709** refresh is post-merge to main.
- Skill names lowercase hyphen-separated. Forbidden in `find-your-moat` name/description: demo, tour, playground, sample, walkthrough-as-the-product.
- Do not change `strategic-moat` 6-question intake or 8-type assessment (optional one-line cross-link only).
- Validator must log `pm-superpowers: discovered 13 skill(s).` then `Validation passed.`
- Do not leave a leftover `using-pm-superpowers` directory.

---

### Task 1: Add `find-your-moat`

**Files:**
- Create: `plugins/pm-superpowers/skills/find-your-moat/SKILL.md`

**Interfaces:**
- Consumes: locked spec flow (2–3 context Qs; 4 scored types; 4 not assessed; save path; handoff).
- Produces: skill name `find-your-moat`; artifact path `docs/strategic-moat/YYYY-MM-DD-find-moat-<slug>.md`; handoff to `strategic-moat` or `competitive-landscape` / `vrio-analysis`.

- [ ] **Step 1: Create the skill directory and `SKILL.md`**

Frontmatter (must match exactly on `name` / `argument-hint`; description must sell a real pass on *their* product and must not contain demo/tour/playground/sample/walkthrough-as-the-product):

```yaml
---
name: find-your-moat
description: >
  Run a thin first-pass moat read on the user's real product — four core
  defensibility types, not a complete assessment. Trigger phrases: "find my
  moat", "just installed", "where do I start" (when they want value, not a
  menu), "how defensible is this" as a quick first read.
argument-hint: "[product-or-company-name]"
---
```

Body must follow sibling tone (`strategic-moat`) but stay thinner. Required rules in the body:

1. Role: strategic moat analyst doing a *thin first pass*, not a complete assessment.
2. Foundational theory: a few lines only — do not copy the full 8-moat `strategic-moat` body.
3. Flow: max 2–3 context questions (product, audience, top 1–2 competitors). No 6-question intake.
4. Score only: feedback loops, network effects, switching costs, unique data/tech (maps to strategic-moat Moats 1–4). Rating: None | Emerging | Moderate | Strong + one evidence + one deepen.
5. Mark not assessed (do not score, do not invent evidence): ecosystem lock-in, economies of scale, brand and trust, regulatory barriers.
6. So-what: 3–5 bullets (strongest, weakest, competitor-copy risk, one do-this-week move).
7. Save to `docs/strategic-moat/YYYY-MM-DD-find-moat-<slug>.md`.
8. Handoff: deepen with `strategic-moat`, or start pipeline at `competitive-landscape` / `vrio-analysis`.
9. Never claim complete defensibility. Never use a sample/fictional product. If no product is named, ask.
10. Optional pointer: full 8-type assessment → `strategic-moat`.

- [ ] **Step 2: Grep the new description for forbidden words**

Run: `rg -n -i 'demo|tour|playground|sample|walkthrough' plugins/pm-superpowers/skills/find-your-moat/SKILL.md`

Expected: no matches in frontmatter `name` or `description`. Body may mention "sample/fictional product" only as a prohibition.

- [ ] **Step 3: Commit**

```bash
git add plugins/pm-superpowers/skills/find-your-moat/SKILL.md
git commit -m "feat: add find-your-moat thin first-pass skill"
```

---

### Task 2: Rename router to `skill-guide`

**Files:**
- Move: `plugins/pm-superpowers/skills/using-pm-superpowers/` → `plugins/pm-superpowers/skills/skill-guide/`
- Modify: `plugins/pm-superpowers/skills/skill-guide/SKILL.md`

**Interfaces:**
- Consumes: existing catalog tables/workflows in `using-pm-superpowers`.
- Produces: frontmatter `name: skill-guide`; catalog row for `find-your-moat`; save-path row `docs/strategic-moat/YYYY-MM-DD-find-moat-<slug>.md`.

- [ ] **Step 1: git mv the directory**

```bash
git mv plugins/pm-superpowers/skills/using-pm-superpowers plugins/pm-superpowers/skills/skill-guide
```

- [ ] **Step 2: Update frontmatter**

```yaml
---
name: skill-guide
description: >
  Guide to all available PM Superpowers skills, recommended workflows, and how
  to get the most out of the plugin. Trigger phrases: "what can you do",
  "help me with PM", "which skill should I use", "pm superpowers help",
  "list skills", "what skills are available", "skill guide"
argument-hint: ""
---
```

- [ ] **Step 3: Update the body**

Keep the existing tables/workflows. Required edits:

1. One-line note near the top: this skill was formerly `using-pm-superpowers`.
2. Available Skills table: add `find-your-moat` as **start here for first value**.
3. Full defensibility → `strategic-moat` (do not present `strategic-moat` as the first-value path).
4. Quick Assessments: first-value / just-installed → `find-your-moat`; full defensibility → `strategic-moat`.
5. Save-path table: add `find-your-moat` → `docs/strategic-moat/YYYY-MM-DD-find-moat-<slug>.md`.
6. Invocation examples: include "find my moat" / first-value language.

- [ ] **Step 4: Confirm no leftover path**

Run: `test ! -e plugins/pm-superpowers/skills/using-pm-superpowers && echo gone`

Expected: `gone`

- [ ] **Step 5: Commit**

```bash
git add plugins/pm-superpowers/skills/skill-guide plugins/pm-superpowers/skills/using-pm-superpowers
git commit -m "refactor: rename using-pm-superpowers to skill-guide"
```

---

### Task 3: Optional one-line cross-link in `strategic-moat`

**Files:**
- Modify: `plugins/pm-superpowers/skills/strategic-moat/SKILL.md` (after title or in the flow intro only)

**Interfaces:**
- Consumes: unchanged 6-question intake and 8-type assessment.
- Produces: one pointer to `find-your-moat` for a quick first read / just-installed path.

- [ ] **Step 1: Add a single sentence after the title/role paragraph**

Exact addition (do not change Steps 1–5, the 8 moat sections, or existing trigger phrases):

```markdown
If the PM wants a quick first read or just installed and wants value now, use `find-your-moat` instead of this full assessment.
```

- [ ] **Step 2: Confirm the 6-question intake and 8-type list are unchanged**

Run: `rg -n "What is the product and who is the target user|Moat 8: Regulatory Barriers" plugins/pm-superpowers/skills/strategic-moat/SKILL.md`

Expected: both still present.

- [ ] **Step 3: Commit**

```bash
git add plugins/pm-superpowers/skills/strategic-moat/SKILL.md
git commit -m "docs: point quick first reads to find-your-moat"
```

---

### Task 4: Update READMEs

**Files:**
- Modify: `README.md` (What's inside + Getting started)
- Modify: `plugins/pm-superpowers/README.md`

**Interfaces:**
- Consumes: new skill name `find-your-moat` and renamed `skill-guide`.
- Produces: first-value lead with `find-your-moat`; utility row `skill-guide` (no `using-pm-superpowers`).

- [ ] **Step 1: Root `README.md`**

1. Getting started (Claude + Cursor): lead with asking "find my moat" on the user's product, not `/strategy` or backlog prioritization as the first action.
2. What's inside — Strategic advisor table: add `find-your-moat` as the first row (**start here for first value**).
3. What's inside — Utility table: replace `using-pm-superpowers` with `skill-guide`.
4. Output save-path table: add `find-your-moat` → `docs/strategic-moat/YYYY-MM-DD-find-moat-<slug>.md`.
5. Update the "Eleven skills" / "11 skills" counts to **13** (12 existing + 1 new; rename does not add a second catalog skill).

- [ ] **Step 2: Plugin `plugins/pm-superpowers/README.md`**

1. Add `find-your-moat` as the first skill section — thin first pass; start here for first value.
2. Rename the `using-pm-superpowers` heading/body to `skill-guide` (formerly `using-pm-superpowers`).
3. Output Locations table: add the `find-your-moat` save path.

- [ ] **Step 3: Grep leftover router name in READMEs**

Run: `rg -n 'using-pm-superpowers' README.md plugins/pm-superpowers/README.md`

Expected: no matches (the historical note lives only in `skill-guide` / this plan / the design spec).

- [ ] **Step 4: Commit**

```bash
git add README.md plugins/pm-superpowers/README.md
git commit -m "docs: lead READMEs with find-your-moat; rename skill-guide"
```

---

### Task 5: Validate packaging

**Files:**
- Test: `scripts/validate-cursor-plugin.mjs` (no validator source change unless it fails for a real reason)

**Interfaces:**
- Consumes: 13 `SKILL.md` files under `plugins/pm-superpowers/skills/`.
- Produces: discovery log of 13 skills; `Validation passed.`

- [ ] **Step 1: Run the validator**

```bash
node scripts/validate-cursor-plugin.mjs
```

Expected:

```
pm-superpowers: discovered 13 skill(s).
Validation passed.
```

- [ ] **Step 2: Confirm skill names on disk**

```bash
ls plugins/pm-superpowers/skills
```

Expected: includes `find-your-moat` and `skill-guide`; does **not** include `using-pm-superpowers`.

- [ ] **Step 3: Commit any validator-driven fixes** (only if Step 1 failed)

---

### Task 6: Open the implementation PR

**Files:** none (git + PR metadata)

- [ ] **Step 1: Push the branch and open a PR**

Title: `Add find-your-moat front door; rename skill-guide`

Body must summarize:

- New `find-your-moat` thin pass (4 types; 4 not assessed; real product only).
- Rename `using-pm-superpowers` → `skill-guide`.
- README + optional `strategic-moat` cross-link.
- Design spec: `docs/superpowers/specs/2026-09-18-find-your-moat-skill-guide-design.md`
- Plan: `docs/superpowers/plans/2026-09-18-find-your-moat-skill-guide.md`
- Validator: `pm-superpowers: discovered 13 skill(s).` / `Validation passed.`
- Post-merge: resubmit Cursor marketplace listing **51593709**; ping Marketing Bot with this PR URL.

Out of this PR: marketplace publish UI, P1 features, Marketing Bot copy.

---

## Spec coverage (self-review)

| Spec requirement | Task |
|---|---|
| New `find-your-moat` skill + frontmatter rules | Task 1 |
| Thin flow (2–3 Qs, 4 types, so-what, save, handoff) | Task 1 |
| Never complete / never sample / ask if unnamed | Task 1 |
| Rename router to `skill-guide`; keep old triggers + "skill guide" | Task 2 |
| Catalog + save-path tables include `find-your-moat` | Task 2 |
| No leftover `using-pm-superpowers` path | Task 2 |
| Optional one-line `strategic-moat` cross-link; intake/8-types unchanged | Task 3 |
| Root + plugin README lead + utility rename | Task 4 |
| Validator discovers 13 skills | Task 5 |
| Implementation PR + post-merge marketplace / Marketing notes | Task 6 |
| Dual packaging, no body duplication, no P1, no publish UI | Global Constraints |
