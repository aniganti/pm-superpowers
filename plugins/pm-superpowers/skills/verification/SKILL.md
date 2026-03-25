---
name: verification
description: >
  Verify the quality and completeness of any PM strategy artifact before sharing
  with stakeholders. Re-reads the document and validates against a structured
  checklist. Trigger phrases: "verify my strategy", "check my document",
  "quality check", "review before sharing", "is this ready to share"
argument-hint: "[path-to-strategy-artifact]"
---

# Verification Before Completion

NO COMPLETION CLAIMS WITHOUT FRESH VERIFICATION EVIDENCE. This skill exists to prevent thin, placeholder-heavy, or internally contradictory strategy artifacts from being shared with stakeholders.

## When to Use

Invoke this skill after any document-producing skill (strategy, competitive-landscape, vrio-analysis, strategic-moat, product-ecosystem, pre-mortem, prioritization, decision-log, stakeholder-alignment, prompt-builder) and before sharing the artifact with stakeholders.

## Process

### Step 1: Load the Artifact

Read the document the PM wants to verify. The PM may provide:
- A file path to a saved artifact
- The content directly in the conversation

If no artifact is provided, ask the PM to specify which document they want verified.

STOP if no artifact is provided and the PM cannot point to one. There is nothing to verify.

### Step 2: Identify the Artifact Type

Determine which skill produced the artifact based on its structure and content:

| Artifact Type | Key Indicators |
|---|---|
| Strategy document | Executive summary, strategic pillars, vision/mission, KPIs |
| Competitive landscape | Competitor profiles table, positioning map, whitespace |
| VRIO analysis | VRIO matrix table, V/R/I/O assessments |
| Strategic moat | 8 moat types with ratings, ethical check |
| Product ecosystem | Value chain diagram, integration opportunities, closed loops |
| Pre-mortem | Tigers/Paper Tigers/Elephants, action plans |

### Step 3: Run the Verification Checklist

Apply the appropriate checklist based on artifact type.

#### Universal Checks (Apply to ALL artifacts)

1. **Substance over placeholders** — Are all sections populated with real content? Flag any "TBD", "TODO", "[fill in]", or suspiciously generic text.
2. **Evidence traceability** — Does every recommendation or conclusion trace back to specific evidence cited in the document? Flag any unsupported claims.
3. **Internal consistency** — Are there contradictions between sections? (e.g., problem statement says "enterprise users" but target market says "SMB")
4. **Specificity** — Are user segments, competitors, metrics, and recommendations specific? Flag any vague or generic language that could apply to any product.
5. **Actionability** — Could a reader take concrete next steps based on this document? Or does it end with vague aspirations?
6. **Completeness** — Are all expected sections present? Cross-reference against the skill's output structure.

#### Strategy-Specific Checks

7. Problem statement follows WHO/WHAT/WHY format with a named user segment
8. At least 2 strategic pillars with VRIO justification
9. North-star metric is quantifiable with baseline/target
10. KPIs connect directly to strategic pillars
11. FAQ has at least 5 questions with substantive answers

#### Competitive Landscape-Specific Checks

7. At least 3 competitors profiled with all columns populated
8. Positioning map has 4+ players
9. At least 3 whitespace opportunities with market size estimates
10. "Do nothing" competitor is included
11. Research sources are dated

#### VRIO-Specific Checks

7. At least 5 resources evaluated
8. Every "Yes" has specific supporting evidence
9. No blank cells in the VRIO matrix
10. Recommendations exist for each populated category

#### Strategic Moat-Specific Checks

7. All 8 moat types assessed with explicit ratings (None/Emerging/Moderate/Strong)
8. Every rating above "None" has specific evidence (not generic claims)
9. Every moat has at least one deepening opportunity identified
10. Top 3 recommendations are concrete and actionable
11. Overall defensibility verdict is candid and evidence-based
12. Ethical check section is present with genuine reflection

#### Product Ecosystem-Specific Checks

7. Value chain is mapped with clear layers (supply, platform, distribution, demand)
8. Integration opportunities (backward and forward) are identified with rationale
9. Portfolio coherence is assessed — products reinforce each other, not just coexist
10. Closed-loop opportunities are identified where applicable
11. Short-term and long-term alignment recommendations are distinct and sequenced

#### Pre-Mortem-Specific Checks

7. At least 5 Tigers across urgency levels
8. At least 1 Elephant (teams always have unspoken concerns)
9. Launch-Blocking Tigers have complete action plans (risk, mitigation, owner, date)
10. Risks span at least 4 failure dimensions
11. Analyst-generated risks are present (not just PM-provided ones)

### Step 4: Present the Verification Report

Format the report as:

```
## Verification Report: [Artifact Title]

**Artifact Type:** [type]
**Verified On:** [date]
**Verdict:** PASS / PASS WITH WARNINGS / FAIL

### Issues Found

#### Critical (Must Fix Before Sharing)
- [Issue]: [Description and location in document]

#### Warnings (Recommended Fixes)
- [Issue]: [Description and suggestion]

#### Notes (Minor Observations)
- [Observation]

### Summary
[1-2 sentence overall assessment]
```

### Step 5: Remediation

If the verdict is FAIL or PASS WITH WARNINGS:

1. List the specific fixes needed
2. Offer to help the PM address each issue
3. After fixes are made, re-run the verification

NEVER issue a PASS verdict if critical issues remain. The PM may choose to share anyway, but the verification must be honest.

---

## Red Flags and Anti-Patterns

- **Rubber-stamp verification.** NEVER issue a PASS just because the PM wants to move on. The whole point is honest assessment.
- **Verifying your own work uncritically.** If you produced the artifact in a prior skill, approach verification with fresh eyes. Look for the gaps you may have glossed over during creation.
- **Skipping the checklist.** NEVER give a subjective "looks good to me." Always run the structured checklist. Checklists catch what judgment misses.
