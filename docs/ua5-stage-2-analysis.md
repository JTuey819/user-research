---
title: UA5 — Stage 2 Analysis
---

# UA5 — Stage 2 Analysis

The Stage 2 deliverable. Pulls together what exists in the space, who has a stake in the system beyond the users, who actually uses it, and what users are doing today when they need what the system would provide.

The sections are written in the order a reader would want to encounter them, but the student does not work on them in that order. Activities inform each other.

The positioning statement is revisited throughout. If any analysis contradicts a clause, the student revises `ua2-positioning-statement.md` — Stage 2 is the second pressure test on the statement.

---

## Landscape

A short survey of the space the system enters. Two or three pages of notes is usually enough.

### Adjacent products

- **MyFitnessPal** — largest nutrition tracking app by user base; strong food database, barcode scanning, calorie/macro logging, social features, integration with fitness trackers. Does well: enormous food database, habit familiarity, broad platform support. Users complain: aggressive paywall transition (barcode scanning, macro tracking moved behind Premium at $29.99/mo), weight-loss-centric design, generic recommendations not adapted to athletic context or training load. Where it overlaps with Surge: food logging, nutritional breakdown, daily tracking. Where it leaves gaps: no adaptation for athletic performance, recovery, or sport-specific guidance; treats all users as weight-loss seekers.
- **Cronometer** — free tier with ads, Gold ~$49.99/yr; stronger on micronutrient tracking than MyFitnessPal; less social. Overlaps: detailed nutritional data. Gaps: still generic, not performance-oriented.
- **Lose It!** — ~$3.33/mo annual; calorie-first framing; weight loss positioning explicit in name and design. Overlaps: food logging. Gaps: performance framing entirely absent.
- **FatSecret** — free barcode scanner; basic feature set; no subscription. Overlaps: food lookup. Gaps: minimal guidance, no athletic context.
- **Cal AI** — AI-powered food scanning; camera-based food recognition behind paywall after free uses. Overlaps: the camera AI scan feature Surge intends to offer. Gaps: no sports nutrition context, paywall friction.
- **Coach advice / trainers** — primary current alternative for athletes; broad, non-personalized ("eat carbs," "avoid fast food before games"). Does well: trusted source, no friction to access. Gaps: not specific, not trackable, not available on demand.
- **YouTube / TikTok fitness creators, Reddit** — free, on-demand, community-driven. Does well: engaging, relatable, free. Gaps: inconsistent quality, not personalized, passive consumption rather than active tracking.

### Open-source candidates

- **USDA FoodData Central** — free, government-maintained nutrition database with verified nutritional data for hundreds of thousands of foods. Could serve as Surge's primary nutritional data source. No license cost. Decision: use this (or a comparable API like Nutritionix or Edamam) for nutritional data rather than building a database from scratch.
- **Open Food Facts** — open-source, community-maintained food database with barcode data and packaged food nutritional info. Complements USDA data for branded/packaged foods.
- **Decision recorded (2026-05-21):** Surge will not build its own nutrition database from scratch. It will plug into an existing verified database for nutritional data. The AI camera recognition layer (identifying what food is in a photo) will be built on top of that data layer — these are two separate problems. This keeps the core data accurate and lets development focus on the athletic performance layer.

### Category

- **The category customers think they're shopping in:** calorie and macro tracking apps ("food tracker," "nutrition tracker," "calorie counter") — not "sports nutrition app." Users search for familiar terms.
- **What that category brings with it:** expectation of a large food database, barcode scanning, daily calorie targets, macro breakdowns (protein/carbs/fat), free tier with premium upsell, habit-loop design (log every meal).
- **Whether this is a fit or a misfit:** partial misfit. Surge inherits the category's feature expectations (food database, logging, scanning) but wants to reframe the purpose — from weight management to athletic performance. The risk: users will compare Surge against MyFitnessPal on database size and feature breadth before they understand the performance angle. The opportunity: the weight-loss framing of existing apps is a genuine complaint, not just a Surge talking point.

### Inherited conventions

Conventions the project is taking on whether it knows it or not. For each, decide explicitly: keep, break on purpose, or note as open.

- Daily food logging — **keep** (the core behavior the category is built on)
- Barcode / camera scanning to identify food — **keep** (the feature that hit the paywall in Jayden/student's experience; Surge's intended differentiator on access)
- Large verified food database — **keep via existing API** (USDA FoodData Central or equivalent; not built from scratch — see Open-source candidates above)
- AI camera food recognition — **keep, build on top of data layer** (separate problem from nutritional data; Surge builds the vision layer, existing database provides the numbers)
- Calorie targets as the primary metric — **break on purpose** (Surge's positioning is performance, not calorie deficit; macro and nutrient guidance should lead, not calories)
- Weight loss as the implied goal — **break on purpose** (Surge explicitly serves athletes trying to fuel performance and gain, not cut)
- Macro breakdown (protein / carbs / fat) — **keep** (athletes expect this; removing it would confuse users)
- Weekly progress summaries — **open** (useful if framed around performance, not weight)
- Social / community features — **open** (not core to the positioning; worth validating whether athletes want this or not)

---

## Stakeholders and users

### Stakeholders

Everyone with a stake in whether the system succeeds beyond the users. Most stakeholders are not users. Most requirements come from stakeholders, not users.

| Stakeholder | Stake | Their version of "success" |
|---|---|---|
| [name or role] | [what they care about] | [what would make this stakeholder happy] |
| [name or role] | … | … |

### Users (recap from Stage 1, with Stage 2 updates)

The user picture from Stage 1 with any updates Stage 2 work surfaced.

- **Primary user type:** [who]
- **Secondary user types (if any):** [who]
- **What's been added or revised since Stage 1:** [bullet list]

### Compliance and accessibility considerations

What has been surfaced about FERPA, COPPA, HIPAA, PII, accessibility, or any other regulatory / safety constraint relevant to the project. Capture in plain language; the student is not producing a compliance document.

- [constraint] — [how it applies; how the project will handle it]

---

## Jobs-to-be-done and scenarios

One subsection per job. Each has the four-question structure plus at least one scenario.

### Job 1 — [short title]

- **JTBD statement:** When I'm [situation], I want to [motivation], so I can [outcome].
- **How do we know it's a real job:** [specific evidence from Stage 1. A quote, an observation, a workaround witnessed firsthand.]
- **What people do today:** [step by step description of the current alternative. Not "they use a spreadsheet" — what columns, which sheet, what they do when the data doesn't fit.]
- **Why has the current way persisted:** [what it does well, what users would lose by switching. Chesterton's fence territory.]

#### Scenario 1.1 — [short title]

A narrative. The user starts with "I have this need" and ends with "my need is met." Includes at least one branch where something doesn't work the first time.

> [User] is doing [activity]. They need to [need]. They open [system / current alternative] and [first step]. Then [second step]. **Something goes wrong:** [thing]. They [recovery action]. Eventually [need is met or not].

**Reads back against positioning statement:** Does this story actually deliver the **key benefit** named in `ua2-positioning-statement.md`? [yes / no, with note]

---

## Current alternatives (staging area for Section 3 — JTBD)

What athletes currently use instead of a dedicated sports nutrition tool. To be woven into the "what people do today" field of each job in Section 3.

- **Apps:** MyFitnessPal, macro trackers, calorie calculators
- **Human guidance:** coaches, teammates, trainers
- **Online content:** TikTok and YouTube fitness creators, Reddit, Google searches
- **Informal systems:** guessing, screenshots of meal plans, eating habits developed over time, rough macro estimation

---

## Open from this stage

Things flagged during Stage 2 that don't yet have a home — for the student to revisit later or carry into Stage 3.

- Open-source food database / nutrition API options not yet researched — check before Stage 3
- What is the real core frustration? Still unclear whether users struggle most with lack of knowledge, app complexity, tracking fatigue, conflicting advice, or consistency
- Do different athlete types (endurance, strength, team sport, recreational gym-goer) experience the same nutrition frustrations? Not yet known
- Would athletes consistently use a performance-focused nutrition app long-term? Current evidence shows frustration exists but does not prove engagement or willingness to switch
- Is "performance nutrition" the right framing, or do athletes naturally think in different terms (fuel, macros, eating clean, recovery, body composition)? Language testing still needed
- Subscription tolerance unknown — users complain about paywalls, but whether they would pay for genuine value is not yet tested
