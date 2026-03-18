---
name: pre-mortem
description: >
  Pre-mortem risk analysis for product launches. Identifies Tigers (real risks),
  Paper Tigers (overblown concerns), and Elephants (unspoken worries) to improve
  launch readiness. Trigger phrases: "pre-mortem", "pre mortem", "launch readiness",
  "risk analysis", "what could go wrong"
argument-hint: "[path-to-prd-or-launch-plan]"
---

# Pre-Mortem Risk Analysis

The goal of a pre-mortem is to **improve launch readiness**, not assign blame. You are helping the PM stress-test their product or launch plan by imagining failure before it happens — so the team can prevent it.

## Process

### 1. Gather Context

Read the PRD or launch plan. The PM may provide:

- A file path to a PRD or launch plan document
- A URL to a document
- A verbal description of the product and launch

If no document is provided, ask the PM to describe:
- What is the product or feature?
- Who is the target user?
- What is the launch timeline?
- What does success look like (metrics, adoption targets, revenue goals)?

### 2. Research (If Relevant)

Use web search to research the competitive landscape, market conditions, or any external factors that could affect the launch. This is especially important if the product is entering a crowded market or a regulated industry.

### 3. Think Step by Step

Work through the following thought exercise carefully:

- **Imagine the product launches in 14 days.**
- **Now imagine it fails** — customers do not adopt, revenue targets miss, reputation takes a hit.
- **What went wrong?** What did we miss? What were we overconfident about?

Consider failure across multiple dimensions:
- Product quality and completeness
- User experience and onboarding
- Go-to-market and positioning
- Technical reliability and scalability
- Competitive response
- Internal alignment and resourcing
- Regulatory or compliance gaps
- Customer support readiness
- Data and analytics instrumentation
- Pricing and packaging

### 4. Categorize Risks

Sort every identified risk into one of three categories:

- **Tigers** — Real problems based on evidence, past experience, or clear logic. These should keep you up at night. They require action.
- **Paper Tigers** — Problems others might worry about, but are unlikely or overblown given the evidence. Worth documenting to align stakeholders and reduce anxiety. Not worth significant resource investment.
- **Elephants** — Unspoken concerns the team is not discussing enough. Could be real; uncertain. They deserve investigation before launch.

**Default to "Tiger" if unsure** — it is better to address risks early and downgrade them later than to ignore them.

### 5. Classify Tigers by Urgency

For every Tiger, assign one of the following urgency levels:

- **Launch-Blocking** — Must be solved before launch. Examples: core feature broken, regulatory blocker, key customer dependency unmet, critical security vulnerability, missing legal approval.
- **Fast-Follow** — Must be solved within 30 days post-launch. Examples: performance issues under load, secondary features incomplete, known UX friction that does not prevent core usage.
- **Track** — Monitor post-launch; solve if it becomes a real issue. Examples: nice-to-have features, edge cases affecting a small percentage of users, speculative competitive threats.

### 6. Create Action Plans for Launch-Blocking Tigers

For every Launch-Blocking Tiger, create a concrete action plan with:

| Field | Description |
|-------|-------------|
| **Risk** | Clear description of the risk and its potential impact |
| **Mitigation** | Concrete action to reduce or eliminate the risk |
| **Owner** | Best owner — function or specific person |
| **Decision/Completion Date** | When the mitigation must be decided on or completed |

### 7. Output Structure

Format the final output as follows:

```
## Pre-Mortem Analysis: [Product Name]

**Date:** [date]
**Launch Target:** [target date]
**Author:** [PM name]

---

### Tigers (Real Risks)

#### Launch-Blocking
- [Risk 1]: [description]
- [Risk 2]: [description]

#### Fast-Follow
- [Risk 3]: [description]
- [Risk 4]: [description]

#### Track
- [Risk 5]: [description]

---

### Paper Tigers (Overblown Concerns)
- [Concern 1]: [why it is overblown]
- [Concern 2]: [why it is overblown]

---

### Elephants (Unspoken Worries)
- [Worry 1]: [why it deserves investigation]
- [Worry 2]: [why it deserves investigation]

---

### Action Plans for Launch-Blocking Tigers

| Risk | Mitigation | Owner | Decision/Completion Date |
|------|------------|-------|--------------------------|
| [Risk 1] | [Action] | [Owner] | [Date] |
| [Risk 2] | [Action] | [Owner] | [Date] |
```

### 8. Save the Output

Save the pre-mortem analysis as `PreMortem-[product-name]-[date].md` in the current working directory or a location the PM specifies.

## Notes

- **Be honest and constructive.** The value of a pre-mortem comes from candor. Do not sugarcoat risks to be polite — but frame everything in terms of improving outcomes, not criticizing decisions.
- **Involve cross-functional perspectives.** Encourage the PM to share the pre-mortem with engineering, design, marketing, sales, CS, and legal. Each function sees risks others miss.
- **Recommend revisiting 2-3 weeks before launch** to verify that mitigations for Launch-Blocking Tigers are on track. If any are slipping, escalate immediately.
- A pre-mortem is most valuable when done early enough to act on the findings. Do not wait until the week before launch.
