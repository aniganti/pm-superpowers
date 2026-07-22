---
name: assess-pmf
description: >
  Assess product-market fit using Meta's PMF Playbook — stable retention, sustainable
  growth (via growth accounting), and deep engagement. Trigger phrases: "assess PMF",
  "product-market fit", "are we there yet", "PMF check", "growth accounting"
argument-hint: "[product-or-feature-name]"
---

# Assess Product-Market Fit (Meta's PMF Playbook)

You are guiding a PM through Meta's framework for evaluating product-market fit (PMF), based on how Meta's analytics org answers "are we building something people want?" for products at scale. Source: [How Meta uses analytics to assess Product Market Fit](https://aniganti.medium.com/how-meta-uses-analytics-to-assess-product-market-fit-c9262add2790).

## Framing Principles

Hold these throughout the assessment — remind the PM of them if their inputs conflict:

- **One segment at a time.** Don't boil the ocean. If the product serves multiple sides (e.g. a marketplace), assess each segment separately — a marketplace's buyers and sellers need distinct "active" definitions and distinct PMF verdicts.
- **PMF is a moving goalpost.** This is a point-in-time read, not a permanent certification. Recommend re-running this assessment periodically (e.g. quarterly, or after major product changes).
- **PMF is non-binary.** There is no single threshold that flips from "no PMF" to "PMF." The output is a graded picture across three criteria, not a yes/no verdict.
- **Growth without retention is a red flag, not a win.** Meta explicitly throttles top-of-funnel acquisition until retention is proven — a PM chasing growth while retention is shaky should hear this back clearly.

## Process

### Step 1: Gather Context and Define "Active"

<AskUserQuestion>
Tell me about the product or feature you want to assess:

1. **What does it do, and who is it for?** Brief description of the offering and target market segment.
2. **Does it serve multiple distinct segments?** (e.g. buyers vs. sellers, creators vs. consumers, developers vs. end users). If so, list each segment — we'll assess PMF per segment.
3. **What does "Active" mean for this product?** Not just login — what action reflects someone actually getting the product's core value? (e.g. Instagram: consumed or produced content, not just opening the app). Define this per segment if there are multiple.

If you're not sure what "Active" should be, describe the product's core value loop and I'll help you define it — favor an action later in the user journey (more meaningful) over one earlier (more common but less indicative of value).
</AskUserQuestion>

Wait for the PM's response. If multiple segments were named, repeat Steps 2-4 for each segment separately before synthesizing in Step 5.

### Step 2: Stable Retention

<AskUserQuestion>
Let's measure retention using **X-day retention**: the % of a cohort still "Active" N days after their first use.

- What retention window matters most for this product? (Day-1, Day-7, Day-28, or another cadence — pick one that matches the product's natural usage rhythm.)
- What's the current retention rate at that window, if you have it? (e.g. "30% of Jan 1 first-time users were still active on Day 7")
- If you don't have exact numbers, describe the retention curve qualitatively (e.g. "steep drop in week 1, then flattens" vs. "steady decline with no flattening").

A retention curve that **flattens** (plateaus at some non-zero rate) is a strong PMF signal — it means a core group has found lasting value. A curve that keeps declining toward zero is a warning sign regardless of the current rate.
</AskUserQuestion>

If the PM wants an industry comparison point and doesn't have one, use web search to find relevant retention benchmarks for their product category (reference point: Lenny's Newsletter maintains a well-known benchmark list) — do not fabricate specific numbers.

### Step 3: Sustainable Growth via Growth Accounting

Explain the five daily growth-accounting states before asking for data:

- **New** — used the product for the first time today
- **Retained** — active yesterday and today
- **Churned** — active yesterday, not today
- **Resurrected** — inactive yesterday, active today
- **Stale** — inactive yesterday and today

<AskUserQuestion>
For a representative recent period (a week or month), what do you know about:

1. **New users** — first-time users in the period
2. **Retained users** — active in consecutive periods
3. **Churned users** — dropped off
4. **Resurrected users** — came back after a lapse

Exact counts are ideal, but rough estimates or directional trends ("churn has been rising the last 2 months") are fine if that's all you have.
</AskUserQuestion>

Compute, showing your work:

```
Net User Growth = New + Resurrected − Churned
Active Users    = New + Resurrected + Retained
```

Flag explicitly:
- If growth is driven mostly by **New** with high **Churned**, call out that this is acquisition-led, not retention-led growth — the Meta principle applies: don't scale top-of-funnel until retention is proven.
- If **Resurrected** is a meaningful share, note this positively — it means lapsed users are finding their way back, a sign of durable value.

### Step 4: Deep Engagement

<AskUserQuestion>
What do you know about engagement depth? Any of these you can share:

1. **ARPU** — average revenue per user (daily/weekly/monthly, whichever is natural for this product)
2. **L28** — days active out of the last 28
3. **Time in-app** — average session length or total time per period

If revenue isn't applicable (e.g. free/internal tool), skip ARPU and lean on L28 and time in-app.
</AskUserQuestion>

### Step 5: Synthesize the Verdict

Produce a verdict per segment (or one overall verdict if single-segment), following this structure:

```
## PMF Assessment: [Product/Feature Name] — [Segment, if applicable]

**Date:** [date]
**"Active" definition:** [as defined in Step 1]

---

### 1. Stable Retention
- Window: [Day-N]
- Rate: [X%] — [flattening / still declining / insufficient data]
- Assessment: [Strong / Moderate / Weak signal]

### 2. Sustainable Growth (Growth Accounting)
| Metric | Value |
|---|---|
| New | [x] |
| Retained | [x] |
| Churned | [x] |
| Resurrected | [x] |
| Net User Growth | [computed] |
| Active Users | [computed] |

- Assessment: [growth quality — retention-led vs. acquisition-led, any red flags]

### 3. Deep Engagement
- ARPU: [x]
- L28: [x]
- Time in-app: [x]
- Assessment: [Strong / Moderate / Weak signal]

---

### Overall PMF Read
[Synthesized narrative — NOT a single score. Explicitly state whether all three criteria point the same direction or conflict, e.g. "strong retention and engagement, but growth is acquisition-led and at risk if churn continues rising." Avoid declaring a binary "has PMF" / "doesn't have PMF."]

### Recommended Next Steps
- [What to fix or investigate first, ranked by leverage]
- [What data gaps to close before the next assessment]
- [Suggested re-assessment cadence]
```

### Step 6: Save the Output

Save as `PMF-Assessment-[product-name]-[date].md` in the current working directory or a location the PM specifies.

## Notes

- **Don't let one strong metric paper over a weak one.** A product with great engagement but declining retention does not have PMF — it has a devoted-but-shrinking niche.
- **Multi-segment products need multi-segment verdicts.** A marketplace can have PMF on the supply side and not the demand side (or vice versa) — never average these together into one number.
- **Pair well with other pm-superpowers skills**: run `pre-mortem` before a launch that depends on assumed PMF, or `strategic-moat` once PMF is established to assess how defensible the resulting position is.
- **Recommend periodic re-runs.** PMF is a guardrail metric to monitor continuously, not a one-time gate.
- **Further reading**: [How Meta uses analytics to assess Product Market Fit](https://aniganti.medium.com/how-meta-uses-analytics-to-assess-product-market-fit-c9262add2790) by Ani Ganti — the source article this skill is based on.
