# Complaints and feature requests: weight/body-composition, progress photos, fasting, hydration, meal planning and grocery apps (round 2)

> **Method and source caveats (read first).** Research date 2026-10-09. As in round 1, reddit.com, apps.apple.com full review pages, trustpilot.com and several blogs (unstar.app, allthingsn.com) could not be fetched (DNS failure or proxy block). **Every user quote below came secondhand, through web-search result extracts of the cited page.** Quotes are as the extract gave them, but I could not read the surrounding thread or review. **No first-hand Reddit thread was retrieved.** Reddit sentiment is therefore missing, not absent.
> - **Source tags:** **[aggregator]** marks justuseapp, mwm.ai and similar sites that reproduce App Store or Play reviews. **[competitor blog]** marks a page run by a rival app (MealThinker, Plan to Eat, unstar, GainFrame, Body Tracker, Nutrola, NutriScan, Pann, Swoodie). **[vendor]** marks the app maker's own page. **[single anecdote]** marks a complaint that rests on one review.
> - **Spread ratings** (HIGH / MEDIUM / LOW / SINGLE) are my judgment, based on how many independent source types repeat a complaint. They are not counts.
> - **Round 1 already covered** adaptive TDEE, batch-cook recipes, recipe URL import, grams-first units and hide-numbers. This file deliberately looks elsewhere.
> - **The biggest new finding is structural:** three meal-planning apps closed or are closing. **Yummly** shut in Dec 2024, **PlateJoy** on 1 Jul 2025 and **Mealime** on **21 Oct 2026**, which is 12 days after this research date. None offered a usable bulk export. This is a live acquisition window and a strong "own your data" argument for nütn.

## 1. Weight and body-composition apps (Happy Scale, Libra, Withings Health Mate, Renpho, Eufy, FitDays, Arboleaf, MacroFactor trend)

### Takeaway
Trend smoothing, goal-date forecasts and milestones are now the expected core of a weight app; Happy Scale is the reference users praise. The new complaints are not about the maths. They are about **data custody**:
- **Data loss:** data is lost on a device upgrade, and accounts split or orphan data.
- **Scale-app sync:** scale apps silently stop writing to Apple Health and give no export.
- **Forced accounts:** scale apps require an account even though the scale is Bluetooth-only.
- **Discontinued apps:** apps are discontinued and take the data with them.

Smaller gaps are body fat from BIA scales presented as precise, menstrual-cycle water retention not modelled, and "progress" wording when someone is already below goal.

### Cited Findings
**Data loss and data custody (new angle, MEDIUM–HIGH)**
- **Happy Scale: data wiped on device upgrade.**
  - **Complaint:** A reviewer who upgraded their phone in Nov 2025 found the data "gone with no way to retrieve it." Buying the paid version did not recover it, and the developer's suggestions were "none of which were applicable." The reviewer still praised the developer's responsiveness.
  - **Source:** [App Store reviews](https://apps.apple.com/us/app/id532430574?see-all=reviews), via search extract. [single anecdote, 2025]
  - **Fix:** automatic on-device and iCloud backup, plus restore that is verified on reinstall or new device. Add a visible "last backed up" stamp and one-tap CSV/JSON export.
- **Happy Scale: iPhone–iPad sync through Dropbox.**
  - **Complaint:** sync "doesn't work very well," so the user is "double-entering data in both devices."
  - **Source:** [mwm.ai](https://mwm.ai/apps/happy-scale/532430574). [aggregator, single anecdote, 2026]
  - **Fix:** native CloudKit or HealthKit-backed sync.
- **Eufy Life: Apple Health sync stopped silently, and no export.**
  - **Complaint:** sync worked "for the first couple of months… at one point it stopped recording the measurements in Apple health." Support called it "a backend issue" and said to wait. The same reviewer: "they do not allow you to reclaim your data."
  - **Source:** [justuseapp](https://justuseapp.com/en/app/1153481724/eufylife/reviews). [aggregator, single anecdote]
  - **Fix:** a scale-agnostic weight log that reads weight from HealthKit, so any scale works, plus a sync-health indicator ("last reading from Health: 2 days ago").
- **Eufy Life: account forced for a Bluetooth scale.**
  - **Complaint:** the scale "was advertised as using just Bluetooth and not needing a remote server connection," but the app would not get past the opening screen without signing up. Sign in with Apple was not offered.
  - **Source:** [justuseapp](https://justuseapp.com/en/app/1153481724/eufylife/reviews). [aggregator, single anecdote]
  - **Vendor confirmation:** Eufy's own listing says "A EufyLife account is needed to use this app" ([App Store, vendor](https://apps.apple.com/us/app/eufy-life/id1153481724)).
  - **Fix:** no-account local-first use (nütn's model).
- **Eufy Life: years of data stranded after adding a second scale.**
  - **Complaint:** "years of data was viewable in the app but not in Apple health… only one data point."
  - **Source:** [justuseapp](https://justuseapp.com/en/app/1153481724/eufylife/reviews). [single anecdote]
  - **Vendor limit:** Eufy support says "only the data under the main user can be synced," and each user needs their own account ([Eufy support, vendor](https://support.nz.eufy.com/support/solutions/articles/154000242614-is-it-possible-to-sync-data-with-other-apps-like-apple-health-google-fit-fitbit-etc-)).
  - **Fix:** a "backfill from Apple Health" import that de-duplicates history on first run.
- **FitDays: multiple users share one account.**
  - **Complaint:** for multiple users "you have to have them under the same account which means it keeps everyone's information in the same account."
  - **Source:** [App Store, FitDays](https://apps.apple.com/us/app/fitdays/id1434527961). [single anecdote]
  - **Fix:** per-person attribution of readings, and ignoring weights that don't match the user. HealthKit carries a source device, so out-of-range readings can be flagged as "not you?"
- **Renpho: two apps and lost days.**
  - **Vendor FAQ:** Renpho runs a "Renpho Health" app and an "Outdated Version" app. Its FAQ says "Renpho Health App registered accounts cannot be logged in on Renpho app," and "if you logout of the Renpho Health app, the data will not sync with Google Fit" ([Renpho FAQ, vendor](https://renpho.com/pages/faq-for-renpho-health-app)).
  - **Complaint:** one user's app "stopped syncing with Google Fit out of nowhere," and days were missing even after the fix, so they had to re-enter weights manually ([Play Store listing, via search extract](https://play.google.com/store/apps/details?id=com.qingniu.renpho&hl=en_US)). [single anecdote]
  - **Fix:** a gap detector ("no weigh-ins for 4 days, check scale sync") and fast manual entry.
- **Withings Health Mate: account and data sharing now required.**
  - **Complaint (2025):** Withings "now requires the user to create an account and to share health data with them," and an update meant the app was "no longer recognizing a device I've been using for over a year" ([justuseapp](https://justuseapp.com/en/app/542701020/withings-health-mate/reviews)). [aggregator, 2025]
  - **Complaint (about Apr 2026):** a community post says the app was replaced by "a new withings app" whose home page shows irrelevant items such as menstrual cycles and adding a child ([Withings community](https://support.withings.com/hc/en-us/community/posts/45404282283537-App-update)). [single anecdote]
  - **Complaint (2022 redesign):** the redesign removed "trends with the granularity of daily data." Users asked whether Withings was "dumbing down Health Mate as a prelude for shifting features to a subscription" ([Withings community](https://support.withings.com/hc/en-us/community/posts/11251967828497)). [older, MEDIUM: a thread]
  - **Paywall context:** Withings Intelligence is paywalled at $9.95/month or $99.50/year ([Notebookcheck](https://www.notebookcheck.net/Withings-Intelligence-promises-deep-insights-into-health-and-fitness-on-smartwatches-and-other-wearables.1035258.0.html)).
  - **Fix:** a free daily-granularity trend view with a customizable home screen that hides irrelevant modules.
- **Adidas/Runtastic Libra scale: app killed in 2020.**
  - **What happened:** the app was pulled from both stores and logins stopped. The scale still displays weight, but the core function is gone. One-star reviews flooded in ([The Register](https://www.theregister.com/2020/09/22/adidas_libra_scale/)). [older, but the canonical "orphaned data" story]
  - **Separate app:** Libra Weight Manager, the Android trend app by Daniel Cachapa, is a different product. Its listed alternatives are Trale and openScale (open source) ([AlternativeTo](https://alternativeto.net/software/libra---weight-manager)). I could not confirm Libra Weight Manager's current status.
  - **Fix:** local-first storage, open export formats, and import from Libra CSV, Happy Scale CSV and Health. Import from competitors is a round-1 theme, but weight-history import specifically is new.
- **Samsung Health: weight management removed.**
  - A Samsung EU community thread is titled "Since weight management was removed, Samsung Health app is…" ([Samsung community](https://eu.community.samsung.com/t5/mobile-apps-services/since-weight-management-was-removed-samsung-health-app-is/td-p/1930700)). Seen only as a search title, with no body read. [LOW]

**Body fat from BIA scales: accuracy and swings (MEDIUM; well documented)**
- **Peer-reviewed study.** A JMIR mHealth 2021 study compared three consumer smart scales with DEXA.
  - **Weight:** accurate, with median errors of 0.3 kg, 0 kg and 0.25 kg.
  - **Fat mass:** median errors of about −2.2 to −4.4 kg, with IQRs reaching about −8 kg. Authors: smart scales "are not accurate for body composition."
  - **Source:** [PubMed 33929337](https://pubmed.ncbi.nlm.nih.gov/33929337/). [peer-reviewed, 2021; no 2024–26 study found]
- **Long-term Renpho review.** Day-to-day body-fat swings of about 2–4 percentage points. Figures should be treated as "directional rather than clinically precise" ([Fitness Tools Reviewed](https://fitnesstoolsreviewed.com/equipment-reviews/renpho-smart-body-scale-review-the-unfiltered-truth-after-6-months/)). [review site]
- **Missing body fat.** Renpho's developer replies say that if only weight and BMI show up, the impedance did not register. Users must stand barefoot for about 15 s and touch all four electrodes ([Renpho FAQ, vendor](https://renpho.com/pages/faq-renpho-health-app)). This produces "missing body fat" days.
- **Fix:** trend body fat over 7–14 days, the same way as weight. Label it an "estimate (BIA ±3–5%)." Prefer **tape measurements** (waist, waist-to-height) as a cheaper and more honest body-composition signal. nütn already has body measurements, so making the waist trend the headline is a differentiator.

**Menstrual-cycle water retention (LOW evidence of public requests, but long-standing)**
- **Trainerize ideas forum, since Aug 2020.** Users ask for clients "to be able to add in her cycle days so this data can be compared to weigh ins," with shading of the weight graph. A commenter notes people have been asking "for 4 years" ([Trainerize ideas](https://ideas.trainerize.com/forums/167887-coach-trainer-abc-trainerize/suggestions/41067958-menstrual-period-tracking-in-app-and-shade-the-wei)). [MEDIUM: an upvoted forum request]
- **Cause.** Healthline lists the menstrual cycle, along with food and water, as a typical cause of daily swings. It says average adult weight can fluctuate "up to 5 or 6 pounds per day" ([Healthline](https://www.healthline.com/health/weight-fluctuation)).
- **Possibly nütn's own backlog.** A GitHub issue, "Cycle-aware weight notes," opened in late Sep 2026 in `TheRealestNwah/fitness-app`. It proposes reading cycle data from Apple Health, shading likely retention days, and keeping plateau detection from calling a cycle bump a stall ([GitHub #158](https://github.com/TheRealestNwah/fitness-app/issues/158)). **Caveat:** this may be the nütn team's own backlog. It is not evidence of user demand.
- **Fix:** an opt-in HealthKit menstrual-flow read. Shade the luteal and menstrual days on the weight chart, and suppress "you gained" or "plateau" messaging inside those windows.

**Wording that rewards loss at any weight (new angle, SINGLE)**
- **Happy Scale.** A reviewer complained that even when "below your goal weight, if you lose weight HappyScale tells you your trends have 'improved'… 'made progress'." They argued this encourages disordered habits and asked for neutral wording ([justuseapp](https://justuseapp.com/en/app/532430574/happy-scale/reviews)). [aggregator, single anecdote]
- **Fix:** goal-direction-aware copy. Once the user is at goal, switch to "maintenance band" language and flag continued loss below goal neutrally or with care. This is related to round 1's "tone" work but specific to the weight trend.

**Trend lag (no complaints found)**
- MacroFactor calls its trend weight "a moving average… that places greater emphasis on more recent weigh-ins" ([MacroFactor help](https://help.macrofactorapp.com/en/articles/21-weight-trend)).
- I found **no** user complaints about the trend lagging the scale. Searches returned only listings.

**Android availability**
- Happy Scale is iOS-only. Reviewers in 2025–26 "wish there were an Android version" ([Unimeal review](https://unimeal.reviews/weight-loss-apps/happy-scale/); [mwm.ai](https://mwm.ai/apps/happy-scale/532430574)). Not relevant to nütn (iOS-only), but it shows the iOS weight-app niche is served by small single-developer apps.

### Inferences
- **The weight-app maths is solved.** Happy Scale and MacroFactor smoothing are both praised. The open field is trust: never lose my data, read from any scale through Apple Health, need no account, and always let me export.
- **Scale-agnostic is the strategic play for nütn.** Pull weight and body fat from HealthKit, whatever the scale brand, and show provenance and staleness. Users of Renpho, Eufy, FitDays and Arboleaf all suffer from vendor apps and could use nütn as the "good front end" for their cheap scale.
- **Body fat** should be shown as a smoothed estimate with an honest error band. Waist measurement should be promoted as the primary body-composition trend.

### Gaps
- No first-hand r/loseit or r/xxfitness threads could be read, so "scale anxiety," "whoosh effect" and cycle-weight posts are not quoted directly.
- I found nothing specific on the **Arboleaf** app.
- I found no Happy Scale goal-date-prediction complaints. Only praise surfaced.
- I found no 2024–26 BIA validation study. The JMIR study is from 2021.

## 2. Progress photos (Progress Body Tracker, Body Tracker/Progress Pics, Shapez, Metamorph and others)

### Takeaway
Users want photos that stay **private** (out of the camera roll, behind Face ID, not uploaded), **comparable** (ghost overlay, consistent framing, slider or side-by-side) and **free**. Recurring anger centres on photo features sitting behind a paywall, or a free photo limit that appears only when uploading.

### Cited Findings
- **Progress Body Tracker: photos paywalled.**
  - **Vendor listing:** Pro "unlocks progress photos, unlimited measurement areas, custom reports, past-data entry" ([App Store, vendor listing](https://apps.apple.com/us/app/body-measurement-photo-weight-tracker-progress/id583840813)).
  - **Third-party view:** the free version "answers only half of the job" ([Body Tracker blog](https://www.bodytrackerapp.com/blog/best-apps-for-progress-photos)). [competitor blog]
  - **Spread:** MEDIUM. Paywalled photos are the norm in this category.
  - **Fix:** free unlimited photos (nütn's model).
- **Progress Body Tracker: comparison slider removed.**
  - **Request:** users ask to "bring back the slider for photo comparison… the old version had a slider to compare past and current photos, and now it's just side by side."
  - **Other requests:** two-decimal custom measurements and a reorderable measurement-input order.
  - **Source:** [Progress feedback board](https://feedback.theprogressapp.com/). [vendor feedback board; MEDIUM, as it is a public request]
  - **Fix:** a before/after wipe slider in addition to side-by-side, decimal precision, and a custom order for measurement fields.
- **Shapez: surprise photo limit.**
  - **Complaint:** a user "reached the limit of photos for free" only at upload time. The developer apologised that "the monetization policy was not fully transparent." Another reviewer "nearly lost months of progress data."
  - **Source:** [App Store, Shapez](https://apps.apple.com/us/app/shapez-body-progress-tracker/id1369905597). [single anecdotes]
  - **Fix:** no limits, and photos backed up with the rest of the data.
- **Body Tracker (Play): fear of auto-subscribing.**
  - **Complaint:** "confusion and fear of automatically subscribing" cost the app a star.
  - **Source:** [Google Play](https://play.google.com/store/apps/details?id=com.thumbstonelabs.bodytransformation&hl=en_US). [single anecdote]
- **Apple Photos as a progress-photo tool.**
  - **Complaint:** "my photos were all slightly different, so comparing them was frustrating," with "no simple side-by-side view." The Hidden album helps keep progress pics "from showing up while you scroll with friends."
  - **Source:** [LocalOneLabs blog](https://localonelabs.com/pages/blog/best-fitness-progress-photo-apps); [GetCurex blog](https://getcurex.com/glp1-blog/top-apps-to-track-progress-photos). [vendor or affiliate blogs]
  - **Fix:** in-app capture straight to app storage, never the camera roll.
- **Ghost overlay is the expected alignment aid.**
  - **Review:** one App Store review: "the ghost overlay helps me take the photo from the same spot every time."
  - **Implementations:** they vary. My Journey has adjustable overlay opacity, a grid and a timer ([GitHub, MyJourney](https://github.com/GreggRoll/MyJourney)). Metamorph lets users choose the first or most recent photo as the ghost ([App Store](https://apps.apple.com/us/app/progress-pic-photos-metamorph/id6544789120)). Fitness Camera adds pose matching ([Google Play](https://play.google.com/store/apps/details?id=com.fitnesscamera&hl=en_US)).
  - **Spread:** HIGH as a feature expectation.
  - **Fix:** an overlay with adjustable opacity, a choice of reference photo, a self-timer, and pose-tagged front/side/back slots.
- **Privacy and AI upload.**
  - **Privacy as a selling point:** Progress Pics advertises "no uploads to third-party servers," Face ID album lock and auto-lock when backgrounded ([App Store](https://apps.apple.com/us/app/progress-pics-photo-then-now/id6758411454)). A guide says some competitors "frequently have poor privacy practices (uploading local photos to third-party servers)" ([GetCurex](https://getcurex.com/glp1-blog/top-apps-to-track-progress-photos)).
  - **AI upload example:** GainFrame sends photos to Google's Gemini API for analysis ([GainFrame blog](https://gainframe.app/blog/best-progress-photo-apps/)). [competitor blog]
  - **Spread:** MEDIUM. Privacy now drives marketing.
  - **Fix:** local-only storage by default, a Face ID lock, blur in the app switcher, and no AI upload without explicit per-photo consent.

### Inferences
- **Free, private progress photos are a differentiator.** Most rivals paywall photos. Combining photos, measurements and weight on one timeline ("weight was flat but waist dropped 2 cm and the photos show it") is the strongest answer to scale anxiety, and few apps do it in one place.
- **Table stakes:** ghost overlay, side-by-side comparison and an app lock. **Delighters:** a wipe slider, auto-generated monthly comparisons, and an export collage with the weight or date stamp optional (privacy).

### Gaps
- I found no first-hand r/progresspics discussion of tooling complaints.
- I could not identify an app named exactly "Body Progress." The closest matches were Progress, Shapez and Body Tracker.

## 3. Fasting apps (Zero, Simple, Fastic, BodyFast)

### Takeaway
Fasting complaints are dominated by **business-model** issues: trial-to-annual "renewal shock," hard cancellation, upsells, and features moved behind Plus. Behind those sit rigid windows and pseudo-precise "autophagy/ketosis zone" claims. The core timer is usually free, so the paywall anger is about history, custom windows, journals and coaching.

### Cited Findings
- **Simple: renewal shock.**
  - **Complaints:** Trustpilot reviewers say "signed up for a week's trial for $9 and then tried to cancel but they were charged $79" and "made it very difficult to cancel" ([Trustpilot, Simple Life](https://www.trustpilot.com/review/simple-life-app.com)). Help-forum users write that they "don't want them to take any more of their money" and that the app would not let them cancel ([JustAnswer](https://www.justanswer.com/software/ql4mt-app-month-give-permission.html)).
  - **Recent reviews:** a review site describes recent 1-star reviews as "dominated by renewal-shock complaints" ([home-cooks.co.uk](https://home-cooks.co.uk/pages/review-simple)).
  - **No reminder before conversion:** one blog claims Simple sends no notification before the trial converts ([Nutrola blog](https://nutrola.app/en/blog/simple-app-charged-me-without-asking-what-to-do)). [competitor blog, unverified]
  - **Spread:** HIGH. Several independent venues report it, though the overall Trustpilot rating is still high and review counts differ by regional page.
  - **Fix:** free, with no trial (nütn's model). Say so explicitly in marketing.
- **BodyFast and Fastic: unexpected charges.**
  - **Complaints:** Trustpilot summaries report "unexpected charges and automatic subscription renewals occurring after trial periods" and "severe difficulties with cancelling" for BodyFast ([Trustpilot, BodyFast](https://www.trustpilot.com/review/www.bodyfast.app)). For Fastic, users report "considerable difficulties when trying to cancel," and some customers feel "tricked into subscriptions" ([Trustpilot, Fastic](https://www.trustpilot.com/review/fastic.com)).
  - **Spread:** MEDIUM–HIGH.
- **BodyFast: rigid windows.**
  - **Complaint:** a user said the app "is lacking flexibility with fasting periods" ([justuseapp, BodyFast](https://justuseapp.com/en/app/1189568780/bodyfast-intermittent-fasting/reviews)). [single anecdote]
  - **Fix:** free-form start and stop, editing past fasts, per-day schedules (for example 16:8 on weekdays and 14:10 at weekends), and a "fast broken early" state that doesn't punish streaks.
- **Zero: paywall creep and MyFitnessPal upsell.**
  - **Blog claim:** a 2026 ranking blog says the advanced journal, custom timer windows and biometric integration were free at launch but moved behind Zero Plus after Zero joined MyFitnessPal. It also says users are "repeatedly prompted to add MyFitnessPal premium on top of Zero Plus" ([unstar.app](https://unstar.app/blog/zero-simple-fastic-life-fasting-bodyfast-intermittent-fasting-apps-ranked-2026)). [competitor blog, search extract only, ownership history unverified]
  - **User review:** an AlternativeTo reviewer says "most of the features are behind a subscription called zero+" ([AlternativeTo](https://alternativeto.net/software/ifast--simple-fast-tracker)). [single anecdote]
  - **Export:** a MyFitnessPal community user dropped Zero once MyFitnessPal added fasting, noting Zero "allows for exporting your data in a readable/parsable json file" ([MFP community](https://community.myfitnesspal.com/en/discussion/10907685/import-fasting-history-from-zero)). That is a **Zero fasting-history import** opportunity for nütn.
  - **Spread:** MEDIUM.
- **Misleading "zones" (autophagy and ketosis).**
  - **Science critiques:** there is "currently no method available to measure autophagy in humans" ([Consensus](https://consensus.app/home/blog/does-the-science-match-the-hype-on-intermittent-fasting/)). The 24–48 h autophagy figures "come from mice," and "deep autophagy" is not a clinically defined stage ([Acibadem blog](https://acibademinternational.com/blog/what-is-autophagy-the-cell-cleaning-science-behind-fasting-claims/)).
  - **App copy:** apps market zones as if they were measured. One listing promises to show "exactly when you enter fat burn, ketosis, and autophagy zones" ([FastingCat, App Store](https://apps.apple.com/app/id6748528990)).
  - **Spread:** LOW as a user complaint (I found no user reviews objecting). It is HIGH as a credibility risk.
  - **Fix:** label stages as "typical timeline (estimate)" and cite the evidence, or drop autophagy claims.
- **Logging food while fasting:** I found **no** direct user complaint in the sources I could reach. See Gaps.

### Inferences
- For nütn, fasting's value lies less in the timer, which is commoditised and free everywhere, than in **integration**:
  - **Auto-close:** logging a meal automatically closes the fast, or asks first.
  - **Zero-calorie items:** black coffee, tea and water can be logged without breaking the fast, if they're flagged as zero-calorie.
  - **Weight overlay:** fasting history is overlaid on the weight trend.
- "Free, no trial, no auto-renew" is a sharp marketing contrast in this category specifically.
- Honest copy on zones is low-cost to build. It differentiates nütn from the zone-heavy competitors and protects the brand.

### Gaps
- No Reddit r/intermittentfasting threads could be read. Complaints about "breaking the fast on log," "Apple Watch complication" and "editing a forgotten start time" are therefore unquoted.
- The ownership timeline of Zero and MyFitnessPal is unverified. One search summary says 2021, but I found no primary source.

## 4. Hydration apps (WaterMinder, Waterllama, Plant Nanny and generic reminders)

### Takeaway
Hydration apps are highly rated, but their complaints are consistent:
- **Basic actions paywalled:** editing or deleting an accidental entry, custom cups and drinks.
- **Health totals:** all drinks are counted as "water" in Apple Health.
- **Reminders:** they fail, spam, take over the screen, break bedtime schedules or override Do Not Disturb.
- **Diet framing:** an unwanted weight-loss framing.

### Cited Findings
- **Waterllama: undo paywalled.**
  - **Complaint:** a user deleted the app because "there is no option to delete water that was added in a day by accident unless you pay $8.99."
  - **Vendor listing:** premium includes "edit water intake history, change glass/cup size."
  - **Source:** [App Store, Waterllama](https://apps.apple.com/us/app/water-tracker-waterllama/id1454778585?see-all=reviews); [mwm.ai](https://mwm.ai/apps/water-tracker-waterllama/1454778585).
  - **Spread:** MEDIUM. The source summary calls it the most common complaint, although Waterllama is rated 4.9 from 149K ratings.
  - **Fix:** free undo and edit, and custom containers.
- **Waterllama: bugs and diet framing.**
  - **Bugs:** a reviewer calls it "laggy and sending duplicate data." Another says the watch app "sometimes it works, sometimes it doesn't."
  - **Framing:** a reviewer objects to the weight-loss framing that "unnecessarily perpetuates disordered-eating and dieting."
  - **Source:** [justuseapp](https://justuseapp.com/en/app/1454778585/water-tracker-waterllama/reviews). [aggregator, single anecdotes]
  - **Fix:** de-duplicated HealthKit writes and hydration copy that is neutral, not diet-framed.
- **Waterllama: barcode request for drinks.**
  - **Request:** "It would be fantastic if… [it] could scan bar codes to enter new/custom drinks with the correct nutritional information (caffeine, calories, etc.)"
  - **Source:** [App Store reviews](https://apps.apple.com/us/app/water-tracker-waterllama/id1454778585?see-all=reviews). [single anecdote]
  - **Fix:** nütn already has a barcode scanner, so let one scan log both nutrition and fluid volume. Drinks then count toward water and calories together, which a standalone hydration app cannot do.
- **WaterMinder: every drink written to Health as water.**
  - **Complaint:** "total ounces get logged to Apple Health… inaccurate if using the app to track non-water drinks such as coffee or even alcohol."
  - **Source:** [App Store, WaterMinder](https://apps.apple.com/us/app/water-tracker-by-waterminder/id653031147). [single anecdote]
  - **Background:** WaterMinder added caffeine logging with a Health sync in 2021 ([9to5Mac](https://9to5mac.com/2021/04/07/waterminder-app-adds-support-for-tracking-caffeine-intake-with-apple-health-integration/)).
  - **Fix:** per-beverage hydration factors, user-editable. Write HKQuantityTypeIdentifierDietaryWater only for the hydrating portion, and DietaryCaffeine and calories separately.
- **Plant Nanny: ads, paywalled plants, unreliable reminders.**
  - **Complaints:** "too many ads/prompts to pay for premium" and "barely any plants to grow unless you pay for it." Notifications "don't ever work even after troubleshooting," and the app "doesn't connect to my Apple Watch so I don't get any of the reminders."
  - **Source:** [justuseapp](https://justuseapp.com/en/app/1424178757/plant-nanny/reviews); [App Store](https://apps.apple.com/us/app/plant-nanny-cute-water-tracker/id1424178757?see-all=reviews). [aggregator, MEDIUM]
- **Generic water-reminder apps: intrusive alerts.**
  - **Complaints:** "full-screen notifications are super annoying… the whole App opens up on your display." Alerts override Do Not Disturb, and the volume reset "right back to max." "The reminder schedule gets wiped out if I change my wake up or bedtime settings." One app "starts spamming water reminder notifications like crazy."
  - **Source:** [Google Play, Water Tracker](https://play.google.com/store/apps/details?id=watertracker.waterreminder.watertrackerapp.drinkwater&hl=en); [Google Play, Remind Drink](https://play.google.com/store/apps/details?id=com.remind.drink.water.hourly). [MEDIUM: several apps]
  - **What users praise:** reminders that are "subtle" and logging after the fact ("add water you've forgotten to add later").
  - **Fix:** smart reminders that are quiet once the goal is met, respect Focus and Do Not Disturb, stop at bedtime, back off after a log, and appear as a normal banner.

### Inferences
- Inside an all-in-one app, hydration's edge is that **food and drink logging already captures fluids**: soups, milk, coffee and barcode-scanned drinks.
- **Table stakes:** one-tap custom containers, an Apple Watch or widget quick-add, free edit and undo, and HealthKit write.
- **Delighters:** per-beverage hydration factors and adaptive reminders that stop at the goal.

### Gaps
- I found no first-hand user debate on whether coffee "counts." The only Health-related complaint is WaterMinder's.
- I found no complaint data on electrolyte tracking or climate- or exercise-adjusted goals.

## 5. Meal planning and grocery apps (Mealime, Eat This Much, Paprika, Plan to Eat, PlateJoy, Samsung Food/Whisk, Prepear)

### Takeaway
The headline is **platform risk**: Yummly closed in Dec 2024, PlateJoy on 1 Jul 2025 and Mealime closes on 21 Oct 2026, all without bulk export. Recipe-hoarding users lost hundreds of recipes. Functional complaints recur across apps:
- **Plans ignore macros**, or nutrition is paywalled.
- **Serving counts are fixed** (2/4/6), so leftovers pile up for solo cooks and families can't scale.
- **Grocery lists** don't subtract what's already in the pantry, don't merge duplicates and don't carry scaled servings.
- **Cost estimates** run well under the actual grocery bill.
- **Food exclusions** are tedious to set up.
- **Recipe rotation** gets repetitive by week three.

### Cited Findings
**Shutdowns and data loss (new angle, HIGH)**
- **Mealime: closing 21 Oct 2026, no export.**
  - **Announcement:** the shutdown is announced in its App Store and Play listings. Pro is free for everyone until then, and there is **no export** for recipes, saved plans or grocery lists ([Pann blog](https://www.pann-app.com/blog/is-mealime-shutting-down); [MealThinker](https://mealthinker.com/blog/mealime-alternative); [Swoodie](https://swoodie.app/blog/mealime-shutting-down)). [competitor blogs; consistent across about 8 sources]
  - **Reason given:** one source says the owner, Albertsons, is folding its features into its retail digital ecosystem ([Pann](https://www.pann-app.com/blog/is-mealime-shutting-down)). [unverified]
  - **Fix:** a Mealime-refugee landing flow (paste a recipe URL, import a screenshot) and a visible "your data is yours: export anytime" promise.
- **PlateJoy: ended 1 Jul 2025.**
  - "PlateJoy will no longer be available as an app or website after July 1st, 2025." Its recipes moved to RVO Health's Wellos app ([PlateJoy support, vendor](https://support.platejoy.com/platejoy-faqs/35663)). [primary]
- **Yummly: shut by Whirlpool on 20 Dec 2024.**
  - **Complaints:** users quoted on an aggregator: "lost everything I saved." Another had "almost 100 recipes & I want to keep as many as possible" but could not find the download option. A third had "over 600 recipes saved," when the only route was per-recipe PDF.
  - **Source:** [unitq scorecard](https://unitq.com/unitq-scorecards/yummly); [Plan to Eat blog](https://www.plantoeat.com/blog/2024/12/yummly-is-closing-discover-the-best-meal-planning-alternative). [aggregator and competitor blog; HIGH as an event]
  - **Fix:** bulk export (JSON plus a human-readable PDF or Markdown) and bulk import of a recipe collection.

**Macros ignored or paywalled (MEDIUM)**
- **Mealime: nutrition on Pro only, and missing amounts.**
  - **Paywall:** nutrition is visible on Pro only ([Plan to Eat review](https://www.plantoeat.com/blog/2023/04/mealime-app-review-pros-and-cons/)). [competitor blog, 2023]
  - **Complaint:** a macro-counting reviewer found ingredients "listed without an amount, such as mayo… treated as though it is a spice. That seems very misleading for someone trying to limit calories or count macros" ([App Store, Mealime](https://apps.apple.com/us/app/mealime-meal-plans-recipes/id1079999103?see-all=reviews&platform=ipad)). [single anecdote]
  - **Fix:** every recipe ingredient carries a quantity and resolves to a food item, so per-serving macros are always computed and shown free.
- **Plan to Eat and Prepear: thin nutrition.**
  - **Plan to Eat:** one review says it has "No nutrition data," while Fortune lists macro counting. **The sources conflict.**
  - **Prepear:** "not a full calorie/macro counter," and the planner, grocery list and nutrition sit in Gold at about $119.99/year.
  - **Source:** [Fortune](https://fortune.com/article/best-meal-planning-apps); [FoodiePrep](https://www.foodieprep.ai/blog/meal-planning-apps-with-builtin-grocery-lists-a-2026-sidebyside-review). [review and competitor sites]

**Fixed servings, leftovers and family portions (MEDIUM)**
- **Mealime: 2, 4 or 6 servings only.**
  - **Complaint:** this "could be an issue if you're only cooking for yourself and you don't want a bunch of leftovers." A family-of-five reviewer said the app "doesn't adjust recipes for families."
  - **Source:** [justuseapp, Mealime](https://justuseapp.com/en/app/1079999103/mealime-meal-plans-recipes/reviews); [Zillennial Zine review](https://thezillennialzine.com/2023/08/13/mealime-review/). [single anecdotes]
  - **Fix:** any serving count, plus a planned-leftovers feature: cook 4, eat 1, and auto-schedule the other 3 portions on later days so they count toward those days' macros.
- **Eat This Much: plans for one person.**
  - **Complaint:** the plan is built around one person's macros, so it is "hard to use for a family."
  - **Source:** [ultimatemealplans](https://ultimatemealplans.com/eat-this-much-review/). [review site]
  - **Fix:** household portions, with one recipe split by each person's target.

**Grocery list logic: pantry, merging and scaling (MEDIUM–HIGH)**
- **Samsung Food: pantry ignored, scaling lost.**
  - **Complaint:** "Recipes don't show which ingredients I have in my Food List, and when I add the ingredients to my shopping list, it adds everything, even items I already have" ([Google Play, Samsung Food](https://play.google.com/store/apps/details?id=com.foodient.whisk&hl=en&gl=US)). [single anecdote, recent]
  - **Third-party view:** a roundup says serving-size changes "don't carry over to shopping lists" and that support "acknowledg[es] bugs but never fix[es] them" ([Pann review](https://www.pann-app.com/blog/samsung-food-whisk-review)). [competitor blog]
- **Eat This Much: no pantry warning, and lists too big.**
  - **Complaint:** adding pantry items doesn't warn that you may already have them. Weekly lists run to "30 to 40 ingredients" and can't be sorted by category or store.
  - **Source:** [ultimatemealplans](https://ultimatemealplans.com/eat-this-much-review/); [Plan to Eat review](https://www.plantoeat.com/blog/2023/10/eat-this-much-app-review-pros-and-cons/). [review and competitor blogs]
- **Plan to Eat: duplicates not merged.**
  - **Complaint:** duplicate ingredients across recipes are "not always merged into one quantity."
  - **Source:** [FoodiePrep](https://www.foodieprep.ai/blog/meal-planning-apps-with-builtin-grocery-lists-a-2026-sidebyside-review). [competitor blog]
- **Paprika: merging is the benchmark.**
  - **Vendor:** Paprika's merging ("1 egg + 2 eggs = 3 eggs") is best-effort. It needs the "quantity unit ingredient" format, and scaled recipes keep their scaling on the list ([Paprika guide, vendor](https://www.paprikaapp.com/help/windows/)).
  - **Praise:** a GitHub request for another app calls Paprika's combine-and-sort its "most-praised feature" ([GitHub issue](https://github.com/NevinJulian/healthtracker/issues/347)).
- **Mealime: list order fixed.**
  - **Complaint:** list "categories and order are not customizable." Others praise check-off that hides items already in the cupboard.
  - **Source:** [justuseapp](https://justuseapp.com/en/app/1079999103/mealime-meal-plans-recipes/reviews). [aggregator]
- **Fix (grocery):** a unit-aware merge in grams first (round 1's grams-first gives nütn an edge in converting cups or tbsp to g for the merge), pantry subtraction, aisle grouping with a custom order, a shared household list, and scaling that carries through to the list.

**Cost (MEDIUM)**
- **Eat This Much: costs underestimated.**
  - **Complaint:** a reviewer's "bill was almost double the estimate." The cause is that each day pulls different recipes. Reviewers suggest locking repeat meals.
  - **Source:** [App Store, Eat This Much](https://apps.apple.com/us/app/eat-this-much-meal-planner/id981637806?see-all=reviews&platform=ipad); [ultimatemealplans](https://ultimatemealplans.com/eat-this-much-review/).
  - **Fix:** ingredient-overlap optimisation (re-use the same ingredients across the week) and user-entered prices, rather than invented estimates.

**Variety, exclusions and paywall (MEDIUM)**
- **Eat This Much: repetition and exclusions.**
  - **Repetition:** recipes repeat "by week 3" ([promealplan](https://www.promealplan.com/en/blog/eat-this-much-review-2026)). [competitor blog]
  - **Exclusions:** users must "click the red X on every variation and capitalization of a food," and the app can't exclude soy while keeping tempeh ([ultimatemealplans](https://ultimatemealplans.com/eat-this-much-review/)).
  - **Paywall and offline:** the weekly view needs Premium, and there is no offline mode.
- **Mealime: swaps and recipes.**
  - **Complaint:** swapping "tends to cycle through three or four of the same recipes," and Pro increasingly gates recipes. One user said it "tries really hard to paywall you."
  - **Source:** [App Store, Mealime](https://apps.apple.com/us/app/mealime-meal-plans-recipes/id1079999103?see-all=reviews&platform=ipad).
- **Fix:** exclusions by ingredient category or tag (all soy except tempeh), and swaps that respect macros and rotate widely.

**Cooking mode (LOW complaint evidence; feature convergence)**
- **What competitors and developers build:** one step at a time in large text, ingredients shown beside each step, auto-detected timers from text such as "simmer 20 minutes," concurrent labelled timers that fire while the phone is locked, a screen wake lock and dark mode.
- **Source:** [Cooklang app, Google Play](https://play.google.com/store/apps/details?id=md.cook.android&hl=en_US); [GitHub spec](https://github.com/kaecyra/gobbler/issues/33); [Drizzle Lemons](https://www.drizzlelemons.com/cook-mode).
- **Paywall example:** Prepear sells "ad-free Cook Mode" in Gold ([FoodiePrep](https://www.foodieprep.ai/blog/meal-planning-apps-in-2026-which-tools-actually-simplify-your-kitchen)).
- **Evidence caveat:** this shows supply-side convergence, not measured user demand.

### Inferences
- **Two meal-planning segments are now orphaned:** Mealime, with its simple weekly plan and auto grocery list, and PlateJoy, with personalised health plans. Both are being pushed towards paid or retail products. A free nütn planner that is macro-aware and exports freely has a timely pitch, especially with Mealime closing on 21 Oct 2026.
- **The key differentiator nütn uniquely enables is the planned-leftovers to food-log link:** cook a batch, portions are scheduled, eating one logs it. This builds on round 1's batch-cook work but adds the plan and list loop.
- **Grams-first units** let nütn merge grocery quantities properly, which is a known weak spot in Plan to Eat and Samsung Food.

### Gaps
- No r/MealPrepSunday or r/EatCheapAndHealthy threads could be read. Leftover and budget complaints are therefore from reviews, not community discussion.
- Paprika user complaints were scarce. I found no confirmation of nutrition support.
- Prices conflict across sources: Plan to Eat at $39 or $49/year, Prepear at about $9.99/month or $119.99/year.

## 6. Praised features versus table stakes across these categories

### Takeaway
Users now **expect** these as the baseline:
- **Weight:** a smoothed trend with forecasts and milestones.
- **Progress photos:** a ghost overlay with side-by-side comparison.
- **Hydration:** one-tap logging with HealthKit write.
- **Grocery lists:** auto-generation with check-off.
- **Fasting:** a free basic timer.

They **praise** honest smoothing that keeps progress from "going down" on a small gain, milestone celebrations, data export, and no subscription (Paprika's one-time price). They **punish** paywalled basics, surprise limits, renewal shock, forced accounts, silent sync failure and data loss on shutdown or upgrade.

### Cited Findings
- **Happy Scale praise.**
  - **Smoothing:** "the graph still shows that my overall trend is going down even after a small gain."
  - **Milestones:** they "self-correct every time you put in your weight." Users enjoy milestone confetti and selectable 7/30/90-day or all-time averages. The progress percentage "won't go down" if you gain a few ounces.
  - **Forecasts:** described as "fairly accurate."
  - **Source:** [Happy Scale App Store](https://apps.apple.com/us/app/happy-scale-weight-loss-tracker-trend-prediction/id532430574); [iPhone JD review, Jan 2025](https://www.iphonejd.com/iphone_jd/2025/01/review-happy-scale.html); [lululemonexpert](https://lululemonexpert.com/2020/01/06/happy-scale-weight-loss-made-motivated/).
  - **Spread:** HIGH positive sentiment.
- **Paprika's one-time price.** Paprika is praised as "not free but… not subscription based" ($29.99 on Mac). Its pantry tracks expiry ([AlternativeTo](https://alternativeto.net/software/paprika-recipe-manager/about); [Paprika, vendor](https://www.paprikaapp.com/)).
- **Zero's JSON export.** Zero's export was valued enough that a departing user mentioned it ([MFP community](https://community.myfitnesspal.com/en/discussion/10907685/import-fasting-history-from-zero)).
- **Prepear's grocery list.** Its sorted list, with Walmart pickup in the US only, is praised ([mysubscriptionaddiction](https://www.mysubscriptionaddiction.com/meal-planning-service-apps)).
- **Subtle hydration reminders.** "subtle, so it's not annoying" ([Google Play reviews, see §4](https://play.google.com/store/apps/details?id=com.water.tracker.remind&hl=en-US)).

### Inferences
**nütn-specific build list, ranked by evidence × fit, NEW angles only:**
1. **Data custody suite.** Verified iCloud backup and restore, a "last backed up" stamp, full export (CSV/JSON) and bulk import. Import sources: Happy Scale or Libra CSV, Zero JSON, Apple Health weight backfill and recipe collections from Mealime or Yummly refugees. *Evidence:* Happy Scale loss, Eufy no-export, Yummly/PlateJoy/Mealime shutdowns.
2. **Scale-agnostic HealthKit weight and body-fat ingest** with source labels, gap and staleness alerts and de-duplication. *Evidence:* Eufy, Renpho, Withings and FitDays sync complaints.
3. **Free, private progress photos.** In-app vault, Face ID, a ghost overlay with opacity control, a wipe slider and pose slots, combined with measurements and weight on one timeline. *Evidence:* Progress and Shapez paywalls, the slider request, privacy marketing.
4. **Planned leftovers and household portions** feeding the food log, plus a **unit-merging, pantry-aware grocery list** that carries scaling. *Evidence:* Mealime, Samsung Food, Eat This Much and Plan to Eat.
5. **Cycle-aware weight chart** (opt-in, HealthKit menstrual data) and **goal-aware wording** at or below goal. *Evidence:* Trainerize request, Happy Scale wording complaint.
6. **Body fat shown as a smoothed estimate with an error band.** The waist trend is promoted as the main body-composition signal. *Evidence:* JMIR 2021, Renpho swings.
7. **Hydration factors per beverage**, honest HealthKit water writes, barcode-to-fluid, free undo, and reminders that stop at the goal and respect Focus. *Evidence:* Waterllama, WaterMinder and generic reminder-app reviews.
8. **Fasting integrated with food logging** (auto-close or confirm on meal log, zero-calorie drinks allowed), flexible per-day windows, editable history and honest "typical timeline" copy instead of autophagy zones. *Evidence:* BodyFast rigidity, the autophagy-claims critique, Zero paywall creep.
9. **Marketing line** for fasting, hydration and meal-planning switchers: "Free. No trial. Nothing to cancel." *Evidence:* Simple, BodyFast and Fastic renewal-shock complaints.

### Gaps
- I have no quantitative prevalence data, such as percentage of 1-star reviews per theme. The spread ratings are qualitative.
- Reddit, the richest source for these categories, could not be read.
