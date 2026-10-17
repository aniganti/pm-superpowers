# Transcript — find your moat for Linear

Re-run of `find-your-moat` on 2026-10-17, following the current `plugins/pm-superpowers/skills/find-your-moat/SKILL.md`. The product, audience, and public pages are the 2026-10-10 inputs. Questions are the skill's, including the substitute. The write-up in section 4 is the skill's output, saved as [`examples/find-your-moat-linear.md`](../examples/find-your-moat-linear.md).

The skill's own save step writes `docs/strategic-moat/2026-10-17-find-moat-linear.md`. This published example lives under `examples/` so a read on Linear is not filed as this repo's strategy note.

## Recording

Follow the sections in order. Save the visual as `demo/find-your-moat.gif` (the README already points there). Aim for about 25 seconds, 5 MB or less, roughly 1200 px wide, a readable font, and a dark theme. Keep account emails and secrets off screen.

Public pages the answers draw on:

- https://linear.app/
- https://linear.app/method/introduction
- https://linear.app/now/rebuilding-delta-sync-read-path
- https://linear.app/switch/migration-guide
- https://linear.app/docs/github

---

## 1. Ask

**You:** find my moat for Linear

## 2. Question — product and audience

**Skill:** Linear is the product. What is it, and who is it for?

**You:** Linear, at linear.app. They call it the product development system for teams and agents: software product and engineering teams, including work they hand to coding agents. The public product turns Slack conversations and customer requests into issues, then plans them with cycles, projects, and initiatives. Cycles are a product feature. Linear's Method (linear.app/method/introduction) describes an n-week cycle as the routine where a team sets priorities and unfinished work moves forward. Their sync-engine post (linear.app/now/rebuilding-delta-sync-read-path) says each client keeps a local database, so creating an issue, changing its status, or navigating the workspace does not need a network round trip. The largest workspaces produce close to one million sync actions a day. I only have those public pages, not internal numbers.

## 3. Question — rivals and the substitute

**Skill:** Name 1–2 rivals, plus the substitute you fear most. A category is fine.

**You:** Jira, and GitHub Issues. The substitute is GitHub Projects: planning in the system where the code already lives. Linear's migration guide (linear.app/switch/migration-guide) names Jira and GitHub Issues, ships native importers for them, and tells you to rewire the tools a team already uses, including GitHub, Slack, and support tools. It also offers two-way sync so a team can try Linear without a hard cutover. Their GitHub doc (linear.app/docs/github) can link pull requests and can sync issues one-way or two-way. Issue sync only picks up issues created after sync is on, unless you import history.

## 4. What the skill returns

**Skill:**

# Find Your Moat — Linear

**Date:** 2026-10-17
**Depth:** Thin first pass (4 types scored, 8 screened). Not a complete defensibility assessment.

## Context

- **Product / audience:** Linear — the product development system for software teams and the coding agents that work with them (public positioning on linear.app). This pass uses public pages only, no internal usage data.
- **Rivals (1–2):** Jira; GitHub Issues.
- **Substitute you fear most:** GitHub Projects — planning in the system where the code already lives.

## Thin scorecard

| Moat type | Rating | Evidence | Deepen |
|---|---|---|---|
| Feedback loops | Moderate | Filing or updating an issue does not wait on the network (Linear's public local-first sync writeup), and Cycles are the product's repeating cadence: the Method describes an n-week cycle as the routine where a team sets priorities and unfinished work rolls forward. [public web] | At the next cycle close, show one pre-filled line of customer-request issues finished that cycle, and see whether the team opens the cycle without a reminder. |
| Network effects | None | N/A, not a dependency [inference] | Do not fund a cross-company network. If the only growth idea is inviting another teammate, count it as seat expansion. |
| Switching costs | Moderate | Linear's migration guide treats a move from Jira or GitHub Issues as an import plus a rewire of GitHub, Slack, and support tools, and offers two-way sync so a team can avoid a hard cutover. [public web] | On one team, write the exit inventory: issues that export, and cycle history plus automations that stay behind. Spend the week making cycle history and automations the reason a team stays. |
| Unique data/tech | Emerging | The public sync-engine post documents a real local-first system, with the largest workspaces producing close to one million sync actions a day, and the public product does not show usage compounding into a dataset Jira or GitHub cannot assemble. [public web] | For one workspace, plot triage-suggestion accept rate against workspace age. If the rate is flat, the advantage is the engine's speed, not a data flywheel. |

## Screen (not scored)

| Moat type | Could this be a primary moat? | Evidence |
|---|---|---|
| Ecosystem lock-in | No | Linear is one workspace. GitHub, Slack, and support-tool connectors are integrations, and the migration guide's two-way sync is a way out, not a suite a team loses by leaving. [public web] |
| Economies of scale | No | N/A, not a dependency [inference] |
| Brand and trust | No | The public site and the Method give software teams a point of view, and they do not show a reputation barrier a faster issue tracker would need years to copy. [public web] |
| Regulatory barriers | No | N/A, not a dependency [inference] |

## So-what

- Strongest scored: Switching costs. A settled team leaves behind issue history, the cycle rhythm, and the GitHub, Slack, and support-tool wiring. The rating stays Moderate because Linear's own importers and two-way GitHub sync are a built-in way through that wall.
- Most at-risk moat: Switching costs — the business depends on issue history, the cycle rhythm, and the tool wiring, and the substitute (GitHub Projects) lets a team plan where the code lives without migrating that history, because Linear's own two-way sync copies new issues into GitHub. [public web]
- Competitor-copy risk: GitHub Projects is the substitute. Linear's GitHub issue sync copies new issues into the system where the code already lives, so a team can plan in GitHub Projects and keep Linear as a mirror. Jira remains the suite teams buy when they want Atlassian's breadth. Local-first speed and the cycle habit are the parts with a slower copy.
- Do this week: On one team, turn on two-way GitHub Issues sync for a single cycle and watch where planning actually happens. If the cycle review stays in Linear, keep sync as an issue mirror. If planning moves to GitHub, move the cycle review back into Linear so the GitHub copy stays issues only.

## 5. Save and handoff

**Skill:** Saved this write-up to `examples/find-your-moat-linear.md`.

Want the full 8-type defensibility assessment? That is `strategic-moat`.

Want competitive context or a VRIO read first? That is `competitive-landscape` or `vrio-analysis`.
