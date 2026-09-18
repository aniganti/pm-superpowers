# PM Superpowers — September 2026 Launch Copy

**Status:** Draft — ready to paste. Do not publish from this file automatically.  
**Repo:** https://github.com/aniganti/pm-superpowers  
**Star placeholder:** Always use `{STARS}` in posts (baseline ~47; never hardcode a live count).  
**Brand hook:** The moat machine — answer “what’s our moat?” in minutes.  
**Positioning:** Not a PRD generator. Interactive strategy workflows (VRIO, moat, competitive research, `/strategy`), not faster doc writing.

**Origin trail**
- 2022 UX Collective: [Product strategy framework (6 steps)](https://uxdesign.cc/product-strategy-framework-a4d49bf5b265)
- 2026 Medium: [I wrote about product strategy in 6 steps in 2022. I just built an AI that runs it.](https://aniganti.medium.com/i-wrote-about-product-strategy-in-6-steps-in-2022-i-just-built-an-ai-that-runs-it-4c6375527a5c)

---

## 1. Show HN

### Title

```
Show HN: PM Superpowers – Claude/Cursor plugin that runs VRIO + moat analysis (not a PRD generator)
```

### Body (ready to paste)

```
In 2022 I wrote a UX Collective piece on a 6-step product strategy framework
(https://uxdesign.cc/product-strategy-framework-a4d49bf5b265). It got a few
dozen claps. Then I spent three more years doing strategy the same way:
Google Doc, fifteen tabs, 4–8 hours I didn’t have.

The problem was never knowledge. Running a real VRIO or moat assessment means
researching competitors, scoring capabilities honestly, and pressure-testing
conclusions. Done properly it takes hours. Done quickly it dies in the first
hard leadership question. So most of the time it doesn’t get done.

PM Superpowers is a Claude Code / Cursor plugin that turns those frameworks
into interactive workflows — not a prompt pack, not a PRD generator.

What’s inside:
• strategic-moat — defensibility across 8 moat types (network effects,
  switching costs, data advantages, ecosystem lock-in, etc.)
• /strategy — Rumelt-kernel 6-step session: market → problem → VRIO pillars →
  design/tech alignment → vision/goals → communication
• competitive-researcher sub-agent — web research so you’re not opening
  fifteen tabs yourself
• Also: vrio-analysis, pre-mortem, prioritization, decision-log,
  stakeholder-alignment

Recommended pipeline:
  competitive-landscape → vrio-analysis → strategic-moat → strategy → pre-mortem

Hook: it’s a moat machine. Ask “what’s our moat?” and get structured analysis
in minutes — evidence, ratings, and deepening opportunities — not adjectives.

Install (Claude Code):
  claude plugin marketplace add aniganti/pm-superpowers
  claude plugin install pm-superpowers
  then /strategy

Cursor: install PM Superpowers from the Cursor marketplace (same repo).

Repo: https://github.com/aniganti/pm-superpowers ({STARS} ★)
2026 write-up: https://aniganti.medium.com/i-wrote-about-product-strategy-in-6-steps-in-2022-i-just-built-an-ai-that-runs-it-4c6375527a5c

I’d love feedback from PMs who’ve tried to run VRIO/moat by hand, and from
folks building strategy tooling that isn’t just “generate a PRD.”
```

---

## 2. Dev.to article

**Suggested title:** The Moat Machine: I Wrote About Product Strategy in 2022. In 2026 I Built the AI Plugin That Runs It.  
**Tags:** `productmanagement`, `ai`, `claude`, `strategy`, `opensource`  
**Canonical URL (when published first on Dev.to):** set Dev.to as canonical if Hashnode mirrors later.

### Full draft (~1,200 words)

```markdown
# The Moat Machine: I Wrote About Product Strategy in 2022. In 2026 I Built the AI Plugin That Runs It.

In December 2022 I published a UX Collective article on a systematic way to
develop and socialize product strategy. Six steps. Rumelt’s strategy kernel.
VRIO for pillars. A path from diagnosis to communication.

It got 52 claps. I was happy about that.

Then I went back to work and spent the next three years doing product strategy
exactly the way I always had: a Google Doc, a lot of tabs, and somewhere
between four and eight hours I didn’t really have.

Not because I didn’t know the frameworks. I knew them well enough to write
about them. The problem was never knowledge. It was execution.

## The problem isn’t “write faster”

Most AI-for-PM tools stop at generating a PRD. They help you write faster, not
think straighter. That sounds helpful until you’re in a leadership review and
someone asks the question that turns a polished doc into wet paper:

**“What’s our moat?”**

If your answer is an adjective — sticky, delightful, AI-powered — you don’t
have a strategy. You have a slide.

The hard part of product strategy isn’t drafting. It’s the work that makes a
draft survive that room:

- Researching competitors without drowning in fifteen tabs
- Scoring your capabilities on Value, Rarity, Imitability, and Organization —
  honestly, not aspirationally
- Assessing defensibility across real moat types (network effects, switching
  costs, data advantages, ecosystem lock-in) instead of picking the buzzword
  that sounds best on a slide
- Stress-testing a launch before the launch stress-tests you

Done properly, this takes hours. Done quickly, it produces analysis that
wouldn’t survive a single hard question. So most of the time, it doesn’t get
done at all — and the roadmap keeps shipping features that don’t compound into
advantage.

There had to be a better way in 2026.

## Origin: from article to plugin

The 2022 piece —
[The systematic approach to developing and socializing product strategy](https://uxdesign.cc/product-strategy-framework-a4d49bf5b265) —
was a field guide. Useful on paper. Still slow in practice. Knowing Rumelt’s
Why / What / How doesn’t magically create an afternoon where you can run VRIO
without interruptions.

In 2026 I shipped what that article implied: an interactive AI workflow that
*runs* the frameworks instead of summarizing them in another essay.

Write-up:
[I wrote about product strategy in 6 steps in 2022. I just built an AI that runs it.](https://aniganti.medium.com/i-wrote-about-product-strategy-in-6-steps-in-2022-i-just-built-an-ai-that-runs-it-4c6375527a5c)

Repo: [aniganti/pm-superpowers](https://github.com/aniganti/pm-superpowers)

## What PM Superpowers actually is

**PM Superpowers** is a Claude Code / Cursor plugin: skills, one sub-agent, and
a shared library of named strategy frameworks. It triggers in conversation —
you don’t copy-paste a mega-prompt from a Notion doc you’ll forget to open.

It is **not** a PRD generator. That distinction matters. Faster docs are easy.
Defensible strategy is scarce.

In practice it feels like a strategy-minded chief of staff who’s read VRIO,
aggregation theory, and every pre-mortem post-mortem — and asks the next hard
question instead of dumping a wall of text. The AI doesn’t freestyle a
plausible-sounding essay; it interviews you along the framework’s actual
dimensions.

### The moat machine

Brand hook, said plainly: **answer “what’s our moat?” in minutes.**

The `strategic-moat` skill walks you through eight moat types, asks for
evidence (not vibes), rates strength, and surfaces deepening opportunities.
You’re pushed to say what product behavior, data, or user dynamics support
each rating — and where the moat is thin.

You leave with a moat profile you can defend: strongest moats, weakest moats,
deepening moves, and a defensibility verdict grounded in *your* product, not a
generic essay about “network effects in tech.”

That’s the moat machine. Not a slogan — a session you can run before the next
strategy review.

### `/strategy` — the six-step session

`/strategy` is the orchestrator from the 2022 framework, now interactive:

1. **Market analysis** — context, stage, constraints worth naming  
2. **Problem space** — the diagnosis, not the feature wishlist  
3. **Strategic pillars via VRIO** — sustained advantage, not workshop themes  
4. **Design and technical alignment** — constraints and risks early  
5. **Vision, mission, goals** — direction tied to pillars  
6. **Communication planning** — how this lands with the people who must buy in  

Grounded in Rumelt’s Why / What / How. The AI interviews you; you don’t
freestyle into a slide deck and call it strategy. Artifacts land in structured
docs you can revisit — not chat scroll you’ll never find again.

### VRIO, without the self-grading curve

Standalone `vrio-analysis` applies the decision tree to concrete capabilities:

- Valuable? If no → disadvantage. Stop.  
- Rare? If no → parity.  
- Inimitable? If no → temporary advantage.  
- Organized to capture value? If no → unused advantage.  
- Yes across the board → sustained competitive advantage.

Most teams skip a gate and still call it a pillar. The skill makes skipping
awkward — which is the point.

### Competitive sub-agent

Moat analysis without competitive intel is fan fiction.

The `competitive-researcher` sub-agent gathers competitive intelligence via
web research so `competitive-landscape` isn’t “please paste everything you
know about competitors.” You review the synthesis; you don’t become a tab
farmer. That landscape then feeds VRIO and moat instead of living in a
separate deck nobody opens.

### How the pieces chain

Recommended full strategy pipeline:

```
competitive-landscape → vrio-analysis → strategic-moat → strategy → pre-mortem
```

External landscape → internal capabilities → defensibility → synthesized
strategy → launch stress-test.

That’s the design intent: workflow-chained, not isolated prompts. Decisions
can be logged with reasoning and alternatives. `stakeholder-alignment` turns
artifacts into briefings and FAQs for specific audiences. `verification`
quality-gates an artifact before you paste it into a QBR.

Also in the box: prioritization (RICE/ICE/weighted, grounded in pillars),
product-ecosystem (aggregation / value chain), prompt-builder, and an
interactive guide to the skills themselves.

Eleven skills. One sub-agent. Zero prompt engineering.

## Install (Claude Code + Cursor)

### Claude Code

```bash
claude plugin marketplace add aniganti/pm-superpowers
claude plugin install pm-superpowers
```

Then run `/strategy`, or ask something like “how defensible is this product?”
or “help me prioritize my backlog.”

### Cursor

Install **PM Superpowers** from the Cursor marketplace (Plugins). Search
`pm-superpowers`, install, reload if needed, and start a strategy session the
same way. The public listing is powered by the same GitHub repo.

(Optional local smoke-test: copy `plugins/pm-superpowers` into
`~/.cursor/plugins/local/` — details in the README. Prefer copying over
symlinks outside that folder.)

## What “good” looks like in a session

You’re not looking for a longer document. You’re looking for:

- VRIO scores you can explain without hand-waving  
- Moat ratings tied to product behavior and evidence  
- Competitive claims that cite something other than “I think”  
- Strategic pillars that fall out of advantage, not sticky-note themes  
- A pre-mortem that names Tigers, Paper Tigers, and Elephants before ship  

If your leadership asks “so what’s our moat?” you should be able to answer in
minutes — with structure — not schedule a follow-up doc.

That’s the moat machine.

## What this is not

A few anti-goals, said out loud so expectations stay honest:

- **Not a PRD generator.** If you need a PRD template, use a PRD template. This plugin is for advantage, defensibility, and strategy communication.
- **Not a replacement for judgment.** It structures the interview and the dimensions; you still own the calls.
- **Not fake certainty.** You’ll get ratings and evidence prompts — not invented market-share charts or vanity metrics.

If those boundaries match how you work, you’re the intended user.

## Star the repo if this is useful

If you build product strategy for a living — or you’ve always wanted to run
VRIO properly and never had the afternoon — try it and star the repo so other
PMs can find it:

**https://github.com/aniganti/pm-superpowers** ({STARS} ★)

Feedback welcome from two groups especially: PMs who’ve run these frameworks
by hand and know where the pain is, and builders who think AI-for-PM should
mean better thinking — not faster PRDs.

---

*Ani Ganti — 2022 framework article on UX Collective; 2026 plugin on GitHub.*
```

---

## 3. Hashnode

**Purpose:** Mirror the Dev.to article for reach; do **not** create two competing canonicals.

### Short note (for the Hashnode draft / settings)

```
Mirror of the Dev.to launch article for Hashnode distribution.

Canonical preference:
• Publish first on Dev.to (or whichever platform you treat as source of truth).
• On Hashnode: set Canonical URL to the Dev.to post URL so SEO credit stays
  with the original.
• If you publish Hashnode first instead, reverse this — point Dev.to’s
  canonical at Hashnode.

Title / body: paste the Dev.to draft as-is (same “moat machine” framing,
origin links, install steps, star CTA with {STARS}).

Do not change the positioning: not a PRD generator; interactive VRIO + moat
+ /strategy + competitive sub-agent workflows.

Links to keep:
• Repo: https://github.com/aniganti/pm-superpowers
• 2022: https://uxdesign.cc/product-strategy-framework-a4d49bf5b265
• 2026: https://aniganti.medium.com/i-wrote-about-product-strategy-in-6-steps-in-2022-i-just-built-an-ai-that-runs-it-4c6375527a5c
```

---

## 4. Launch week — X + Threads (14 slots)

**Cadence:** Day 1–7 × AM + PM = 14 slots.  
**Rules applied:** ≥60% moat/VRIO-focused; every 3rd slot has an explicit star CTA; no fake metrics; always `{STARS}` not a hardcoded count.  
**Pillars used:** moat machine, VRIO, pre-mortem, meme/contrast, origin story.

Star CTA slots (every 3rd): **Day2 AM (#3), Day3 PM (#6), Day5 AM (#9), Day6 PM (#12)** — plus Day7 PM close also includes star (bonus close CTA).

Character counts below are targets ≤280 for single X posts; threads labeled Tweet 1/N.

---

### Day 1 AM — Hook (moat)

**X**
```
What’s our moat?

Most teams answer with adjectives.
The moat machine answers with evidence — 8 moat types, ratings, deepening moves — in minutes.

PM Superpowers: Claude/Cursor plugin. Not a PRD generator.

https://github.com/aniganti/pm-superpowers
```

**Threads**
```
What’s our moat?

If your answer is a vibe (“we’re sticky”), you don’t have a moat — you have a slide.

PM Superpowers is a Claude/Cursor plugin that runs strategic-moat + VRIO + /strategy as interactive workflows.

Moat machine energy: evidence, ratings, deepening opportunities — in minutes, not a weekend doc.

Not a PRD generator. Thinking tools for PMs who have to survive the hard question in the room.

Repo: https://github.com/aniganti/pm-superpowers
```

---

### Day 1 PM — VRIO sharpness

**X (thread)**
```
Tweet 1/3
VRIO isn’t a worksheet you fill with hope.

V — valuable?
R — rare?
I — inimitable?
O — organized to capture it?

Skip a gate → you don’t have sustained advantage. You have a feature.

Tweet 2/3
PM Superpowers runs vrio-analysis on YOUR product — interviews you, scores the decision tree, feeds pillars into /strategy.

Tweet 3/3
Moat machine + VRIO in one plugin for Claude Code / Cursor.
https://github.com/aniganti/pm-superpowers
```

**Threads**
```
Hot take: most “differentiation” decks fail VRIO in under two minutes.

Valuable? Maybe.
Rare? Doubt it.
Inimitable? Definitely not.
Organized to capture value? …awkward silence.

The plugin’s vrio-analysis skill walks the decision tree for real capabilities — then strategic-moat pressure-tests defensibility across 8 types.

That’s the moat machine: minutes to a defensible answer, not hours of tab archaeology.

https://github.com/aniganti/pm-superpowers
```

---

### Day 2 AM — Star CTA (#3) + origin

**X**
```
2022: I wrote the 6-step strategy framework on UX Collective.
2026: I built the Claude/Cursor plugin that runs it — VRIO, moat, /strategy, competitive sub-agent.

Star if you want more PMs to find the moat machine ({STARS} ★):
https://github.com/aniganti/pm-superpowers
```

**Threads**
```
Origin story, short:

2022 — UX Collective article on product strategy in 6 steps.
2026 — PM Superpowers: the AI workflows that actually run VRIO + moat + Rumelt /strategy.

Same frameworks. Less “Google Doc and vibes.” More structured interviews.

If that sounds useful, a star helps other PMs find it ({STARS} ★):
https://github.com/aniganti/pm-superpowers

2022: https://uxdesign.cc/product-strategy-framework-a4d49bf5b265
2026: https://aniganti.medium.com/i-wrote-about-product-strategy-in-6-steps-in-2022-i-just-built-an-ai-that-runs-it-4c6375527a5c
```

---

### Day 2 PM — Eight moats (moat)

**X (thread)**
```
Tweet 1/2
“We have a moat” usually means one buzzword.

strategic-moat checks eight — network effects, switching costs, data advantages, ecosystem lock-in, and more — with evidence required.

Tweet 2/2
Moat machine for Claude/Cursor. Not a PRD generator.
https://github.com/aniganti/pm-superpowers
```

**Threads**
```
Moat checklist energy:

• Network effects?
• Switching costs?
• Data advantages?
• Ecosystem lock-in?
• …and four more — rated with evidence, not adjectives.

That’s what strategic-moat does inside PM Superpowers.

Ask “what’s our moat?” → leave with a profile: strongest, weakest, deepening opportunities.

Minutes. Not a strategy offsite.

https://github.com/aniganti/pm-superpowers
```

---

### Day 3 AM — Pipeline (moat/VRIO)

**X**
```
Full strategy pipeline (the good kind):

competitive-landscape
→ vrio-analysis
→ strategic-moat
→ /strategy
→ pre-mortem

External truth → internal advantage → defensibility → plan → stress test.

Moat machine, chained.
https://github.com/aniganti/pm-superpowers
```

**Threads**
```
How the moat machine chains (so you’re not running skills in a vacuum):

1) competitive-landscape (+ researcher sub-agent)
2) vrio-analysis on real capabilities
3) strategic-moat across 8 types
4) /strategy synthesizes pillars
5) pre-mortem before you ship hope

Each step feeds the next. That’s the difference between a prompt pack and a workflow plugin.

Claude Code or Cursor. Same repo.
https://github.com/aniganti/pm-superpowers
```

---

### Day 3 PM — Star CTA (#6) + meme/contrast

**X**
```
AI-for-PM starter pack:
❌ “Generate a PRD”
✅ “Run VRIO + moat so we can defend the roadmap”

PM Superpowers = moat machine, not a doc printer.

Star the repo ({STARS} ★):
https://github.com/aniganti/pm-superpowers
```

**Threads**
```
Meme but true:

Them: “Can your AI write my PRD?”
Us: “Can your PRD survive ‘what’s our moat?’”

PM Superpowers is intentionally not a PRD generator. It’s interactive strategy: VRIO, strategic-moat, /strategy, competitive research sub-agent.

If you want that to spread, star it ({STARS} ★):
https://github.com/aniganti/pm-superpowers
```

---

### Day 4 AM — Competitive sub-agent (supports moat)

**X**
```
Moat analysis without competitive intel is fan fiction.

PM Superpowers’ competitive-researcher sub-agent does the web digging; you review the synthesis — then feed it into VRIO + strategic-moat.

Fewer tabs. Sharper moat.
https://github.com/aniganti/pm-superpowers
```

**Threads**
```
Unpopular PM truth: your moat claim is only as good as your competitive landscape.

That’s why the plugin ships a competitive-researcher sub-agent with competitive-landscape — so VRIO and strategic-moat aren’t built on “I think Competitor X is weak.”

Moat machine = evidence in, defensibility out.

https://github.com/aniganti/pm-superpowers
```

---

### Day 4 PM — Pre-mortem (pillar)

**X**
```
Before you launch, run the funeral.

pre-mortem in PM Superpowers: Tigers (real), Paper Tigers (scary-looking), Elephants (unnamed).

Moat tells you why you win. Pre-mortem tells you how you still lose.
https://github.com/aniganti/pm-superpowers
```

**Threads**
```
Strategy without a pre-mortem is optimism with formatting.

After strategic-moat + /strategy, run pre-mortem:

• Tigers — real risks, own them
• Paper Tigers — look scary, aren’t
• Elephants — the thing nobody wants to say

Name the Elephant two weeks early. Your launch will thank you.

Still the moat machine’s sibling skill — defensibility + failure modes.
https://github.com/aniganti/pm-superpowers
```

---

### Day 5 AM — Star CTA (#9) + install

**X**
```
Install the moat machine:

Claude Code:
claude plugin marketplace add aniganti/pm-superpowers
claude plugin install pm-superpowers
→ /strategy

Cursor: marketplace → PM Superpowers

Star if it helps ({STARS} ★):
https://github.com/aniganti/pm-superpowers
```

**Threads**
```
Getting started (no prompt engineering):

Claude Code:
• claude plugin marketplace add aniganti/pm-superpowers
• claude plugin install pm-superpowers
• /strategy  or  “how defensible is this product?”

Cursor: install PM Superpowers from Plugins (same GitHub repo).

Then run strategic-moat when someone asks “what’s our moat?”

Star so other PMs find it ({STARS} ★):
https://github.com/aniganti/pm-superpowers
```

---

### Day 5 PM — VRIO → pillars (moat/VRIO)

**X (thread)**
```
Tweet 1/2
Strategic pillars shouldn’t be themes from a workshop sticky wall.

They should fall out of VRIO: which capabilities are valuable, rare, hard to copy, and organized?

Tweet 2/2
/strategy does that interview → pillars → communication plan.
Moat machine upstream optional, recommended.
https://github.com/aniganti/pm-superpowers
```

**Threads**
```
Workshop sticky → “pillars” is how you get a strategy nobody can defend.

VRIO → pillars is how you get 2–4 sources of sustained advantage you’ll still believe next quarter.

PM Superpowers `/strategy` runs that path. Pair with strategic-moat when the room asks the only question that matters: what’s our moat?

https://github.com/aniganti/pm-superpowers
```

---

### Day 6 AM — Origin deep cut (moat)

**X**
```
I didn’t need another article about strategy.
I needed the article to run itself.

2022 framework → 2026 Claude/Cursor plugin:
moat + VRIO + /strategy + competitive sub-agent.

https://github.com/aniganti/pm-superpowers
```

**Threads**
```
The gap between “I know VRIO” and “I ran VRIO this week” is where strategy goes to die.

That’s why PM Superpowers exists: take the 2022 six-step framework and make it an interactive session — plus strategic-moat as the moat machine, plus a competitive sub-agent so research isn’t the blocker.

Knowledge wasn’t the bottleneck. Execution was.

https://github.com/aniganti/pm-superpowers
https://uxdesign.cc/product-strategy-framework-a4d49bf5b265
```

---

### Day 6 PM — Star CTA (#12) + leadership question

**X**
```
The question that kills vague strategy decks:

“What’s our moat?”

Answer it in minutes — 8 types, evidence, deepening moves.

Star the moat machine ({STARS} ★):
https://github.com/aniganti/pm-superpowers
```

**Threads**
```
Save this for your next strategy review:

Leader: What’s our moat?
You: [opens strategic-moat session]

Ratings. Evidence. Strongest / weakest. Deepening opportunities.
Optional: VRIO pillars already chained from the pipeline.

Not a PRD. Not adjectives.

If that workflow should be easier to find, star it ({STARS} ★):
https://github.com/aniganti/pm-superpowers
```

---

### Day 7 AM — Meme / contrast (moat)

**X**
```
Feature factory: ship more.
Moat machine: defend more.

PM Superpowers — VRIO, strategic-moat, /strategy, competitive research.
Claude Code + Cursor.

https://github.com/aniganti/pm-superpowers
```

**Threads**
```
Two kinds of PM tooling:

1) Helps you write the doc faster
2) Helps you survive “is this actually defensible?”

PM Superpowers is #2 on purpose.

Moat machine. VRIO decision trees. /strategy sessions. Competitive sub-agent.
Still not a PRD generator — and that’s the feature.

https://github.com/aniganti/pm-superpowers
```

---

### Day 7 PM — Close + star (moat + CTA)

**X (thread)**
```
Tweet 1/2
Launch week close: if “what’s our moat?” still takes a week and a Google Doc, try the moat machine.

strategic-moat · VRIO · /strategy · competitive sub-agent
Claude Code + Cursor · not a PRD generator

Tweet 2/2
Star / try / roast it ({STARS} ★):
https://github.com/aniganti/pm-superpowers

2022 → 2026 origin in the README + Medium write-up.
```

**Threads**
```
Week wrap:

PM Superpowers = moat machine for PMs.
Answer “what’s our moat?” in minutes with structured evidence — then chain VRIO → /strategy → pre-mortem.

Born from a 2022 UX Collective framework. Built as a 2026 Claude/Cursor plugin.

Not a PRD generator. Interactive strategy that holds up in the room.

Try it. Star it if it helps ({STARS} ★):
https://github.com/aniganti/pm-superpowers

Thanks for following along — feedback from framework nerds and skeptical PMs equally welcome.
```

---

## Appendix — Quick checklist before posting

- [ ] Replace `{STARS}` with the live count only at post time (or leave as-is if your scheduler supports a token). Baseline context ~47 — never invent growth metrics.
- [ ] Confirm Claude marketplace + Cursor listing instructions still match README.
- [ ] Show HN title ≤80 chars-ish; body links work.
- [ ] Dev.to published before Hashnode mirror (or swap canonicals intentionally).
- [ ] X posts: paste thread parts separately; verify ≤280 each.
- [ ] Do not claim fake user counts, revenue, or “#1” rankings.

---

*File prepared for launch ops. Nothing in this document has been published.*
