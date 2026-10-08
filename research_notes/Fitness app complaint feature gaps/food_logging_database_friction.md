# Food Logging: Database Accuracy and Logging-Friction Complaints (MyFitnessPal, Cronometer, Lose It!, FatSecret, Yazio, MacroFactor, Carbon)

> **Method and source-quality note (read first).** I collected this research on 2026-10-08. From this environment, direct fetches of reddit.com, trustpilot.com, apps.apple.com, forums.cronometer.com and community.myfitnesspal.com were **blocked**: the proxy denied the connection or DNS failed. So every user quote below came through web-search result excerpts. The excerpts quote the underlying page, but I could not open the full threads. Reddit quotes appear only where another indexed page (a news write-up, a review site) reproduced them.
>
> A large share of the comparison content online is **SEO marketing by competing apps**: Nutrola, NutriScan, PlateLens, Fitia, Hoot, Bento Bunny, Amy Food Journal, unstar.app, ai-food-tracker.com, calorie-trackers.com and similar sites. Their numbers are flagged where cited. MacroFactor's own speed data is self-published, since Stronger By Science is the developer.
>
> Loudness ratings (HIGH / MEDIUM / LOW / SINGLE-ANECDOTE) are my judgment. They rest on how many independent source types repeat a complaint, not on measured counts, except where a count is given.

## 1. Food database complaints (user-submitted/duplicate entries, wrong barcodes, missing regional/branded/restaurant foods, verified-entry problems, international users)

### Takeaway
The loudest, most durable database complaint concerns **MyFitnessPal's crowdsourced database**. A search returns many duplicate entries with conflicting values, and nothing tells the user which one is right. Lose It!, FatSecret and Yazio draw the same complaint with less volume.

The reverse complaint hits the **curated databases** (Cronometer, MacroFactor): they are accurate but **too small**, with gaps in branded, restaurant and non-US foods. Users say they are pushed back to MFP or forced into custom-food entry. Neither model solves the problem users actually voice: "show me which entry to trust, and let me fix it."

### Cited Findings

**MyFitnessPal: duplicates and conflicting entries (HIGH; recurring for 10+ years and still current in 2026)**
- MFP community forum thread titles show the complaint keeps coming back: "Why are MFP food entries so wildly inaccurate?", "There is SO much items in the database with incorrect nutritional values.", "Barcode scanner pulling incorrect products?", "Wrong information when scanned." — [MFP Community: wildly inaccurate](https://community.myfitnesspal.com/en/discussion/10804613/why-are-mfp-food-entries-so-wildly-inaccurate); [MFP Community: SO much items incorrect](https://community.myfitnesspal.com/en/discussion/10862172/there-is-so-much-items-in-the-database-with-incorrect-nutritional-values); [MFP Community: barcode pulling incorrect products](https://community.myfitnesspal.com/en/discussion/10911919/barcode-scanner-pulling-incorrect-products); [MFP Community: wrong info when scanned](https://community.myfitnesspal.com/en/discussion/10603533/wrong-information-when-scanned)
- One MFP forum user tested the barcode scanner on "at least 10 different items and only 1 turned up correctly". SINGLE-ANECDOTE, undated in the excerpt. — [MFP Community (via search excerpt)](https://community.myfitnesspal.com/en/discussion/1192054/has-anyone-notices-the-scanner-doesnt-always-get-it-right)
- A teardown review searched for a chain sandwich and got **eleven results whose calorie values spanned about 200 kcal**. It notes that picking a wrong community entry "is silent and there is no signal to warn you." Green-check "verified" entries are better but "only cover branded products." — [the-app-reviewer.com MFP teardown](https://the-app-reviewer.com/teardowns/myfitnesspal/)
- A long-time MFP user on the Cronometer forum: the database "has become both it's biggest strength, and one of it's biggest weaknesses. It has millions of items, but a vast majority of them are user generated". The same thread says member input was "often lacking or just plain wrong". The thread is **older (about 2019)**. — [Cronometer forum: Chronometer or Myfitnesspal?](https://forums.cronometer.com/discussion/3080/chronometer-or-myfitnesspal)
- Competitor-blog claims (flagged as biased) describe a "wall of entries" for banana ranging from 72 to 121 kcal, and say anyone can submit with "no requirement to cite a source, no nutritionist review, and no automated deduplication". — [Nutrola (competitor): MFP database full of wrong entries](https://nutrola.app/en/blog/myfitnesspal-database-full-of-wrong-entries)
- Error magnitude: a 2026 blog review of validation studies (not independently verified) says barcode-scanned packaged foods are close to reference values. Restaurant dishes, home recipes and generic free-text entries, "where user-submitted data dominates", can drift **100 to 500 kcal** in either direction. — [kcalm.app research review](https://kcalm.app/blog/myfitnesspal-vs-cronometer-accuracy-research-review/)
- MFP recipe import "has calorie counts and nutritional info that is way off (much higher) than the nutritional facts on the website I imported from". A reply says you must "go through every ingredient and work out if MFP has picked something appropriate from the database and/or parsed the correct quantity. It often doesn't." — [MFP Community: imported recipe doesn't match](https://community.myfitnesspal.com/en/discussion/10873514/imported-recipe-doesnt-match-websites-nutrition-info)
- Older but useful as a reference point: a Dutch peer-reviewed barcode study found **FatSecret had the most incorrectly identified products (10%)**, while MyFitnessPal and Yazio had about 1%. **OLDER, about 2018.** — [Public Health Nutrition (Cambridge)](https://www.cambridge.org/core/journals/public-health-nutrition/article/food-identification-by-barcode-scanning-in-the-netherlands-a-quality-assessment-of-labelled-food-product-databases-underlying-popular-nutrition-applications/89358D29215F914E8B6ED31777FF99FC)

**Lose It! (MEDIUM)**
- Reviews describe the database as "largely user-submitted, with similar verification weakness as MyFitnessPal". A long-time user says "there are A LOT of foods that just aren't on here" and creates their own entries. — [Trustpilot Lose It! (via search excerpt)](https://www.trustpilot.com/review/loseit.com?page=2); [calorietrackerlab Lose It review](https://calorietrackerlab.com/reviews/lose-it/)

**Yazio (MEDIUM, with structural issues confirmed by Yazio's own help pages)**
- A Google Play reviewer says nutrition info is often wrong. They could not edit an existing entry or create their own version when one already existed. — [Yazio Google Play listing (via search excerpt)](https://play.google.com/store/apps/details?id=com.yazio.android&hl=en_US)
- Yazio's help center confirms that **a barcode "cannot be changed once it has been assigned to a food"**, so a wrongly mapped barcode can't be reassigned by users. Users can edit name, producer and nutrition of public foods, but "not possible to edit the original serving size." — [Yazio Help: edit public foods](https://help.yazio.com/hc/en-us/articles/4576053290001-How-can-I-edit-public-foods)
- A competitor claims Yazio's search mixes manufacturer-verified, community and branded entries with no clear label, so "users routinely pick the first plausible-looking result" (biased source). — [Nutrola (competitor): Yazio wrong entries](https://nutrola.app/en/blog/yazio-database-full-of-wrong-entries)
- Yazio is strong for DACH and European brands and weaker for North American and Asian foods. — [Nutrola (competitor), cited via search](https://nutrola.app/en/blog/why-is-yazio-so-inaccurate)

**FatSecret (LOW-MEDIUM)**
- "Barcode entries arrive with errors, and serving sizes vary between duplicate foods". Reviews also say there is no verification indicator on entries. These are competitor blogs. — [NutriScan (competitor): FatSecret alternatives](https://nutriscan.app/blog/posts/best-fatsecret-alternatives-2026-570c8b0fab); [Nutrola (competitor): FatSecret review](https://nutrola.app/en/blog/fatsecret-review-2026)
- On the positive side, FatSecret supports a kJ/kcal "Swap Units" toggle to match non-US labels. — [FatSecret help](https://www.fatsecret.com/fatsecret-app-help/getting-started/cant-find-food)

**Cronometer: curated but too small (MEDIUM; mostly a "missing food" complaint, not an accuracy one)**
- Users report missing restaurant items: no plain Wendy's double stack, and Panera and McDonald's items not searchable, so they had to be copied from earlier diary entries. Staff suggested creating custom foods. — [Cronometer forum: restaurant/fast food](https://forums.cronometer.com/discussion/2470/how-to-input-restaurant-or-fast-food-options)
- "A lot of food was missing from the database which means that I still have to enter foods manually." — [Cronometer forum: Many many things missing](https://forums.cronometer.com/discussion/comment/6750)
- Foods disappear from search because curated entries for older product versions are retired. — [Cronometer forum: foods not showing up](https://forums.cronometer.com/discussion/3518/many-foods-not-showing-up-anymore-on-browser)
- A feature request asks for generic restaurant menu items ("Cronometer doesn't have much in the way of generic menu items"). The poll had only 5 votes, so low demand signal. — [Cronometer forum: generic restaurant foods](https://forums.cronometer.com/discussion/4038/should-cronometer-database-include-generic-restaurant-food-options)
- Cronometer's own docs admit that branded and restaurant entries carry only label nutrients. — [Cronometer blog: accurate data tips](https://cronometer.com/blog/accurate-data-tips/)
- A European user argued that Cronometer's carb handling mis-fits EU labels (net vs total carbs). Staff said the web version lets you pick other label formats. Older. — [Cronometer forum, via search](https://forums.cronometer.com/discussion/3080/chronometer-or-myfitnesspal)

**MacroFactor: curated but gaps (MEDIUM)**
- App Store: "I got my girlfriend a subscription too but she went back to myfitnesspal due to the abysmal food database in this app." Another review: "the database just doesn't have enough of the items I eat on a daily basis to move from myFitnessPal." — [MacroFactor App Store reviews (via search excerpt)](https://apps.apple.com/us/app/macrofactor-macro-tracker/id1553503471?see-all=reviews&platform=iphone)
- Outlift: "Macrofactor was slower to expand because it uses a verified food database. It's now quite good internationally, but it took almost two years to get there." — [Outlift MacroFactor review](https://outlift.com/macrofactor-review/)
- A justuseapp-aggregated review says some foods don't appear in search or the barcode scanner, so the user falls back to quick-add macros. — [justuseapp MacroFactor reviews](https://justuseapp.com/en/app/1553503471/macrofactor-diet-sidekick/reviews)
- MacroFactor states 1.36M verified search foods plus about 4M barcode entries (vendor figure). — [MacroFactor vs Cal AI](https://macrofactor.com/macrofactor-vs-cal-ai/)

**Carbon Diet Coach (LOW volume, split opinion)**
- Google Play: "the food search is pretty bad. Like, I will type the exact name and it won't pop up". The reviewer says this discourages logging. — [Carbon Google Play (via search excerpt)](https://play.google.com/store/apps/details?id=com.joincarbon.nutrition&hl=en_US)
- Reviewers contradict this. FeastGood says the "food database was impressive", and Garage Gym Revisited calls it "extensive". — [FeastGood Carbon review](https://feastgood.com/carbon-diet-coach-review/); [Garage Gym Revisited](https://garagegymrevisited.com/carbon-diet-coach/)
- A review site lists "limited food DB" as a weakness. — [macro-trackers.com Carbon](https://www.macro-trackers.com/reviews/carbon)

**International and regional**
- Common causes of wrong values: reformulated products with stale data, a serving size different from the label default, and "the barcode mapped to the wrong product (a regional mismatch...)". — [getdietly developer note](https://www.getdietly.com/developers/missing-nutrition-data/)
- AI and photo recognition is notably worse on non-Western cuisines. One benchmark reports MFP Meal Scan at 58.3% identification on East Asian and 61.1% on South Asian dishes. Competitor-run, biased. — [ai-food-tracker.com MFP](https://ai-food-tracker.com/reviews/myfitnesspal/)
- A peer-reviewed 2024 study called for AI training "especially for mixed dishes and culturally diverse foods". — [Nutrients 2024 (MDPI)](https://www.mdpi.com/2072-6643/16/15/2573)

**Raw vs cooked entries (MEDIUM, a chronic source of silent error)**
- Searching "chicken breast" returns entries labeled raw, cooked, or unspecified. A user-submitted "pasta, 100g, 350 cal" could be dry pasta or a mislabeled cooked weight. — [Nutrola (competitor)](https://nutrola.app/en/blog/raw-vs-cooked-weight-the-biggest-calorie-tracking-mistake)
- A Fitbit community user uses "25% loss as a guide" when they can't weigh raw food. — [Fitbit Community](https://community.fitbit.com/t5/Healthy-Eating/Weighing-Food-cooked-or-raw/td-p/4742041)
- A vendor blog cites a "62% unsure raw vs cooked" survey statistic (IFIC 2019). I could not verify it, so treat it as unconfirmed. — [Nutrola (competitor)](https://nutrola.app/en/blog/raw-vs-cooked-weight-calorie-difference-why-it-confuses-everyone)

### Inferences
- The unmet need is **trust signaling and correction**, not raw database size. Users of big crowdsourced DBs (MFP, Lose It!, Yazio, FatSecret) can't tell which entry is right. Users of curated DBs (Cronometer, MacroFactor) can't find their food. An app that ranks verified entries first, collapses duplicates, shows a source or confidence badge, and makes "fix this entry / remap this barcode" a one-tap action addresses both camps.
- The silent nature of the error makes it worse: users discover it only when weight doesn't move. "Silent", "no signal" and "after the first month" phrasing recurs in reviews.
- The international, regional-barcode and kJ issues are under-served across all apps except Yazio (EU) and FatSecret (kJ toggle).

### Gaps
- I could not read Reddit threads directly (blocked). I have no direct r/loseit, r/MyFitnessPal, r/Cronometer or r/MacroFactor quotes about databases beyond those reproduced on other sites.
- I found no independent, quantified complaint-frequency analysis (e.g., % of 1-star reviews mentioning database accuracy) other than a competitor's analysis of MFP reviews that I could not open (unstar.app, blocked).
- A March 2024 MyFitnessPal "data corruption" incident is discussed on a personal blog ([blog.kamens.us](https://blog.kamens.us/2024/03/27/myfitnesspal-is-not-telling-the-whole-truth-about-recent-data-corruption-incident/)). I could not read its content, so its relevance to diary or database integrity is unverified.

## 2. Logging friction (taps, search ranking, serving/unit confusion, recipe builder, copying meals/days, quick add, templates, editing past entries, eating out, home cooking)

### Takeaway
Friction complaints cluster around four things:
1. **Search-then-pick-then-adjust-portion** loops; Hacker News calls this the core pain.
2. **Serving-unit mismatches**: you can't log in grams, cups aren't offered, and recipes are stuck in "servings."
3. **Recipe building and import**: tedious and error-prone.
4. **Copy and repeat-meal regressions** after redesigns.

MyFitnessPal's April 2026 "Today" redesign is the single loudest recent friction event. It added taps, buried the diary and broke single-item copy. MacroFactor's whole pitch is fewer taps plus history-driven suggestions.

### Cited Findings

**Search-select-adjust is the core pain (HIGH)**
- Hacker News: MyFitnessPal meant "searching, choosing an entry, and adjusting portions, which took much longer". A developer of a plain-text logger describes database-search apps as slow, with user-submitted entries that are often wrong. — [HN 44220135](https://news.ycombinator.com/item?id=44220135); [HN 47185429](https://news.ycombinator.com/item?id=47185429)
- Hacker News (older, 2024): "data entry is one of the biggest sources of friction". — [HN 40053711](https://news.ycombinator.com/item?id=40053711)
- Carbon: typing the exact name doesn't surface the food (see section 1). — [Carbon Google Play](https://play.google.com/store/apps/details?id=com.joincarbon.nutrition&hl=en_US)
- Cronometer's "search experience requires more taps and selections than modern competitors"; its "interface feels technical, and daily logging can be time-consuming" (third-party reviews). A Cronometer forum user on a redesign: "there's a lot of friction to use it, just to use it as a diary and tracker" (SINGLE-ANECDOTE). — [welling.ai MacroFactor vs Cronometer](https://www.welling.ai/articles/macrofactor-vs-cronometer-2026); [Cronometer forum comment](https://forums.cronometer.com/discussion/comment/18542)

**Tap counts (vendor-measured, directional only)**
- MacroFactor's own "Food Logging Speed Index" counts the actions for the same tasks:

  | Task | MacroFactor | MyFitnessPal | Cronometer |
  |---|---|---|---|
  | Food search | 10 | 15 | 17 |
  | Barcode | 5 | 7 | — |
  | Multi-add | 6 | 9 | — |
  | Four workflows total | 24 | 36 | — |

  Cronometer comes out about 1.7x MacroFactor's actions overall. The analysis was done in **May 2022**. — [MacroFactor vs MyFitnessPal](https://macrofactor.com/macrofactor-vs-myfitnesspal-2025/); [MacroFactor vs Cronometer](https://macrofactor.com/macrofactor-vs-cronometer/); [Macroo, noting the 2022 date](https://www.macroo.app/blog/macrofactor-vs-myfitnesspal)
- A secondhand timing claim puts Cronometer at about 45 s per meal and MacroFactor at about 35 s. Unverified; cited by competitor NutriScan. — [NutriScan](https://nutriscan.app/blog/posts/macrofactor-vs-cronometer-2026-62a278ee64)

**MyFitnessPal April 2026 redesign: copy, diary and taps (HIGH, current)**
- v26.16.0 (April 21, 2026) replaced the Diary tab with a card-based "Today" screen. Users must "tap into each meal to see its contents". The diary sits behind "View All". Analytics firm mwm reported the rating fell **from 3.24 to 1.54 stars** (single source, unverified against the App Store). — [mwm.ai](https://mwm.ai/articles/app-updates/myfitnesspal-v26-16-0-replaces-diary-with-new-ui-sparking-rating-drop-in-april-2026); [PiunikaWeb](https://piunikaweb.com/2026/04/24/myfitnesspal-new-update-complaints/)
- A Reddit user (quoted by press) says the diary "has been ruined by being converted to a list of gigantic, space-consuming cards". — [PiunikaWeb](https://piunikaweb.com/2026/04/24/myfitnesspal-new-update-complaints/)
- The update removed copying of **individual food items** between meals. An official MFP Reddit account advised copying the whole meal and deleting unwanted items. — [mwm.ai](https://mwm.ai/articles/myfitnesspal-v26-16-0-replaces-diary-with-new-ui-sparking-rating-drop-in-april-2026)
- MFP forum ("New Interface Flawed"):
  - "no longer possible to copy an entire day"
  - "meals are collapsed into summaries which adds an extra step"
  - a bug: "Log More" adds to a custom meal "get logged by default to breakfast", made harder to spot by the collapsed view.
  
  Another thread says "you can no longer choose which items from the day to copy and paste over all at once." — [MFP Community: New Interface Flawed](https://community.myfitnesspal.com/en/discussion/10957519/new-interface-flawed); [MFP Community: Complaints about the new interface](https://community.myfitnesspal.com/en/discussion/10960299/complaints-about-the-new-interface); [MFP Community: Bring back old layout](https://community.myfitnesspal.com/en/discussion/10950832/bring-back-old-layout)
- MFP says the Today tab is "the path forward", with no option to revert, and it set up a feedback webform. — [MFP Support](https://support.myfitnesspal.com/hc/en-us/articles/45276346234637-New-App-Experience-Today-Tab-and-More); [MFP Blog](https://blog.myfitnesspal.com/myfitnesspal-today-screen-progress-tab-update/)
- An earlier 2025 rollout reportedly removed copying meals from previous days. — [Consumer Rights Wiki](https://consumerrights.wiki/w/MyFitnessPal_regressive_upgrade)

**Yazio: added screens and lost quick logging (MEDIUM)**
- Google Play: a recent update added screens, so the user must go through several menus to log a meal. Trustpilot: a multi-year daily user quit because there was "no possibility to quickly log meals". Users also complain about post-log pop-ups and "healthy tips" (called "judgmental", with eating-disorder concern) and about streak nags. — [Yazio Google Play](https://play.google.com/store/apps/details?id=com.yazio.android&hl=en_US); [Trustpilot Yazio](https://www.trustpilot.com/review/yazio.com)

**Lose It!: ads during entry (MEDIUM)**
- "very intrusive ads that highjack the screen just as you are trying to enter meal data" (Trustpilot). Users also criticize a recent cluttered UI redesign. — [Trustpilot Lose It!](https://www.trustpilot.com/review/loseit.com?page=2)
- Cronometer's free tier is "increasingly disrupted by full-screen video ads" (Fitia, a competitor). — [Fitia](https://fitia.app/learn/article/best-cronometer-alternatives-2026/)

**Serving-size and unit confusion (HIGH for MFP recipes, MEDIUM elsewhere)**
- MFP recipes output only "servings". Users ask for a gram option; the thread "Allow gram option when creating a recipe" exists. The universal workaround: "If I make (say) 1057 grams of lasagna, it's 1057 servings. When I eat 223 grams of the lasagna, I'd log 223 servings." — [MFP Community: Allow gram option](https://community.myfitnesspal.com/en/discussion/10926417/allow-gram-option-when-creating-a-recipe); [MFP Community: Recipe serving size confusion](https://community.myfitnesspal.com/en/discussion/10722091/recipe-serving-size-confusion-in-myfitnesspal/p2); [MFP Community: Units of Measure for Create Recipe](https://community.myfitnesspal.com/en/discussion/10897109/units-of-measure-for-create-recipe)
- MacroFactor App Store: "some foods won't give me the option to select cup, tbsp etc. It'll only show grams, oz, serving, lb". — [MacroFactor App Store reviews](https://apps.apple.com/us/app/macrofactor-macro-tracker/id1553503471?see-all=reviews&platform=iphone)
- Yazio: "Unable to adjust amounts". Users also ask to see what quantity an AI estimate assumed. — [Trustpilot Yazio](https://www.trustpilot.com/review/yazio.com)
- On Yazio public foods, "not possible to edit the original serving size." — [Yazio Help](https://help.yazio.com/hc/en-us/articles/4576053290001-How-can-I-edit-public-foods)

**Recipe builder and import (MEDIUM-HIGH)**
- MFP recipe import:
  - Failures: "Page not found"; the recipe_parser URL errors.
  - Ingredient-match failures force manual verification, and the replacement search is "just not very obvious".
  - Counterpoint: one user imported about 35 recipes with only 1 failure.
  - Posts span 2021–2024.
  
  — [MFP Community: problems importing recipes](https://community.myfitnesspal.com/en/discussion/10908651/problems-importing-recipes); [MFP Community: Can no longer import recipes](https://community.myfitnesspal.com/en/discussion/10903190/can-no-longer-import-recipes); [MFP Community: Recipe imports](https://community.myfitnesspal.com/en/discussion/10867526/recipe-imports)
- Cronometer "recipe logging clunky" (Fitia, competitor). A multi-ingredient dish means "searching for and entering each component separately". — [Fitia](https://fitia.app/learn/article/best-cronometer-alternatives-2026/); [Nutrola/welling via search](https://www.welling.ai/articles/macrofactor-vs-cronometer-2026)
- Cronometer has a "Cooked Recipe Weight" feature, but users report a bug when "exploding" a recipe with a cooked weight. They ask to set cooked weight via quick-adjust without deleting the diary item. — [Cronometer forum: Cooked Recipe Weight vs Explode](https://forums.cronometer.com/discussion/4753/cooked-recipe-weight-vs-explode-recipe-energy); [Cronometer forum: adjust recipe](https://forums.cronometer.com/discussion/5717/change-to-adjust-recipe-feature)
- Carbon: no recipe import from URLs (competitor claim). "Retroactively making adjustments can be annoying" (Garage Gym Revisited). — [Nutrola (competitor)](https://nutrola.app/en/blog/is-carbon-diet-coach-worth-it-2026); [Garage Gym Revisited](https://garagegymrevisited.com/carbon-diet-coach/)
- MacroFactor:
  - One reviewer says custom foods didn't show up when adding food and there was "no option for your recipes". This is contradicted by other reviews that say recipes are supported.
  - "for a multi-component plate that's several entries" (Bento Bunny).
  - SINGLE-ANECDOTE: meal items duplicated until the app was restarted.
  
  — [justuseapp MacroFactor](https://justuseapp.com/en/app/1553503471/macrofactor-diet-sidekick/reviews); [Bento Bunny](https://www.bentobunny.app/reviews/macrofactor-review)

**Eating out / restaurant (MEDIUM)**
- Cronometer: restaurant foods are missing and users must improvise (see section 1).
- MacroFactor positions AI as better than beginners for restaurant meals, where people "forget to account for sauces". — [MacroFactor Help: AI Food Logging](https://help.macrofactorapp.com/en/articles/258-ai-food-logging)

**Expectation shift toward AI and chat (emerging, LOW-MEDIUM)**
- A late-2025 MacroFactor App Store reviewer says food logging "feels totally outdated" compared with logging through AI chat tools. — [MacroFactor App Store (via search)](https://apps.apple.com/ca/app/macrofactor-macro-tracker/id1553503471?see-all=reviews&platform=ipad)

### Inferences
- **Repeat-meal speed is the biggest lever.** People eat the same breakfasts. The loudest 2026 backlash (MFP) was about breaking copy and repeat flows, and MacroFactor's most-cited advantage is history-driven suggestions.
- **Grams-first everywhere**: recipes logged by weight, with unit conversions always available (g, oz, cup, tbsp, piece). Users already use clumsy "1 serving = 1 g" workarounds.
- **A home-cooking "batch recipe" flow** would hit a clear, repeated pain: enter ingredients raw, weigh the cooked pot, log the portion by grams.
- **Never put ads or nags inside the entry flow.** Complaints about ads and post-log tips are specifically about interruption at the moment of entry.

### Gaps
- I found no independent (non-vendor) tap or time benchmark across apps. The MacroFactor index is self-published and from 2022.
- I found few concrete complaints about "editing past entries" or "quick add" specifically. Quick add appears mostly as a workaround when the DB lacks a food.
- I found no specific complaint data on meal templates or "saved meals" beyond the copy regressions.

## 3. Barcode scanning, photo/AI logging (MFP Meal Scan, Cal AI, Lose It! Snap It, MacroFactor AI), voice logging: accuracy and trust

### Takeaway
**Barcode** complaints are mostly about **paywalls** (MFP and Lose It! moved scanning to Premium) and **wrong mappings**, especially for non-US products.

**Photo AI** draws the sharpest accuracy criticism. A July 2026 study found four popular apps undercounted by **about 250–345 kcal per meal**. Users report inconsistent numbers for the same plate, failures on mixed dishes and hidden oils, and portion misjudgment.

AI becomes trustworthy when it returns **editable, itemized entries** that the user can verify (MacroFactor's approach, plus "Photo & Text"). A single opaque number earns less trust. Voice logging has almost no independent accuracy data.

### Cited Findings

**Barcode paywall (HIGH for MFP, MEDIUM for Lose It!)**
- MFP moved Barcode Scan to Premium. **OLDER: the change dates to about 2022**, and it is still a top complaint. A competitor's analysis of 202 negative MFP reviews found 59 mention Premium or paywall, and 27 name the barcode scanner. Competitor-run (unstar.app); I couldn't open it, so this rests on the search excerpt. — [punishedbacklog](https://punishedbacklog.com/hey-myfitnesspal-were-not-paying-for-a-damn-barcode-scanner/); [MFP Community: Scan barcode only for premium?](https://community.myfitnesspal.com/en/discussion/10903889/scan-barcode-only-for-premium); [unstar.app (competitor), via search](https://unstar.app/blog/is-myfitnesspal-premium-worth-it-paywall-app-reviews-2026)
- As of Feb 2026, MFP Premium ($79.99/yr) unlocks Meal Scan, Barcode Scan and Voice Log; Premium+ is $99.99/yr. — [MFP Winter 2026 release (AOL)](https://lite.aol.com/sports/other/story/0022/20260224/9659625.htm)
- Lose It!: "Now you have to pay a membership fee in order to get the barcode scanner to work." The help center reportedly says Lose It! is moving Scan It and the label scanner to Premium. Sources conflict on the current status. — [Trustpilot Lose It!](https://www.trustpilot.com/review/loseit.com?page=2); [fitbudd](https://www.fitbudd.com/post/lose-it-premium-review)
- Yazio barcode is praised as "finds nearly everything scanned", but wrong mappings can't be fixed by users (see section 1). — [Yazio App Store reviews (via search)](https://apps.apple.com/us/app/ai-calorie-tracker-by-yazio/id946099227?see-all=reviews)
- Competitor-run 100-barcode test: Yazio found 82/100 with 6 major errors; FatSecret found 88/100 with 15 major errors. Biased; I could not verify the methodology. — [Nutrola (competitor)](https://nutrola.app/en/blog/we-scanned-100-barcodes-in-8-calorie-apps-accuracy-results)
- MacroFactor barcode outside North America is called unreliable (unsourced review-site claim). — [fuelnutrition MacroFactor review](https://fuelnutrition.app/reviews/macrofactor-review)

**Photo AI accuracy: research (strongest evidence)**
- **July 2026 study (ScienceDaily):**
  - 102 meals were photographed into MyFitnessPal, Lose It!, Cal AI and Appediet.
  - All four **underestimated calories by about 250–345 kcal per meal** on average and underestimated fat by about 30 g.
  - MFP and Lose It! were more accurate on higher-calorie meals than on lower-calorie ones.
  - The lead researcher's advice: people using photo apps "without adjusting the portions or entering the amounts of food should take the results with a grain of salt."
  
  — [ScienceDaily, Jul 2026](https://www.sciencedaily.com/releases/2026/07/260726015237.htm); [Yahoo coverage](https://creators.yahoo.com/lifestyle/story/scientists-find-ai-calorie-counting-apps-may-underestimate-meals-by-hundreds-of-calories-045417483.html)
- **Nutrients 2024 (peer-reviewed):**
  - Food-identification accuracy across AI-enabled apps: MyFitnessPal 97%, Fastic 92%, **Lose It! and FatSecret 46% each** (18/39).
  - The authors concluded that "automatic energy estimations from AI-enabled food image recognition were inaccurate".
  - They called for better handling of mixed dishes and culturally diverse foods.
  
  — [Nutrients 2024, MDPI](https://www.mdpi.com/2072-6643/16/15/2573); [PMC mirror](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC11314244/)
- Treat with suspicion: pages reporting PlateLens at 1.1% MAPE versus MFP at 11.2% ("Dietary Assessment Initiative", "clinicalnutritionreport.com" meta-analysis) look like they may be affiliated with or promoting PlateLens. Do not rely on them without verifying the authors. — [dietaryassessmentinitiative.org](https://dietaryassessmentinitiative.org/publications/six-app-validation-study-2026/); [clinicalnutritionreport.com](https://clinicalnutritionreport.com/research/ai-calorie-tracker-accuracy-meta-analysis-2026/)

**Cal AI (HIGH volume of accuracy complaints relative to its fame)**
- CNBC: customer reviews show "numerous complaints about the app's accuracy". Users must still manually input what the app can't detect and correct errors. The founder claims about 90% accuracy; a Reddit user notes the claim comes with "zero citations". — [CNBC, Sep 2025](https://www.cnbc.com/2025/09/06/cal-ai-how-a-teenage-ceo-built-a-fast-growing-calorie-tracking-app.html)
- User reviews:
  - An 18 oz steak was logged at about **23,000 kcal**.
  - "highly inaccurate" compared with the plate, so the user stopped using photo.
  - Persistent "error in processing the photo".
  - Positive: "usually accurate to within 10 percent" over the first weeks.
  
  — [justuseapp Cal AI reviews](https://justuseapp.com/en/app/6480417616/cal-ai-calorie-tracking/reviews); [Cal AI App Store](https://apps.apple.com/us/app/cal-ai-calorie-tracker/id6480417616)
- Review sites report:
  - Mixed meals with a 30–50%+ error margin.
  - Re-scanning after a portion correction returns "a different wrong number" — the app doesn't learn from edits.
  - Users also cite billing friction during the trial.
  
  — [calorierankings Cal AI](https://calorierankings.com/reviews/cal-ai/); [fuelnutrition Cal AI](https://fuelnutrition.app/reviews/cal-ai-review)

**MFP Meal Scan (MEDIUM)**
- FeastGood hands-on: Meal Scan "pulled up a ton of suggestions that I had to choose from (some of which were correct, most of which were not)... no more efficient than simply manually adding my food". Favorites were faster for repeat meals. — [FeastGood meal scan test](https://feastgood.com/meal-scan-accuracy-for-nutrition-apps/)
- Competitor benchmark: 71.2% identification overall, with a 58.3% East Asian and 61.1% South Asian subset. Biased. — [ai-food-tracker.com](https://ai-food-tracker.com/reviews/myfitnesspal/)
- Feb 2026: MFP added "Photo Upload" (log later from a plate photo) for Premium iOS users. — [MFP Winter 2026 release](https://lite.aol.com/sports/other/story/0022/20260224/9659625.htm)

**Lose It! Snap It (MEDIUM)**
- A user quoted by Hoot (a competitor) says calorie estimation from a photo "doesn't work", is "misleading for new users", and should be removed. — [Hoot Fitness (competitor)](https://www.hootfitness.com/blog/best-lose-it-alternatives-faster-logging-smarter-feedback)
- One review found the category was identified about 70% of the time, but a bowl of pasta was logged at 400–700 kcal "depending on angle and lighting". Snap It returns candidate lists that need confirmation and is Premium-only. — [Amy Food Journal (competitor-adjacent)](https://www.amyfoodjournal.com/blog/lose-it-app-review); [Bento Bunny](https://www.bentobunny.app/reviews/lose-it-review)
- Another benchmark reported 68.7% identification, ±22% portion error and an 11.2 s median (competitor). — [ai-food-tracker.com Lose It!](https://ai-food-tracker.com/reviews/lose-it/)
- At its 2016 launch, the CEO said a picture alone could not reliably identify food (**OLDER**). — [Engadget 2016](https://www.engadget.com/2016-09-29-lose-it-snap-it-app.html)

**Yazio photo AI (LOW-MEDIUM)**
- Trustpilot complaints: a very large bowl of pasta was analysed as a small portion, and the same photo gave different results on re-upload. Users ask the app to show which quantity the estimate assumed. — [Trustpilot Yazio](https://www.trustpilot.com/review/yazio.com)

**Consistency across photo apps**
- HN plain-text-logger developer: photo-scan apps gave inconsistent numbers for the same plate. — [HN 47185429](https://news.ycombinator.com/item?id=47185429)

**What makes AI trustworthy (design signals from sources)**
- MacroFactor AI returns **editable itemized entries** and offers "Photo & Text" for complex meals. It recommends that "everyone reviews their AI results before logging", good lighting, top-down shots, and a fist or common object in frame for scale. — [MacroFactor Help: AI Food Logging](https://help.macrofactorapp.com/en/articles/258-ai-food-logging); [MacroFactor blog](https://macrofactor.com/ai-food-logging/)
- Reviewers advise checking "fats, sauces, calorie-dense toppings, large starch portions, and branded products". "The image is a starting point, not ground truth." — [Amy Food Journal MacroFactor review](https://www.amyfoodjournal.com/blog/macrofactor-review)
- Recognition is easier than portioning: real-world performance "is limited by portion size estimation, occlusion, mixed dishes, lighting variability, camera angle, and cultural diversity". — [fitia AI photo accuracy (competitor) via search](https://fitia.app/learn/article/ai-calorie-photo-apps-accuracy-2026/)

**Voice logging**
- I found no independent accuracy data. One review notes that Meal Scan, voice and search all resolve to a selected database entry and amount, so voice inherits database-match and oil/sauce uncertainty. — [Amy Food Journal MFP review](https://www.amyfoodjournal.com/blog/myfitnesspal-review)

### Inferences
- Photo AI's error is **directionally biased low** (the July 2026 study). That is the worst direction for weight-loss users and could explain stalls; an app could counter it with "hidden fat/oil" prompts.
- Trust comes from **transparency plus editability**: itemized foods, a visible assumed gram weight per item, and a confidence flag. An instant number, a re-roll and learning from corrections all matter too.
- Barcode is "table stakes". Paywalling it is a top driver of negative reviews, so a free and accurate barcode flow plus label-photo OCR for missing items is a differentiator.

### Gaps
- I found no rigorous voice-logging accuracy studies.
- I found no independent tests of MacroFactor's AI photo accuracy. The FeastGood four-app comparison results were cut off in the excerpt.
- I could not verify the unstar.app review-count statistics directly (domain blocked).

## 4. Features users cite as the reason they SWITCHED

### Takeaway
There are two main switching vectors:
- **MFP → Cronometer** for verified data and micronutrient accuracy. Cronometer says 64% of its users tried MFP first.
- **MFP or Cronometer → MacroFactor** for logging speed, history-driven suggestions, no ads and the adaptive coach.

Reverse switches do happen. **MacroFactor or Cronometer → back to MFP** happens because the curated database lacks everyday foods. The **paywalling of barcode scanning and macros** (MFP, Lose It!) and **disruptive redesigns** (MFP 2026, Yazio) push people out.

### Cited Findings
- Cronometer's own survey: "as much as 64% of Cronometer users try or use ... MyFitnessPal, before coming over to us". Its blog also says many miss MFP's community. Vendor data. — [Cronometer blog: MFP to Cronometer](https://cronometer.com/blog/my-fitness-pal-to-cronometer/)
- Cronometer pitches staff-reviewed submissions and lab-analysed sources (e.g., NCC, University of Minnesota) as the accuracy draw. Vendor claim. — [Cronometer blog](https://cronometer.com/blog/my-fitness-pal-to-cronometer/)
- MFP-to-Cronometer switchers cite frustration that MFP member input "was often lacking or just plain wrong" (older forum post). — [Cronometer forum](https://forums.cronometer.com/discussion/3080/chronometer-or-myfitnesspal)
- MacroFactor's switch pitch is "50% fewer taps/clicks" than MFP. The figure is vendor-derived, from 2022. — [BroBible](https://brobible.com/gear/article/why-choosing-macrofactor-over-myfitnesspal-is-the-easiest-decision-ever/); [MacroFactor vs MFP](https://macrofactor.com/macrofactor-vs-myfitnesspal/)
- The MacroFactor feature most cited for speed is history: "after a few days, your most frequent breakfast foods float to the top when you open breakfast logging", without manually curating favorites. — [Macroo comparison](https://www.macroo.app/blog/macrofactor-vs-myfitnesspal)
- A long-time MacroFactor user credits quick barcode scans and a large food library for staying two years. — [MacroFactor App Store reviews](https://apps.apple.com/us/app/macrofactor-macro-tracker/id1553503471?see-all=reviews&platform=iphone)
- Reverse switch: a partner "went back to myfitnesspal due to the abysmal food database". Another reviewer did not move from MFP because of database gaps. — [MacroFactor App Store reviews](https://apps.apple.com/us/app/macrofactor-macro-tracker/id1553503471?see-all=reviews&platform=iphone)
- MacroFactor having no free tier is a blocker: "no free option, just waste of time" (App Store). — [MacroFactor App Store](https://apps.apple.com/us/app/macrofactor-macro-tracker/id1553503471)
- Push factors out of MFP:
  - The barcode paywall (27 of 202 negative reviews in a competitor analysis).
  - The April 2026 Today redesign; the rating reportedly fell from 3.24 to 1.54.
  
  — [unstar.app via search](https://unstar.app/blog/is-myfitnesspal-premium-worth-it-paywall-app-reviews-2026); [mwm.ai](https://mwm.ai/articles/app-updates/myfitnesspal-v26-16-0-replaces-diary-with-new-ui-sparking-rating-drop-in-april-2026)
- Push factors out of Lose It!:
  - Macros paywalled; a Reddit user quoted: "The lose it app now doesn't let you see your daily macros without a subscription."
  - The barcode move to Premium.
  - Auto-renew and cancellation complaints.
  
  — [Trustpilot Lose It! / search aggregation](https://www.trustpilot.com/review/loseit.com?page=2)
- Push factor out of Yazio: lost quick logging after an update. — [Trustpilot Yazio](https://www.trustpilot.com/review/yazio.com)
- Cal AI users leave over accuracy on complex meals and trial billing friction (review site). — [calorierankings Cal AI](https://calorierankings.com/reviews/cal-ai/)

### Inferences
- The ideal switch target combines **Cronometer-grade trust** (verified-first, source shown), **MFP-grade coverage** (branded, restaurant, international via barcode and label OCR fallback), and **MacroFactor-grade speed** (history-ranked suggestions, minimal taps). It must also leave core logging — barcode, macros, copy — un-paywalled and ad-free.
- **Coverage is the main reason people return to MFP**, so a curated database alone isn't enough. A trusted fallback is needed: label-photo OCR to create the food, plus community entries clearly badged as unverified.

### Gaps
- I found no survey or quantitative study of switching reasons. All evidence comes from vendor claims, reviews and forum anecdotes.
- Reddit "why I switched" threads (r/MacroFactor, r/Cronometer) could not be accessed directly.

## 5. Recurring "I wish it would…" feature requests

### Takeaway
The requests that recur fall into a handful of groups, below. Each item is sourced in sections 1–4; the key ones are repeated here.

### Cited Findings
- **Units and recipes**
  - Log recipes in grams instead of "servings". MFP forum threads: "Allow gram option when creating a recipe", "Recipe with serving size in grams", "Units of Measure for Create Recipe". — [MFP Community](https://community.myfitnesspal.com/en/discussion/10926417/allow-gram-option-when-creating-a-recipe); [MFP Community](https://community.myfitnesspal.com/en/discussion/10435568/recipe-with-serving-size-in-grams); [MFP Community](https://community.myfitnesspal.com/en/discussion/10897109/units-of-measure-for-create-recipe)
  - Offer household units (cup/tbsp) alongside weight. — [MacroFactor App Store reviews](https://apps.apple.com/us/app/macrofactor-macro-tracker/id1553503471?see-all=reviews&platform=iphone)
  - Adjust a recipe's cooked weight quickly, without deleting the diary item. — [Cronometer forum](https://forums.cronometer.com/discussion/5717/change-to-adjust-recipe-feature)
- **Copying and editing**
  - Bring back single-item copy, whole-day copy and multi-select copy (MFP 2026). — [MFP Community](https://community.myfitnesspal.com/en/discussion/10957519/new-interface-flawed); [mwm.ai](https://mwm.ai/articles/myfitnesspal-v26-16-0-replaces-diary-with-new-ui-sparking-rating-drop-in-april-2026)
  - "Bring back old layout": a scrollable single-list diary. — [MFP Community](https://community.myfitnesspal.com/en/discussion/10950832/bring-back-old-layout)
  - Let me edit or override a wrong public entry, or create my own version of it (Yazio). — [Yazio Google Play](https://play.google.com/store/apps/details?id=com.yazio.android&hl=en_US); [Yazio Help](https://help.yazio.com/hc/en-us/articles/4576053290001-How-can-I-edit-public-foods)
- **Restaurant coverage**: generic restaurant and menu items (Cronometer; low vote count). — [Cronometer forum](https://forums.cronometer.com/discussion/4038/should-cronometer-database-include-generic-restaurant-food-options)
- **AI transparency**
  - Show the quantity the AI estimate is based on (Yazio). — [Trustpilot Yazio](https://www.trustpilot.com/review/yazio.com)
  - Remove or label misleading photo estimates (Lose It! Snap It user, via competitor blog). — [Hoot Fitness](https://www.hootfitness.com/blog/best-lose-it-alternatives-faster-logging-smarter-feedback)
  - Learn from my corrections instead of re-guessing (Cal AI; review site). — [calorierankings](https://calorierankings.com/reviews/cal-ai/)
- **Free core logging**: keep barcode scanning and macro view free (MFP, Lose It!). — [MFP Community](https://community.myfitnesspal.com/en/discussion/10903889/scan-barcode-only-for-premium); [Trustpilot Lose It!](https://www.trustpilot.com/review/loseit.com?page=2)
- **No interruptions during entry**: no ads, pop-ups or "healthy tips" mid-entry (Lose It!, Yazio, Cronometer free tier). — [Trustpilot Lose It!](https://www.trustpilot.com/review/loseit.com?page=2); [Trustpilot Yazio](https://www.trustpilot.com/review/yazio.com); [Fitia](https://fitia.app/learn/article/best-cronometer-alternatives-2026/)
- **Free-text and chat logging** ("just type what I ate"), with an expectation set by AI chat tools. — [HN 47185429](https://news.ycombinator.com/item?id=47185429); [MacroFactor App Store (late 2025)](https://apps.apple.com/ca/app/macrofactor-macro-tracker/id1553503471?see-all=reviews&platform=ipad)
- **Recipe import that works**: import from URL that matches ingredients correctly and lets you swap a bad match easily (MFP; Carbon lacks URL import). — [MFP Community](https://community.myfitnesspal.com/en/discussion/10873514/imported-recipe-doesnt-match-websites-nutrition-info); [Nutrola (competitor) on Carbon](https://nutrola.app/en/blog/is-carbon-diet-coach-worth-it-2026)

### Inferences
- A feature list that would answer the most-repeated complaints:
  1. A verified-first, deduplicated search with a source/confidence badge.
  2. One-tap "report/fix entry" and barcode remap.
  3. Label-photo OCR to create missing foods.
  4. Grams-first logging with all units convertible.
  5. A batch-cook recipe flow: raw ingredients, cooked total weight, log by grams.
  6. History-ranked suggestions per meal slot.
  7. Copy item, meal or day, with multi-select.
  8. Itemized, editable AI (photo, text, voice) that shows assumed grams and prompts for oils and sauces.
  9. No paywall or ads on core logging.

### Gaps
- I could not count frequency per request. Reddit and the full app-store review corpora were inaccessible, so I based ordering on the number of independent source types rather than counts.
