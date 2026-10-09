# Workout Logging UX: User Complaints & Feature Gaps (Strong, Hevy, JEFIT, Fitbod, Gravl, Boostcamp)

> **Method caveat (read first):** This sandbox's network proxy blocked direct fetches of reddit.com, apps.apple.com, trustpilot.com and most review blogs (HTTP 403 / DNS failures, 2026-10-08). Every finding below comes from web-search result extracts, not full-page reads. **No verbatim Reddit thread could be retrieved.** Most "Reddit sentiment" here is secondhand, via comparison blogs, and many of those blogs are written by **competing app makers** (Sensai, Cora Health, PR Path, RepReturn, Push/Pull, GymGod, Setgraph, Arvo, Dr. Muscle and others). Cora Health's "Reddit quotes" are self-described **paraphrases**, not real posts. App Store and Google Play complaints are individual reviews surfaced via aggregators (justuseapp, AppGrooves, mwm.ai, grand-screen), so each counts as a **single anecdote** unless marked otherwise. Dates are 2025–2026 unless flagged. Treat the "Inferences" sections as hypotheses.

## 1. Set logging speed and friction (taps, previous values, warm-ups, RPE, drop sets, supersets, unilateral, bodyweight, timed exercises)

### Takeaway
Strong's reputation for the fastest, least cluttered set entry is the main reason lifters stay on it. Recurring friction across apps comes from three sources. Advanced set types (drop sets, supersets, RPE/RIR) are missing, hard to find or paywalled. Mid-workout edits don't stick or don't flow back into the routine. Inconsistent set-completion behaviour is a problem in AI-driven apps (Fitbod, Gravl).

### Cited Findings
- A roundup of "200+ Reddit threads" calls Strong "the lifter's lifter app", with the "fastest logging", the r/weightroom default and "no fluff". A sample sentiment it gives is that Strong's UI is "just faster for actual gym sets". **Paraphrased by a competitor blog, not verbatim.** — [Cora Health](https://www.corahealth.app/blog/best-workout-tracker-reddit)
- An HN commenter (Strong user) says it offers "enough detail without cluttering the interface". **Single anecdote.** — [HN 39605923](https://news.ycombinator.com/item?id=39605923)
- **Hevy:** a Google Play reviewer complains there is no option to "save & update routine" after changing an exercise mid-workout, so mid-session changes don't flow back to the template. **Single anecdote.** — [Hevy Google Play via search extract](https://play.google.com/store/apps/details?id=com.hevy)
- **Hevy:** the warm-up set calculator is **Pro-only**. — [Sensai Hevy review 2026](https://www.sensai.fit/blog/hevy-review-2026); [aitoolsbakery Hevy review](https://aitoolsbakery.com/blog/hevy-review/)
- **Strong:** the plate calculator and warm-up calculator are PRO-only (listed among PRO unlocks). — [aitoolsbakery Strong review](https://aitoolsbakery.com/blog/strong-app-review/); [RepReturn Strong review](https://repreturn.com/strong-app-review/)
- **Hevy supersets have a discoverability problem.** Hevy's own FAQ answers a user who "could not find supersets": tap the three dots next to an exercise and choose the add-to-superset option. — [Hevy set types page](https://www.hevyapp.com/features/workout-set-types/)
- Users keep asking for advanced set types in other trackers. A Bevel feature request asks for supersets, drop sets, pause sets and myo-reps; the developer replied in Sept 2025 that supersets were coming. This shows the request pattern, not the six target apps. — [Bevel feedback](https://feedback.bevel.health/feature-requests/p/supersets-for-strength-tracking)
- A common implementation failure: drop sets and RPE "existed in the data model but had no way in from the UI". From an open-source tracker PR, Sept 2026. — [liftt PR #10](https://github.com/yjouini/liftt/pull/10)
- Trainerize users complain that the "most popular coaching app" still lacks RIR/RPE targets, and the feature board has several duplicate requests (adjacent app, not one of the six). — [ABC Trainerize ideas](https://ideas.abcfitness.com/forums/167887-coach-trainer-abc-trainerize/suggestions/45057220-adding-a-dropset-cluster-set-pnf-1-2-rep-reps)
- Some apps gate RPE/RIR logging behind paid tiers (example: Strive Pro). — [Strive blog](https://strive-workout.com/2026/04/03/best-gym-tracker-app/)
- **Fitbod (as a logger):** an App Store reviewer says some workouts let you log each set and others don't (estimated at "30–40% of exercises"). The app also jumps to the next exercise before the last set is logged, forcing them to exit and go back. **Single anecdote, date unclear (2018–2024 range).** — [Fitbod App Store reviews](https://apps.apple.com/us/app/fitbod-gym-fitness-planner/id1041517543?see-all=reviews)
- **Fitbod:** adding exercises or sets mid-workout is "hit or miss", and one edit reset completed exercises. The user now screenshots before each edit. **Single anecdote.** — [Fitbod App Store reviews](https://apps.apple.com/us/app/fitbod-gym-fitness-planner/id1041517543?see-all=reviews)
- **Fitbod:** a session was recorded as 299 minutes against an actual hour, and there is no easy way to edit the duration mid- or post-session. **Single anecdote.** — [Fitbod App Store reviews](https://apps.apple.com/us/app/fitbod-gym-fitness-planner/id1041517543?see-all=reviews)
- **Fitbod:** sometimes a set isn't counted and the workout is marked unfinished ("annoying but not a major flaw"). **Single anecdote.** — [Fitbod App Store reviews](https://apps.apple.com/gb/app/fitbod-workout-gym-planner/id1041517543?see-all=reviews)
- **Gravl:** suggested weights don't carry over between near-identical exercises. A barbell hip thrust at 200 lb led to a 50 lb suggestion for the dumbbell version, because the two are separate exercises. **Single anecdote.** — [Gravl App Store reviews](https://apps.apple.com/us/app/gravl-ai-personal-trainer/id6450921637?see-all=reviews)
- **JEFIT:** after a fresh start, the first set often didn't save, and the user had to exit and restart the exercise. **Single anecdote, undated.** — [AppGrooves JEFIT negative reviews](https://appgrooves.com/ios/449810000/jefit-workout-planner-gym-log/jefit-inc/negative)
- **JEFIT:** a forum post warns that version 11.35.3 was "a disaster". A commenter wrote: "It's all glitz with no functionality that works for those of us who actually work out… Stay away from the upgrade." **Undated, likely pre-2023, flag as older.** — [JEFIT Q&A](https://www.jefit.com/q&a/97270376/AJCrowley/i-m-getting-the-impression-from-latest-reviews-that-jefit-version-11353-(latest-rollout)-is-a-disaster-with-little-or-no)
- An adjacent openGym feature request asks for a "focus workout view — one set at a time", keeping unilateral L/R sets. This shows a demand for a less dense, single-set screen. — [openGym issue #221](https://github.com/DuarteSantos8/openGym/issues/221)

### Inferences
- The likely winning pattern is Strong-level speed (previous values pre-filled, one tap to complete a set) plus a first-class, discoverable way to add drop sets, supersets, RPE/RIR and warm-ups. Free plate and warm-up calculators would also undercut both Strong and Hevy, which paywall them.
- An edit made during a workout should offer to update the routine ("save & update routine").
- AI-driven loggers (Fitbod, Gravl) lose trust when their automation overrides manual logging (skipping ahead, not counting sets). Manual override must always win.

### Gaps
- No sourced complaints were found specifically about **unilateral (L/R) logging**, **assisted/bodyweight load entry** (e.g., negative weight for assisted pull-ups), or **timed/distance exercise** entry in these six apps. These are likely real gaps, but they are unverified here because Reddit was not reachable.
- No measured "taps per set" comparison was found.

## 2. Rest timers (auto-start, lock-screen notifications, Watch/Wear OS, Live Activities, bugs)

### Takeaway
Rest-timer complaints are mostly about reliability in the background or on the lock screen (especially Android) and about the timer interfering with media audio. Missing modern iOS surfaces (Live Activities) were a reason to leave Strong, though Strong's release notes claim it has since added them.

### Cited Findings
- **Hevy (Android):** a changelog says v1.30.30 fixed the rest-timer alarm not sounding in the background on some Android 14 devices. The app added in-settings instructions for Android 14 background timer issues. **Source is an APK mirror site; confirm against official notes.** — [Hevy APK changelog mirror](https://hevy-gym-log-workout-tracker.apk.dog/)
- **Hevy:** the Live Activity widget on iOS and Android shows the rest timer after a set is marked complete, with ±15 s and skip controls. Android requires lock-screen, badge and pop-up notification permissions; iOS requires "Allow Access When Locked". The setup takes several steps, so it is a likely support burden. — [Hevy Help: Live Activity](https://help.hevyapp.com/hc/en-us/articles/35649846517399-How-to-Use-Hevy-s-Live-Activity-on-iOS-and-Android)
- **Hevy:** a later App Store note says users "can now change the default rest timer" with shorter and longer options, which implies this was previously limited. — [Hevy App Store listing](https://apps.apple.com/cg/app/hevy-gym-tracker-workout-log/id1458862350)
- **Strong:** an HN commenter was looking for a replacement because Strong's developer "hasn't kept pace with newer iOS features like Live Activities". **Single anecdote; conflicts with** Strong's App Store release notes, which list Live Activity and Dynamic Island rest-timer support in v6.5.0. — [HN 48932784](https://news.ycombinator.com/item?id=48932784); [Strong App Store](https://apps.apple.com/us/app/strong-workout-tracker-gym-log/id464254577)
- **Strong (Watch):** release notes list fixes for "timer and workout updates during Live Sync" (6.4.3), finished Live Sync workouts not appearing on the phone, and watch crashes (6.4.1). **Older, likely 2021–2023.** — [Strong App Store](https://apps.apple.com/us/app/strong-workout-tracker-gym-log/id464254577)
- **Strong (Watch):** the help centre says you can't change all rest timers for an exercise from the watch, and calls the watch app "due for a significant redesign". **Possibly older.** — [Strong Help: Apple Watch](https://help.strongapp.io/article/224-workout-on-apple-watch)
- **Boostcamp:** after a redesign, the rest-timer sound can leave media volume lowered until the app is force-closed, which is "frustrating mid-set". **Single anecdote.** — [Boostcamp App Store reviews](https://apps.apple.com/us/app/boostcamp-workout-programs/id1529354455?see-all=reviews&platform=iphone)
- **Boostcamp:** workout progress on the lock screen "rarely shows up anymore", and the user relied on it for timing rest. **Single anecdote.** — [Boostcamp App Store reviews](https://apps.apple.com/us/app/boostcamp-workout-programs/id1529354455?see-all=reviews&platform=iphone)
- Lock-screen rest alerts failing is a cross-app problem (Freeletics iOS forum thread). — [Freeletics forum](https://forum.freeletics.com/t/rest-timer-notification/10557)

### Inferences
- A rest timer that auto-starts on set completion, shows on a Live Activity / Android ongoing notification, ducks rather than mutes audio, and alerts reliably while locked is table stakes. Getting it wrong is a top source of mid-set frustration.
- A guided permission check ("your timer won't alert while locked; fix it") would reduce Android 14+ failures.

### Gaps
- I could not confirm whether Hevy has a native Wear OS app or what its Wear OS complaints are.
- No evidence was found on Strong Wear OS.

## 3. Exercise library (missing exercises, custom exercises, duplicates, machine variations, video demos)

### Takeaway
Library complaints centre on caps on custom exercises (Hevy free: 7), demo videos locked behind paywalls (JEFIT), machine variants treated as unrelated exercises (Gravl), and custom exercises not appearing in search (Boostcamp).

### Cited Findings
- **Hevy free:** custom exercises are capped at 7 (unlimited on Pro). — [Sensai Hevy review 2026](https://www.sensai.fit/blog/hevy-review-2026); [Push/Pull vs Hevy](https://push-pull.app/blog/push-pull-vs-hevy)
- **Hevy:** library of about 400 exercises, smaller than Fitbod or JEFIT (competitor blog claim). — [Sensai 4-way comparison](https://www.sensai.fit/blog/hevy-vs-strong-vs-fitbod-vs-jefit)
- **Hevy:** has a help article on resetting data for "Duplicate Exercise / Routines and Manual Deletion", which suggests duplicates (e.g., after imports) are common enough to document. — [Hevy Help: Reset Data](https://help.hevyapp.com/hc/en-us/articles/35119576252951-Reset-Data-Duplicate-Exercise-Routines-and-Manual-Deletion)
- **JEFIT free:** you can browse exercises but can't watch video instructions, and the free tier is ad-supported. A critic says "a recent update seems to have lowered the quality of the free version". **Competitor source (Dr. Muscle), undated.** — [Dr. Muscle JEFIT review](https://dr-muscle.com/jefit-review-alternative/)
- **Boostcamp:** some custom exercises don't show up in exercise search on some days. **Single anecdote.** — [Boostcamp App Store reviews](https://apps.apple.com/us/app/boostcamp-workout-programs/id1529354455?see-all=reviews&platform=iphone)
- **Gravl:** barbell and dumbbell hip thrusts are separate exercises with no shared strength estimate. The AI generator also doesn't offer the machines a user wants, even with variety turned on. **Single anecdotes.** — [Gravl App Store reviews](https://apps.apple.com/us/app/gravl-ai-personal-trainer/id6450921637?see-all=reviews)
- **Fitbod:** a Medium critique says the complaints in reviews under five stars centre on "lack of tailoring, such as being unable to add an exercise". **Older.** — [Medium Fitbod critique](https://medium.com/product-x-management/app-critique-fitbod-b78db0b8e61e)
- **Gravl:** a changelog acknowledges AI photo-imports not matching existing exercises (an exercise-matching problem). — [Gravl App Store](https://apps.apple.com/us/app/gravl-ai-personal-trainer/id6450921637)

### Inferences
- An exercise "family" or variant model (barbell, dumbbell, machine and cable versions of a movement linked for e1RM and suggestions) and unlimited free custom exercises are clear points of difference.
- Fuzzy matching on import is needed to avoid creating duplicates.

### Gaps
- No direct sourced list of "most-requested missing exercises" was found.
- No machine-brand variation complaints were sourced.

## 4. Data and history (charts, PRs/e1RM, volume per muscle, search, export/import, data loss, sync, offline)

### Takeaway
Data portability is now expected, and Strong→Hevy CSV import is a documented, well-trodden switching path. The serious complaints are data loss: JEFIT cloud sync failures, Gravl wiping data, and Boostcamp web/app edits reverting. Free tiers that truncate history (Hevy: 3 months of charts) and cloud dependence in low-signal gyms are also recurring complaints.

### Cited Findings
- **Hevy free:** charts and graphs are limited to 3 months of history; Pro unlocks all-time. — [Sensai Hevy review 2026](https://www.sensai.fit/blog/hevy-review-2026)
- **Strong:** "all charts" and body measurements are PRO unlocks. — [aitoolsbakery Strong review](https://aitoolsbakery.com/blog/strong-app-review/)
- **Hevy imports Strong CSV natively:** Settings > Export & Import Data > Import Strong CSV. Strong must be set to **English** and the weights to **kg** before exporting. Hevy only supports unedited files, and **routines do not transfer** and must be rebuilt by hand. — [Hevy Help: Import Strong CSV](https://help.hevyapp.com/hc/en-us/articles/38001424401943-How-to-Import-Strong-App-CSV-Files-and-Export-Your-Data-in-Hevy); [Hevy Help: Log previous workouts & import CSV](https://help.hevyapp.com/hc/en-us/articles/35687878672663-Tutorial-Log-Previous-Workouts-and-Import-CSV)
- A community CLI, **strong2hevy**, exists because users wanted routines plus history, explicit exercise mapping and duplicate-safe reruns via the Hevy API. — [GitHub strong2hevy](https://github.com/criccomini/strong2hevy)
- Competing and open-source trackers now ship "import Strong/Hevy CSV" as a launch feature (e.g., HyperFit PR "bring your history", the jim PR #293, Arvo, Reps). — [HyperFit PR #149](https://github.com/harshssd/HyperFit/pull/149); [jim PR #293](https://github.com/traxon99/jim/pull/293); [Arvo blog](https://arvo.guru/blog/hevy-to-arvo-csv-import); [Reps](https://trackreps.com/transfer-workout-history/)
- **Hevy:** CSV export is free; API access is a paid-tier feature (HN commenter). — [HN 42528329](https://news.ycombinator.com/item?id=42528329)
- **Hevy:** "once a workout is deleted, it cannot be recovered by our team". Support also warns that reinstalling or clearing app data can delete locally stored, unsynced data. — [Hevy Help: Apple Watch sync troubleshooting](https://help.hevyapp.com/hc/en-us/articles/33996260919703-Hevy-Apple-Watch-Sync-Issues-Step-by-Step-Troubleshooting-Guide); [Hevy Help: Health Connect](https://help.hevyapp.com/hc/en-us/articles/36957110114455-Health-Connect-Not-Receiving-Hevy-Data-Here-s-How-to-Fix-It)
- **Hevy:** added a warning when device storage is low before or during a workout "to help ensure your data is never lost". **From an APK mirror changelog.** — [Hevy APK changelog mirror](https://hevy-gym-log-workout-tracker.apk.dog/)
- **Hevy:** "requires an internet connection for many features, which can frustrate lifters who train in low-signal gyms"; data lives on its servers. **Competitor blog claim, unverified.** — [Setgraph Hevy vs Strong](https://setgraph.app/ai-blog/hevy-vs-strong-app-comparison-2026)
- **Strong:** cross-device sync is "limited or may require premium/cloud" (competitor blog, low confidence). — [GymGod Strong vs Hevy](https://gymgod.app/blog/strong-vs-hevy)
- **JEFIT:** a review titled "deleted all my logs" says logs stopped reaching the online account and a login problem blocked recovery, losing about 70 sessions. The aggregator's top problems include "logs haven't been syncing with online account since April". **Aggregator, single anecdote, date unclear.** — [justuseapp JEFIT reviews](https://justuseapp.com/en/app/449810000/jefit-workout-planner-gym-log/reviews); [justuseapp JEFIT problems](https://justuseapp.com/en/app/449810000/jefit-workout-planner-gym-log/problems)
- **JEFIT:** in a developer reply on the App Store, JEFIT attributes crashes and missing logs to how workouts are saved and resumed after interruptions. — [JEFIT App Store reviews](https://apps.apple.com/us/app/jefit-workout-plan-gym-tracker/id449810000?see-all=reviews)
- **Gravl:** a user had to clear app data to fix a freeze and "lost all their data". Another reports "all my saved workouts in the library is gone after an update", and the developer apologised. The changelog acknowledges "workouts failing to save". **Single anecdotes.** — [Gravl App Store reviews](https://apps.apple.com/us/app/gravl-ai-personal-trainer/id6450921637?see-all=reviews); [mwm.ai Gravl](https://mwm.ai/apps/personal-trainer-gravl/6450921637)
- **Boostcamp:** a long-time user says data doesn't sync well between the web and mobile versions, losing data. Program edits made on the web revert when the app is opened, and the editor shows different numbers from the viewer. **Single anecdote.** — [Boostcamp App Store reviews](https://apps.apple.com/us/app/boostcamp-workout-programs/id1529354455?see-all=reviews&platform=iphone)
- **Fitbod:** unstructured per-exercise notes are "effectively invisible" when reviewing history, and the competitor raises concerns about data access after cancelling. **Biased (paper-logbook vendor).** — [Forge Logbooks](https://www.forgelogbooks.com/blog/fitbod-vs-workout-logbook)
- **Offline:** offline-first indie trackers market "basement gym, zero signal, no problem" (Rakoon), no account required, CSV export. This positions offline use as an unmet need. Trainerize users have requested offline logging for years. — [Rakoon Product Hunt](https://www.producthunt.com/posts/rakoon); [Trainerize: offline option](https://ideas.abcfitness.com/forums/167887-coach-trainer-abc-trainerize/suggestions/6623779-offline-option-for-the-app)
- HN Show-HN builders cite local-first, no-login storage as their reason for building new trackers. — [HN 48932784](https://news.ycombinator.com/item?id=48932784); [HN 42526769](https://news.ycombinator.com/item?id=42526769)

### Inferences
- Local-first storage with background sync, a visible "saved locally / synced" indicator, crash-safe autosave of the in-progress session, a deleted-workout bin, and Strong/Hevy CSV import that includes routines would address the most damaging complaints (losing data) and remove the main switching cost.

### Gaps
- No sourced complaints were found specifically about **e1RM formula accuracy**, **per-muscle volume** charts, or **history search** in these apps.
- Hevy's per-muscle "set count" features weren't evaluated.

## 5. Apple Watch / wearables, heart rate, Apple Health writes

### Takeaway
Watch logging is the most fragile area for every app. Hevy publishes a troubleshooting guide for "missing workout data / unable to save" on the watch. Fitbod and Gravl users report watch-phone desyncs that erase progress. JEFIT writes inflated workout durations to Apple Health.

### Cited Findings
- **Hevy:** its own guide says repeated freezing, missing workout data, or being unable to save a workout from Apple Watch should not be treated as a normal delay. — [Hevy Help: Apple Watch sync issues](https://help.hevyapp.com/hc/en-us/articles/33996260919703-Hevy-Apple-Watch-Sync-Issues-Step-by-Step-Troubleshooting-Guide)
- **Hevy vs Strong (Watch):** a competitor comparison rates Hevy's Watch app as "generally reliable" (with periods where it "fails to sync properly", fixed in updates) and Strong's as "sometimes inconsistent". **Single author opinion.** — [PonteFuerte comparison](https://www.pontefuerteai.com/blog/hevy-vs-strong-vs-pontefuerteai-workout-app-comparison)
- **Hevy → Apple Health:** a one-way export of strength workouts and lean body mass, which must be switched on, and **no backfill** of earlier workouts. — [Constant blog](https://trainconstant.com/blog/hevy-apple-health)
- **Hevy:** wearable integration is "logging-only" (it doesn't adapt to recovery data). — [Sensai 4-way comparison](https://www.sensai.fit/blog/hevy-vs-strong-vs-fitbod-vs-jefit); [RepReturn Hevy review](https://repreturn.com/hevy-app-review/)
- **Fitbod:** a workout logged on the watch never appeared on the phone, and the watch then fell back to the phone app and erased progress. Workouts occasionally don't sync to Apple Health. **Single anecdotes.** — [Fitbod App Store reviews](https://apps.apple.com/us/app/fitbod-gym-fitness-planner/id1041517543?see-all=reviews)
- **Gravl:** Apple Watch sync is a recurring issue in the aggregator's summary, and the watch loses connection to the iPhone mid-session. — [grand-screen Gravl reviews](https://grand-screen.com/apps/gravl-personal-trainer/reviews/); [mwm.ai Gravl](https://mwm.ai/apps/personal-trainer-gravl/6450921637)
- **JEFIT:** workouts sync to Apple Health with inflated durations because the end isn't registered. Health sync must be selected by hand after every workout, with no resync option. A forgotten "finish" logs everything since the app was last opened. **Single anecdotes.** — [AppGrooves JEFIT](https://appgrooves.com/ios/449810000/jefit-workout-planner-gym-log/jefit-inc/negative); [justuseapp JEFIT reviews](https://justuseapp.com/en/app/449810000/jefit-workout-planner-gym-log/reviews)
- **Strong (Watch):** the help centre admits limited watch editing and a pending redesign; past release notes fix Live Sync bugs and watch crashes. **Older.** — [Strong Help](https://help.strongapp.io/article/224-workout-on-apple-watch); [Strong App Store](https://apps.apple.com/us/app/strong-workout-tracker-gym-log/id464254577)
- A Garmin user (HN) says watch-based gym logging can't handle mid-workout changes such as adding sets or swapping equipment. — [HN 42262232](https://news.ycombinator.com/item?id=42262232)

### Inferences
- An auto-end or "did you forget to finish?" prompt with duration correction would fix the inflated-duration complaint common to Fitbod and JEFIT.
- Treat the phone as the source of truth with conflict-free merges from the watch. Never let the watch "fall back" and overwrite phone progress.

### Gaps
- No sourced heart-rate-specific complaints for Hevy or Strong were found.
- No Wear OS or Garmin native app complaints were found for these apps.

## 6. Paywalls, price changes, and social features

### Takeaway
Both market leaders now cap free routines (Strong 3, Hevy 4). Hevy also caps custom exercises (7) and chart history (3 months). Gravl's hard 3-workout paywall, revealed only after onboarding, draws anger. Hevy's social feed is a known polarising point: users can make workouts private, but reportedly can't remove the Discover feed.

### Cited Findings
- **Strong free:** unlimited logging but **3 custom routines**; the paywall starts at routine #4. **PRO:** ~$4.99/mo or $29.99/yr in the US (sources vary from $3.99–4.99/mo and $23.99–29.99/yr), lifetime $79.99–$99.99. One outlier page wrongly claims "3 workouts". — [RepReturn Strong](https://repreturn.com/strong-app-review/); [aitoolsbakery Strong](https://aitoolsbakery.com/blog/strong-app-review/); [Sensai Hevy vs Strong](https://www.sensai.fit/blog/hevy-vs-strong-2026); [App Pricing Lab Strong IAPs](https://apppricinglab.com/iap/apple/464254577)
- **Hevy free:** 4 routines, 7 custom exercises, 3 months of graphs, weight and waist only for measurements. Warm-up calculator and Hevy Trainer are Pro-only. **Pro:** $2.99/mo, $23.99/yr, $74.99 lifetime. The App Store also lists a $3.99 monthly SKU, so price reports conflict, and one review cites $5.99/mo and $34.99/yr. A tracker shows no Pro price change as of Sept 30, 2026. — [Sensai Hevy review](https://www.sensai.fit/blog/hevy-review-2026); [getpulsesignal Hevy price log](https://getpulsesignal.com/changes/hevy); [Hevy pricing](https://hevy.com/pricing)
- **Conflict:** Hevy's App Store copy says "Create an unlimited amount of routines", while its help centre caps free at 4. — [Sensai Hevy review](https://www.sensai.fit/blog/hevy-review-2026)
- **Strong:** I found no confirmed reporting of a Strong price hike or user backlash. A 2025 "pricing model changes" article looks like unsourced SEO content. — [App Pricing Lab](https://apppricinglab.com/iap/apple/464254577)
- **Strong:** "no AI roadmap… the pace of new features has clearly slowed while competitors ship". **Competitor blog opinion.** This and the HN Live Activities complaint form a "stagnation" switching narrative. — [PR Path Strong vs Hevy](https://prpath.app/blog/strong-vs-hevy-2026.html); [HN 48932784](https://news.ycombinator.com/item?id=48932784)
- **JEFIT:** the free tier is ad-supported with paywalled videos; the paid tier is listed at $69.99/yr; privacy labels include cross-app tracking data. — [JEFIT App Store](https://apps.apple.com/us/app/workout-tracker-gym-log-exercise-trainer-by-jefit/id449810000); [Dr. Muscle JEFIT review](https://dr-muscle.com/jefit-review-alternative/)
- **Gravl:** most users can log 3 workouts before a paid plan is required. Users complain they discovered the limit only after 10–15 minutes of onboarding, and that "free trial doesn't even let you use it for a week". — [Gravl App Store reviews](https://apps.apple.com/us/app/gravl-ai-personal-trainer/id6450921637?see-all=reviews); [mwm.ai Gravl](https://mwm.ai/apps/personal-trainer-gravl/6450921637)
- **Boostcamp:** users complain of a "growing number of features moving behind a paywall" and pricing they consider too high (review-summary level). — [mwm.ai Boostcamp](https://mwm.ai/apps/boostcamp-gym-workout-fitness/1529354455)
- **Hevy social feed:** users can set a private profile, private default workout visibility, hidden suggested users and no Live PR notifications. A third-party review quotes Hevy's help centre: the Discover feed stays on the Home screen and "there is currently no way to remove it". **Not confirmed on Hevy's page.** — [Hevy Help: privacy](https://help.hevyapp.com/hc/en-us/articles/34461853165079-How-to-keep-my-information-private-Account-Single-Private-Workout-Remove-Social-Media-Features); [aitoolsbakery Hevy review](https://aitoolsbakery.com/blog/hevy-review/)
- Feed sentiment is split: "some users love the community feed; others find it distracting and unnecessary for a pure weightlifting app". Hevy also "pushes its premium version", which some find cluttering. — [Setgraph comparison](https://setgraph.app/ai-blog/hevy-vs-strong-app-comparison-2026)
- Garage Gym Reviews recommends Hevy specifically "if community is a priority" for its social feed. — [Garage Gym Reviews](https://www.garagegymreviews.com/best-weightlifting-app)

### Inferences
- A generous free logger with no routine cap, free plate and warm-up calculators, full history, and social features that are fully optional (removable) targets the specific annoyances in both leaders.
- Being clear about the paywall up front (before onboarding) avoids Gravl-style backlash.

### Gaps
- No primary source was found for a Strong or Hevy price increase. A widely discussed "Hevy raised prices" event, if one happened, could not be verified.
- Reddit's actual sentiment about the Hevy feed could not be retrieved.

## 7. Crashes and bugs that lose a workout mid-session

### Takeaway
Mid-session losses usually come from three things: the OS killing the app on screen lock or app switch (Boostcamp, JEFIT), freezes that require a force-quit (Boostcamp completion screen, Gravl, JEFIT), and buggy updates. Every app here has at least one credible report.

### Cited Findings
- **Boostcamp:** the app sometimes resets during a workout when the screen locks and loses the session (seen twice). **2022, older.** — [Boostcamp App Store reviews](https://apps.apple.com/us/app/boostcamp-workout-programs/id1529354455?see-all=reviews&platform=iphone)
- **Boostcamp:** locks up on the workout-completion screens and needs a force-close; the developer confirmed a bug. The app also reloads when switching apps on Android. A review summary cites recent crashes, slow loading, and history and program-editing bugs. — [Boostcamp App Store reviews](https://apps.apple.com/us/app/boostcamp-workout-programs/id1529354455?see-all=reviews&platform=iphone); [mwm.ai Boostcamp](https://mwm.ai/apps/boostcamp-gym-workout-fitness/1529354455)
- **Gravl:** freezes completely if you exit the app mid-use and stays locked even after a phone restart. — [Gravl App Store reviews](https://apps.apple.com/us/app/gravl-ai-personal-trainer/id6450921637?see-all=reviews)
- **JEFIT:** the workout screen froze and kicked the user out, and support emails went unanswered. User crash reports are dated as late as Sept 24, 2025. Release notes for v15.1.0 fix crashes on deleting an exercise and on opening the app. — [AppGrooves JEFIT](https://appgrooves.com/ios/449810000/jefit-workout-planner-gym-log/jefit-inc/negative); [justuseapp JEFIT problems](https://justuseapp.com/en/app/449810000/jefit-workout-planner-gym-log/problems); [JEFIT App Store](https://apps.apple.com/us/app/workout-tracker-gym-log-exercise-trainer-by-jefit/id449810000)
- **Fitbod:** crashed when creating or updating a workout and when logging a set mid-workout. **Single anecdote.** — [Fitbod App Store reviews](https://apps.apple.com/us/app/fitbod-gym-fitness-planner/id1041517543?see-all=reviews)
- **Hevy:** I found no reports of a 2025–26 update wiping workouts. Hevy ships every 1–2 weeks and did a "native redesign" in July 2026, a risk point but with no evidence of loss. Its minor bugs include the measurement-date picker rolling the year backwards (Google Play). — [Hevy community updates](https://www.hevyapp.com/community-updates/); [Hevy Google Play](https://play.google.com/store/apps/details?id=com.hevy)

### Inferences
- Persist every set to disk the moment it is ticked, restore the in-progress workout after a kill or crash, and never block "finish" on a network call. These are the main defences against the most-hated failure mode.

### Gaps
- No Strong mid-session data-loss reports were surfaced in 2023–26 (possibly because Strong is stable, or because Reddit was unreachable).

## 8. What makes users switch (e.g., Strong → Hevy) and recurring "I wish it would…" requests

### Takeaway
Users move from Strong to Hevy for a more generous free tier (4 routines vs 3, free CSV export), social and program-sharing features, faster feature shipping and modern iOS surfaces, helped by Hevy's native Strong CSV import. Users stay on, or return to, Strong for speed and lack of clutter. Users leave AI apps (Fitbod, Gravl) for plain loggers when the automation fights manual control or loses data.

### Cited Findings
- Reddit sentiment (secondhand): Hevy is preferred if you want to follow others' programs or care about the social feed; Strong is preferred for fastest logging and a private log. — [Cora Health](https://www.corahealth.app/blog/best-workout-tracker-reddit); [PonteFuerte](https://www.pontefuerteai.com/blog/hevy-vs-strong-vs-pontefuerteai-workout-app-comparison)
- Hevy wins on "a more generous free tier" and social features; Strong wins as a "minimal private lifting log". — [PonteFuerte](https://www.pontefuerteai.com/blog/hevy-vs-strong-vs-pontefuerteai-workout-app-comparison); [Sensai Hevy vs Strong](https://www.sensai.fit/blog/hevy-vs-strong-2026)
- Switching is easier because Hevy imports Strong CSVs and many guides cover it (Hevy help, YouTube, strong2hevy), but routines don't migrate. — [Hevy Help](https://help.hevyapp.com/hc/en-us/articles/38001424401943-How-to-Import-Strong-App-CSV-Files-and-Export-Your-Data-in-Hevy); [YouTube walkthrough](https://www.youtube.com/watch?v=9USuU0KG2so); [ayjc migration blog](https://blog.ayjc.net/posts/migrate-strong-hevy-app/)
- Strong leaver (HN): looking for a replacement because Strong "hasn't kept pace" with iOS features. Another Strong fan would switch if something "filled the gap" for the parts of their training it misses. — [HN 48932784](https://news.ycombinator.com/item?id=48932784); [HN 27503597](https://news.ycombinator.com/item?id=27503597) (older, 2021)
- Hevy user wishes (HN): Hevy Trainer "keeps suggesting the same set over and over" and they want more guidance; another wants coverage beyond strength (other training types). — [HN 48932784](https://news.ycombinator.com/item?id=48932784); [HN 42262232](https://news.ycombinator.com/item?id=42262232)
- Gravl: a long-term user says it "became just like every other workout app"; another says the AI mode is "terrible" but the standard PPL splits work well. This suggests users fall back to plain logging. — [Gravl App Store reviews](https://apps.apple.com/us/app/gravl-ai-personal-trainer/id6450921637?see-all=reviews)
- Hevy limitation: it is a logger, not a coach. It doesn't write programs, adjust loads for recovery, or use wearable data. — [RepReturn Hevy](https://repreturn.com/hevy-app-review/)
- Strong limitation: no built-in programming, coaching or adaptation. — [RepReturn Strong](https://repreturn.com/strong-app-review/); [Setgraph](https://setgraph.app/ai-blog/hevy-vs-strong-app-comparison-2026)
- **Recurring "I wish it would…" requests (consolidated from the findings above):**
  - Save mid-workout changes back to the routine — [Hevy Play review](https://play.google.com/store/apps/details?id=com.hevy).
  - Easy, discoverable supersets, drop sets, myo-reps and RPE/RIR — [Hevy FAQ](https://www.hevyapp.com/features/workout-set-types/); [Bevel](https://feedback.bevel.health/feature-requests/p/supersets-for-strength-tracking).
  - Edit workout duration and auto-detect a forgotten finish — [Fitbod reviews](https://apps.apple.com/us/app/fitbod-gym-fitness-planner/id1041517543?see-all=reviews); [JEFIT reviews](https://justuseapp.com/en/app/449810000/jefit-workout-planner-gym-log/reviews).
  - Reliable lock-screen rest timer and Live Activity — [HN](https://news.ycombinator.com/item?id=48932784); [Boostcamp reviews](https://apps.apple.com/us/app/boostcamp-workout-programs/id1529354455?see-all=reviews&platform=iphone).
  - Offline and local-first logging — [Rakoon](https://www.producthunt.com/posts/rakoon); [Trainerize ideas](https://ideas.abcfitness.com/forums/167887-coach-trainer-abc-trainerize/suggestions/6595234-allow-workout-stats-to-be-tracked-without-a-wirele).
  - Linked exercise variants for weight suggestions — [Gravl reviews](https://apps.apple.com/us/app/gravl-ai-personal-trainer/id6450921637?see-all=reviews).
  - A one-set-at-a-time focus view — [openGym #221](https://github.com/DuarteSantos8/openGym/issues/221).
  - Smarter "what next" progression guidance in the logger — [HN](https://news.ycombinator.com/item?id=48932784).
  - Routines included in Strong→Hevy migration — [strong2hevy](https://github.com/criccomini/strong2hevy).
  - The option to remove the social feed — [aitoolsbakery](https://aitoolsbakery.com/blog/hevy-review/).

### Inferences
- The switching pattern suggests one opening: a logger as fast as Strong, at least as generous as Hevy's free tier, offline-first, with lightweight progression guidance and one-tap import of Strong/Hevy history *and routines*. That combination would target users of both leaders.
- Rating context: Strong scores ~4.9 on iOS (~109k ratings) and 4.3 on Google Play; Hevy ~4.9 (~192k); JEFIT ~4.8 (~47k); Boostcamp ~4.8 (~9.1k). The complaints come from a vocal minority, but they cluster on data loss and paywalls. — [aitoolsbakery Strong](https://aitoolsbakery.com/blog/strong-app-review/); [Hevy pricing](https://hevy.com/pricing); [JEFIT App Store](https://apps.apple.com/us/app/jefit-workout-plan-gym-tracker/id449810000?see-all=reviews); [Garage Gym Reviews Boostcamp](https://www.garagegymreviews.com/boostcamp-review)

### Gaps
- No verbatim Reddit switching threads (r/HevyApp, r/StrongApp, r/weightroom, r/fitness) could be retrieved; the proxy blocked reddit.com. Real switch reasons and their relative frequency are unquantified.
- No Trustpilot data was retrievable.
- Stronger by Science and BarBend logger comparisons were not retrieved.
