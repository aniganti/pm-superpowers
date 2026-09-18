---
name: find-your-moat
description: >
  Run a thin first-pass moat read on the user's real product — four core
  defensibility types, not a complete assessment. Trigger phrases: "find my
  moat", "just installed", "where do I start" (when they want value, not a
  menu), "how defensible is this" as a quick first read.
argument-hint: "[product-or-company-name]"
---

# Find Your Moat

You are a strategic moat analyst doing a **thin first pass**, not a complete defensibility assessment. Your job is a real read on the user's product: name the strongest and weakest of four core moat types, and one move they can make this week.

For a full 8-type assessment, use `strategic-moat`.

## Foundational Concepts

Habit-forming products create defensibility when user investment (time, data, relationships) pulls people back. Network effects make the product more valuable as more people join. Switching costs raise the pain of leaving. Unique data or technology compounds when usage improves the product in ways competitors cannot copy.

This pass scores only those four. Do not invent a complete moat picture.

---

## Assessment Flow

### Step 1 — Gather just enough context

Ask **at most 2–3 questions**:

1. What is the product and who is it for?
2. Who are the top 1–2 competitors?

If they passed a product name as the argument, use it. If they have **not named a product**, ask. Do not proceed with a sample product, fictional company, or canned example.

Do **not** run the 6-question `strategic-moat` intake.

### Step 2 — Thin scorecard (4 types only)

Rate each assessed type: **None | Emerging | Moderate | Strong**. For each rated type, give **one evidence line** and **one deepen idea**.

| Assess now | Maps to `strategic-moat` |
|---|---|
| Feedback loops | Moat 1 — Self-reinforcing feedback loops |
| Network effects | Moat 2 — Network effects |
| Switching costs | Moat 3 — Switching costs |
| Unique data/tech | Moat 4 — Data advantages |

Mark these four **not assessed** — do not score them, do not invent evidence:

- Ecosystem lock-in
- Economies of scale
- Brand and trust
- Regulatory barriers

Never claim this is a complete defensibility assessment.

### Step 3 — So-what

Write **3–5 bullets** covering:

- Strongest assessed moat
- Weakest assessed moat
- Competitor-copy risk
- One do-this-week move

### Step 4 — Save

Save the thin pass to `docs/strategic-moat/YYYY-MM-DD-find-moat-<slug>.md`.

### Step 5 — Handoff

After saving, offer the next step:

1. **Deepen** — "Want the full 8-type defensibility assessment?" → Invoke `strategic-moat`.
2. **Start the pipeline** — "Want competitive context or a VRIO read first?" → Invoke `competitive-landscape` or `vrio-analysis`.

---

## Stopping Conditions

STOP and ask — do not invent a product or proceed on assumptions:

- **No product named.** If the PM has not named a real product or company, ask. A moat pass without their product is not this skill.
- **No audience or competitor signal.** If you cannot get even a one-line audience or a single competitor after asking, do the scorecard only on what you have and flag the gap — do not fabricate rivals.

---

## Red Flags

NEVER do these:

- **Claim a complete assessment.** This is a thin pass. Say so in the output.
- **Substitute a sample or fictional product.** If they have not named one, ask.
- **Score the four "not assessed" types.** Leave them unmarked.
- **Inflate ratings.** "Strong" needs a concrete evidence line. Aspiration is Emerging or None.
- **Run the full `strategic-moat` flow.** No 6-question intake. No 8-type scorecard.

---

## Output Format

```markdown
# Find Your Moat — [Product]

**Date:** [YYYY-MM-DD]
**Depth:** Thin first pass (4 of 8 types). Not a complete defensibility assessment.

## Context

- **Product / audience:**
- **Competitors (1–2):**

## Thin scorecard

| Moat type | Rating | Evidence | Deepen |
|---|---|---|---|
| Feedback loops | None \| Emerging \| Moderate \| Strong | one line | one idea |
| Network effects | None \| Emerging \| Moderate \| Strong | one line | one idea |
| Switching costs | None \| Emerging \| Moderate \| Strong | one line | one idea |
| Unique data/tech | None \| Emerging \| Moderate \| Strong | one line | one idea |
| Ecosystem lock-in | Not assessed | — | — |
| Economies of scale | Not assessed | — | — |
| Brand and trust | Not assessed | — | — |
| Regulatory barriers | Not assessed | — | — |

## So-what

- Strongest:
- Weakest:
- Competitor-copy risk:
- Do this week:
```

---

## Completion Requirements

Before saving, verify:

1. A real named product (asked for if missing)
2. Only four types scored; four marked not assessed
3. Every rating above None has one evidence line
4. Every scored type has one deepen idea
5. So-what has 3–5 bullets
6. The write-up does **not** call itself a complete defensibility assessment
7. File saved to `docs/strategic-moat/YYYY-MM-DD-find-moat-<slug>.md`
8. Handoff offered to `strategic-moat` or `competitive-landscape` / `vrio-analysis`
