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

Save the pre-mortem analysis to `docs/pre-mortems/YYYY-MM-DD-pre-mortem-[product-name].md`.

## Notes

- **Be honest and constructive.** The value of a pre-mortem comes from candor. Do not sugarcoat risks to be polite — but frame everything in terms of improving outcomes, not criticizing decisions.
- **Involve cross-functional perspectives.** Encourage the PM to share the pre-mortem with engineering, design, marketing, sales, CS, and legal. Each function sees risks others miss.
- **Recommend revisiting 2-3 weeks before launch** to verify that mitigations for Launch-Blocking Tigers are on track. If any are slipping, escalate immediately.
- A pre-mortem is most valuable when done early enough to act on the findings. Do not wait until the week before launch.

---

## Stopping Conditions

STOP and inform the PM if any of these conditions are met — do not proceed with assumptions:

- **No launch scope.** STOP if no PRD, launch plan, or verbal description is provided and the PM cannot describe the product, target user, or launch timeline. A pre-mortem without a defined launch scope is theater.
- **No success criteria.** STOP if the PM cannot define what success looks like. Without success criteria, you cannot meaningfully assess what failure looks like.
- **Launch already happened.** If the product has already launched, this is a post-mortem, not a pre-mortem. Recommend a retrospective instead.

---

## Red Flags and Anti-Patterns

NEVER tolerate these — push back directly:

- **Paper Tiger without evidence.** NEVER let the PM classify a risk as Paper Tiger without specific evidence for why it is overblown. Optimism is not evidence. "I don't think that'll happen" is not a rationale — demand data, precedent, or structural reasons.
- **No Launch-Blocking Tigers.** If the analysis produces zero Launch-Blocking Tigers, be skeptical. Either the launch is exceptionally well-prepared (rare) or the analysis is too optimistic. Challenge the PM: "Are you sure there is nothing that would stop this launch if left unaddressed?"
- **Vague mitigations.** NEVER accept "we'll figure it out" or "we'll monitor it" as a mitigation for a Launch-Blocking Tiger. Mitigations must be concrete: specific action, specific owner, specific date.
- **Missing owners.** Every Launch-Blocking Tiger action plan MUST have a named owner (function or person). "The team" is not an owner.
- **Risk avoidance disguised as analysis.** If every risk is classified as "Track" or "Paper Tiger," the PM is avoiding hard conversations. Push back — some risks are real and urgent.
- **Ignoring the "do nothing" risk.** ALWAYS consider: what happens if we delay the launch? Sometimes the biggest risk is not launching at all (competitive window closing, market timing, team morale).

---

## Completion Requirements

Before saving the pre-mortem, verify ALL of the following:

1. At least 5 Tigers identified across all urgency levels
2. At least 2 Paper Tigers with explicit rationale for why they are overblown
3. At least 1 Elephant identified (teams always have unspoken concerns)
4. Every Launch-Blocking Tiger has a complete action plan (risk, mitigation, owner, date)
5. Risks span at least 4 of the 10 failure dimensions (product quality, UX, GTM, technical, competitive, alignment, regulatory, CS, instrumentation, pricing)
6. The analysis includes risks the PM did NOT initially mention (the analyst's independent assessment)

If any criterion is not met, do not save — inform the PM what is missing and continue the analysis.

---

## Workflow — Next Steps

After completing the pre-mortem, offer these natural next steps:

1. **Prepare for stakeholder alignment** — "Would you like help preparing a stakeholder briefing to share these findings and get buy-in on mitigations?" → Invoke the `stakeholder-alignment` skill.
2. **Log key decisions** — "Would you like to capture the risk mitigation decisions in a decision log for future reference?" → Invoke the `decision-log` skill.
3. **Verify the output** — "Would you like me to run a quality verification on the pre-mortem before you share it?" → Invoke the `verification` skill.

**Full Strategy Pipeline**: competitive-landscape → vrio-analysis → strategic-moat → strategy → **pre-mortem**
