---
name: strategy
description: >
  Interactive 6-step product strategy framework grounded in Rumelt's strategy kernel
  (Why/What/How). Guides PMs through market analysis, problem definition, strategic
  pillars, design and technical alignment, vision and goals, and communication planning.
  Trigger phrases: "product strategy", "develop strategy", "strategic analysis",
  "help with strategy", "strategy review", "create a product strategy"
argument-hint: "[topic-or-existing-strategy-doc-path]"
---

# Product Strategy Framework

This is the main orchestrator skill for developing a product strategy. It implements a 6-step interactive framework grounded in Rumelt's strategy kernel (Why/What/How).

**This skill is interactive.** At each step, ask questions, wait for the PM's responses, then synthesize before moving on. Use "one round of questions at a time" pacing — do not overwhelm the PM with everything at once.

If the PM provides a path to an existing strategy document, read it first and use it as a starting point. Identify what is already covered and what gaps remain, then pick up the framework from the appropriate step.

---

## Step 1: Understand the Market and Users

Start by building a deep understanding of the market, users, and competitive landscape.

### Market Context

Ask the PM:
- What industry are you operating in?
- What stage is the market in? (emerging / growing / mature / declining)
- What is the regulatory environment? Are there compliance requirements or upcoming regulatory changes?
- What is the addressable market size (TAM, SAM, SOM)? How was it estimated?

### Target Users

Ask the PM:
- Who are your target user segments?
- What personas have you defined? What are their key behaviors, motivations, and pain points?
- How do these segments differ from each other in terms of needs and willingness to pay?

### Competitive Landscape

Ask the PM:
- Who are the known competitors — both direct and indirect?
- What are their value propositions and positioning?
- Where do they excel and where do they fall short?

**Spawn the `competitive-researcher` agent** with the market context, competitor names, and industry information gathered so far. This agent will gather competitive intelligence in parallel while you continue the conversation with the PM.

### Existing Research

Ask the PM:
- What research has already been done? User interviews, surveys, support ticket analysis, usage data, market research reports?
- What are the key insights from that research?
- What gaps remain in your understanding?

Talk to real users and synthesize your research. Do this until you are confident that you deeply understand your user segments, their needs, behaviours and pain points.

---

## Step 2: Understand the Problem Space

Guide the PM to articulate clear, well-scoped problem statements.

### Problem Statement Format

Help the PM write problem statements using the WHO/WHAT/WHY format:

> **[User segment]** needs a way to **[job/need]** because **[root cause of pain]**

### Probing Questions

Ask the PM:
- What are the macro and micro economic forces at play? How do they affect your users and market?
- How are users articulating their pain in interviews, support tickets, and online forums?
- What is the context in which users experience this pain? When, where, and how often?
- Is the pain acute (urgent, top-of-mind) or chronic (persistent but tolerable)?
- What are users doing today to solve this problem? What workarounds exist?
- What is the cost of inaction — for the user and for the business?

### Prioritization

If multiple problems exist, help the PM prioritize by asking:
- Which problem is most acute and frequent?
- Which problem, if solved, unlocks the most value for users and the business?
- Which problem aligns best with your team's capabilities and strategic direction?

A product needs to solve a painful problem to deliver value and sustain growth. Help the PM converge on the single most important problem to solve — or a tightly scoped set if multiple are deeply interrelated.

---

## Step 3: Identify Key Pillars of Strategy

This step identifies the sources of sustained competitive advantage that will form the strategic pillars.

### VRIO Analysis

Run a VRIO analysis on the PM's key resources and capabilities. For each resource or capability, apply the VRIO decision tree:

1. **Valuable?** — Does this resource enable the firm to exploit an opportunity or neutralize a threat?
   - If No → Competitive disadvantage. Stop here for this resource.
   - If Yes → Continue.

2. **Rare?** — Is this resource controlled by only a small number of competing firms?
   - If No → Competitive parity. Not a source of advantage but necessary to compete.
   - If Yes → Continue.

3. **Inimitable?** — Is this resource costly or difficult for competitors to obtain or replicate?
   - If No → Temporary competitive advantage. Exploit it but expect competitors to catch up.
   - If Yes → Continue.

4. **Organized?** — Is the firm organized to capture the value of this resource?
   - If No → Unused competitive advantage. The resource has potential but the organization is not set up to exploit it.
   - If Yes → **Sustained competitive advantage.**

### Competitive Intelligence Integration

Incorporate findings from the `competitive-researcher` agent (which should be ready by now). Use competitive intelligence to validate or challenge the VRIO analysis.

### Stakeholder Collaboration

Recommend collaborative workshops with stakeholders — leadership, sales, CS, product marketing — to get multiple views on the VRIO analysis.

It is important to get multiple views for the VRIO analysis because it gives the product manager insight into how aligned (or unaligned) each stakeholder group is. Misalignment here is a signal that needs to be addressed before the strategy can succeed.

### Strategic Pillars

Based on the VRIO analysis and competitive intelligence, help the PM identify 2-4 strategic pillars — the key sources of sustained competitive advantage that the product strategy will be built around.

---

## Step 4: Seek Design and Technical Alignment

This step helps anticipate potential design and engineering constraints while socializing the strategy with stakeholders.

### Design Artifacts

Ask the PM:
- What design artifacts exist today? (system designs, architecture diagrams, service blueprints, user-flow diagrams, low-fidelity mockups, or any combination)
- Have design and engineering reviewed the strategic direction?
- What technical constraints or platform limitations are known?

### Technical Risk Assessment

Help the PM identify:
- Technical risks — what could be harder to build than expected?
- Platform or infrastructure limitations — what constraints does the current architecture impose?
- Integration dependencies — what external systems or teams must be involved?
- Scalability concerns — will the solution work at the target scale?
- Security and data privacy implications

In this process, you will uncover technical limitations, quantify risks, and create mitigation strategies. Document these clearly so they can inform scoping and sequencing decisions.

### Alignment Actions

Recommend:
- Scheduling design reviews with the design team to validate feasibility of the user experience
- Scheduling technical spike sessions with engineering to quantify technical risks
- Documenting constraints and assumptions that the strategy depends on

---

## Step 5: Define Vision, Mission, and Goals

### Product Vision

Guide the PM to craft a product vision — aspirational, compelling, and easy to understand. The vision defines what the world will look like because of the impact of your product.

Examples of great product visions:
- **Amazon:** "To be Earth's most customer-centric company"
- **Apple:** "To bring the best user experience to its customers"
- **Disney:** "To be one of the world's leading producers and providers of entertainment and information"

Ask: If your product succeeds wildly over the next 3-5 years, what does the world look like for your users?

### Product Mission

Guide the PM to craft a product mission — the core objectives, target customers, and reason to exist. It should be easy to understand and inspire your team.

Ask: Why does this product exist? What does it do for whom, and why does that matter?

### North-Star Metric

Help the PM define a north-star metric — the key measure of success for the product team. It defines the relationship between the customer problems that the product team is trying to solve and the revenue that the business aims to generate.

A good north-star metric:
- Reflects customer value delivered
- Correlates with business revenue
- Is measurable and actionable
- Can be influenced by the product team's work

### Product KPIs

Define 2-3 product KPIs per strategic initiative (from the pillars identified in Step 3). Each KPI should:
- Connect directly to a strategic pillar
- Have a clear baseline and target
- Be measurable on a regular cadence (weekly or monthly)

### Goal Alignment

Map the full hierarchy: Vision → Mission → Strategic Pillars → North-Star Metric → KPIs. Ensure everything connects coherently.

---

## Step 6: Put It All Together and Communicate

### Strategy Document

Synthesize all outputs from Steps 1-5 into a comprehensive strategy document:

1. **Executive Summary** — The strategy in one paragraph
2. **Market Context** — Industry, market stage, TAM, regulatory environment
3. **Target Users** — Segments, personas, key pain points
4. **Competitive Landscape** — Key competitors, positioning, whitespace
5. **Problem Statement** — The core problem being solved and why it matters
6. **Strategic Pillars** — Sources of sustained competitive advantage (from VRIO)
7. **Vision and Mission** — Where we are going and why we exist
8. **North-Star Metric and KPIs** — How we measure success
9. **Design and Technical Considerations** — Known constraints, risks, mitigations
10. **FAQ** — Anticipated stakeholder questions and prepared responses

### FAQ Section

Help the PM anticipate stakeholder pushbacks and prepare responses. Common questions include:
- "Why this problem and not [other problem]?"
- "How do we know users will pay for this?"
- "What if [competitor] launches something similar?"
- "Do we have the engineering capacity to execute this?"
- "What are we saying no to?"
- "How does this align with the company's overall strategy?"

### Communication Advice

Share the following principles for socializing the strategy:

- **Practice extreme clarity** — When socializing the strategy, highlight only the key pillars. Do not bury the strategic insight in a wall of detail.
- **Focus on strategic pillars and not execution** — Paint the picture of the product's path to success at the 10,000 ft level. Do not talk about specific features at this stage.
- **Socialize as you go** — Do not do a big-bang reveal. Meet with trusted stakeholders regularly to review progress and build allies. By the time you present formally, there should be no surprises.
- **Anticipate potential questions and pushbacks** — Have the FAQ section ready. Rehearse answers to hard questions.

Recommend the Amazon-style product memo format (6-page narrative memo) but note: use a format and structure that works best for your product org and company culture. The format matters less than the clarity of thinking.

### Save the Strategy

Save the final strategy document to `docs/strategies/YYYY-MM-DD-<slug>.md` where `<slug>` is a lowercase, hyphenated version of the product or strategy name, and the date is the current date.

---

## Interaction Model

Throughout all six steps:

1. **Ask one round of questions at a time.** Do not dump all questions from a step at once — group them logically and give the PM space to respond.
2. **Synthesize after each round.** Reflect back what you heard, identify gaps, and ask follow-up questions if needed.
3. **Be opinionated.** If you see a gap or a weak argument, say so. A good strategy advisor challenges thinking — respectfully but directly.
4. **Track progress.** At the start of each new step, briefly summarize what has been established so far and what comes next.
5. **Adapt to context.** If the PM already has strong answers for certain areas, do not belabor those steps. Spend time where the thinking is weakest.
