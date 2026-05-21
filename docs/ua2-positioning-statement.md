---
title: UA2 — Positioning Statement
---

# UA2 — Positioning Statement

The deliverable of Stage 1. Drafted in Pass 1 from current belief, revised across Passes 2–4 as research and interview evidence comes in. Every clause must be defensible by the time Stage 1 exits.

The statement at the top is the public-facing artifact — short, clean, one paragraph. The evidence record below it is the working document where the student's thinking lives. The messiness in the evidence record is the point. Cleaning it up to look polished destroys the record of learning. This is a living document; its git history is part of the deliverable.

---

## Statement

> For athletes and gym-goers who are training hard toward a specific goal but don't yet know how to eat in a way that actually supports it, Surge is a sports nutrition tracking app that helps users understand how their daily food choices affect performance and recovery. Unlike MyFitnessPal and other general calorie-tracking apps, our product focuses on translating sports nutrition into practical guidance tied to a user's training and activity.

---

## Status

Per-clause status. Mirrors the per-clause status in `UA0-PROJECT-STATUS.md`.

- **Target customer:** evidenced by interview
- **Need or opportunity:** evidenced by interview
- **Product name:** refined by research
- **Product category:** refined by research
- **Key benefit:** evidenced by interview
- **Primary competitive alternative:** evidenced by interview
- **Primary differentiation:** evidenced by interview

Status values: `not started` | `drafted from belief` | `drafted-unconfirmed` | `refined by research` | `evidenced by interview` | `stable`.

---

## Evidence

One subsection per clause. Updated continuously across all five passes.

### Target customer

- **Current belief:** Athletes and gym-goers who are training hard toward a specific goal but don't yet know how to eat in a way that actually supports it.
- **Basis for the belief:** Origin conversation — friend had a goal to gain weight for football season; student has personal experience with a doctor recommending eating more. Both are people with a nutrition goal but no specific plan.
- **Evidence found:**
  - 2026-05-07: Origin conversation with student — friend (competitive athlete) had a deadline to gain weight for football season; student was told by doctor to eat more with no specific guidance
  - 2026-05-14: Interview with Jayden (basketball athlete) showed a strong connection between food choices and sports performance. He described actively trying to avoid poor performance caused by eating badly before games.
  - 2026-05-14: Interview with Jessica (gym-goer, student's sister) confirmed the target extends beyond team sport athletes. She structures eating deliberately around training (carbs before, protein after, fiber throughout), thinks about food group coverage daily, and has formal nutrition knowledge. Gym-goers with goals are clearly in the target.
- **Reasoning:** The target customer was broadened from "high school athletes" to a more performance-oriented athlete segment because the underlying behavior is not age-specific. Now further complicated: two distinct sub-segments are emerging — (1) less-informed athletes who don't know what to eat and need guidance (Jayden), and (2) already-knowledgeable athletes who know what to eat but carry ongoing monitoring overhead (Jessica). These may need different product angles.
- **Alternatives considered:** "Any user" — dropped because too broad to build for; "people with health conditions" — dropped because athletes feel like a more natural anchor
- **Weaknesses / unknowns:** The two sub-segments (knowledge-seekers vs. monitoring-reducers) are meaningfully different. It is still unclear which is the primary user the product is built for — or whether the product can serve both without losing focus. Still need interviews with endurance athletes and strength/lifting-focused athletes.
- **What would change my mind:** If further interviews show the knowledgeable sub-segment (Jessica) is much larger and more underserved than the less-informed sub-segment (Jayden), the framing of the product may need to shift toward monitoring convenience rather than nutritional guidance.

### Need or opportunity

- **Current belief:** Athletes receive vague or generic nutrition advice and struggle to translate it into concrete daily eating decisions tied to athletic performance.
- **Basis for the belief:** Student's personal experience — doctor said "eat more" with no specifics; all available guidance is generic rather than personalized.
- **Evidence found:**
  - 2026-05-07: Student said "I feel like I have trouble understanding which food groups I should be eating the most and the nutrition values I'm getting. All I hear is just eat more protein and vegetables."
  - 2026-05-14: Jayden described receiving broad advice such as "eat carbs" and "avoid fast food before games," but lacked specific guidance on what to actually eat. He also described negative physical effects after eating poorly before a game and trying to course-correct afterward.
  - 2026-05-14: Public complaints about existing nutrition apps often mention lack of adaptation to training load, recovery, or athletic context — "My recovery score in Whoop has zero influence on the calorie target MFP suggests for the day." / "Most apps assume one body type, one activity intensity, one metabolic profile."
  - 2026-05-14: Interview with Jessica revealed a different shape of the same need: she monitors food group coverage daily ("all the time"), traces back her eating to identify gaps, and adjusts at home when something is missing. Her problem is not lack of knowledge — it is the recurring cognitive overhead of checking coverage. She would refuse formal calorie tracking ("be miserable"). This is a distinct need mode: ongoing lightweight completeness-checking vs. Jayden's need for translation of advice into action.
- **Alternatives considered:** "Athletes don't know how to track calories" — dropped because the problem is less about tracking and more about understanding what specific nutrients they need; "athletes lack nutritional knowledge" — partially wrong, at least for the Jessica sub-segment who has formal training
- **Weaknesses / unknowns:** The need now has two documented flavors: (1) knowledge gap — not knowing what to eat for your sport (Jayden); (2) monitoring friction — knowing what to eat but carrying mental overhead to verify daily coverage (Jessica). It is unclear whether one product can resolve both or whether they require different design directions.
- **What would change my mind:** If further interviews show the monitoring-friction need is predominant and the knowledge-gap need is rare, the clause framing should shift from "translate advice into action" toward "reduce the cognitive load of coverage-checking."

### Product name

- **Current belief:** NutriScan — "Nutri" from nutrition, "Scan" from the core feature of scanning food with AI
- **Basis for the belief:** Student's own naming rationale — the name reflects what the app literally does
- **Evidence found:**
  - 2026-05-07: Student said "the name is heavily inspired by the main feature of the app which is the ability to scan your food contents with AI and provide a nutrition chart"
- **Alternatives considered:** None yet
- **What would change my mind:** If user research shows the name causes confusion (e.g., people think it scans barcodes only, not actual food)

> Mostly internal; thin evidence here is acceptable.

### Product category

- **Current belief:** Sports nutrition tracking app.
- **Basis for the belief:** Student's own description — "a health app that helps users maintain a good, nutritional diet" — revised by research showing users compare against calorie and macro tracking apps like MyFitnessPal.
- **Evidence found:**
  - 2026-05-07: Student described it as a health app focused on nutrition
  - 2026-05-14: Users currently compare solutions against calorie and macro tracking apps like MyFitnessPal. Existing apps are commonly perceived as weight-loss-oriented rather than performance-oriented. Public reviews frequently frame MyFitnessPal around dieting — "This app has helped me a lot last year losing weight ... This year I'm trying to bulk ... I wish it was set up more for my macros." / "I would recommend for anyone trying to lose weight."
- **Alternatives considered:** "Fitness app" — related but fitness implies exercise; "diet app" — has weight-loss connotations that don't fit the athlete/gain-weight use case; "health and nutrition app" — too broad, indistinguishable from competitors
- **Weaknesses / unknowns:** Need more evidence about whether athletes themselves think in terms of "sports nutrition" or simply "fitness tracking" and "macro tracking."
- **What would change my mind:** If users consistently categorize it differently when searching (e.g., search for "food tracker" or "meal planner" instead of "sports nutrition")

### Key benefit

- **Current belief:** Surge helps athletes understand how food choices affect performance and recovery and turns broad nutrition advice into practical daily guidance.
- **Basis for the belief:** Student's personal articulation of what the app delivers beyond features, refined by Jayden interview.
- **Evidence found:**
  - 2026-05-07: Student said "after using NutriScan, you'll walk away with confidence of your own body"
  - 2026-05-14: Jayden clearly connected eating habits with athletic outcomes and described adjusting eating behavior after poor performance experiences.
  - 2026-05-14: Interview with Jessica complicated the "confidence" framing significantly. She already has nutritional confidence — took classes, dismisses uninformed advice, has a clear self-directed approach. The benefit she'd respond to is not about gaining understanding but about reducing the mental load of monitoring what she already understands. Her described practice — tracing back her eating to find gaps — suggests the emotional value she'd want is closer to "I don't have to keep a mental tally" than "I finally understand my body."
- **Alternatives considered:** "You'll know your exact macro breakdown" — too feature-focused; "you'll reach your weight goal" — too outcome-specific and hard to guarantee; "confidence in your body" — resonates for the less-informed sub-segment but not for already-knowledgeable users; "reduce the mental load of daily nutrition monitoring" — possible alternative framing worth testing
- **Weaknesses / unknowns:** The "confidence" framing may bifurcate: it lands for users who lack knowledge (Jayden), but falls flat for users who already have it (Jessica). The key benefit may need to be rewritten to address both, or the product needs to choose which sub-segment to optimize for. Still need more interviews to determine which is larger and more underserved.
- **What would change my mind:** If most interviewees describe the problem in terms of mental overhead and convenience rather than knowledge or confidence, the benefit clause should shift away from "confidence" toward friction reduction.

### Primary competitive alternative

- **Current belief:** MyFitnessPal, generic calorie-tracking apps, coach advice, internet research, and informal nutrition habits.
- **Basis for the belief:** Student's direct experience trying existing apps and hitting paywalls; Jayden's interview revealing coach advice as the primary current workaround.
- **Evidence found:**
  - 2026-05-07: Student said "I've tried a couple food scanner apps that have a similar purpose but I realized that they are all paid apps and some of them require monthly subscriptions"
  - 2026-05-14: Jayden relied primarily on broad coach guidance rather than a dedicated sports nutrition tool.
  - 2026-05-14: Public discussions criticize existing apps for being too generic, too weight-loss-focused, or disconnected from athletic performance — "MyFitnessPal was great five years ago. Now it is bloated, aggressively paywalled features that used to be free." / "almost everything on the home screen is under a paywall ... they're locking Macros???"
- **Alternatives considered:** "General healthy eating advice" — still real but less specific than the apps; "doing nothing / winging it" — also real and possibly the most common actual behavior
- **Weaknesses / unknowns:** Need more evidence about what athletes actually stick with long-term, why users abandon nutrition apps, and whether athletes prefer coaches/content creators over apps.
- **What would change my mind:** If athletes don't actually try existing apps before giving up, the real alternative might be "doing nothing" rather than paid apps

### Primary differentiation

- **Current belief:** Surge focuses specifically on translating sports nutrition into practical guidance tied to training and athletic activity rather than generic calorie counting.
- **Basis for the belief:** Student's personal motivation refined by interview evidence — athletes understand nutrition matters but struggle to apply broad advice practically.
- **Evidence found:**
  - 2026-05-07: Student directly stated desire to make app accessible without heavy subscription costs
  - 2026-05-14: Interview evidence suggests athletes understand nutrition matters but struggle to apply broad advice practically.
  - 2026-05-14: Public complaints show frustration with apps that fail to adapt recommendations to activity, recovery, or training context.
- **Alternatives considered:** "Better AI features" — dropped for now; "free/no paywall" — still relevant but not sufficient on its own since free alternatives exist
- **Weaknesses / unknowns:** Still need stronger evidence that athletes would consistently prefer a performance-focused approach over simpler calorie tracking.
- **What would change my mind:** If athletes consistently prefer simple calorie tracking over performance-tied guidance, or if free/freemium model proves unsustainable
