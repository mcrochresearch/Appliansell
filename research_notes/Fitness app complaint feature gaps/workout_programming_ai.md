# Workout Programming / AI-Coaching Apps: Complaints and Feature Gaps

> **Method and source caveats (read first).** Direct page fetches were blocked in this environment. WebFetch could not resolve apps.apple.com, garagegymreviews.com or dr-muscle.com, and the egress proxy returned 403 for reddit.com. Every finding below therefore comes from search-engine result extracts (extended web search) of the cited pages, not from my own reading of the full page. **No first-hand Reddit threads could be retrieved.** Reddit sentiment shows up only where a third party summarized it (mostly Dr. Muscle's "Fitbod Review Reddit" roundup). Many sources are **competitor blogs**: Dr. Muscle, Mesostrength, StrengthLab360, Volm, Sensai and Ondara all sell rival apps, so their claims are marked [competitor]. Single-user anecdotes are marked [single anecdote]. Dates: most sources are 2024–2026. The Dr. Muscle Reddit roundup was about 529 days old at search time (roughly mid-2025), and some Trustpilot excerpts are older and undated.

## 1. Progression logic: what the algorithms get wrong with weights and reps

### Takeaway
The most-cited progression complaints are erratic or illogical load and rep targets (Fitbod, Gravl), loads that don't transfer between related exercises (Gravl), weights that can't be loaded on the user's equipment (Fitbod), and, for trackers like Hevy and Strong, no automatic progression on self-built routines at all. RP is criticized for adding volume (sets) rather than load, and Alpha Progression draws little progression criticism in what I could find.

### Cited Findings
**Fitbod**
- **Erratic targets between sessions:** One reviewer "maxed out an exercise at 13 reps at 50 pounds, and a couple of days later Fitbod wanted 15 reps at 40 pounds." Another reviewer described targets that "jumped around between sessions." [aggregated reviews, single anecdotes] — [Autonomous Fitbod review 2026](https://www.autonomous.ai/ourblog/fitbod-app-review); [JustUseApp Fitbod reviews](https://justuseapp.com/en/app/1041517543/fitbod-workout-fitness-plans/reviews); [AppSupports negative reviews](https://appsupports.co/1041517543/fitbod-workout-fitness-plans/negative-reviews)
- **Odd early suggestions,** e.g. "35 lb lateral raises." A reviewer on another site said suggested weights are "a little off, but it's easy enough to adjust." — [Autonomous](https://www.autonomous.ai/ourblog/fitbod-app-review); [TechRadar](https://www.techradar.com/health-fitness/fitbod-app-review)
- **No established overload model:** Dr. Muscle's 2025 review says Fitbod's weight recommendations "are often inaccurate and do not follow any established principles of progressive overload." Its 2024 review cites a user complaint about "dangerously heavy weights." [competitor; single anecdote for the "dangerous" claim] — [Dr. Muscle Fitbod review 2025](https://dr-muscle.com/fitbod-workout-app-review/); [Dr. Muscle Fitbod review 2024](https://dr-muscle.com/fitbod-app-review-alternative/)
- **Not exercise science:** A Trustpilot reviewer wrote that the workouts "don't seem to create workouts that follow proper exercise science with reps and weight or good form." [older and undated, single anecdote] — [Trustpilot Fitbod p.2](https://www.trustpilot.com/review/www.fitbod.me?page=2)
- **Custom workouts not progressed:** A Reddit user (per the Dr. Muscle roundup) was "excited" until finding a "critical flaw": the inability to progressively overload custom workouts. They found it "cumbersome to manually log increases in volume or intensity and then edit saved workouts." [secondhand Reddit, about mid-2025] — [Dr. Muscle Fitbod Reddit roundup](https://dr-muscle.com/fitbod-review-reddit/)
- **Fitbod's own position:** Its help center says the algorithm "starts conservatively," especially for new users and unlogged exercises, and that recommendations drop after time off. If a weight is too heavy, users should reduce it and keep the rep count. This conflicts with the "too heavy" anecdotes above. — [Fitbod Algorithm Q&A](https://help.fitbod.me/hc/en-us/articles/16254175592215-Fitbod-s-Algorithm-Q-A)

**Plate and dumbbell rounding (Fitbod, Hevy)**
- **Fitbod and empty barbells:** One reviewer said Fitbod had no option to say a barbell has no fixed plates, so prescriptions of 30–40 lb on a 45 lb bar were impossible to follow. They wanted to tell Fitbod they "don't have fixed barbells." [aggregator, single anecdote] — [Autonomous](https://www.autonomous.ai/ourblog/fitbod-app-review)
- **Fitbod increment settings:** Fitbod does let users set the increments they own for dumbbells, kettlebells and barbells, via Edit per equipment type. The complaint may therefore be partly a discoverability issue. — [Fitbod help: My Plan](https://help.fitbod.me/hc/en-us/articles/34336407191191-My-Plan)
- **Hevy rounding:** Hevy has plate and dumbbell rounding settings, and Hevy Trainer treats dumbbell weight as per-dumbbell. Its plate calculator is barbell-only, and users have asked for a dumbbell version. — [Hevy workout settings](https://www.hevyapp.com/features/workout-settings/); [Hevy Trainer settings help](https://help.hevyapp.com/hc/en-us/articles/43572343844247-How-Hevy-Trainer-Settings-Work); [Hevy plate calculator help](https://help.hevyapp.com/hc/en-us/articles/34518876511383)

**Gravl**
- **Loads don't transfer between related lifts:** "there are two separate exercises for barbell hip thrusts and dumbbell hip thrusts. somehow if you can do 200 lbs in barbell it thinks you can only do 50 with a dumbbell." [single anecdote, review aggregator, 2025–26] — [Grand-Screen Gravl reviews](https://grand-screen.com/apps/gravl-personal-trainer/reviews/)
- **Inconsistent weight recommendations:** An aggregator summary flags the "consistency" of the AI's weight recommendations. Reviewers also note that recommendations depend on accurate logging of weight, reps and effort. — [mwm.ai Gravl](https://mwm.ai/apps/personal-trainer-gravl/6450921637); [Grand-Screen](https://grand-screen.com/apps/gravl-personal-trainer/reviews/)

**Hevy and Strong (trackers)**
- **No auto-progression on user-built routines:** Hevy's automatic progression runs only inside Hevy Trainer's generated programs, and Strong has none. [competitor, Volm 2026] — [Volm: Hevy vs Strong](https://www.volm.app/blog/hevy-vs-strong)
- **Demand signal:** A third-party open-source project, "hevy-autopilot," applies auto-progression rules to Hevy routines and logs weekly changes (issues dated 2026-09-21 and 2026-09-28). This suggests users are building workarounds. — [GitHub hevy-autopilot #12](https://github.com/aterreno/hevy-autopilot/issues/12)

**Alpha Progression**
- **Few progression complaints:** A Google Play reviewer said it was "very good at predicting exactly how many reps I could do at various weights, unless it was the second workout in the same muscle group." That points to a weakness in fatigue carryover within a week. [single anecdote] — [Google Play Alpha Progression](https://play.google.com/store/apps/details?id=com.alphaprogression.alphaprogression&hl=en_US)
- **RIR is optional:** The progression model works without RIR, and one reviewer liked that recommendations react set-by-set to logged RIR. — [Fitnessdrum Alpha Progression review 2026](https://fitnessdrum.com/alpha-progression-app-review/)

**RP Hypertrophy**
- **Progresses mainly by adding sets:** The critique argues that "only increasing sets" risks "excess volume, more time in the gym, and blunted strength gains." [competitor] — [Dr. Muscle RP critique](https://dr-muscle.com/rp-hypertrophy-app-critique/)
- **Volume logic seen as simple:** A Trustpilot reviewer says the "algorithm" is "much less sophisticated than they make it seem," with volume change "a simple calculation based on your feedback." [single anecdote] — [Trustpilot RP (CH)](https://ch.trustpilot.com/review/renaissanceperiodization.com)

**Coach-led apps**
- **Future:** A reviewer's human coach "never encouraged scaling up weights even after the workouts felt too easy." Human coaching apps can also fail at progression. [single anecdote] — [Athletech News Future review](https://athletechnews.com/product-of-the-week-future-app-personal-training-review/)

### Inferences
- The core gap is load modeling across related exercises. A system should estimate e1RM per movement pattern and map it across variants (barbell to dumbbell, machine to free weight) rather than treating each exercise as a cold start.
- Users want the progression rule to be visible and deterministic, e.g. "hit top of rep range at RIR ≥2 → +2.5 kg." Session-to-session jumps that look random erode trust faster than conservative but predictable rules.
- Equipment-aware rounding (plates owned, dumbbell jumps, empty bar weight, machine stack increments) is table stakes and still trips users up.

### Gaps
- I found no first-hand Reddit threads on failed-set handling, i.e. whether apps keep the same weight after a missed rep target or back off. Reddit was inaccessible.
- I found no explicit complaints that apps ignore RPE/RIR inputs, apart from RP's slider confusion (section 4).
- I found no JuggernautAI-specific complaints about load jumps. Its RPE-based autoregulation was not criticized in what I could see.

## 2. Exercise selection: randomness, variety, equipment, substitutions and injuries

### Takeaway
Fitbod's and Gravl's generated sessions are criticized for too much rotation, which undermines progressive overload, for illogical muscle-group choices, and for not surfacing equipment users actually want. Gravl users report that preset splits beat the "AI mode." JuggernautAI is accused of the opposite problem, getting stuck repeating the same exercises.

### Cited Findings
- **Fitbod, illogical choices:** Redditors reported suggestions like "insisting on hitting quads and hamstrings daily." A workaround is to exclude many exercises and stick to "a few variations per muscle group," since constant variation "isn't supported by science." [secondhand Reddit, about mid-2025] — [Dr. Muscle Fitbod Reddit roundup](https://dr-muscle.com/fitbod-review-reddit/)
- **Fitbod, skewed muscle balance:** A reviewer said Fitbod "won't let you forget about leg day, but it seems to neglect chest and triceps exercises unless you manually change the muscle groups." [single anecdote] — [JustUseApp Fitbod](https://justuseapp.com/en/app/1041517543/fitbod-workout-fitness-plans/reviews); [Grand-Screen Fitbod](https://grand-screen.com/apps/fitbod-workout-gym-planner/#reviews)
- **Fitbod, positive on customization:** A reviewer can "exclude exercises I can't do, set the type of regimen and equipment available," which helps with injuries. — [Mix & Match Mama Fitbod review, Oct 2024](https://mixandmatchmama.com/2024/10/fit-bod-app-review/)
- **Gravl, AI mode vs presets:** "the AI mode is terrible, but the PPL, and other typical training splits work very well." [single anecdote, 2025–26] — [Grand-Screen Gravl](https://grand-screen.com/apps/gravl-personal-trainer/reviews/)
- **Gravl, equipment preferences ignored:** "The workout generator is great but even with variety set I don't get machines/equipment I want to use." [App Store review, single anecdote] — [Gravl App Store reviews](https://apps.apple.com/us/app/gravl-ai-personal-trainer/id6450921637?see-all=reviews&platform=iphone)
- **Gravl, too little variety:** A reviewer says the AI "doesnt create enough variations in the workouts to keep back to back days different." This is the opposite of the Fitbod complaint, so users want controllable variety. — [Google Play Gravl](https://play.google.com/store/apps/details?id=com.liteup.getgains&hl=en)
- **JuggernautAI, stuck in a loop:** Users report auto-programming that repeats exercises and gets "caught in a cycle (keeps prescribing same exercises)." [competitor] — [Dr. Muscle JuggernautAI review](https://dr-muscle.com/juggernaut-workout-app-review/)
- **RP Hypertrophy, little help choosing exercises:** "Minimal help, if any, with choosing exercises." [competitor] — [Dr. Muscle RP critique](https://dr-muscle.com/rp-hypertrophy-app-critique/)
- **Alpha Progression, planner mismatch:** A Google Play reviewer said the "workout generators and planners didn't give me the sort of plans I was personally looking for." — [Google Play Alpha Progression](https://play.google.com/store/apps/details?id=com.alphaprogression.alphaprogression&hl=en_US)
- **Ladder, constant substitutions in small gyms:** In "a tiny apartment gym, a lot of Ladder's advantage evaporates because you're constantly subbing exercises." [forum post, single anecdote; the forum sites are low-quality and possibly SEO-generated] — [ClarkConnect forum](https://clarkconnect.com/forum/t/can-you-help-me-with-an-honest-ladder-fitness-app-review/2619)
- **Boostcamp GZCLP, rigid substitutions:** A program reviewer found the substitution list "restrictive." [program review, not app logic] — [Boostcamp GZCLP reviews](https://www.boostcamp.app/cody-lefever/gzcl-program-gzclp/reviews)

### Inferences
- Users want a stable core with controlled rotation: fixed main lifts that progress, plus a rotating accessory slot, and a user-set variety dial that the engine actually respects.
- Equipment profiles need to work as positive preferences ("I want machines") as well as constraints ("I don't have X").
- Substitutions should carry load history over (ties to the section 1 Gravl hip-thrust issue).

### Gaps
- I found no sourced complaints specifically about apps ignoring injuries or limitations, beyond Fitbod's exclude-list praise and Ladder's "risky for novices" note.
- I found no sourced "weird split" complaints with specifics.

## 3. Program structure: mesocycles, periodization, volume, missed days, travel, time limits, cardio

### Takeaway
RP's mesocycle model draws complaints about auto-volume overshooting, deload timing and short mesocycles. Alpha Progression's built-in deloads are praised. Coach and community apps (Ladder, Caliber, Alpha) are criticized for narrow scope: lifting only, no cardio or mobility. I found almost no sourced complaints about handling missed days or travel.

### Cited Findings
- **RP, auto-volume overshoots:** A long-time user says leaving muscles on "auto" "often drives volume higher than you need." Their workaround is to set most muscles to "average" and start at the low end. They also say the app "often deloaded later than they liked," so they pre-plan a deload every 5–6 weeks. [forum post, single anecdote; low-quality forum] — [Ditchnet forum](https://ditchnet.org/t/can-anyone-share-an-honest-rp-hypertrophy-app-review/2143)
- **RP's official answer on "so many sets":** The app "will only give you as many sets as you can recover from and prefer to do." If you report pushing your limits, "even if those are just time limits, it will NOT give you any more sets." This doubles as an admission that time-limited users must use the feedback sliders to cap volume. — [RP Help: Why so many sets](https://help.rpstrength.com/hc/en-us/articles/32600133107863-Why-is-the-app-giving-me-so-many-sets-Long-Workouts)
- **RP, mesocycle length and volume floor:** The 4-week mesocycle "might be a bit short," and users had to manually add sets when the app suggested only one set for a body part. [competitor] — [Dr. Muscle RP review 2025](https://dr-muscle.com/rp-hypertrophy-app-review/)
- **RP, no rest periods:** No timer, and "There's no rest periods even prescribed!" [competitor] — [StrengthLab360 RP review](https://strengthlab360.com/blogs/reviews-and-tests/the-rp-hypertrophy-app-review-why-strengthlab360-is-superior)
- **Volume benchmark:** A systematic review suggests about 12–20 weekly sets per muscle as an optimum standard for trained young men. This is useful for judging "too many sets" complaints. — [PubMed 35291645](https://pubmed.ncbi.nlm.nih.gov/35291645/)
- **Alpha Progression, deloads praised:** The app does "a fantastic job of telling you when to have deload weeks." A Play reviewer said "this app even has deload weeks!" — [HotelGyms guide](https://www.hotelgyms.com/blog/how-to-use-alpha-progression); [Google Play Alpha Progression](https://play.google.com/store/apps/details?id=com.alphaprogression.alphaprogression&hl=en_US)
- **Fitbod, no deload feature found:** I found no Fitbod deload feature. Its blog gives only generic advice to cut volume and intensity by "approximately 50%." — [Fitbod blog: bodybuilding deload](https://fitbod.me/blog/bodybuilding-deload/)
- **Fitbod, rest days are manual:** The app "doesn't schedule rest periods for you," so users have to plan them manually. [secondhand Reddit] — [Dr. Muscle Fitbod Reddit roundup](https://dr-muscle.com/fitbod-review-reddit/)
- **Alpha Progression, lifting only:** No cardio, HIIT or mobility sessions, "No audio-cues. No mobility routines," and no Apple Watch app. Reviewers call it a "weightlifting app" rather than a "workout app." — [Fitnessdrum Alpha review](https://fitnessdrum.com/alpha-progression-app-review/); [Fitnessdrum comparison](https://fitnessdrum.com/alpha-progression-vs-fitbod-vs-hevy-vs-boostcamp/)
- **Caliber, strength only:** "primarily focused on strength training—less ideal for cardio-centric goals." — [Sports Nerd Caliber](https://sports-nerd.com/brand/caliber/)
- **Ladder, rigid team structure:** Users can switch teams only twice a month, and there is "no Android app." [blog] — [Outdoorsy Nomad Ladder review 2026](https://www.outdoorsynomad.com/ladder-fitness-app-review/)
- **Boostcamp, structured programs:** Programs include built-in periodization and deload weeks, and "Auto-progressions fill in your weights." I found no independent complaints about Boostcamp's progression engine. [developer claim] — [Boostcamp App Store](https://apps.apple.com/it/app/boostcamp-workout-programs/id1529354455); [Boostcamp site](https://www.boostcamp.app/)
- **Boostcamp GZCLP, plateaus:** A reviewer felt gains plateaued, and another saw "minimal" muscle development after 15 weeks. [program design, not app] — [Boostcamp GZCLP reviews](https://www.boostcamp.app/cody-lefever/gzcl-program-gzclp/reviews)

### Inferences
- Time-limited sessions are a real pain point for volume-driven apps. Users want a "minutes available" input that caps sets, rather than routing time limits through recovery sliders.
- Hybrid lifting plus cardio/mobility integration is a frequent gap across hypertrophy-focused apps (Alpha, RP, Caliber).
- User-controllable deload timing (fixed every N weeks vs fatigue-triggered) is wanted.

### Gaps
- I found no sourced complaints on how apps handle missed or skipped workouts (shift the schedule vs drop the session), travel or hotel gyms, or temporary equipment profiles. Reddit was likely the main source and was inaccessible.

## 4. Recovery awareness: sleep, soreness, fatigue, cycle, and Fitbod's recovery map

### Takeaway
Fitbod's muscle-recovery percentages are a model, not a measurement. Even Fitbod says so, and reviewers note they can't account for sleep, illness or stress. RP's subjective feedback sliders (pump, soreness, workload) confuse beginners and produce "weird" adjustments when misused. I found no sourced evidence that Fitbod, JuggernautAI or RP use wearable sleep/HRV data or menstrual cycle phase.

### Cited Findings
- **Fitbod says the map is an estimate:** The recovery estimate is a model and "you know how you feel," and users can manually adjust a muscle's recovery percentage. — [Fitbod Help: Muscle Recovery](https://help.fitbod.me/hc/en-us/articles/360006269014-Muscle-Recovery)
- **Fitbod, accuracy limits:** Tracking is "more accurate than you might expect…but not infallible," and the app "can't account for external stress, such as poor sleep, illness, or life demands." — [Fitness Tools Reviewed](https://fitnesstoolsreviewed.com/app-reviews/fitbod-review-is-the-ai-gym-app-worth-it/)
- **Fitbod, trustworthiness unclear:** How trustworthy the recovery values are "remains unclear." [competitor] — [Dr. Muscle Fitbod bodybuilding review](https://dr-muscle.com/fitbod-bodybuilding-review/)
- **RP, sliders confuse beginners:** The pump, soreness and effort sliders confuse "newer lifters who don't yet have a good internal reference point." — [Dr. Muscle RP beginners](https://dr-muscle.com/rp-hypertrophy-app-beginners/)
- **RP, misused sliders cause odd adjustments:** "If you're adjusting those based on how mentally tired you are instead of how your performance and muscles feel, the app will react in weird ways." "Onboarding is confusing, especially with all the sliders and auto stuff." [single anecdote, low-quality forum] — [Ditchnet forum](https://ditchnet.org/t/can-anyone-share-an-honest-rp-hypertrophy-app-review/2143)
- **RP, manual feedback only:** Users "must manually report feedback, with no AI-driven adaptation." [competitor] — [StrengthLab360](https://strengthlab360.com/blogs/reviews-and-tests/the-rp-hypertrophy-app-review-why-strengthlab360-is-superior)
- **RP, pump as a volume signal questioned:** "chasing the pump" is "simply a novel way to stand out." [competitor] — [Dr. Muscle RP critique](https://dr-muscle.com/rp-hypertrophy-app-critique/)
- **Wearable data gaps (Future, Caliber):** Future encourages an Apple Watch, and without one the trainer gets less data. Caliber "does not automatically pull wearable biometric data" and lacks Garmin integration. — [Athletech News](https://athletechnews.com/product-of-the-week-future-app-personal-training-review/); [Cora Health Caliber](https://www.corahealth.app/compare/caliber); [Sports Nerd Caliber](https://sports-nerd.com/brand/caliber/)
- **Gravl, watch sync problems:** Apple Watch sync problems are reported (a v1.36.2 review), and there is no Galaxy Watch sync. — [mwm.ai Gravl](https://mwm.ai/apps/personal-trainer-gravl/6450921637); [Grand-Screen Gravl](https://grand-screen.com/apps/gravl-personal-trainer/reviews/)

### Inferences
- Users would value a readiness input (sleep, HRV, soreness, cycle phase, life stress) that visibly modulates the day's session, with a one-tap override. Today this is either absent (Fitbod uses only training history) or fully manual and confusing (RP sliders).
- The sliders need anchored definitions, e.g. "soreness that lasted more than 48–72 hours," to reduce garbage-in.

### Gaps
- I found no first-hand user complaints that the Fitbod recovery map is wrong, e.g. "it says my chest is 100% but I'm still sore." There are only reviewer-level caveats.
- I found no sourced data on whether any of the listed apps ingest sleep or HRV to adjust loads.

## 5. Trust: black-box recommendations, explanations, overrides, AI vs established programs

### Takeaway
Users and reviewers repeatedly prefer proven templates or explainable logic over opaque AI. Examples: Gravl users rate preset PPL above "AI mode," and Fitbod Redditors treat the app as a tracker. RP's interface "hides the logic behind its decisions," and its automatic volume changes can seem random. Apps are positioning around transparency and established programs (Liftosaur, Boostcamp).

### Cited Findings
- **RP, hidden logic:** The interface "often hides the logic behind its decisions," and automatic volume changes "can seem random." [low-quality forum] — [Ditchnet forum](https://ditchnet.org/t/can-anyone-share-an-honest-rp-hypertrophy-app-review/2143)
- **Fitbod as a tracker, not a coach:** Redditors generally treat Fitbod as a tracking tool, and "the key to results lies in your own efforts." One 7-month user was stronger but "looked the same." [secondhand Reddit] — [Dr. Muscle Fitbod Reddit roundup](https://dr-muscle.com/fitbod-review-reddit/)
- **Fitbod, bodybuilding results:** Fitbod "seems to fall short when it comes to bodybuilding," quoting a Reddit user who lost about 50 lb but "never visually saw an increase in muscle mass." [competitor; secondhand] — [Dr. Muscle Fitbod bodybuilding review](https://dr-muscle.com/fitbod-bodybuilding-review/)
- **Gravl, presets beat AI mode:** Preset splits work, AI mode is "terrible." [single anecdote] — [Grand-Screen Gravl](https://grand-screen.com/apps/gravl-personal-trainer/reviews/)
- **Explanations as a quality bar:** A tool that "just shows the next workout with no explanation is asking you to trust a black box." The same review rates Fitbod relatively strong on transparency and FitnessAI weaker. — [Leland AI fitness tools 2026](https://www.joinleland.com/library/a/ai-fitness-tools)
- **Market response, proven programs:** Liftosaur markets "proven routines like GZCLP, 5/3/1, or Basic Beginner Routine" with user-defined progression logic. Boostcamp markets nSuns, GZCLP and 5/3/1 with auto-progression. [developer claims] — [Liftosaur App Store](https://apps.apple.com/sl/app/liftosaur-scriptable-workouts/id1661880849); [Boostcamp](https://www.boostcamp.app/)
- **Research, comprehensiveness:** An AHA-cited 2024 study found AI exercise recommendations about 90% accurate on facts but only about 40% comprehensive. — [American Heart Association, Jan 2026](https://www.heart.org/en/news/2026/01/05/whats-the-best-way-to-use-ai-in-your-workout)
- **Research, trust:** A 2025 pilot study found AI-tool users had significantly higher trust (p=0.030) than non-users, and coaches often couldn't tell AI-made plans from expert plans. — [PMC11908068](https://pmc.ncbi.nlm.nih.gov/articles/PMC11908068)
- **Research, consistency of LLM prescriptions:** 2026 arXiv studies examine how consistent repeated LLM exercise prescriptions are (titles only seen, results not verified). — [arXiv 2604.11287](https://arxiv.org/pdf/2604.11287); [arXiv 2604.19598](https://arxiv.org/pdf/2604.19598)
- **Standalone chatbots lack history:** A standalone chatbot "has no record of what you lifted last week." — [Verro blog](https://www.verrotraining.com/blog/https/wwwverrotrainingcom/blog/ai-wrote-your-workout-why-thats-both-a-breakthrough-and-a-trap)

### Inferences
- The winning pattern appears to be "established template + transparent auto-progression + explainable adjustments + easy override," not free-form AI generation.
- Each recommendation should carry a one-line reason, e.g. "+2.5 kg because you hit 3×10 at RIR 2 last week."

### Gaps
- I could not retrieve Jeff Nippard or Mike Israetel commentary on competing apps, or YouTube transcript summaries.
- I found no first-hand Reddit threads on "why did it pick this."

## 6. Pricing complaints: AI coaching and human-coach apps

### Takeaway
Price-to-value is a dominant complaint for JuggernautAI (about $35/mo), RP (about $35/mo, 2.8 on Trustpilot) and the human-coach apps (Future at $149–199/mo; Caliber and Ladder with unclear or conflicting pricing). Billing and trial friction (JuggernautAI, Fitbod, Gravl) compounds it.

### Cited Findings
- **JuggernautAI, price and value:** Listed at $34.99/mo, with annual pricing conflicting between $299.99 and $349.99 across sources. A Play reviewer said the "app needs significant improvement to justify the price." Dr. Muscle says bugs are enough "to be weary about paying $35/month." Some reviewers call it a "steal" or "reasonable." — [Garage Gym Reviews 2026](https://www.garagegymreviews.com/juggernautai-review); [arvo.guru](https://arvo.guru/vs/juggernaut-ai); [Google Play JuggernautAI](https://play.google.com/store/apps/details?id=com.jtsstrength.juggernautai&hl=en_US); [Dr. Muscle](https://dr-muscle.com/juggernaut-workout-app-review/); [JuggernautAI App Store reviews](https://apps.apple.com/us/app/juggernautai/id1515756471?see-all=reviews)
- **JuggernautAI, billing friction:** A user was charged $35 immediately after downloading, because the trial applied only to website signups. Another user found no in-app subscription management, cancellation needed the website, and the app asks for "all of your info before telling you what plans cost." [single anecdotes] — [JustUseApp JuggernautAI](https://justuseapp.com/en/app/1515756471/juggernautai/reviews); [Google Play](https://play.google.com/store/apps/details?id=com.jtsstrength.juggernautai&hl=en_US)
- **RP Hypertrophy, price and reputation:** About $34.99/mo or $299.99/yr, with a Trustpilot rating of 2.8. Common complaints include a dated interface, limited analytics, a steep learning curve and no offline mode. [competitor] — [Mesostrength 2026](https://mesostrength.com/blog/rp-hypertrophy-alternatives)
- **RP, offline use:** "PLEASE make this app work WITHOUT an internet connection." This is a repeated App Store complaint. — [RP App Store reviews](https://apps.apple.com/us/app/rp-hypertrophy/id1555614554?see-all=reviews&platform=iphone)
- **Future:** $149–199/mo is "steep," there is "no real-time coaching," and form feedback is async and requires video. — [BarBend](https://barbend.com/future-app-review/); [Garage Gym Reviews Future](https://www.garagegymreviews.com/future-app-review); [Sports Nerd Future](https://sports-nerd.com/brand/future/)
- **Caliber:** "Lack of transparent pricing information." Premium 1-on-1 coaching is reported from about $200/mo, with a range of about $50–300+ across sources. Users report communication delays with coaches. — [Forbes Health](https://www.forbes.com/health/weight-loss/caliber-app-review/); [Sports Nerd Caliber](https://sports-nerd.com/brand/caliber/); [Cora Health](https://www.corahealth.app/compare/caliber)
- **Ladder:** No real free tier, "pricey ($15–$45/month)," with sources conflicting on price. Coaching feedback quality "varies widely," and "nobody watches you lift unless you pay for a form-check tier." — [Outdoorsy Nomad](https://www.outdoorsynomad.com/ladder-fitness-app-review/); [Sensai 2026, competitor](https://www.sensai.fit/blog/ladder-app-review-2026)
- **Gravl:** Most users can log only 3 workouts before paying, the trial feels shorter than advertised, and the price feels high with few plan options. — [Neura Health](https://neura.health/insight/gravl-workout-app-review); [Grand-Screen](https://grand-screen.com/apps/gravl-personal-trainer/reviews/); [Autonomous Gravl](https://www.autonomous.ai/ourblog/gravl-app-review)
- **Fitbod:** One user reports a failed cancellation and a double charge of $15.99. [single anecdote] — [PissedConsumer Fitbod](https://fitbod.pissedconsumer.com/review.html)
- **Alpha Progression:** About €12.99/mo, or $5–10/mo per a third party. Reviewers say "the best features need Pro." — [Alpha App Store DE](https://apps.apple.com/DE/app/id1462277793); [Fitnessdrum](https://fitnessdrum.com/alpha-progression-app-review/)

### Inferences
- Roughly $30–35/mo is the point where users expect near-coach quality and punish bugs hard. Billing dark patterns (trial only via web, no in-app cancel) generate disproportionate negative reviews.

### Gaps
- I found no sourced willingness-to-pay data.

## 7. Women-specific complaints and cycle-aware training

### Takeaway
I found no sourced r/xxfitness complaints. Reddit was blocked, and searches returned no indexed threads. I found no evidence that Fitbod, JuggernautAI or RP offer menstrual-cycle-aware programming. A cluster of niche apps (Fourmula, WeGLOW, Ondara, HerGym, FitrWoman, Wild.AI) markets cycle-phase training, which suggests unmet demand, but that evidence is marketing rather than complaints.

### Cited Findings
- **No cycle features found:** Searches found no cycle-aware training in Fitbod, JuggernautAI or RP. Juggernaut's closest women-specific resource is a nutrition book ("Renaissance Woman"). — [JTS Renaissance Woman](https://shop.jtsstrength.com/products/renaissance-woman)
- **Cycle-phase apps:** WeGLOW, Ondara and HerGym adjust intensity, volume and exercise selection by cycle phase. FitrWoman gives daily recommendations from logged symptoms. Sources conflict on whether Wild.AI adjusts training or only tracks. [developer claims; Ondara's comparison table is self-published] — [WeGLOW](https://www.weglow.app/article/best-strength-training-app-for-women); [Ondara 2026](https://ondara.app/resources/best/best-strength-training-apps-women/); [HerGym](https://apps.apple.com/us/app/-/id6756255956); [FitrWoman](https://play.google.com/store/apps/details?id=com.orreco.myfitr.woman&hl=en_US); [HealthyWomen](https://www.healthywomen.org/tech-talk-hp/menstrual-fitness-apps)
- **Cycle app "androcentric":** A user comment on the "28" cycle app calls its view of women "so androcentric for a cycle app" and its aesthetics "very aspirational." [single anecdote] — [28 App Store](https://apps.apple.com/is/app/28-cycle-syncing-workouts/id6443715544)
- **Mainstream apps lacking women-specific programming:** Ladder "works for lifting, but it's not for the pilates people." [TikTok, single anecdote] — [TikTok discover page](https://www.tiktok.com/discover/honest-review-of-define-ladder-fitness-app)
- **Privacy concern:** Flo was sued for sharing sensitive health data with Google and Meta, which is relevant if a lifting app ingests cycle data. — [Wikipedia: Flo](https://en.wikipedia.org/wiki/Flo_(app))

### Inferences
- A cycle-aware option in a mainstream lifting app looks like an unfilled niche. It should be opt-in, overridable, support irregular cycles, contraception and perimenopause, and be privacy-first. The evidence that phase-based training improves outcomes is mixed, which I did not verify here, so it should be framed as autoregulation rather than an optimization promise.

### Gaps
- I found no first-hand r/xxfitness complaints about male-default programming or glute emphasis. This needs direct Reddit access.
- I did not search the research on cycle-phase training efficacy.
