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
| Apple App Store / Google Play | Distribution gatekeepers; approve the app before any user can download it; enforce health data, privacy, and age policies; take 30% cut on any in-app purchases | App passes review, stays live, complies with platform health and privacy guidelines |
| Nutrition database provider (USDA / Nutritionix / Edamam) | Data licensor; terms of service govern how nutritional data can be displayed, attributed, and used commercially | Surge uses the data within the terms; proper attribution displayed |
| Parents of teen athletes | Their child is using an app that collects health and personal data; parental trust affects adoption among the high school segment | App is transparent about what it collects; no data shared without consent; age-appropriate experience |
| Coaches and trainers | Influencers, not users; if they recommend Surge it accelerates adoption; if they dismiss it, it loses an entire team | App gives athletes useful, accurate guidance — not advice that contradicts what the coach is already telling them |
| The developer (student/maintainer) | Owns the codebase, data infrastructure, and product decisions; time and resources are real constraints | App ships, users stay, data doesn't create liability |

### Users (recap from Stage 1, with Stage 2 updates)

The user picture from Stage 1 with any updates Stage 2 work surfaced.

- **Primary user type:** Athletes and gym-goers who are training hard toward a specific goal but don't yet know how to eat in a way that actually supports it (Jayden profile — knowledge-seeker, not monitoring-reducer)
- **Secondary user types:** Coaches and trainers who might refer athletes to the app; not users themselves but influential in adoption
- **What's been added or revised since Stage 1:**
  - Sub-segment decision made: primary user is the knowledge-seeking athlete (Jayden), not the already-knowledgeable monitoring-reducer (Jessica)
  - Compliance flag added: teen users under 13 require special handling (COPPA)
  - Aggregate data use identified: users' data contributes to recommendations for others — needs disclosed consent at signup

### Compliance and accessibility considerations

What has been surfaced about FERPA, COPPA, HIPAA, PII, accessibility, or any other regulatory / safety constraint relevant to the project. Capture in plain language; the student is not producing a compliance document.

- **PII and health-adjacent data** — Surge collects age, body weight, activity level, fitness goals, and food logs. This is personal and health-adjacent data. Both App Store and Google Play require a published privacy policy disclosing what is collected and how it is used. Users must explicitly consent before data collection begins.
- **Aggregate data / recommendation system** — Surge uses patterns from existing users to generate recommendations for new users. This data practice must be disclosed to users at signup — they need to know their data contributes to recommendations for others, and they need to consent to that.
- **COPPA (under-13 users)** — Surge's target includes high school athletes, some of whom may be under 13. COPPA prohibits collecting personal information from children under 13 without verifiable parental consent. Surge must either implement age verification and a parental consent flow, or explicitly restrict the app to users 13 and older.
- **Nutritional advice liability** — Surge gives food and nutrition guidance. If that guidance is framed as medical or clinical advice, it enters regulated territory. The app should make clear it is a general nutrition tracking and guidance tool, not a medical service or dietitian substitute.
- **Accessibility** — no specific accessibility requirements surfaced yet; open for Stage 3 consideration.

---

## Jobs-to-be-done and scenarios

### Job 1 — Figure out what to eat for my sport

- **JTBD statement:** When I'm training hard toward a specific athletic goal, I want to know whether what I'm eating is actually supporting that goal, so I can stop guessing and feel confident my effort isn't being wasted.
- **How do we know it's a real job:**
  - Michael B (football, Stage 2 form): describes his food choices in vague performance terms — "it's healthy and helps me prepare for football practice" — but can't specify what nutrients he's targeting or whether he's getting enough. Goal is to "get faster even though I have a smaller body," but his nutrition strategy is purely intuitive.
  - Alarie A (volleyball, Stage 2 form): eats two meals a day, "hasn't thought about it in a while," and her coach told her to "just condition more than diet." She assumes she works off whatever she eats. No app, no tracking, no guidance.
  - Jayden (basketball, Stage 1 interview): confirmed knowledge gap firsthand — training hard but uncertain whether his eating is aligned with his performance goals. The need was clear enough that it was the anchor for the primary user profile.
- **What people do today:**
  1. Eat what feels healthy or what parents prepare, without a nutritional frame tied to their sport.
  2. Ask coaches — the most trusted source. Coaches say things like "eat clean," "just condition more," or give a rough calorie number ("eat 5000 calories"). No specifics on timing, micronutrients, or sport-specific guidance.
  3. Watch TikTok / YouTube fitness content, Reddit — general fitness advice, not calibrated to the individual's sport, training load, or body.
  4. Adjust by feel after a bad workout or a period of low energy. No systematic review.
  5. Use sport season as a reset trigger: Michael B describes getting back on track in late summer because "I have sports in the fall I need to be ready for." The correction is seasonal, not continuous.
- **Why has the current way persisted:**
  - Coach advice is trusted and free. It requires no additional effort.
  - The knowledge gap is tolerable day to day — you don't feel a direct link between yesterday's meal and today's sprint time. The pain is diffuse.
  - Athletes credit their workout for feeling good or bad, not their food. Alarie: "I feel that I work it off during practice." The causal chain between nutrition and performance isn't felt concretely.
  - Every app that exists (MFP, Cronometer) is built for weight management, not athletic performance. Athletes see these as diet tools and don't self-select into them.

#### Scenario 1.1 — Pre-season gut check

> **Michael B** is three weeks out from the start of football season. He's been eating casually all summer — some not-great choices, more fast food than usual. He wants to get "back on track" before camp. He knows he should be eating more protein and fewer empty carbs, but that's the extent of his framework. He has no idea what his actual daily protein intake is, whether his pre-practice meal timing is helping or hurting, or how many calories a player his size needs for his specific goal of getting faster.
>
> He thinks about downloading a nutrition app. He searches "nutrition app" in the App Store. He sees MyFitnessPal, opens it, and immediately hits a prompt to set a weight-loss goal. **Something goes wrong:** the app is clearly designed for people who want to lose weight. He's trying to get faster, not lighter. The onboarding doesn't map to his goal at all. He closes it and puts his phone down.
>
> He asks his coach at the first team workout. Coach says: "Eat clean, stay hydrated, get your protein in." Michael B nods, eats chicken and rice that night, and considers it handled. He goes into camp not knowing whether he's fueling correctly.

**Reads back against positioning statement:** No — the current alternative (coach advice) delivers generic guidance without the confidence that comes from knowing your intake actually matches your goal. The key benefit ("confidence that your nutrition is working for your performance") is not delivered by the workaround. This is the job Surge is built to fill.

---

### Job 2 — Log food without it being more work than the workout

- **JTBD statement:** When I already have a rough sense of what I should be eating and I'm training consistently, I want to log my food quickly without hunting for items or doing manual math, so I can stay consistent without the app becoming a second job.
- **How do we know it's a real job:**
  - Ryan C (football, Stage 2 form): downloaded MyFitnessPal, used it briefly, then stopped — "I found the extra work not to be worth it as I was pretty aware of what I was eating already and the nutrients it had." He knows his rough targets (~4000–5000 cal/day, high protein and carbs — told by his coach). The app confirmed what he already knew but cost more time than it saved.
  - Jessica (gym-goer, Stage 1 interview): monitors food group coverage mentally every day — protein, dairy, fiber, vegetables. Has taken nutrition classes. Does not use an app because her informal mental system is accurate enough and frictionless.
- **What people do today:**
  1. Maintain a rough mental model of daily intake — not exact calories, but a sense of whether protein, carbs, and vegetables were covered.
  2. Ask coaches when the mental model breaks down ("I try to contact my coaches — they usually know the most about proper training and eating habits" — Ryan C).
  3. Eyeball serving sizes and skip logging entirely on days when meals were prepared by someone else (parents, restaurants).
  4. Download an app, try it for a day or two, abandon it when it asks too many questions or doesn't have the food.
- **Why has the current way persisted:**
  - Mental estimation is genuinely low-friction. Ryan C knows chicken and rice is good. He doesn't need an app to tell him that.
  - MFP exists but has friction: barcode scanning is behind a paywall, the food database requires search, entries need correction. The overhead is real.
  - Coaches fill the gap for high-stakes questions. They're always available and trusted.
  - The cost of being slightly wrong is invisible. You don't feel 200 missing calories. The workaround "works well enough."

#### Scenario 2.1 — Trying to hit 5000 calories

> **Ryan C** is in football offseason, trying to bulk for next season. His coach told him to eat 5000 calories a day, high protein and carbs. He has no idea if he's hitting that. Most days he eats what his parents cook plus a post-workout meal he puts together himself. He tries MyFitnessPal for two days.
>
> **Something goes wrong:** barcode scanning on the packaged rice his mom buys is locked behind MyFitnessPal Premium. He has to search manually. The search returns six versions of "white rice" with different calorie counts. He picks one, logs it, moves on. By the end of day one he's at 3,200 calories logged but suspects he missed a few things. Day two he skips logging breakfast because he's running late. He uninstalls the app.
>
> He goes back to eyeballing and asks his coach at the next practice. Coach says "you look good, keep it up." He takes that as confirmation and stops thinking about it. He probably isn't hitting 5000 most days, but there's no feedback loop to tell him.

**Reads back against positioning statement:** No — the workaround (mental estimation + occasional coach check-in) doesn't give Ryan the feedback loop he needs. The key benefit isn't delivered. Note: this is the secondary user profile; the primary user (Job 1) is the bigger unlock for Surge, but this job represents a real retention risk — users who already know their macros will abandon any app with high logging friction.

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
