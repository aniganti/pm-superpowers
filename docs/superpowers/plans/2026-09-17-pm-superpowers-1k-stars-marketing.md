# PM Superpowers 1k Stars Marketing — Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Ship a launch-spike week (Show HN + Dev.to/Hashnode + X/Threads burst) then run a fully unattended daily X/Threads engine so Ani Ganti does not manually paste posts, on the path to ~1,000 GitHub stars for `aniganti/pm-superpowers`.

**Architecture:** Grok Bot owns content rules + routines. Postiz (preferred) schedules/publishes to X and Threads after one-time OAuth. Launch long-form (Show HN, Dev.to, Hashnode) is drafted by the agent and published once (browser or site UI), not daily-automated. Weekly digests go only to Ani.

**Tech Stack:** Grok Bot (`update_state` skills/routines), Postiz plugin `58737848`, GitHub API for star counts, `aniganti/pm-superpowers` README, Medium origin URLs.

**Spec:** `docs/superpowers/specs/2026-09-17-pm-superpowers-1k-stars-marketing-design.md` (PR #8).

## Global Constraints

- Brand spine: moat / defensibility machine — answer “what’s our moat?” in minutes.
- Origin line: 2022 UX Collective framework → 2026 agent plugin.
- Fully unattended X/Threads after Task 1–3 wiring (no per-post approval).
- No auto-replies/DMs; no paid boosts; kill-switch via pause routines.
- Show HN + Dev.to/Hashnode = launch-only (not recurring spam).
- ≥60% of ongoing posts are moat/VRIO/defensibility; every 3rd post has explicit star CTA.
- Never invent metrics; fill star counts from live GitHub API.
- Assume 280-char X limit unless Ani confirms Premium.
- Standing publish permission already chosen by Ani; still confirm once when first connecting Postiz accounts.

---

### Task 1: Connect Postiz for X + Threads

**Files / surfaces:**
- Install marketplace plugin `58737848` (postiz) into Ani’s Cursor/Grok Bot account
- Ani completes OAuth for X and Threads in Postiz

**Interfaces:**
- Produces: working Postiz scheduling path the daily routine can call (CLI/skill documented by the plugin)

- [ ] **Step 1: Install Postiz**

Call `InstallPlugin` with `plugin_id: "58737848"` after a one-line framing SendToUser that this enables unattended X/Threads scheduling. If InstallPlugin requires a widget confirm first, use the widget then install.

- [ ] **Step 2: Discover Postiz skill/tools**

Read the installed `postiz` skill and list available schedule/publish commands. Confirm Threads + X are supported destinations.

- [ ] **Step 3: Hand Ani account connection**

SendToUser: connect X and Threads in Postiz (OAuth). Use `request_box_help` if browser login is required on the box. Do not proceed to Task 3 until both accounts show connected.

- [ ] **Step 4: Smoke-test one draft schedule**

Schedule a **private/test** or clearly labeled draft post (or schedule then delete) via Postiz to prove the path works. Record the exact command/pattern in the content-rules skill notes for Task 2.

- [ ] **Step 5: Confirm standing unattended permission**

SendToUser one confirmation: “Posts will go out on the daily cadence without asking each time. Say pause marketing to stop.” Treat prior “fully unattended” answer as the grant; this message is the on-the-record reminder.

---

### Task 2: Save `pm-superpowers-content-rules` skill on Grok Bot

**Files:**
- Create via `update_state` target `skill` action `write`
- Name: `pm-superpowers-content-rules`
- Description: `use this when drafting or scheduling PM Superpowers marketing posts for X, Threads, or launch copy`

**Interfaces:**
- Produces: skill body the daily/weekly routines must follow verbatim for brand rules

- [ ] **Step 1: Write skill body**

Skill body MUST include:
- One-liner + origin line from the spec
- Do/Don’t list
- Channel accents
- Pillar mix (≥60% moat/VRIO)
- Star CTA every 3rd post
- Live star fetch: `https://api.github.com/repos/aniganti/pm-superpowers`
- Medium links:
  - https://uxdesign.cc/product-strategy-framework-a4d49bf5b265
  - https://aniganti.medium.com/i-wrote-about-product-strategy-in-6-steps-in-2022-i-just-built-an-ai-that-runs-it-4c6375527a5c
- Repo: https://github.com/aniganti/pm-superpowers
- Kill-switch phrase: owner says “pause marketing”
- Postiz scheduling pattern discovered in Task 1
- Never invent metrics; never auto-reply

- [ ] **Step 2: Save skill**

`update_state` skill write with name, description, body. Mention it to Ani as a pill if the host supports `sand-workflow` links.

- [ ] **Step 3: Sanity check**

Draft one sample X post + one Threads post in chat using the skill rules (do not publish yet). Confirm ≤280 chars for single tweets / labeled thread parts.

---

### Task 3: Create daily unattended posting routine

**Files:**
- `update_state` target `routine` action `create`

**Interfaces:**
- Consumes: `pm-superpowers-content-rules` skill; Postiz from Task 1
- Produces: scheduled daily fires that publish without asking Ani

- [ ] **Step 1: Create routine**

- **name:** `PM Superpowers daily social`
- **schedule:** `0 10,16 * * 1-5` (10:00 and 16:00 America/Toronto weekdays) — two posts/day Mon–Fri during launch week intensity; after launch week, optionally update to `0 10 * * 1-5` (once daily) unless star velocity still warrants 2×
- **prompt (intent, not frozen tool args):**

```
You are running the PM Superpowers unattended social engine.
1. Read and follow the pm-superpowers-content-rules skill.
2. Fetch live star count from GitHub for aniganti/pm-superpowers.
3. Draft ONE X post and ONE Threads post for this slot (moat/VRIO bias; star CTA if this is every 3rd post in the running cadence — track cadence in agent memory).
4. Schedule/publish both via Postiz for immediate or next-slot publish without asking Ani.
5. If Postiz or GitHub fails, note the failure for the weekly digest and stop quietly (no spam retries).
6. If Ani has paused marketing, do nothing.
Do not send replies or DMs. Do not post to HN/Dev.to/Hashnode from this routine.
```

- [ ] **Step 2: Confirm save**

Tell Ani the routine exists, cadence, and kill-switch phrase.

- [ ] **Step 3: Optional first manual fire**

If tools allow a one-off test run, fire once and verify posts appear in Postiz queue / live. Otherwise wait for first scheduled fire and check in weekly digest.

---

### Task 4: Create weekly digest routine

**Files:**
- `update_state` target `routine` action `create`

- [ ] **Step 1: Create routine**

- **name:** `PM Superpowers weekly stars digest`
- **schedule:** `0 9 * * 1` (Monday 09:00 America/Toronto)
- **prompt:**

```
Weekly PM Superpowers marketing digest for Ani only.
1. Fetch current GitHub stars for aniganti/pm-superpowers and estimate 7-day delta if prior count is in memory; otherwise record today’s baseline.
2. Summarize what the daily social routine posted last week (from memory/logs), or say unknown.
3. Note any Postiz/GitHub failures.
4. Suggest 3 themes for next week under the moat-machine spine.
5. Send this digest to Ani. Do not publish anything publicly.
Update agent memory with today’s star count for next week’s delta.
```

- [ ] **Step 2: Confirm to Ani**

One line: Monday 9am digest is on.

---

### Task 5: README moat-machine surface pass

**Files:**
- Modify: `README.md` (hero / “What is this, really?” / Getting started CTA)
- Optionally add Medium links near the top

**Interfaces:**
- Produces: PR on `aniganti/pm-superpowers`

- [ ] **Step 1: Draft README edits**

Update centered strong tagline toward: moat machine / defensibility in minutes, while keeping dual Claude+Cursor install truth. Add short Origin blurb with both Medium links. Add explicit star CTA near top.

- [ ] **Step 2: Open PR via CloudAgent**

Launch CloudAgent on `https://github.com/aniganti/pm-superpowers` with the exact README copy changes. Do not break install instructions.

- [ ] **Step 3: Ask Ani to merge**

Send PR URL; do not merge without Ani.

---

### Task 6: Draft launch copy pack

**Files:**
- Create in repo or `/workspace` then PR: `docs/superpowers/launch/2026-09-launch-copy.md`

Must include ready-to-paste:

1. **Show HN title + body** (origin arc + moat hook + repo + not-a-PRD-generator)
2. **Dev.to article** (800–1500 words outline filled with full draft)
3. **Hashnode note** (canonical/cross-post instructions)
4. **14 X posts + 14 Threads posts** for days 1–7 at 2×/day (rewrite sharpened from old spreadsheet; moat-heavy; live star placeholders as `{STARS}`)

- [ ] **Step 1: Write the launch copy file**
- [ ] **Step 2: PR or attach for Ani**
- [ ] **Step 3: Ani approval of Show HN + Dev.to titles only** (social burst can auto-schedule)

---

### Task 7: Execute launch week

- [ ] **Step 1: Schedule X/Threads burst** via Postiz from Task 6 copy (replace `{STARS}` with live count at schedule time)
- [ ] **Step 2: Publish Dev.to** (browser computerUse or Ani handoff if login needed); mirror Hashnode
- [ ] **Step 3: Publish Show HN** weekday US morning; monitor comments; Ani replies personally
- [ ] **Step 4: Confirm daily routine remains enabled** for post-launch cadence
- [ ] **Step 5: Record baseline stars** in agent memory on launch day

---

### Task 8: Post-launch ops

- [ ] **Step 1: After 7 days, review velocity** in Monday digest
- [ ] **Step 2: If 2×/day is noisy or low ROI, update daily routine to `0 10 * * 1-5`**
- [ ] **Step 3: Keep kill-switch documented** in profile/memory

---

## Spec coverage checklist

| Spec section | Tasks |
|---|---|
| Branding / messaging | 2, 5, 6 |
| Launch week | 5, 6, 7 |
| Always-on engine | 1, 2, 3, 4 |
| Guardrails / kill-switch | 1, 3, 4 |
| Metrics / weekly digest | 4, 8 |
| Scheduler choice | 1 (Postiz) |

## Self-review notes

- No TBD placeholders in task steps.
- Postiz chosen over Zernio for skill+multi-platform scheduling; swap only if Postiz cannot connect Threads.
- HN/Dev.to stay human-gated at publish time because of login + spam norms; drafting is automated.
