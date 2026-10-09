# Underserved users: cycle and menopause, beginners, older adults, injury and rehab, accessibility, neutral language

**Source note (read first).** WebFetch and curl were blocked in this session: DNS failures and a proxy `connect_rejected` for applevis.com, popsci.com, doi.org, unstar.app and foundation.mozilla.org. Everything below therefore comes from **web-search result snippets and summaries**, so it is secondhand.
- Text in "quotes" is the wording the search tool returned from the page. Treat it as near-verbatim, not checked character for character.
- No Reddit thread surfaced directly in any search. Subreddit-level sentiment is a **gap**, and the gaps are noted per section.
- Dates are given where the snippet stated them. Today is 2026-10-09.
- Round 1 already covered generic cycle-aware training, Whoop excluding contraception users (a claim now partly outdated, see §1), calorie-hiding / ED-safe mode, and sex-versus-gender inputs. This file avoids repeating those.

Format per finding: **App or context** · user complaint (quote) · source · how widespread · feature that would fix it.

---

## 1. Cycle tracking alongside training: privacy, paywalls, cycle-aware training, perimenopause/menopause, PCOS, contraception, symptoms

### Takeaway
Since round 1 the field has moved fast:
- Apple (iOS 27, WWDC June 2026) and Oura (May 2026) added perimenopause/menopause and hormonal-contraception support.
- Whoop (March 2026) says its cycle model now adapts to irregular cycles, perimenopause and birth control.
- In July 2026, Mozilla gave its only 10/10 to the app that stores data **on-device with no account** (Euki), and Stardust scored 2/10.

The durable complaints are:
1. Privacy and trust, sharpened by the Aug 2025 Meta/Flo jury verdict.
2. Aggressive paywalls on basic features.
3. Predictions that break on irregular, PCOS or perimenopausal cycles.
4. Cycle-sync apps that treat "workouts" as low-impact classes rather than lifting.

### Cited Findings

**Privacy after Dobbs**
- **Mozilla *Privacy Not Included*, six-app hands-on review (published July 16, 2026).**
  - Scores: Euki 10/10, Clue 8, Flo 7, Period Calendar 6, Planned Parenthood Spot On 5, Stardust 2.
  - Euki earned the only perfect score because it "stores health information locally and requires no account".
  - Clue was praised for "granular privacy controls that separate consent for research, analytics, recommendations, and advertising".
  - Mozilla noted an app can keep period dates internal "while still telling advertising or analytics companies that a specific device is using a reproductive-health application".
  - Widespread: high-profile and covered by many outlets.
  - Fix: local-only storage, no account required, no third-party analytics SDKs on health screens, and per-purpose consent toggles.
  - Sources: [CyberInsider](https://cyberinsider.com/mozilla-study-ranks-euki-as-the-most-private-period-tracker/); [Captain Compliance](https://captaincompliance.com/education/mozilla-tested-six-period-tracker-apps-only-one-earned-a-perfect-privacy-score/); [Digital Trends](https://www.digitaltrends.com/phones/stardust-flo-and-other-popular-period-trackers-flunk-mozillas-latest-privacy-test/); [Mozilla Foundation page](https://foundation.mozilla.org/en/privacynotincluded/period-tracker/) (could not fetch).
- **Stardust.**
  - Mozilla found it sharing reproductive details with the analytics firm RudderStack. Stardust disputes this and says RudderStack "does not receive personally identifiable information". — [SC World](https://www.scworld.com/brief/period-tracking-app-stardust-shares-sensitive-user-data-with-third-parties-report-finds)
  - After Roe it promoted itself as "encrypted", but TechCrunch found standard SSL rather than the promised end-to-end encryption, and the E2E claims were removed. — [Mozilla Stardust review](https://www.mozillafoundation.org/en/nothing-personal/stardust-privacy-review/)
  - As of May 2026 its policy names Meta's and Google's ad-measurement tools as partners. — same source
  - Fix: honest, specific privacy claims, plus an in-app data-flow screen.
- **Flo / Meta jury verdict (Aug 1, 2025).**
  - A San Francisco federal jury found Meta violated the California Invasion of Privacy Act by intercepting Flo users' data, for conduct between 2016 and 2019. Flo and Google settled earlier.
  - Consumer Reports told ex-Flo users to file a legal **data deletion request**, which is "different from account deactivation".
  - Widespread: major news story.
  - Fix: true in-app delete (not just deactivate), and no ad SDKs.
  - Sources: [Tom's Guide](https://www.tomsguide.com/computing/online-security/jury-finds-meta-illegally-collected-data-from-womens-health-app-flo-what-you-need-to-know); [Consumer Reports Innovation Lab](https://innovation.consumerreports.org/a-jury-verdict-against-meta-a-call-to-delete-your-data-with-flo/); [Lawdragon, 2025-08-25](https://www.lawdragon.com/news-features/2025-08-25-big-tech-on-trial-jury-finds-meta-liable-for-misusing-women-health-data)
- **Complaint mix in Flo's 1-star reviews.** A commercial blog's tally found "Data-Sharing and Privacy Fears (28%)" was the top cluster. Others were "a paywall over nearly every feature", lost history with "no restore option on a new phone", predictions that stop updating, and a premium chat described as "pre-written".
  - The method is undisclosed, so treat it as indicative only.
  - Fix: free core features, export and backup of cycle data, and a human-written or clearly labelled AI chat.
  - Source: [unstar.app, Flo review 2026](https://unstar.app/blog/is-flo-legit-safe-period-tracker-app-reviews-2026)

**Paywalls**
- **Clue.**
  - Google Play reviewers say: "they've taken nearly every single functionality and locked it behind a paywall"; another says constant upgrade prompts make it "frustrating and unusable".
  - A 2025 critique says previously free features moved behind Clue Plus.
  - Clue's reply: "there will always be a free version".
  - Widespread: recurring in reviews.
  - Fix: no feature regressions behind a paywall, and no upsell interstitials while logging.
  - Sources: [Clue on Google Play](https://play.google.com/store/apps/details?id=com.clue.android&hl=en_US); [Ferne Health critique](https://ferne.health/blog/clue-alternative/)
- **Wild.AI (cycle-aware training).**
  - Reviewers say they can no longer see their own logged data without paying, that trend graphs became subscription-only, and that daily recommendations stopped reflecting check-ins.
  - Garmin data had not synced "for months", and support took weeks to reply.
  - Monthly and yearly plans were listed at the same price, and the subscribe/support buttons were broken.
  - Pricing: the App Store lists $14.99 Basic and $79.99/yr. A 2026 article says pricing changed after an "ownership transition".
  - Widespread: multiple reviews across both stores.
  - Fix: never lock users out of their own historical data; reliable wearable sync.
  - Sources: [AppBrain Wild AI](https://www.appbrain.com/app/wild-ai/com.wildai.wild); [Google Play](https://play.google.com/store/apps/details?id=com.wildai.wild&hl=en_CA&gl=US); [App Store reviews](https://apps.apple.com/us/app/wild-ai-hormones-fitness/id1482294997?see-all=reviews&platform=iphone); [go-go-gaia 2026](https://www.go-go-gaia.com/blog/cycle-aware-training-apps.html)
- **Cycle-sync workout apps (Drop It, Lively, Cycle Diet).**
  - Drop It: "expensive to subscribe" for something "basic", and "why should I pay for something every woman has naturally". It is rated 3.8 from only 10 ratings, so the sample is small.
  - Lively: "upsell prompts are persistent".
  - Fix: a free cycle-aware layer inside an existing training app.
  - Source: [Drop It App Store](https://apps.apple.com/us/app/cycle-sync-workouts-drop-it/id6746949244)
- **Oura.**
  - Cycle Insights requires Gen3+ and an active membership ($5.99/mo).
  - Oura's own blog admits that one of new members' "biggest complaints" was waiting **60 nights** before seeing predictions. Its fix claims predictions from "as little as 1 night" plus a period start date.
  - A third-party guide cites users saying the subscription "feels mandatory for basic functionality" and that predictions took "nearly three months" to stabilize. Those sources are unnamed, so treat the quotes cautiously.
  - Fix: useful from day 1 using the logged period start; show a prediction window with an explicit confidence level.
  - Sources: [Oura blog, Cycle Insights update](https://ouraring.com/blog/oura-cycle-insights-update/); [Oura support](https://support.ouraring.com/hc/en-us/articles/4410663885331-Cycle-Insights); [carefocusdaily guide](https://carefocusdaily.com/selfcare/oura-cycle-tracking-guide)

**Cycle-aware training: fit for lifters**
- **Lunaletics** says it is "not the right app if you do not have a natural menstrual cycle", for example if postmenopausal or using hormonal contraception. Its early-cycle workouts "can be quite challenging". — [Lunaletics App Store](https://apps.apple.com/us/app/lunaletics-cycle-syncing-app/id6744465014)
- **Cycle Diet** offers a "low-impact workout format only – not suitable for advanced training goals". — [health-time review 2026](https://www.health-time.com/en/article/1145_1_cd_womens-health_story_guide_en_reviewed-cycle-diet-app-2026-minutes)
- **The 28 app** is fine for "workouts and meal planning, not for family planning". — [Natural Womanhood](https://naturalwomanhood.org/28-app-review/)
- Widespread: this is a structural gap.
  - Cycle-sync apps are built around classes rather than progressive overload.
  - Lifting apps have no cycle layer.
  - This fits nütn's niche: a strength program plus an optional cycle overlay.

**Contraception users (update to round 1)**
- **Whoop.** Its March 2026 white paper says Menstrual Cycle Insights "adapts for variable cycles, perimenopause, hormonal birth control", with birth-control status as a model input. A Whoop page says it is available "both with and without hormonal birth control".
  - **This contradicts round 1's "Whoop excludes contraception users" finding as of 2026.**
  - Sources: [Whoop white paper](https://www.whoop.com/us/en/thelocker/menstrual-cycle-insights-white-paper/); [Whoop life-stages article](https://ww2.whoop.com/thelocker/whoop-features-support-reproductive-health-through-all-life-stages/); [Wareable, Mar 2026](https://www.wareable.com/health-and-wellbeing/whoop-women-blood-biomarker-panel-advanced-labs-hormonal-symptom-predictions)
- **Oura** added "Hormonal Birth Control support" for "pills, patches, IUDs, implants, and other methods", rolling out globally May 6, 2026. — [Android Authority, May 2026](https://www.androidauthority.com/oura-launches-hormonal-health-features-3662688/); [FoneArena](https://www.fonearena.com/blog/481589/oura-adds-hormonal-birth-control-support-and-menopause-insights.html)
- **Natural Cycles (used as contraception).**
  - Users report unexpected annual price increases and short renewal notice. One got only account credit, not a refund, after auto-renewal.
  - Cost: "$120 a year", and insurance denied the claim.
  - The thermometer "is not backlit" and the previous reading shows "for a split-second". Sync needs a manual Bluetooth button press.
  - An April 2025 review reports pregnancy after a "green day": "red days are only a prediction".
  - Sources: [Trustpilot](https://www.trustpilot.com/review/www.naturalcycles.com); [App Store reviews](https://apps.apple.com/us/app/natural-cycles-fertility-app/id765535549?see-all=reviews); [The Lowdown, Apr 2025](https://thelowdown.com/contraceptives/natural-cycles-app)
  - Relevance to nütn: never present a basic tracker's fertile-window estimate as contraception.

**Perimenopause and menopause**
- **Apple, iOS 27 / watchOS 27 (WWDC, June 2026).**
  - Cycle Tracking adds perimenopause and menopause support.
  - Notifications fire when cycle patterns are "suggestive of perimenopause", for users 40+.
  - Symptom logging covers hot flashes, night sweats, sleep changes and more.
  - Apple says it is not for birth control or diagnosis.
  - Implication: free OS-level competition, so nütn should **read/write HealthKit cycle data rather than duplicate it**.
  - Sources: [Femtech Insider](https://femtechinsider.com/apple-adds-menopause-and-perimenopause-support-to-health-app/); [Apple Watch User Guide (watchOS 27)](https://support.apple.com/guide/watch/pym0x6ny1te5/watchos)
- **Oura.** Perimenopause Check-In launched Aug 2025 (US). Menopause Insights, a questionnaire on the "Menopause Impact Scale", followed in May 2026. — [Android Authority](https://www.androidauthority.com/oura-launches-hormonal-health-features-3662688/); [Athletech News](https://athletechnews.com/oura-deepens-womens-health-offerings-across-hormonal-life-stages/)
- **Clue Perimenopause mode (2023).**
  - Paid, part of Clue Plus.
  - Cycle View compares cycles instead of counting down, and adds 14 options (hot flashes, night sweats, brain fog, HRT, vaginal dryness and others).
  - Clue's own UX research found the opening message "Your period is [##] days late" upset users.
  - A MetaFilter subscriber said it mostly "reconfigures the layout of tracking categories" and that they "would never pay $10/mo" for it.
  - Fix: a no-countdown, no "late" framing mode, with peri symptoms in the free tier.
  - Sources: [Clue intro](https://helloclue.com/articles/menopause/introducing-clue-perimenopause); [Marianne Yates UX case study](https://www.marianneyates.com/ux-ui/clue-perimenopause-mode---marianne-yates); [MetaFilter](https://ask.metafilter.com/377584/Is-Clue-Menopause-worth-the-subscription)
- **Menopause-app category.**
  - A 2025 systematic review of 80 App Store apps found that 96% offer symptom tracking but concluded that "existing symptom-recording methods were ineffective". Only 27.5% integrate wearables. — [Research Square preprint](https://www.researchsquare.com/article/rs-10448173/v1)
  - JMIR 2025: researchers warn that constant prompts can make symptoms feel "more of a problem than they actually are". — [JMIR 106205](https://doi.org/10.2196/106205) (secondhand via search)
  - Comparison sites report:
    - Balance users must re-enter data already on Apple Watch or Garmin, because there is no wearable integration.
    - Health reports broke after an update.
    - MenoLife has sync issues.
    - Source: [healthjourneylabs 2026](https://healthjourneylabs.com/menopause-journey/blog/best-menopause-apps-2026.html)
  - Widespread: moderate.
  - Fix: low-friction one-tap symptom logging, wearable/HealthKit import, and an optional reminder cadence.
- **HRT logging is a distinct need.** Dedicated HRT trackers exist (HRTMe, Regimen, TALIA, Crest). Crest's developer said they built it because they "couldn't find an app that tracked HRT properly". HotFlash "counts days since the last period, instead of pretending to predict an irregular cycle".
  - Fix: a medication/HRT dose log (patch change days, gel pumps, progesterone) shown alongside sleep, mood and training.
  - Sources: [donedose HRT guide](https://www.donedose.com/guides/best-hrt-tracker-app); [Crest, Google Play](https://play.google.com/store/apps/details?id=com.femhq.crest&hl=en_US); [go-go-gaia 2026](https://www.go-go-gaia.com/blog/best-perimenopause-tracking-app.html)
- **Midlife women and fitness apps.**
  - A Reddit commenter (r/fitness, quoted in a vendor guide): "Most fitness apps seem ignorant of menopause."
  - The same guide says most apps are "built for 25-year-olds chasing PRs".
  - Single-app review: "no hormone-aware programming, no injury prevention framework, and no structured path for perimenopause or menopause".
  - These are secondhand and from vendor-adjacent sources.
  - Sources: [verold.com 2026](https://www.verold.com/best-fitness-apps-women-over-40-2026/); [trainwell perimenopause apps](https://www.trainwell.net/blog/best-personal-trainer-apps-perimenopause-menopause)

**PCOS and irregular cycles**
- **Prediction method.** Clue, Flo, Stardust and Spot On "all use some version of a rolling average", which works only when cycles are consistent. With swings from 25 to 35 days, "the algorithm is essentially guessing".
- **PCOS-app blog claim.** Mainstream apps flag "late" or "missed" periods as user error or ask whether the user is pregnant.
- **Mumsnet.** Flo was "completely wrong about ovulation".
- **Flo's 2019 health assessment** flagged a user's acne and irregular cycle as possible PCOS, when she had just changed birth control.
- **Unverified numbers.** Accuracy figures on these sites ("22%", "18%") have no traceable study and come from competing PCOS apps.
- Widespread: high among irregular-cycle users.
- Fix: an "irregular / PCOS" mode with no countdown or "late" alerts, a range-based estimate or none, and symptom-first logging.
- Sources: [pcostracker.app, Flo alternatives](https://www.pcostracker.app/blog/flo-app-alternatives/); [Mumsnet](https://www.mumsnet.com/talk/pregnancy/4689141-flo-app-being-inaccurate); [Advisory Board, 2019](https://www.advisory.com/daily-briefing/2019/11/11/pcos)

### Inferences
- nütn's "basic period tracker" competes with free Apple Health (iOS 27). It wins only by **joining cycle data to training, nutrition, sleep and mood**, which single-purpose apps can't do.
  - Example: "Your RPE at the same load averages 0.5 higher in the 5 days before your period."
  - Framing should stay observational, not medical.
- Privacy is a competitive weapon nütn can claim if true: free, ad-free, no ad SDKs, local-first cycle data, delete that actually deletes, and no account needed for cycle data. Mozilla's top score went exactly to that pattern.
- Modes needed beyond "regular cycle":
  - hormonal contraception (method picker);
  - irregular / PCOS (no predictions, or a range only);
  - perimenopause (cycle comparison, hot flashes, night sweats, brain fog, joint pain, HRT log);
  - postmenopause (no cycle, symptoms only);
  - pregnancy/postpartum pause.
- Cycle-aware training should be **opt-in autoregulation**, e.g. "feeling flat? use the lighter variant". Do not prescribe phase-based programs, because the evidence is contested (see round 1).

### Gaps
- No r/xxfitness, r/Menopause or r/PCOS threads surfaced (Reddit blocked or not indexed), so subreddit-specific quotes are missing.
- No user complaints yet about Apple's iOS 27 perimenopause feature or Oura's Menopause Insights; they are too new.
- No independent validation of Whoop's or Oura's prediction-accuracy claims.
- FitrWoman: no complaint data found. It is still updated (v3.4.2.1, Dec 2025) and free. — [AppBrain](https://www.appbrain.com/app/fitrwoman/com.orreco.myfitr.woman)

---

## 2. Beginners: where they quit and what onboarding helps

### Takeaway
Beginners don't quit because programs are too hard so much as because they don't know what to do, feel watched, and lose motivation once novelty fades (weeks 3–12). Thin form guidance is the most concrete app-level complaint. Early consistency in the first ~28 days is the strongest predictor of sticking with it.

### Cited Findings
- **Gym intimidation (Oct 2025, Pollfish, 1,000 US gym-goers; commissioned by Musclebooster).**
  - 51% have felt intimidated or judged while working out; 34% more than once.
  - Gen Z: 66%.
  - Top triggers: "how other people looked at them" (53%) and "feeling out of their comfort zone" (48%).
  - UK sister poll: 47%; women 28% versus men 14%.
  - Brand-commissioned, so treat as directional.
  - Sources: [Musclebooster US](https://musclebooster.welltech.com/gymtimidation-us); [Musclebooster UK](https://musclebooster.welltech.com/gymtimidation-uk)
- **Older and undated polls.**
  - Virgin Active (2,000 UK): 26% avoided gyms because unsure how to operate equipment or afraid no one would help.
  - Gymshark (1,000 women): 88% have had gym anxiety; 66% skipped a workout because of it.
  - Sources: [Health Club Management](https://www.healthclubmanagement.co.uk/health-club-management-news/'Gymtimidation'-holding-back-potential-members/317987); [Gymshark blog](https://www.gymshark.com/blog/article/gym-anxiety)
  - Fix:
    - an "I'm new / first visit" mode with equipment explainers (what the machine looks like and how to adjust it);
    - quiet-hours / home / dumbbell-only variants;
    - substitutions when equipment is taken.
- **Peer-reviewed gym anxiety (India, Aug–Oct 2025, n=384).** High gym-related anxiety ~36%; avoidance 27.8%; 94.4% prefer less-crowded hours. — [IJCMPH](https://www.ijcmph.com/index.php/ijcmph/article/view/15661)
- **Dropout timing (large app cohort, PubMed / SportRxiv preprint).**
  - Median time to dropout was 19 weeks in the published version.
  - The preprint: 18.1% of beginners were still adherent at 6 months, median dropout 14 weeks, and consistency in the first 28 days was the strongest predictor of long-term adherence (522,994-user cohort).
  - The two versions differ, as noted by the source.
  - Sources: [PubMed 42638731](https://pubmed.ncbi.nlm.nih.gov/42638731/); [SportRxiv 709](https://sportrxiv.org/index.php/server/preprint/view/709)
  - Fix: optimise onboarding for **attendance streaks of 2–3 sessions per week for 4 weeks**, not load progression.
- **When quitting happens.** The critical window is weeks 3–12, when "the novelty is gone, the early soreness has faded, and visible results still haven't shown up". This is vendor content, and there is no peer-reviewed evidence that DOMS itself drives quitting.
  - Fix: early non-scale progress markers (reps added, sessions completed, e1RM up) and a "why results take time" nudge around week 3.
  - Sources: [getfitcraft adherence stats](https://getfitcraft.com/science/workout-adherence-statistics); [dailyburn beginners 2026](https://dailyburn.com/life/health/best-workout-apps-for-people-who-have-never-exercised-before-2026-guide/)
- **Session length.** A beginner guide suggests 15–25 minute first sessions, because anything longer "is more likely to lead to soreness and burnout in your first two weeks". This is vendor advice. — [dailyburn](https://dailyburn.com/life/health/best-workout-apps-for-people-who-have-never-exercised-before-2026-guide/)
- **Form guidance (Fitbod).**
  - A reviewer says "a two-second looping animation isn't going to teach you the movement safely for someone who hasn't learned a squat or hip hinge"; beginners "will need external resources".
  - Another user was "disappointed with some of the exercise instructions".
  - Widespread: moderate, and the most specific app-level beginner complaint found.
  - Fix: real how-to (video or multi-angle images) plus 2–3 key cues plus "common mistakes", and a "learn this lift" progression (goblet squat → box squat → back squat).
  - Sources: [Fitness Tools Reviewed](https://fitnesstoolsreviewed.com/app-reviews/fitbod-review-is-the-ai-gym-app-worth-it/); [Yahoo Health review](https://health.yahoo.com/wellness/fitness/online-fitness/articles/fitbod-app-review-good-beginners-193000972.html)
  - **nütn has no exercise videos, only cue text** (round-1 inventory).
- **Progression whiplash (Fitbod).** Progression "sometimes jumps way too fast, and other times it just doesn't change much for a while", and the default "cycles through the same 15-20 exercises".
  - Contradicting the premise: reviews say starting weights "err on the conservative side". No "too hard" complaints surfaced.
  - Fix: explain each progression step ("+2.5 kg because you hit all reps at RPE ≤8").
  - Source: [Fitness Tools Reviewed](https://fitnesstoolsreviewed.com/app-reviews/fitbod-review-is-the-ai-gym-app-worth-it/)
- **Beginner-specific apps** position on reducing "psychological barriers":
  - "Core: Let's Start Here" (free, from a college capstone);
  - Fitloop (Reddit Recommended Routine with built-in progression levels).
  - Sources: [Core App Store](https://apps.apple.com/us/app/core-lets-start-here/id6755366891); [Fitloop](https://apps.apple.com/us/app/id1474941254)

### Inferences
- Beginner fixes that fit nütn:
  - an onboarding question "How familiar are you with a gym?" that switches on plain-language labels (hide RPE/RIR/MEV/MRV jargon, or use "how many more reps could you do?");
  - a 2–3 day full-body starter with machine/dumbbell variants;
  - a first-week soreness explainer;
  - attendance-based streaks.
- nütn's deep engine (mesocycles, MEV/MRV, DUP) is a jargon risk for beginners. Progressive disclosure is the fix.

### Gaps
- No r/beginnerfitness or r/fitness30plus quotes surfaced.
- No controlled evidence links soreness management to retention.
- No App Store reviews where a beginner says an app was "too advanced" were found.

---

## 3. Older adults (50+)

### Takeaway
Studies, not app reviews, are the main evidence:
- small fonts and no magnification;
- unintuitive navigation;
- frustration with manual logging;
- one-size-fits-all programming;
- privacy worries.

The content older users want is seated/standing variants, low-impact options, structured balance work, fall-risk feedback, and bone-friendly resistance training. Medication, exercise and bone-health tools are fragmented across separate apps.

### Cited Findings
- **Senior Fit study (arXiv, Oct 2025; 25 participants aged 65–85).**
  - Participants valued video demonstrations and reminders.
  - "Some expressed frustration with manual logging and limited personalization."
  - A Facebook-group component "excluded others unfamiliar with the platform".
  - In an earlier analysis (Dec 2024), participants preferred automatic tracking and hesitated over camera-based features.
  - Fix: auto-import from Apple Health/Watch, minimal typing, no social-platform dependency.
  - Sources: [arXiv 2510.24638](https://arxiv.org/pdf/2510.24638); [ResearchGate, Senior Fit](https://www.researchgate.net/publication/387642365_USER-CENTERED_ANALYSIS_OF_A_FITNESS_APP_FOR_OLDER_ADULTS_SENIOR_FIT)
- **UT Arlington (Feb 2025).** "Many were concerned about privacy and how their data would be used." — [UTA News](https://www.uta.edu/news/news-releases/2025/02/26/research-backed-app-helsp-seniors-stay-active)
- **Health-app usability (2025, 100 older adults).**
  - Problems: "insufficient font size, lack of screen magnification, and unintuitive interface designs".
  - Recommended: adjustable font sizes and magnification.
  - Fix: full Dynamic Type support, large-tap-target mode, and a simplified home.
  - Source: [PMC12761059](https://pmc.ncbi.nlm.nih.gov/articles/PMC12761059)
- **Systematic review (2025, 132 articles).** Essentials: "simplified navigation, enlarged text and touch targets, voice interaction, and error-tolerant interfaces". Cognitive overload and digital literacy remain barriers. — [PMC12350549](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC12350549/)
- **Mainstream app fit.**
  - Apps default to "high-impact exercises, heavy loading, and intensity-first programming that's poorly matched" to people over 60–70. This is a vendor comparison.
  - A senior app reviewer, after three sessions: "this is a one size fit all type program".
  - Wanted: seated alternatives, low-impact options, structured balance programming, and stability tests with fall-risk feedback (e.g. Bold starts with a fall-risk assessment).
  - Fix: a "joint-friendly" filter, seated/standing/floor-free variants per exercise, and a balance block (single-leg stance timer, tandem stance) with progress tracking.
  - Sources: [getfitcraft seniors](https://getfitcraft.com/compare/best-fitness-apps-for-seniors); [seniorliving.org 2026](https://www.seniorliving.org/cell-phone/apps/exercise/)
- **Frail older adults (Age and Ageing, 2023).** Exercise apps "only provide exercise instructions and lacked other features", with no tracking or clinician integration. — [Age and Ageing afad227](https://academic.oup.com/ageing/article/52/12/afad227/7503299)
- **Osteoporosis apps.**
  - A 2019 review of 19 apps: 74% gave no clear instructions for the elderly; reminders and visual aids appeared in only 11%; "low quality, poor performance". This is older.
  - BONE IQ targets strength training for osteopenia and menopausal women. OsteoApp is mostly a medication reminder.
  - Sources: [ResearchGate systematic review](https://www.researchgate.net/publication/347618411_Mobile_Health_Applications_for_Osteoporosis_Support_Available_on_the_Market_A_Systematic_Review); [Healthify NZ](https://healthify.nz/apps/o/osteoporosis-apps)
- **Medication plus bone health.** The Wellhealth feasibility study (osteoporosis meds) generated dose reminders. Medication logging averaged 62.4%, and 49% (15/32) reported high satisfaction. This shows that pairing a med schedule with health tracking is feasible. — [PMC13294653](https://pmc.ncbi.nlm.nih.gov/articles/PMC13294653/)
- **Insurance-funded competition.** SilverSneakers GO has a seated/chair yoga library and is free with many Medicare Advantage plans. — [getfitcraft seniors](https://getfitcraft.com/compare/best-fitness-apps-for-seniors)

### Inferences
- nütn already has supplements. Extending to a **medication schedule** (name, dose, time, reminder, "taken" tick) serves both 50+ users and HRT users from §1 with one feature.
- A "Bone & balance" program template fits nütn's program engine: resistance with impact options, balance, and posture. So does a "joint-friendly" substitution rule in the exercise database (e.g. leg press for back squat, landmine press for overhead press).

### Gaps
- No r/over60fitness or r/fitness30plus quotes surfaced.
- No App Store reviews from 50+ users complaining about text size in a named fitness app, apart from Trainerize (§5).

---

## 4. Injury and rehab: pain logging, exercises to avoid, return-to-training, physio apps

### Takeaway
Mainstream lifting apps have no structured pain input. Strong uses free-text pinned notes. Hevy's injury feature lives only inside its paid AI "Trainer". Rehab apps track pain but not loaded strength training. The gap is a regular program that knows about an injury and adjusts. Physio-app complaints centre on generic, repetitive plans, content cuts, bugs, and paywalls before seeing any exercise.

### Cited Findings
- **Strong.**
  - Help centre: "we get a lot of feature requests around notes".
  - Its own example note is "Left shoulder felt off today, was only able to do 5 reps on the last set".
  - Pinned notes recur on every session of that exercise but "will not display on the history screen".
  - Widespread: the vendor says it is frequent.
  - Fix: a structured per-exercise pain flag (0–10 plus location) that shows in history and trends.
  - Source: [Strong Help Center](https://help.strongapp.io/article/134-how-do-notes-work)
- **Hevy.**
  - Injury Management exists only in Hevy Trainer. Users "flag injuries" and the program replaces "high-risk exercises" or adds warnings, and the injury can be removed once healed.
  - No "avoid list" was found for manual logging.
  - Fix: a global "avoid / caution" list honoured by every program and by search.
  - Sources: [Hevy Trainer](https://www.hevyapp.com/features/workout-plan-generator/); [Hevy App Store](https://apps.apple.com/us/app/hevy-workout-tracker-gym-log/id1458862350)
- **Guide on injury-aware apps.** Check whether an app accepts "the movement, range, loading pattern, or exercise you already know you need to avoid", not just a body-part label.
  - Fix: restrictions by movement pattern (e.g. "no overhead pressing", "no loaded spinal flexion"), not just "shoulder".
  - Source: [budy.fit](https://budy.fit/workout-app-for-injuries)
- **Stronge.** Daily pain check-ins change the session rather than just logging it. This is a pattern to borrow. — [stronge.app](https://stronge.app/)
- **Rehab-first trackers.**
  - ACL Recovery Tracker: 0–10 pain with location and context, and a staged path from Week 0 post-op to return-to-sport at Week 48+.
  - Injury Recovery Tracker (Android): a calendar colour-coded by pain, workout and mood.
  - Neither does general strength programming.
  - Fix in nütn: a "return-to-training" ramp (e.g. 50% → 70% → 85% → 100% of pre-injury working loads over N weeks, gated by pain ≤ 3/10). It should be presented as user-set, not medical advice.
  - Sources: [ACL Recovery Tracker](https://apps.apple.com/us/app/acl-recovery-tracker/id6759330025); [Injury Recovery Tracker](https://play.google.com/store/apps/details?id=com.inesthetechie.recovery_tracker&amp%3Bhl=en)
- **UW design study (runner app).** Real-time pain entry, without unlocking the device, "was identified as a priority". [Older, class project] — [UW CSE440](https://courses.cs.washington.edu/courses/cse440/19wi/assets/samples/2f/2f_hermes.pdf)
- **Stronglifts.** Deloads after a break are driven by time away, not by pain. — [Stronglifts](https://stronglifts.com/app/)
- **Hinge Health.**
  - Rated 4.9 from 129K ratings, so complaints are a minority.
  - "The exercises, which DO HELP, are repetitive, standard and GENERIC. I just don't think I'm getting individual attention."
  - A Trustpilot reviewer says sessions were cut from ~20 to ~9 min and "The videos are permanently removed"; Hinge advised following audio.
  - Sensors "can't tell that I am standing up".
  - Users were told to skip what they couldn't do and "not substitute exercises".
  - Fix: substitutions when an exercise hurts, keeping videos, and variety over weeks.
  - Sources: [Trustpilot Hinge Health](https://www.trustpilot.com/review/hingehealth.com); [App Store](https://apps.apple.com/us/app/hinge-health/id1429270372)
- **Kaia Health.**
  - "Won't even let you see a single exercise before forcing you to sign up", with only a 7-day trial.
  - The assessment showed "100% complete", then looped back.
  - The plan shows only the main focus area, and other areas sit behind extra taps.
  - Sources: [justuseapp Kaia reviews](https://justuseapp.com/en/app/1100673977/kaia-back-pain-relief/reviews); [Kaia on Google Play](https://play.google.com/store/apps/details?id=com.kaiahealth.app&hl=en_US)
- **PT Wired (clinic-branded home exercise app).**
  - 3.0★ from only 8 Google Play reviews: can't mark exercises complete, and it crashes when scrolling within an exercise.
  - Clinicians on Capterra rate it 4.9 from 16 reviews.
  - A competitor cites price spikes from add-ons and rigid annual contracts.
  - Thin data.
  - Sources: [PT Wired Google Play](https://play.google.com/store/apps/details?id=com.ptwired.ptwiredapp&amp%3Bhl=en_US); [Capterra](https://www.capterra.com/p/186679/PT-Wired/reviews/); [SPRY competitor blog](https://www.sprypt.com/blog/top-pt-wired-alternatives-and-competitors)
- **Arthritis home exercise.** A qualitative study (2024) of PT and patient views on apps exists, but its findings were not retrievable. — [PMC11006223](https://pmc.ncbi.nlm.nih.gov/articles/PMC11006223/)

### Inferences
- nütn could own "train around it" for lifters, which neither Strong nor Hevy's free tier does:
  - **an injury record**: area, movement restrictions, start date, and an optional "my physio said…" note;
  - **per-set pain 0–10** that is one tap, optional, and recorded alongside RPE;
  - an **avoid/caution list** that program generation and the exercise picker respect;
  - **pain-trend charts** per exercise;
  - a **return-to-training ramp** template;
  - a "PT exercises" custom program type with simple completion ticks, which replaces buggy clinic apps for home exercise programs.
- Copy must stay non-clinical: "you told us X hurts, so we've swapped Y", never diagnose.

### Gaps
- No r/physicaltherapy or r/weightroom "pain log" threads surfaced.
- No user-review evidence that physio-app exercises caused flare-ups. One reviewer attributed their flare-up to skipping stretches.

---

## 5. Accessibility: VoiceOver, Dynamic Type, colour-blind charts, one-handed use, wheelchair users, adaptive training

### Takeaway
Blind users can generally navigate fitness apps, but **adjusting set/rep/weight controls** is where VoiceOver breaks. Dynamic Type is often unsupported or truncates text: Trainerize users have asked since about 2020, still in Feb 2026, and Hevy truncates. Wheelchair users get pushes but not distance, can't switch modes for mixed walking/rolling, and find adaptive content paywalled or scarce. Only 4 of about 1,735 apps were tailored for deaf/hard-of-hearing or blind/low-vision users.

### Cited Findings
- **AppleVis forum, "Free accessible app for tracking workouts?"** A user logging exercises, sets, reps and weights said some apps "almost work, but they don't work with VoiceOver for adjusting reps or sets".
  - Widespread: a recurring theme on AppleVis.
  - Fix: steppers with `accessibilityAdjustableAction` (swipe up/down to change reps or weight), labelled values ("Set 2, 8 reps, 60 kilograms"), and VoiceOver custom actions ("complete set", "copy previous").
  - Source: [AppleVis forum](https://www.applevis.com/forum/ios-ipados/free-accessible-app-tracking-workouts) (could not fetch, snippet only)
- **Strong on AppleVis.** "Fully accessible with VoiceOver, but the interface could be easier to navigate and use." This is an older review. — [AppleVis Strong](https://www.applevis.com/apps/ios/health-fitness/strong-workout-tracker-gym-log)
- **HeavySet on AppleVis.** "One of the most accessible apps of its kind", "isn't perfect, but is quite useable". RepCount's recent updates added "better VoiceOver labels on the workout screen". — [AppleVis HeavySet](https://applevis.com/apps/ios/sports-activities/heavyset-gym-workout-log); [RepCount App Store](https://apps.apple.com/us/app/repcount-gym-workout-tracker/id594982044)
- **Audio graphs.** The Steps app tuned its Workout tab for VoiceOver, with charts supporting **audio graphs** (May 2022). Apple Health supports audio graphs.
  - Fix: implement `AXChartDescriptor` on nütn's charts (weight trend, e1RM, sleep, cycle).
  - Source: [AppleVis Unlimited May 2022](https://www.applevis.com/blog/applevis-unlimited-whats-new-noteworthy-may-2022)
- **Apple Fitness+.** Audio Hints switch on automatically with VoiceOver. AFB (Mar 2023) found the "Add to My Workouts" control is announced as a button but cannot be reached via rotor button navigation. — [AFB AccessWorld](https://afb.org/aw/march2023/choosing-workout-app); [AppleVis blog](https://www.applevis.com/blog/apple-makes-fitness-workouts-more-accessible-blind-low-vision-subscribers-addition-audio-hints)
- **Aaptiv on AppleVis.** "The rating portion isn't accessible, but everything else is." This is an older review. — [AppleVis Aaptiv](https://www.applevis.com/apps/ios/health-fitness/aaptiv-1-audio-fitness-app)
- **MyFitnessPal and the paywalled barcode scanner (Premium since Oct 1, 2022).**
  - Community: "as a Dyslexic person, this wasn't an 'ease of use' feature, this is an accessibility feature."
  - "If MFP does not have a policy of making Premium free for people who need it for accessibility issues, they should."
  - An AppleVis reviewer rated MFP "Very Accessible" but "tedious", and liked how it reads barcodes.
  - Fix: keep barcode scanning, voice logging and photo label logging free. **nütn already does.**
  - Sources: [MFP Community "Accessibility"](https://community.myfitnesspal.com/en/discussion/10883149/accessibility); [MFP support](https://support.myfitnesspal.com/hc/en-us/articles/360032271672-The-barcode-scanner-is-not-working-in-the-iOS-app); [AppleVis MFP](https://www.applevis.com/apps/ios/health-fitness/myfitnesspal-calorie-counter)
- **Voice logging as an accessibility path.** RepLog, SaySet and VoiceFitLog parse "Bench press, 80 kilograms, 8 reps, 3 sets". Their VoiceOver support is unverified.
  - nütn has food voice logging. Extending it to sets would help blind users, one-handed users and anyone mid-set.
  - Sources: [RepLog](https://apps.apple.com/us/app/replog-voice-workout-tracker/id6764242522); [SaySet](https://sayset.fit/)
- **Discoverability study (PMC).** Of about 1,735 apps reviewed, only **four** were tailored fitness apps for deaf/hard-of-hearing or blind/low-vision users. They were "rare and difficult to locate" in App Store search, and cost was a barrier.
  - Fix: name accessibility features in the App Store description, and keep core features free.
  - Source: [PMC13526966](https://pmc.ncbi.nlm.nih.gov/articles/PMC13526966/)
- **Dynamic Type: Trainerize.**
  - The request is that supporting dynamic type "gives clients the ability to set font to their preferred size".
  - The vendor said it was "on the roadmap … haven't been able to act on it this year due to COVID".
  - Comments as late as **Feb 2026** still say text is too small; one user over 40 asks for larger font and darker input-box edges.
  - Widespread: a long-running vote thread.
  - Fix: full Dynamic Type including accessibility sizes, plus higher-contrast input borders.
  - Source: [ABC Trainerize ideas](https://ideas.abcfitness.com/forums/167887-coach-trainer-abc-trainerize/suggestions/16372018-adjust-the-app-to-support-dynamic-type-so-that-tex)
- **Dynamic Type: Hevy.** It supports dynamic type but isn't fully optimised: "a lot of text gets cut off".
  - Counterexample: one open-source gym app deliberately **disabled** Dynamic Type to keep designed sizes.
  - **Relevance to nütn:** a React/Capacitor web view does not inherit iOS Dynamic Type automatically. It needs `-apple-system-body` / `font: -apple-system-body` or a native bridge.
  - Sources: [codakuma, Dynamic Type](https://codakuma.com/dynamic-type/); [BOGA3 PR #348](https://github.com/Brotherhood-of-Ghisa/BOGA3/pull/348)
- **Colour-blind charts.** No named fitness-app user complaint was found. Design guidance says red/green series "can literally make the visualisation unusable", and that this is common in wellness status indicators.
  - Fix: never use colour alone (add icons or labels), and use blue/orange pairs.
  - Source: [Baseline, colourblind designer](https://baselinehq.com/blog/colourblindness-information-ui-design-red-green-problems-tips-tricks.html)
- **Apple Watch wheelchair mode.**
  - "In wheelchair mode you have to use a workout to get distance", which is annoying for whole-day distance such as train to office.
  - Users can see pushes but not miles.
  - Mixed walkers/rollers want automatic switching between steps and pushes.
  - Outdoor walks pushing someone else's wheelchair can't be tracked.
  - Some users got stuck in the mode.
  - Accuracy: a 2020 study (15 + 15 participants) found good accuracy for arm cycling and high-frequency pushing, poor for low-frequency and overground pushing. A 2023 review says research "remains scarce".
  - Fix in nütn: when HealthKit's wheelchair-use flag is on, show pushes and wheelchair workouts instead of steps, never show "steps 0 / goal missed", and allow manual distance.
  - Sources: [Apple Community 254556536](https://discussions.apple.com/thread/254556536); [Apple Community 250799209](https://discussions.apple.com/thread/250799209); [Apple Community 254513449](https://discussions.apple.com/thread/254513449); [ScienceDirect 2020](https://www.sciencedirect.com/science/article/pii/S1877065720300804); [PMC10577091](https://pmc.ncbi.nlm.nih.gov/articles/PMC10577091)
- **Adaptive/seated training.**
  - Wheel Fit App Store reviewer: "most of the workouts are locked behind an additional monthly subscription", and the app uses AI-generated images of wheelchair users rather than real people.
  - Wheel With Me reviewer: "it's hard finding an app that has a wheelchair option".
  - Its founders were "tired of having to piece together workouts from nondisabled trainers".
  - A 2025 paraplegia app pilot wants users to "turn floor exercises on or off" and substitute wheelchair-based alternatives.
  - Fix: an equipment/ability profile with "seated only", "no floor work", "upper-body only" and "one arm" toggles that filter the exercise database and program generator.
  - Sources: [Wheel Fit App Store](https://apps.apple.com/us/app/wheel-fit-wheelchair-fitness/id6464079536); [Wheel With Me Google Play](https://play.google.com/store/apps/details?id=breakthroughapps.com.wheelwithme&amp%3Bhl=en_US&amp%3Bgl=US); [PMC13261973](https://pmc.ncbi.nlm.nih.gov/articles/PMC13261973/)
- **Home fitness built for able-bodied users.** "Home-based fitness products … have been built for able-bodied users." — [ClinicalTrials NCT07189546](https://clinicaltrials.gov/study/NCT07189546)

### Inferences
- nütn has 481 `aria-` usages but **VoiceOver and Dynamic Type are untested** (round-1 inventory). The top three fixes:
  1. VoiceOver-adjustable set/rep/weight controls.
  2. Dynamic Type through `-apple-system-*` fonts plus layouts that reflow, not truncate.
  3. Chart text alternatives or audio graphs.
- One-handed use: there was no direct evidence, but it follows from mid-set logging. Bottom-anchored primary actions, large "complete set" targets and voice logging all help.
- A free, ad-free app with no paywalled accessibility features is a real differentiator, given the MFP barcode and Wheel Fit paywall complaints.

### Gaps
- No r/Blind or r/disability threads surfaced.
- No recent (2025–26) AppleVis reviews of Hevy, Strong, MFP or Cronometer could be read (blocked).
- No direct user complaint about one-handed use or colour-blind charts in a named fitness app was found.

---

## 6. Body image and neutral language (non-weight goals, gender-inclusive options)

### Takeaway
Beyond round 1's calorie-hiding finding:
- Hiding weight is now a mainstream setting: Whoop's "Hide Metrics" and Withings' "Eyes Closed Mode".
- ED-recovery apps go further with codes a clinician can unlock (BlindWeight).
- Period apps are criticised for pink, "girls" framing and gendered notifications that cause dysphoria. Users want optional gender/pronoun settings and the ability to switch off fertility/pregnancy modules.
- There is an opposing, politicised complaint about inclusive wording.

### Cited Findings
- **Hiding weight.**
  - **Whoop** "Hide Metrics" hides weight and lean body mass for members who "don't want to track it" (More > App Settings > Hide Metrics). — [Whoop support](https://support.whoop.com/s/article/Body-Composition-Weight-Trends?language=en_US)
  - **Withings** "Eyes Closed Mode" hides weight on the scale screen but still syncs it. — [Gizmodo](https://gizmodo.com/withings-body-smart-scale-hide-weight-mode-health-app-1850332724)
  - **BlindWeight** conceals weight behind a code a provider can read, built for ED recovery. — [BlindWeight App Store](https://apps.apple.com/cl/app/blind-weight/id6736515366)
  - Fix: a per-metric "hide" setting (weight, calories, body fat) that still records in the background, with an optional "share with my clinician" export.
- **Gendered period apps.**
  - Fitbit Community, nonbinary user: "Female Health" framing would deter people who get periods, since a trans man may not want a tool reminding him "the world assumes his body makes him female".
  - Users want to set gender or pronouns to avoid dysphoria-triggering notifications; Eve's "hey girl!" is the example.
  - A walkthrough of six apps found 4 targeting "women and girls" and none letting users specify gender.
  - Vice criticises "pink colour schemes and cutesy flower decorations".
  - Clue is praised as "the only app of its kind that isn't pink and excessively feminine".
  - Widespread: consistent across advocacy sources (anecdotal).
  - Fix: the module is named "Cycle", not "Women's health"; a neutral palette; no gendered push copy; and pregnancy/fertility modules can be switched off.
  - Sources: [Fitbit Community](https://community.fitbit.com/t5/Menstrual-Health-Tracking/Eesh-Female-Health-isn-t-very-Trans-friendly/td-p/2758108); [Red Moon Gang, May 2022](https://redmoongang.com/2022/05/13/how-inclusive-are-period-tracking-apps/); [Medium research walkthrough](https://medium.com/@tnimiana/exploring-the-affordances-of-menstrual-health-tracking-apps-for-trans-and-non-binary-menstruators-e4614eb1f6c8); [Vice](https://www.vice.com/en/article/qvp5yd/the-strange-sexism-of-period-apps); [Clue LGBTQIA+](https://helloclue.com/articles/lgbtqia/how-is-the-lgbtqia-community-using-clue)
- **Opposing complaint.** Flo drew backlash in 2023 for saying it was for "everyone with periods—regardless of gender". The coverage is one-sided. — [Fox News](https://www.foxnews.com/media/period-tracking-app-ignites-controversy-after-welcoming-transgender-women-with-periods.print)
- **Neutral food language.** The weight-loss app Simple is praised for not labelling meals "bad" or "good": "There's no body shaming and no food shaming." — [Garage Gym Reviews](https://www.garagegymreviews.com/best-weight-loss-app)
- **Older-women stereotype.** Reviewers say good apps should "keep increasing load while protecting joints, rather than quietly swapping strength work for stretching". This is vendor content. — [trainwell 50s](https://www.trainwell.net/blog/best-personal-trainers-women-in-50s)

### Inferences
- The least-contested path is user-controlled presentation with no imposed identity framing:
  - "Cycle" opt-in from settings rather than gated by sex;
  - neutral copy ("your cycle", "you");
  - per-metric hide toggles;
  - goal choices that include strength, energy, sleep, mood, mobility, "manage symptoms" and "return from injury", alongside weight.
- Keep the opt-in shown at onboarding for anyone who selects female sex, but don't auto-enable it.

### Gaps
- There is no 2024–26 survey quantifying demand for weight-hiding or gender-neutral cycle tracking. The evidence is anecdotal and from advocacy sources.

---

## Cross-section priority list for nütn (inferred from the above)

| # | Feature | Serves | Evidence strength |
|---|---|---|---|
| 1 | Local-first cycle data, no ad SDKs, real delete; say so on the App Store page | Cycle trackers (post-Dobbs) | Strong (Mozilla Jul 2026, Flo verdict Aug 2025) |
| 2 | Cycle modes: contraception picker, irregular/PCOS (no countdown), perimenopause (symptoms + HRT), postmenopause; HealthKit cycle read/write | Cycle and menopause users | Strong (Apple iOS 27, Oura, Whoop and Clue moved this way) |
| 3 | Medication/HRT schedule with reminders (extend supplements) | Peri/menopause, 50+, rehab | Moderate |
| 4 | Injury profile + per-set pain 0–10 + avoid list respected by generator + return-to-training ramp | Injured lifters | Moderate (Strong notes requests, Hevy paywalled Trainer) |
| 5 | Beginner mode: plain language (hide RPE/MEV jargon), short starter program, form media + common mistakes, attendance streaks for 4 weeks | Beginners | Moderate (gym-anxiety polls, adherence cohort, Fitbod form critique) |
| 6 | VoiceOver-adjustable set steppers, chart audio graphs/descriptions, Dynamic Type reflow | Blind/low-vision, 50+ | Moderate (AppleVis, Trainerize Feb 2026, Hevy truncation) |
| 7 | Ability filters: seated-only, no-floor, upper-body-only, joint-friendly; wheelchair-aware activity (pushes, no step shaming) | Wheelchair users, 50+, injured | Moderate |
| 8 | Voice logging of sets | Blind, one-handed, mid-set | Weak–moderate |
| 9 | Per-metric hide (weight/calories/body fat), neutral "Cycle" naming, non-weight goals | Body-image, trans/nonbinary | Moderate (Whoop/Withings precedent) |
