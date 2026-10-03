# PM Superpowers — 1k Stars Marketing Design

**Date:** 2026-09-17  
**Owner:** Ani Ganti  
**Goal:** Reach ~1,000 GitHub stars on [aniganti/pm-superpowers](https://github.com/aniganti/pm-superpowers) as soon as possible, with fully unattended social posting after one-time setup.  
**Status:** Design approved in conversation (§§1–3); awaiting owner review of this written spec before implementation planning.

---

## 1. Context

### Product
PM Superpowers is a dual-format agent plugin (Claude Code + Cursor / Grok Bot) that turns proven product-strategy frameworks into interactive skills: `/strategy`, competitive landscape, VRIO, strategic moat (8 moat types), ecosystem, pre-mortem, prioritization, decision log, stakeholder alignment, verification, etc.

### Origin (credibility assets)
- **2022:** [How to create and communicate a product strategy in 6 steps](https://uxdesign.cc/product-strategy-framework-a4d49bf5b265) (UX Collective).
- **2026:** [I wrote about product strategy in 6 steps in 2022. I just built a Claude plugin that runs it for you.](https://aniganti.medium.com/i-wrote-about-product-strategy-in-6-steps-in-2022-i-just-built-an-ai-that-runs-it-4c6375527a5c)

The plugin is the runnable form of that published thinking — not a prompt pack invented for virality.

### Prior content system (reviewed)
A Jul–Aug 2026 X/Threads spreadsheet queued daily posts across pillars (framework education, tool demos, memes, hot takes, social proof, builder journey). Strengths: clear pillars, dual-platform copy, 280-char thread splits. Gaps: **nothing was posted**; posting was explicitly manual; channels beyond X/Threads were missing; conversion-to-star CTAs were soft; at ~47 stars the mix over-taught and under-launched.

### Constraints locked with owner
| Decision | Choice |
|---|---|
| Automation level | Fully unattended — schedule and post without per-post approval |
| Timeline | ASAP — speed over polish |
| Ongoing channels | X + Threads (daily cadence) |
| Launch channels | Show HN + Dev.to + Hashnode (one-time / rare follow-ups, not daily spam) |
| Approach | **A — Launch spike** |
| Brand spine | Moat / defensibility machine — answer “what’s our moat?” in minutes |

---

## 2. Branding & messaging (§2 approved)

### One-liner
**PM Superpowers is the moat machine for product teams — run a real defensibility analysis in minutes, not a blank Google Doc.**

### Origin line (HN / Dev.to / launch)
**In 2022 I published a 6-step product strategy framework. In 2026 I built the Claude/Cursor plugin that runs it.**

### Positioning stack
1. **Hook (growth):** moat / defensibility machine.  
2. **Credibility:** years of published strategy writing → runnable agent plugin.  
3. **Product truth:** full strategy suite (VRIO, moats, pre-mortem, `/strategy`, competitive research, etc.).

Do **not** replace the moat wedge with a generic “AI strategy” pitch. Do **not** lead with “AI writes PRDs.”

### Do / Don’t
**Do**
- Name concrete moat types / VRIO dimensions.
- End conversion posts with an explicit repo + star CTA.
- Link the 2022 article when telling the origin story.
- Mention Claude Code *and* Cursor/Grok Bot install where relevant.

**Don’t**
- Auto-reply to mentions or DMs (v1).
- Claim unverified traffic mix or fake social proof.
- Post paid boosts or engagement bait without a separate decision.
- Endlessly repost Show HN / Dev.to (spam risk).

### Channel accents
| Channel | Accent |
|---|---|
| X / Threads | Sharp moat hooks, short threads, install + star CTA |
| Show HN | “I productized my own strategy writing into an agent plugin” |
| Dev.to / Hashnode | Longer origin + install walkthrough |

---

## 3. System shape (§1 approved)

Two layers:

1. **Launch week (days 0–7)** — coordinated Show HN + Dev.to/Hashnode + X/Threads burst around one story.  
2. **Always-on engine (day 8+)** — unattended daily X + Threads via a scheduler, fed by Grok Bot routines.

**Guardrails**
- Standing kill-switch: owner message (“pause marketing”) pauses routines.  
- No auto-replies / DMs.  
- No paid promotion in v1.  
- Weekly star-count digest to owner only (not public).

---

## 4. Launch week pack (§3 approved)

### Day 0 — Repo surface
- README hero + one-liner → moat machine.
- Prominent links to 2022 + 2026 Medium posts.
- Install paths for Claude Code and Cursor / Grok Bot.
- Clear “Star if this saved you an afternoon” CTA.

### Day 1 — Show HN
- **Title pattern:** `Show HN: PM Superpowers – agent plugin that runs a real moat/strategy analysis`
- **Body:** origin arc (2022→2026) + what `strategic-moat` / `/strategy` / competitive sub-agent do + repo link + honest “what it is not” (not a PRD generator).
- Post once; monitor comments manually or via a light digest routine (replies stay human).

### Day 1–2 — Dev.to + Hashnode
- Long-form = expanded 2026 Medium follow-up: problem (strategy takes hours), solution (interactive skills), install, example moat/VRIO run, star CTA.
- Cross-post to Hashnode with canonical link preference to avoid duplicate-content muddle where possible.

### Days 1–7 — X / Threads burst
- **Cadence:** 2×/day.
- **Themes:** moat hooks, VRIO one-liners, origin one-liners, install CTAs, live star milestones.
- **Source:** rewrite/sharpen high-performing ideas from the old spreadsheet; drop soft “build in public” filler and unverified claims.
- Respect 280-char limits unless X Premium is confirmed later; keep thread labeling for multi-part posts.

### Launch success criteria (week 1)
- Show HN + Dev.to/Hashnode live.
- ≥14 scheduled X/Threads posts shipped without owner paste.
- Measurable star lift vs pre-launch baseline (track absolute stars + 7-day delta).

---

## 5. Always-on automation (§3 approved)

### Components
| Piece | Role |
|---|---|
| **Scheduler** | Postiz or Zernio (decide at implementation): OAuth to X + Threads; schedule/publish API |
| **Daily Grok Bot routine** | Fetch live GitHub star count → draft 1–2 posts from brand rules → push to scheduler → no chat approval |
| **Weekly Grok Bot routine** | Digest: stars, 7-day delta, what posted, suggested themes next week — notify owner only |
| **Content rules skill** | Encodes brand spine, do/don’t, channel accents, CTA patterns, 280-char splits |
| **Kill-switch** | Pause/resume routines on owner command |

### Content generation rules (engine)
- Default to **moat / VRIO / defensibility** angles ≥60% of posts.
- Rotate secondary pillars: pre-mortem, competitive research, origin story, star milestones.
- Auto-fill `[X]` star placeholders from live GitHub API.
- Every 3rd post includes explicit `github.com/aniganti/pm-superpowers` + star ask.
- Never invent metrics; if insights unavailable, omit.

### Out of scope for v1
- Auto-replies, Reddit bots, LinkedIn, email newsletter, paid ads.
- Fully unattended Show HN / Dev.to posting on a schedule (launch-only).
- Video/GIF generation for every post (optional later; text-first for speed).

### One-time human setup (cannot be skipped)
1. Connect X + Threads to the chosen scheduler.  
2. Grant Grok Bot access to the scheduler (plugin/API key as required).  
3. Approve standing unattended-publish permission in chat (already chosen; confirm once at wiring).  
4. Merge any pending logo/README marketing surface PRs if still open.

---

## 6. Metrics

| Metric | Cadence | Target signal |
|---|---|---|
| GitHub stars (absolute) | Daily in engine; weekly digest | Path to 1,000 |
| 7-day star delta | Weekly | Acceleration after launch week |
| Posts shipped unattended | Weekly | 100% of scheduled X/Threads without owner paste |
| Referral sanity | Weekly (GitHub traffic if available) | Social / referral bumps after launch posts |

No vanity engagement KPIs as primary success — **stars** are the north star.

---

## 7. Risks & mitigations

| Risk | Mitigation |
|---|---|
| Unattended brand damage | Narrow content rules skill; kill-switch; no replies |
| HN / Dev.to spam perception | Launch-once policy; high-quality origin story |
| Scheduler / API outages | Routine logs failure in weekly digest; retry next day |
| 280-char thread breakage | Validate length before schedule; prefer single sharp posts when unsure |
| Moat-only fatigue | 60% moat floor, not 100%; rotate secondary pillars |

---

## 8. Implementation sequence (after this spec is approved)

1. Choose and connect scheduler (Postiz vs Zernio) for X + Threads.  
2. Save content-rules skill + daily/weekly routines on Grok Bot.  
3. README / social surface pass for moat-machine + Medium links.  
4. Draft and schedule launch-week copy (Show HN, Dev.to, Hashnode, X/Threads burst).  
5. Ship launch day; flip always-on engine to unattended.  
6. Weekly digests until 1k stars; then revisit cadence.

---

## 9. Open items for implementation planning

- Final scheduler choice (Postiz vs Zernio) after comparing auth + scheduling APIs.  
- Confirm whether Ani now has X Premium (affects thread vs single-post defaults).  
- Exact Show HN posting time (weekday US morning recommended).  
- Whether Hashnode is mirror-only or primary for long-form SEO.

---

## Appendix — Messaging crib

**Hook:** Answer “what’s our moat?” in minutes.  
**Proof:** 2022 framework article → 2026 agent plugin.  
**CTA:** Star [aniganti/pm-superpowers](https://github.com/aniganti/pm-superpowers) if it saves you an afternoon.  
**Not:** A PRD writer. A judgment / defensibility workflow.
