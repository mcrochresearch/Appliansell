# User complaints and feature requests: habit, journaling, mood and meditation apps (round 2)

Scope: Daylio, How We Feel, Bearable, Finch, Headspace, Calm, Stoic, Reflectly, Day One, Streaks, Habitica, Fabulous, Atoms, Loop Habit Tracker, Way of Life, Balance and Waking Up. Researched 2026-10-09.

**How the sources were reached:**
- **Blocked:** Reddit, apps.apple.com, Trustpilot, Hacker News, hn.algolia, justuseapp and metafilter all failed to load (proxy 403 or DNS failure).
- **Read directly:** only GitHub (Loop Habit Tracker discussion #88).
- **Secondhand:** everything else comes from search-engine snippets of those pages, or from blogs and aggregators that quote users.
  - Quotes marked **[snippet]** are text the search engine returned from the named page. I could not open the page to check the full context or the date.
  - Many of the blogs are written by competitors (HabitBox, Rosebud, Nuju, Bestie, Noodl, Sproutapp, Calmevo). These are marked **[competitor blog]**, so treat them as opinion.
- **Round 1 topics excluded:** one-tap mood logging, streak guilt for food logging, generic correlations and the Daylio backup paywall.

**Fields used for each finding:** the app, the complaint as a short quote, the source, how widespread it seems, and the feature that would fix it in nütn.

---

## 1. What do users complain about? (new angles: flexible schedules, pausing and illness, journal privacy, prompts, notifications, guilt, gamification decay, paywalls)

### Takeaway
The strongest new complaint clusters are:
1. **Rigid schedules.** Users want "X times per week", skipped days and pauses for illness or holidays that do not count as failure.
2. **Subscription and billing traps.** Headspace, Calm and Fabulous are dominated by this, and Waking Up and Day One users complain about price hikes.
3. **Notification spam and pop-ups.** Users cannot turn off the non-reminder pings separately (Fabulous, Calm).
4. **Content and prompt repetition.** Reflectly, Stoic and Calm feel repetitive after weeks or months.
5. **Journal privacy.** Users worry about server storage and want local-only storage or a separate lock.

Loop Habit Tracker's GitHub thread is the best primary source. It shows skip-day and holiday requests going back years, until the feature shipped in Loop 2.0.

### Cited Findings

**A. Rigid schedules, skipping, pausing and illness mode**
- **Loop Habit Tracker: no way to skip a day for external reasons** (feature request, Apr 2016). "A user should be able to skip a day without breaking the streak if he was unable to perform activity due to external factor."
  - Widespread? The original post has 7 thumbs-up, and a follow-up by torkelsson ("sometimes it is impossible to meet the goals due to external factors") has 9. The thread stayed active for four years.
  - Fix: a per-habit "skip" state (a blue dash) that is neutral for streaks and scores.
  - Source: [GitHub uhabits #88](https://github.com/iSoron/uhabits/discussions/88) (read directly)
- **Loop: losing the streak to illness** (Oct 2017). "loosing the streak beacause of beeing ill ist demotivating" (sic).
  - Widespread? 3 thumbs-up.
  - Fix: an illness or rest mode that freezes streaks.
  - Source: [GitHub uhabits #88](https://github.com/iSoron/uhabits/discussions/88)
- **Loop: no answer for holidays and vacations** (Jul 2020). "I just don't know what to do with these when I'm on vacation or when there's a holiday."
  - An earlier comment noted that a lunch-walk habit makes no sense on a holiday: checking it would be false, and leaving it unchecked would be unfair.
  - Fix: holiday and vacation pauses with start and end dates.
  - Source: [GitHub uhabits #88](https://github.com/iSoron/uhabits/discussions/88), plus a [search summary of the same thread](https://github.com/iSoron/uhabits/discussions/88)
- **Loop: weekday habits are penalised** (Apr 2016). "It should be possible to do this habit five days a week and reacht 100% as fast as other habits."
  - Fix: schedules of "N times per week" or chosen weekdays, scored against that target.
  - Source: [GitHub uhabits #88](https://github.com/iSoron/uhabits/discussions/88)
- **Loop: users refuse to fake a completion.** One commenter wants to "not lie about completing the habit" (4 thumbs-up). The MetaFilter asker said much the same: "I'd prefer to suspend a habit than lie and say I did it when I couldn't."
  - Fix: honest skip and pause states, never "mark done to save your streak."
  - Sources: [GitHub #88](https://github.com/iSoron/uhabits/discussions/88); [MetaFilter](https://ask.metafilter.com/310949/Habit-Tracking-App-vacation-suspend) [snippet]
- **Loop's maintainer agrees streaks are a weak metric.** "streaks are a very poor measure of habit strength" (9 thumbs-up).
  - Loop's answer is a decaying "habit strength" score, so a few missed days after a long run do not wipe out progress.
  - Skip support was announced for Loop 2.0 (Aug 2020).
  - Sources: [GitHub #88](https://github.com/iSoron/uhabits/discussions/88); [Loop GitHub description](https://github.com/vyu1/uhabits) [snippet]
- **Pauses should be per habit, not global.** A commenter wrote: "this should be done for habits individually. You may want to do your personal habits but not your work habits."
  - Source: [GitHub #88](https://github.com/iSoron/uhabits/discussions/88) [snippet via search]
- **Competitors are shipping pause features.**
  - Habitify has an "Off Mode" with start and end dates, and streaks are kept during it. Its own help article admits that breaking a streak after "a busy day, an illness, or a well-deserved break" is discouraging.
  - Sources: [Habitify Off Mode](https://intercom.help/habitify-app/en/articles/6178415-off-mode); [Habitify streak article](https://intercom.help/habitify-app/en/articles/6113621-learn-about-streak-in-habitify) [snippet]
- **Streaks (Crunchy Bagel): no backfilling for a day you forgot to log.**
  - Users praise its HealthKit auto-completion and its $5.99 one-time price, but missing a day resets the streak, and there is a hard cap of 24 tasks.
  - Widespread? Raised mainly by competitor blogs. The app itself is rated about 4.8 from about 27K ratings.
  - Fix: let users edit past days, and complete habits automatically from HealthKit.
  - Sources: [HabitBox Streaks alternatives](https://habitbox.app/blog/streaks-app-alternatives) [competitor blog]; [apppicked review](https://www.apppicked.com/en/blog/streaks-habit-tracker-ios-review); [MacStories](https://www.macstories.net/reviews/developer-crunchy-bagel-releases-a-mac-catalyst-version-of-streaks/)
- **Atoms (James Clear): a 6-habit cap and a rigid habit format.**
  - Quotes: "even at close to $100 a year, you can only track 6 habits total". Habits must follow "I'll do X at Y, to become Z", with "No Habit Stacking, no breaking a habit." The calendar "only shows a week at a time."
  - Widespread? Several reviews from 2024–25. One 2026 review lists a lower price ($39.99 a year), so pricing has changed.
  - Fix: unlimited habits, habit stacking, "quit" or negative habits, and a month or year history view.
  - Sources: [JustUseApp Atoms reviews](https://justuseapp.com/en/app/6474421906/atoms-from-atomic-habits/reviews) [snippet]; [Luke Sizmur review](https://world.hey.com/luke.sizmur/my-atoms-review-1f3bd5df) [snippet]; [learnofchrist 2026 review](https://learnofchrist.com/resources/atoms)
- **Bearable: symptoms could be logged only once a day.**
  - A June 2025 App Store reviewer said its correlations were "simply not helpful" for their illness because same-day effects could not be captured. The developer replied that time-of-day logging exists.
  - Fix: multiple timestamped check-ins per day, and correlations within a single day.
  - Source: [aelivra Bearable review roundup](https://aelivra.co/explore/compare/bearable-app-review) [secondhand]

**B. Subscription traps and billing, as a reason users distrust "wellness" apps**
- **Headspace: charged after cancelling, and refunds refused** (Trustpilot, 2025).
  - Quotes: "still been charged, despite multiple requests and attempts to cancel". Another user tried "to cancel on renewal date and was told it was too late." Another: "u can't cancel subscriptions from within the app, only thru google play", and the subscription did not show up in Google Play either.
  - Widespread? This is the dominant theme of Headspace's Trustpilot pages across the US, UK, Canada, New Zealand and Australia, and of its [BBB complaints](https://www.bbb.org/us/ca/santa-monica/profile/health-and-wellness/headspace-usa-1216-348372/complaints).
  - Fix: nütn is free with no subscription. Make that explicit in onboarding and on store screenshots.
  - Sources: [Trustpilot Headspace](https://www.trustpilot.com/review/headspace.com), [UK](https://uk.trustpilot.com/review/headspace.com?page=6), [CA](https://ca.trustpilot.com/review/headspace.com?page=8) [snippets]
- **Calm: no warning before renewal, and no refund.** "did not receive a renewal reminder or notification that I was about to be charged."
  - Trustpilot's summary also notes "problems accessing the app despite paying" and "unhelpful automated systems."
  - Sources: [Trustpilot Calm p3](https://www.trustpilot.com/review/calm.com?page=3), [p4](https://www.trustpilot.com/review/calm.com?page=4) [snippets]
- **Fabulous: charged after cancelling a trial.**
  - An Apple Community thread (about 2025) is titled "Predatory scam app developer FABULOUS". The user cancelled the trial and kept being charged, including for a second app from the same developer.
  - A Trustpilot reviewer (developer reply dated March 2026) says the company tried several times to take £34.99 after the cancellation was confirmed.
  - A JustUseApp reviewer accuses it of "scamming people via free trials, charging after people they've cancelled".
  - Sources: [Apple Community](https://discussions.apple.com/thread/256002729); [Trustpilot NL](https://nl.trustpilot.com/reviews/69bc4213d3ca560f785b169d); [JustUseApp Fabulous](https://justuseapp.com/en/app/1203637303/fabulous-daily-routine-planner/reviews) [snippets]
- **Waking Up: price hikes drive long-time users away.**
  - "The pricing in Canada when up almost 100%. Used the app for 4 years but due to this crazy price increase I stopped my subscription."
  - In the UK, £139 a year was called unaffordable.
  - Users also report confusion over 30-day versus 15-day trials, a credit card required up front, and a paywall around day 7 of the intro course.
  - Sources: [Trustpilot Waking Up](https://www.trustpilot.com/review/wakingup.com) [snippet]; [productivity-apps.com](https://www.productivity-apps.com/apps/waking-up-meditation) [aggregator]
- **Day One: the switch to subscription angered long-time buyers.**
  - A forum post by a 13-year user: they bought the app in 2012 and now find it "no longer essential" at $49 a year. Australian regional pricing was about 63% higher. They ask for a lifetime option. (Post is about 261 days old, so roughly early 2026.)
  - Source: [Day One forum](https://forums.dayoneapp.com/forums/topic/feedback-from-a-13-year-user-app-complexity-workflow-changes-and-pricing-conc/); [Beebom](https://beebom.com/day-one-alternative-journal-apps/)
- **Finch: basic tasks behind a paywall, and "exploitative" in-app purchases.**
  - Quotes: "the more basic tasks (the ones I would like motivation to do) are locked behind a paywall". "monthly events used to be better, but now unless you pay you're hardly getting anything". "$10 a month subscription crazy expensive".
  - One App Store reviewer said the purchases "felt a tad exploitative ... given that people using a mental health app may be vulnerable."
  - Widespread? A minority view. Finch is rated about 4.9 with hundreds of thousands of reviews.
  - Sources: [Google Play Finch](https://play.google.com/store/apps/details?id=com.finch.finch&hl=en); [App Store UK reviews](https://apps.apple.com/gb/app/finch-self-care-pet/id1528595748?see-all=reviews) [snippets]; [snaptroid](https://snaptroid.co.uk/finch-app-review/) [secondhand]
- **Balance: a "free year" that felt locked.**
  - "This is the only free trial I've used where the software appeared to be fully locked."
  - A competitor blog warns of "sticker shock" when year two begins.
  - Sources: [JustUseApp Balance](https://justuseapp.com/en/app/1361356590/balance-meditation-sleep/reviews) [snippet]; [driftinward](https://driftinward.com/articles/discover/balance-app-alternative-2026/) [competitor blog]
- **Bearable: insights and history behind Premium.**
  - Some users reportedly churned because insights and older history are locked. Bearable's own pricing page confirms that Premium gates "correlations ... and the option to review historic health data."
  - Source: [aelivra](https://aelivra.co/explore/compare/bearable-app-review) [secondhand]

**C. Notification fatigue and pop-ups**
- **Fabulous: random pings that cannot be turned off on their own.**
  - "there are several other random notifications and emails from the app throughout the day ... I have not figured out a way to disable these notifications without silencing all notifications."
  - Users also get alerts for challenges they finished long ago, and "opening the app often means dismissing two or three messages" before doing anything.
  - Fix: separate toggles per notification category. Never send promotional pushes. Retire notifications for finished programs.
  - Sources: [Trustpilot IE Fabulous p7](https://ie.trustpilot.com/review/thefabulous.co?page=7); [appsupports negative reviews](https://appsupports.co/1203637303/fabulous-daily-routine-planner/negative-reviews) [snippets]
- **Fabulous: the rigid "journey" gates features.**
  - The app makes users drink water each morning for three days before other features unlock, and "you can't put your own goals into it."
  - Fix: let users pick their own goals from day 1.
  - Sources: [Healthline review](https://www.healthline.com/healthy/fabulous-app-review); [ChoosingTherapy Fabulous](https://www.choosingtherapy.com/fabulous-app-review/) [snippets]
- **Calm and Calm Health: unwanted pop-ups, even for paying users.**
  - "every time [I] go on the app there are pop ups". If users are paying, "there should be no ads or pop-ups."
  - Sources: [Calm Health App Store reviews](https://apps.apple.com/us/app/calm-health/id1669369516?see-all=reviews&platform=iphone); [Calm Google Play](https://play.google.com/store/apps/details?id=com.calm.android&hl=en) [snippets]
- **Habitica: excessive notifications, no offline mode, complexity.**
  - Sources: [AlternativeTo Habitica](https://www.alternativeto.net/software/habitica/about/) [snippet]
- **Novelty fades and alerts get ignored.** A community post says a new tracker feels useful for about three days, then "the wrong one is just another notification you learn to ignore."
  - Source: [myhabits.in community](https://myhabits.in/community/best-features-habit-tracker-app-adhd-brain) [secondhand]

**D. Guilt and anxiety caused by gamification**
- **Calm: the streak widget raises anxiety.** A reviewer on the main Calm App Store page says the large adherence and streak widget on the home screen is a "clumsy attempt at gamification [that] only serves to raise my anxiety, not lower it."
  - Fix: let users hide streaks and counters inside calm or meditation surfaces.
  - Source: [Calm App Store reviews (Mac)](https://apps.apple.com/us/app/calm/id571800810?see-all=reviews&platform=mac) [snippet]
- **Calm: only some content counts toward the streak.** Music and soundscapes do not count; only meditations and sleep stories do. Calm has to publish a support page on "How to Correct a Broken Streak" by manually adding sessions.
  - Fix: count any mindful activity, and allow honest backfill.
  - Sources: [Calm support: streaks](https://support.calm.com/hc/en-us/articles/115002473827-How-to-View-Your-Meditation-Stats-History-and-Streak-in-Calm); [Calm support: broken streak](https://support.calm.com/hc/en-us/articles/360008704893-How-to-Correct-a-Broken-Streak)
- **Meditation apps generally: a 200-day streak lost to a hospital stay.** A 2026 roundup quotes a user who "lost their 200-day streak after missing a day in the hospital."
  - Source: [unstar.app 2026 roundup](https://unstar.app/blog/mental-health-app-reviews-what-users-say-about-wellbeing-apps-2026) [secondhand; app not specified]
- **Habit trackers in general (Hacker News).**
  - "If you have a streak in the hundreds and then lose it inadvertently ... it can be crushing."
  - "Seeing streaks feels like some extra pressure attached."
  - One user said they would pay for an option to remove streaks completely. Others call Duolingo-style freezes essential.
  - Source: [Ask HN: What do you want in a habit tracker?](https://news.ycombinator.com/item?id=33842599) [snippet]
- **Habitica: the HP damage mechanic.**
  - An old GitHub issue is titled "Missed dailies do massive amounts of damage".
  - Habitica's own fan wiki says users with anxiety or depression struggle "even finding the energy to finish dailies ... in the worst case, it can result in a player leaving Habitica."
  - Habitica does offer a "pause damage" toggle. A 2024 neurodivergent review notes it has "no cost or downside to pausing."
  - Sources: [GitHub #3161](https://github.com/HabitRPG/habitica/issues/3161); [Habitica wiki: Adapting for Anxiety and Depression](https://habitica.fandom.com/wiki/Adapting_Habitica_for_Anxiety_and_Depression); [bipolarcoaster 2024](https://bipolarcoaster.blog/2024/08/31/neurodivergent-app-review-habitica/)
- **Habitica: rewards that stop working.**
  - The novelty wears off ("hedonic adaptation"). Self-reporting lets users tap from the couch. Users spend "more time managing Habitica than managing their actual habits."
  - Source: [pledgd blog](https://www.pledgd.com/blog/habitica-alternatives) [competitor blog; cites Reddit without links]
  - A 2025 G2 review is titled "Good idea, tiring on the long term". Source: [G2 Habitica](https://www.g2.com/sellers/habitica) [snippet]
  - An academic paper found that Habitica's mechanics "reward users for procrastination under certain circumstances". Source: [ResearchGate](https://www.researchgate.net/publication/327451529_Counterproductive_effects_of_gamification_An_analysis_on_the_example_of_the_gamified_task_manager_Habitica)

**E. Generic or repetitive prompts and content**
- **Reflectly: prompts stop helping after a few weeks.** "After a few weeks of use, the initial charm can begin to fade, and the guided prompts, once helpful, start to feel repetitive."
  - The AI is "closer to a well-designed prompt sequence than true personalized intelligence".
  - Sources: [Bestie 2024 Reflectly review](https://bestieai.app/topics/wellness/reflectly-app-review-good-bad-ai-alternative); [Rosebud roundup](https://www.rosebud.app/blog/best-journal-apps) [competitor blogs]
- **Stoic: prompts repeat after several months.** The AI "occasionally default[s] to generic motivational language", and long-time users note the app's focus has narrowed.
  - Sources: [selfpause Stoic review 2026](https://www.selfpause.com/resources/stoic); [reflection.app comparison](https://www.reflection.app/best-journaling-apps-compared/stoic-vs-reflectly) [competitor blogs]
- **Calm: the meditation library feels recycled.** "The meditation selection is repetitive and there's rarely new content". The soundscape-while-meditating option was removed. Of Daily Calm: "a bit repetitive after a while."
  - Sources: [Calm Health App Store reviews](https://apps.apple.com/us/app/calm-health/id1669369516?see-all=reviews&platform=iphone) [snippet]; [Product Hunt Calm reviews](https://www.producthunt.com/products/calm/reviews)
- **Finch: mood auto-detection and keywords.** The app "chooses your mood based on recognized words, which can sometimes be completely wrong". Journaling keywords "can be random". The gamification and companion features become "overcrowded and boring over time".
  - Source: [Lidiant Substack, ADHD mood-tracking review](https://lidiant.substack.com/p/random-adhd-lemon-1-mood-tracking)
  - Fix: let the user choose their own mood and emotion (nütn already does this), and adapt prompts to recent entries and questionnaire scores.

**F. Journal privacy (encryption, server storage, app lock)**
- **Day One: users object to journals stored on the developer's servers.** One reviewer doesn't "believe it's safe to have such personal data on the servers of DayOne developers" and wants iCloud instead.
  - Day One says entries are end-to-end encrypted (AES-GCM-256) and that this is on by default.
  - Sources: [JustUseApp Day One 2024](https://justuseapp.com/en/app/1044867788/day-one-journal-private-diary/reviews) [snippet]; [Day One privacy FAQ](https://dayoneapp.com/privacy-faqs/)
- **Day One: unexpected encryption-key prompts.** Users were asked for a key they never saved. Staff confirmed on 21 Apr 2025 that an iOS update prompted even users who had no encrypted journals.
  - Fix: if nütn encrypts, never strand users behind a key they did not knowingly create.
  - Source: [Day One forum](https://forums.dayoneapp.com/forums/topic/plus-user-encryption-key/)
- **Users want local-only storage for mood and journal data (Hacker News).** For a diary, cloud storage is "very privacy-intrusive". Users want optional sync and clear details on encryption at rest.
  - Source: [Show HN: Mood Tracker](https://news.ycombinator.com/item?id=20590555) [snippet]
- **Users want a separate journal password.** Face ID that falls back to the device passcode doesn't protect against family members who know that passcode.
  - Apple Journal locks with Face ID, Touch ID or passcode.
  - Sources: [BGR](https://www.bgr.com/tech/iphone-journal-app-is-now-available-but-theres-something-you-should-do-before-you-use-it/); [Apple Support](https://support.apple.com/guide/iphone/protect-your-journal-entries-iph9c59b1557/ios)
- **What a journal lock should include** (pattern from open-source app-lock work):
  - lock when the app opens and when it returns from the background;
  - a privacy cover in the app switcher;
  - hide entry text from widgets and notifications;
  - fall back to the passcode, with protection against locking yourself out.
  - Sources: [gaming-journal #69](https://github.com/TheRealestNwah/gaming-journal/issues/69); [echo PR #59](https://github.com/FrankDitz/echo/pull/59); [mise PR #103](https://github.com/MGRL2201/mise/pull/103)
- **Mozilla's 2022 audit of mental-health apps.** 28 of 32 mental-health and prayer apps got the "*Privacy Not Included" warning, including Calm, Headspace and Bearable. Mozilla called the category the worst it had reviewed in six years.
  - This audit is from 2022 and the apps may have changed since.
  - Source: [Mozilla Foundation](https://www.mozillafoundation.org/en/blog/top-mental-health-and-prayer-apps-fail-spectacularly-at-privacy-security/)

**G. Data loss and missing small features (How We Feel)**
- **Data loss on a phone change.** A user lost a year of logs and says "you can't restore your data."
- **Forced "Reason" page.** An update forced the Reason entry page. The user wants to skip it and says it "feels like data mining."
- **AI.** Users are uneasy about AI features, though it is off by default and can be disabled.
- **Missing features users ask for:**
  - a "neutral" mood;
  - editing timestamps;
  - a setting for when the day resets;
  - more useful charts;
  - an Apple Watch app.
- Sources: [JustUseApp How We Feel 2026](https://justuseapp.com/en/app/1562706384/how-we-feel/reviews); [App Store reviews](https://apps.apple.com/us/app/how-we-feel/id1562706384?see-all=reviews&platform=iphone); [Google Play](https://play.google.com/store/apps/details?id=org.howwefeel.moodmeter&hl=en_US) [snippets]

### Inferences
- **The biggest unmet need is honest pause and skip states, set per habit.** Every streak-based app forces users to choose between lying and losing their streak. Loop, Way of Life and Habitify fixed this, and their users notice.
- **Free with no trial matters most in meditation.** Billing complaints dominate the negative reviews of Headspace, Calm, Fabulous and Waking Up. In nütn's store copy, the strongest differentiator is "no trial, no card, no auto-renew", not any one feature.
- **Notifications need per-category controls and an off switch for anything that is not a reminder.** Fabulous shows that coach-style "nudges" mixed with reminders backfire.
- **Prompt fatigue sets in after weeks to months.** Static prompt lists will go stale. Rotating prompts tied to the user's recent mood, emotions and questionnaire trends would answer the "generic" complaint. This is an inference; no source tested it.

### Gaps
- I could not read Reddit, the App Store or Trustpilot directly, so there are no true counts of how often each complaint appears. "Widespread" is judged only from repetition across sources and from thumbs-up counts on GitHub.
- I found no 2024–2026 primary complaints about Daylio beyond round 1, and no Stoic or Reflectly user quotes (only competitor blogs).
- No recent Mozilla *Privacy Not Included* re-review (after 2023) of these specific apps turned up.

---

## 2. Which features do users praise?

### Takeaway
Users praise:
- **Flexibility and forgiveness:** Loop's decaying strength score, Way of Life's "skip" that doesn't break the chain, and Atoms' "never miss twice."
- **Emotion vocabulary and short strategies:** How We Feel.
- **Resurfacing and structure:** Day One's On This Day, templates and prompts.
- **Correlations:** Bearable, despite its setup burden.
- **Free with no paywall:** How We Feel, and Waking Up's scholarship.
- **HealthKit auto-completion and one-time pricing:** Streaks.
- **Gentle, structured sequences:** Balance.
- **Customisation and the Year in Pixels view:** Daylio.

### Cited Findings
- **Daylio: custom moods and activities, and Year in Pixels.**
  - Users can create custom moods with their own colour and emoji, and a customisable activity icon library. Year in Pixels "provides a very nice summary for your yearly emotions" and is "real motivation to keep a streak alive."
  - Criticism: it becomes "a mindless daily ritual that generates beautiful charts but zero actionable wisdom."
  - Sources: [moodtrackers.org review](https://moodtrackers.org/daylio-app-review/); [calmevo 2026](https://calmevo.com/daylio-review/); [ixcoach 2026](https://www.ixcoach.com/learn/daylio-mood-tracker-review-2026)
- **How We Feel: a rich emotion vocabulary, free, no ads.**
  - Quotes: "by far more comprehensive than any other check-in app"; "SO easy to use"; "entirely free and there are no features locked behind a paywall." It also works "like a private social media with just my friends" (sharing with friends).
  - Strategies are short videos of about one minute, grouped into cognitive, movement, mindfulness and social.
  - Sources: [App Store How We Feel](https://apps.apple.com/us/app/how-we-feel/id1562706384); [Wet Paint Art Therapy review](https://www.bethanyaltschwager.com/blog-1/2022/7/22/weekly-app-review); [Yale Medicine](https://medicine.yale.edu/news-article/the-how-we-feel-app-helping-emotions-work-for-us-not-against-us/)
- **Bearable: automatic correlations.**
  - The app finds links users "never would have connected on their own." Weekly correlation reports are useful to show doctors. Users consistently rate it the most thorough all-in-one tracker.
  - Sources: [aelivra](https://aelivra.co/explore/compare/bearable-app-review); [ChoosingTherapy Bearable](https://www.choosingtherapy.com/bearable-app-review/); [Despite Pain](https://despitepain.com/review-bearable-app-track-your-health/)
- **Way of Life: simple yes/no/skip with chains.**
  - "Seeing the chains grow keeps me going". Users wanted "a check box for whether they did it that day, yes or no". A skip does not break the streak, and users set their own target streak lengths.
  - Rated about 4.7–4.8 on the App Store.
  - One user wished for small celebrations, such as "confetti after a week."
  - Sources: [App Store Way of Life reviews](https://apps.apple.com/us/app/way-of-life-habit-tracker/id393159800?see-all=reviews&platform=iphone); [AppFollow](https://apps.appfollow.io/ios/way-of-life-habit-tracker/393159800?country=us); [JustUseApp](https://justuseapp.com/en/app/393159800/way-of-life-habit-tracker/reviews) [snippets]
- **Loop Habit Tracker: forgiveness, privacy and flexible schedules.**
  - It supports "3 times every week", "every other day" and similar schedules. Its strength score means "a few missed days after a long streak ... will not completely destroy your entire progress."
  - Data never leaves the phone, and no account is needed.
  - Sources: [Loop GitHub](https://github.com/vyu1/uhabits); [Google Play Loop](https://play.google.com/store/apps/details?id=org.isoron.uhabits&hl=en)
- **Atoms: identity framing and "never miss twice."**
  - Each check-in is "a vote for the type of person you want to be". "We keep streaks alive even if you miss a day if you show back up the next day."
  - Sources: [Fortune 2024](https://fortune.com/well/2024/02/14/atomic-habits-james-clear-app-goals-atoms); [YourStory 2024](https://yourstory.com/2024/05/james-clear-atoms-app-transform-habits)
- **Streaks: completion straight from HealthKit, and a one-time price.**
  - Link a task to Mindful Minutes and "Streaks marks it done automatically." Users value the one-time purchase over a subscription.
  - Sources: [makeheadway Streaks review](https://makeheadway.com/blog/streaks-app-review/); [mwm.ai](https://mwm.ai/apps/streaks/963034692)
- **Day One: On This Day, templates and prompts.**
  - On This Day is "one of Day One's most-loved features". "Creating Templates to prompt my thinking really helps me to keep my journaling habit solid."
  - Basic templates, prompts and On This Day are free; the AI "go deeper" prompts are paid.
  - Sources: [Day One releases](https://dayoneapp.com/releases/); [Day One features](https://dayoneapp.com/features/); [Google Play Day One](https://play.google.com/store/apps/details?id=com.dayoneapp.dayone&hl=en_US) [snippets]
- **Stoic: fixed morning and evening prompts.** Users say these keep a daily check-in habit going.
  - Source: [selfpause](https://www.selfpause.com/resources/stoic)
- **Balance: skills build up step by step.** Sessions start short and build up. Plans "slowly and methodically teach concrete skills." A daily check-in personalises the sessions.
  - Sources: [Vico Whitmore, Medium](https://vico-whitmore.medium.com/balance-app-review-ed3db5043e50); [JustUseApp Balance](https://justuseapp.com/en/app/1361356590/balance-meditation-sleep/reviews)
- **Waking Up: a free scholarship.**
  - "Free for Anyone Who Can't Afford It". Reviewers report getting a free year, or "100% off ... for 2 years", "no questions asked."
  - Sources: [App Store CA listing](https://apps.apple.com/ca/app/waking-up-meditation-wisdom/id1307736395); [innercalmguide](https://innercalmguide.com/articles/waking-up-review.html)
- **Interactive widgets.** On iOS 17+, users can tick off habits from the home screen without opening the app. Competitors advertise this; HabitKit and Habit Streak say lock-screen widgets are read-only.
  - Sources: [HabitKit help](https://www.habitkit.app/blog/ios-home-screen-widgets-habit-tracker/); [habit-streak.com](https://habit-streak.com/en/blog/app-guides/widgets-for-habit-tracking)
  - I found no user forum demand data for widgets.

### Inferences
- nütn's MIND module already covers the How We Feel pattern (free, emotion naming). The praised parts it could add are:
  - On This Day resurfacing;
  - a Year in Pixels or calendar heatmap;
  - templates;
  - one-minute strategies linked to the selected emotion;
  - an interactive tick-off widget;
  - automatic completion from HealthKit Mindful Minutes for breathwork.

### Gaps
- No primary user quotes praising Finch's gentle pet design or How We Feel's strategies were reachable, because Reddit is blocked.
- No data on how often widgets are used or how much users want them.

---

## 3. What do users with ADHD, depression or anxiety say helps or hurts? (user reports only)

### Takeaway
User and blogger reports agree:
- **What hurts:** punishing mechanics (Habitica HP damage, streak resets, a pet you "let down"), streak counters on calm surfaces, and alert floods.
- **What helps:** low-effort check-ins, structure broken into small steps (Fabulous journeys, Balance), forgiving or pausable systems (Habitica's pause, Loop's score, Finch "not a chore"), and emotion naming.

Direct first-person quotes from people with these conditions are scarce in reachable sources.

### Cited Findings
- **Anxiety and depression, on Finch:** other journaling apps and mood trackers "all felt like a chore, but not Finch."
  - Source: [alternativeto / Finch user](https://alternativeto.net/software/finch--self-care-pet/about) [snippet]
- **ADHD, on Finch (author's view):** missing a day turns into avoidance because reopening the app means facing guilt about the pet. "missing a streak or letting a cute pet down lands harder than it should". The problem starts when the check-in "starts generating more guilt than motivation".
  - Source: [Noodl](https://noodl.prepshotz.com/blog/finch-app-alternative-adhd/) [competitor blog; opinion]
- **ADHD, on Finch (positive):** it helps "your brain feel unstuck when tasks aren't clearly laid out or feel too big to start."
  - Source: [Yahoo Tech](https://tech.yahoo.com/apps/articles/8-android-apps-rescue-stress-140910138.html)
- **ADHD blogger on Finch:** the gamification became "overcrowded and boring over time", the app "wasn't satisfying my needs anymore, so I moved on", and mood auto-detection was sometimes "completely wrong."
  - Source: [Lidiant Substack](https://lidiant.substack.com/p/random-adhd-lemon-1-mood-tracking)
- **Depression and anxiety, on Habitica:** users struggle with "even finding the energy to finish dailies" and may leave the app. The community advises pausing damage and keeping dailies few and small.
  - Sources: [Habitica wiki](https://habitica.fandom.com/wiki/Adapting_Habitica_for_Anxiety_and_Depression); [bipolarcoaster 2024 neurodivergent review](https://bipolarcoaster.blog/2024/08/31/neurodivergent-app-review-habitica/)
- **ADHD and rejection sensitivity, on Habitica:** HP loss "can create shame spirals."
  - Source: [checkthat.ai](https://checkthat.ai/brands/habitica/alternatives) [competitor-style opinion]
- **Anxiety, on Calm's streak widget:** "only serves to raise my anxiety, not lower it."
  - Source: [Calm App Store reviews](https://apps.apple.com/us/app/calm/id571800810?see-all=reviews&platform=mac) [snippet]
- **ADHD and structure, on Fabulous:** "Many users with ADHD-adjacent tendencies" find its Journeys helpful "because they break routines into small, clearly defined steps." Others call the same journeys inflexible.
  - Sources: [theliven](https://theliven.com/blog/wellbeing/dopamine-management/fabulous-app-review); [ChoosingTherapy](https://www.choosingtherapy.com/fabulous-app-review/)
- **ADHD and notifications:** "just another notification you learn to ignore". An unsourced claim says ADHD apps "lose 40%+ users within two weeks" (no method given; don't use it).
  - Sources: [myhabits.in](https://myhabits.in/community/best-features-habit-tracker-app-adhd-brain); [sproutapp](https://www.sproutapp.tech/blog/adhd-habit-tracker) [vendor blog]
- **Bad days:** people skip logging "on exactly the days that matter most, the bad ones" when logging feels like a task.
  - Source: [vantagefit](https://www.vantagefit.io/en/blog/best-mood-tracker-apps/) [blog]
- **Mental-health use of Bearable:** it "can work just as well for someone with anxiety or depression". Setup can take more than 10 minutes to log everything, and users feel overwhelmed.
  - Sources: [Despite Pain](https://despitepain.com/review-bearable-app-track-your-health/); [aelivra](https://aelivra.co/explore/compare/bearable-app-review)
- **Vulnerability and money:** Finch's purchases "felt a tad exploitative ... given that people using a mental health app may be vulnerable."
  - Source: [Finch App Store UK](https://apps.apple.com/gb/app/finch-self-care-pet/id1528595748?see-all=reviews) [snippet]

### Inferences
- Design rules for nütn these reports suggest:
  - streaks can be hidden or paused in MIND;
  - no penalties, only "welcome back" messages after gaps;
  - the minimum viable check-in counts in full;
  - no upsell prompts anywhere near low-mood states (nütn has no paywall anyway).

### Gaps
- There are no reachable first-person Reddit posts from r/ADHD or r/depression; Reddit returned 403.
- No user-reported data specific to How We Feel or Bearable for ADHD.
- No sources specifically on users finding PHQ- or GAD-style questionnaires in apps helpful or distressing.

---

## 4. What makes users abandon these apps?

### Takeaway
Reported reasons fall into five groups:
1. Money: price hikes, trial traps, and paywalls on history and insights.
2. Penalties: punishing mechanics that turn one miss into avoidance.
3. Novelty fade: in gamification and in content or prompts.
4. Effort: setup and logging take too long (Bearable, Habitica's upkeep).
5. Lost trust: data loss on a device change, intrusive pop-ups and notifications, and being forced into features (How We Feel's Reason page, Fabulous gating).

### Cited Findings
- **Price hike:** "Used the app for 4 years but due to this crazy price increase I stopped my subscription" (Waking Up). Source: [Trustpilot](https://www.trustpilot.com/review/wakingup.com) [snippet]
- **Subscription switch:** a 13-year Day One user now finds the app "no longer essential" at $49 a year. Source: [Day One forum](https://forums.dayoneapp.com/forums/topic/feedback-from-a-13-year-user-app-complexity-workflow-changes-and-pricing-conc/)
- **Access restrictions:** a paying Waking Up user quit after the web app blocked VPNs. Source: [Trustpilot](https://www.trustpilot.com/review/wakingup.com) [snippet]
- **Novelty decay:**
  - Habitica: "novelty decay ... core loop cannot scale". Source: [pledgd](https://www.pledgd.com/blog/habitica-alternatives) [competitor blog]
  - Reflectly: "initial charm can begin to fade". Source: [Bestie](https://bestieai.app/topics/wellness/reflectly-app-review-good-bad-ai-alternative)
  - Finch: "overcrowded and boring over time". Source: [Lidiant](https://lidiant.substack.com/p/random-adhd-lemon-1-mood-tracking)
- **Admin overhead:** users spend more time managing Habitica than doing the habits. Source: [pledgd](https://www.pledgd.com/blog/habitica-alternatives) [secondhand]
- **Setup burden:** Bearable takes more than 10 minutes to log everything, and the flexibility overwhelms new users. Source: [aelivra](https://aelivra.co/explore/compare/bearable-app-review)
- **Data loss:** a How We Feel user lost a year of logs after changing phones. Source: [JustUseApp How We Feel](https://justuseapp.com/en/app/1562706384/how-we-feel/reviews) [snippet]
- **Offline requirement:** Habitica needs an internet connection, a "breaking 'feature'" for one reviewer who stopped before even creating a character. Source: [AlternativeTo Habitica](https://www.alternativeto.net/software/habitica/about/)
- **Tester abandonment:** reviewers tested apps for 90 days, and "most were abandoned by week 2." This is a self-run test, not a population statistic. Source: [expirel](https://expirel.com/best-apps-for-habit-tracking) [blog]
- **Notification fatigue:** Fabulous sends irrelevant alerts for challenges finished long ago. Source: [appsupports](https://appsupports.co/1203637303/fabulous-daily-routine-planner/negative-reviews) [snippet]
- **Content runs out:** Calm users report recycled meditations, cycling "through about eight favorites by week four" of sleep stories. Sources: [autonomous.ai Calm review](https://www.autonomous.ai/ourblog/calm-app-review); [Calm Health App Store](https://apps.apple.com/us/app/calm-health/id1669369516?see-all=reviews&platform=iphone)
- **UI churn:** Headspace redesigns made favourite courses harder to find (attributed to Reddit). Source: [makeheadway Headspace review](https://makeheadway.com/blog/headspace-app-review/) [secondhand]

### Inferences
- The causes of abandonment map to concrete nütn safeguards:
  - lifetime-free messaging;
  - pause and illness mode;
  - streaks that can be hidden;
  - "welcome back" with no penalty;
  - prompts that rotate and adapt;
  - CSV/JSON export plus iCloud backup, so a reinstall never loses data (round 1 covered the backup paywall; this is the device-change angle);
  - optional journal lock;
  - per-category notification toggles;
  - quick starter templates instead of a long setup.

### Gaps
- I found no independent retention studies (for example in JMIR) with abandonment rates for these specific apps.
- The Habitica 2024 JMIR Serious Games study is cited by pledgd, but I could not verify it.
- I found no reliable 2024–2026 reports about Headspace removing streaks or similar features.
