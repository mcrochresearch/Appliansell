# nütn current feature inventory (source code, master @ e65b126, 8 Oct 2026)

Scope: what the nütn app does **today**, read from the code in the read-only checkout `/home/user/forged-worktrees/master-ro` (HEAD `e65b126985dd`, "Ship audit: every button, every action — 195 defects fixed…", #211). Every finding cites a file path (relative to the repo root; links point into the checkout). Status labels: **HAVE** (works end to end in the shipping build), **PARTIAL** (exists but limited, degraded, or needs something extra), **GATED** (behind a flag, env var, or backend), **UNMOUNTED/DEAD** (code exists, nothing reaches it), **WEB-ONLY**, **GAP** (absent).

Abbreviations: FEED = food module, IRON = workouts, REST = sleep/recovery, FORGE/MIND = mood/journal/coach. "Legacy shell" = the four-module UI that ships by default. "v7" = the five-screen shell that is opt-in.

## 0. Which UI ships, and what every feature depends on

### Takeaway
The shipping UI is the **legacy four-module shell** (home CommandCenter, FORGE/MIND, IRON, FEED, REST). The v7 shell (Today/Log/Move/Reflect/You) is **opt-in per device**: a Profile toggle, or the internal build flag `VITE_V7_SHELL=true`. Data is offline-first in local storage. Cloud sync, AI coach, label-photo scan and server-side food search all need env-configured back ends (Supabase plus a FastAPI backend whose model is by default a **local MLX Qwen model**). The app is iOS only, built with Capacitor; a web build exists for tests and Pages.

### Cited Findings
- v7 is opt-in. App.jsx reads the per-device key `kn_v7_shell`, and `VITE_V7_SHELL=true` only changes the default. The comment reads: "Legacy modules are the shipping surface; the v7 shell renders only when the stored flag is true." — [nutn-app/src/App.jsx:L77-81, L217, L615-616](/home/user/forged-worktrees/master-ro/nutn-app/src/App.jsx)
- The `build:ios` script does not set the v7 flag. Only `build:ios:internal` sets `VITE_V7_SHELL=true`. — [nutn-app/package.json](/home/user/forged-worktrees/master-ro/nutn-app/package.json)
- There is a "v7 shell (preview)" toggle in Profile. — [nutn-app/src/components/ProfileScreen.jsx:L1239](/home/user/forged-worktrees/master-ro/nutn-app/src/components/ProfileScreen.jsx)
- v7 is "a shell plus five dashboards, 871 lines against the legacy modules' 10,491". Its screens hand the actual work to legacy modules through `onOpenLegacyScreen` "excursions". Progress table: logging was brought inside v7 (food search, barcode, label photo, describe, recipes, manual entry; workouts from empty/mesocycle/recent/favourite, with supersets). REST was folded into Today as a "first cut"; HRV, exposure and supplements are still REST-tab only. Thirteen long-tail tools sit under You → More. Things deliberately left in FEED/IRON: "custom-food builder, meal templates, copy-yesterday; Smart Generate and program setup". — [nutn-app/V7-MIGRATION.md](/home/user/forged-worktrees/master-ro/nutn-app/V7-MIGRATION.md)
- The only release feature flag is `FEATURES.COMMUNITY: false`, with the reason "no report-or-block moderation yet (App Review 1.2) — off for 2.0". — [nutn-app/src/config/features.js](/home/user/forged-worktrees/master-ro/nutn-app/src/config/features.js)
- Stack: React 19 + Vite 5, Capacitor 6 iOS, Supabase (auth + sync), FastAPI backend ("authenticated proxy for the AI coach and server-side services; the app never holds a model provider key"). Bundle ID `com.kiln.kilnapp`, version 2.0, minimum iOS 16. — [nutn-app/README.md](/home/user/forged-worktrees/master-ro/nutn-app/README.md)
- Front-end env vars are `VITE_BACKEND_URL`, `VITE_SUPABASE_URL`, `VITE_SUPABASE_ANON_KEY`, `VITE_USDA_API_KEY` (fallback), `VITE_OURA_CLIENT_ID` and `VITE_WHOOP_CLIENT_ID`. In `.env.example`, `VITE_BACKEND_URL` is empty. — [nutn-app/README.md](/home/user/forged-worktrees/master-ro/nutn-app/README.md), [nutn-app/.env.example](/home/user/forged-worktrees/master-ro/nutn-app/.env.example)
- Native plugins linked into the iOS build: App, Browser, Camera, Filesystem, Haptics, Keyboard, LocalNotifications, Preferences, Share, StatusBar, and @perfood/capacitor-healthkit. `@capacitor-mlkit/barcode-scanning` is in package.json but **not** in the SPM package. — [nutn-app/ios/App/CapApp-SPM/Package.swift](/home/user/forged-worktrees/master-ro/nutn-app/ios/App/CapApp-SPM/Package.swift), [nutn-app/capacitor.config.ts](/home/user/forged-worktrees/master-ro/nutn-app/capacitor.config.ts)
- The latest audit (RUN-LEDGER) pressed 971 of 1,021 UI handlers (95%) across 12 lanes. Round 1 confirmed and fixed 80 findings and round 2 fixed 79 more, each with a regression test. Handlers it did not press "sit on screens nothing mounts, or need native iOS, a backend scan result, or an owner-only clinical path". — [ship-audit/RUN-LEDGER.md](/home/user/forged-worktrees/master-ro/ship-audit/RUN-LEDGER.md)

### Inferences
- When mapping complaints, treat the legacy modules as what users actually see. A v7 capability counts as shipped only for someone who turns on the preview toggle.
- Any feature that calls the backend (coach chat, label-photo scan, lab-PDF parse, server-side food search) depends on a deployed backend and a reachable model host. With the defaults (`MODEL_PROVIDER=local`, MLX on a separate machine), those features are fragile in production.

### Gaps
- I could not confirm which env values the App Store / TestFlight binary was built with (whether `VITE_BACKEND_URL` and Supabase are set). `Info.plist` app-bound domains list a Supabase project and `188-166-54-193.sslip.io`, which suggests a backend host is configured ([nutn-app/ios/App/App/Info.plist:L49-54](/home/user/forged-worktrees/master-ro/nutn-app/ios/App/App/Info.plist)), but the source does not prove it.

## 1. Food logging (FEED)

### Takeaway
FEED is broad. It has an offline table, USDA and Open Food Facts search, typed barcode lookup, recipes, custom foods, meal templates, copy-from-day, quick add, water, fasting, adaptive TDEE with a weekly check-in, diet programs with diet breaks, MFP and Cronometer CSV import, and CSV/JSON export. The weak spots: **camera barcode scanning is not in the iOS build** (you type the digits); **photo AI meal recognition does not exist** (only nutrition-label photo OCR, and that needs a backend vision model); **voice logging is web-only** (native relies on keyboard dictation into a text parser); recipe URL import likely fails on iOS because of CORS; portions are a servings multiplier with no g/oz/cup unit picker.

### Status table
| Feature | Status | Evidence |
|---|---|---|
| Offline food table | HAVE (small) | 82 entries, although the header says "300 most commonly logged foods" |
| USDA FoodData Central | HAVE / GATED | via backend `/api/food/*` (falls back to `DEMO_KEY` when no key) or a direct `VITE_USDA_API_KEY` call |
| Open Food Facts | HAVE | client hits `world.openfoodfacts.org/api/v2` directly, and also via backend |
| Verification tiers (Gold/Verified/Community) | HAVE | `FOOD_TIERS`, `assignTier`, sorting by tier |
| Barcode: camera scan | GAP in the shipped build | MLKit plugin not linked; code gates on `isPluginAvailable('BarcodeScanner')` |
| Barcode: typed digits | HAVE (needs network) | `BarcodeEntry` → `lookupBarcodeUnified` (backend → cache → OFF → USDA) |
| Nutrition-label photo scan | GATED | camera → backend `/api/feed/scan-label` → owner's vision model; 503 → "type the values" |
| Photo / AI meal (dish) recognition | GAP | no dish-recognition route; aiMealAnalysis.js says it is served via labelScanner (label only) |
| Describe / natural-language logging | HAVE (rule parser) | `parseNaturalLanguageItems` splits "2 eggs and toast" → search terms + counts; no LLM |
| Voice logging | WEB-ONLY | Web Speech API hidden on native; no mic usage strings; native = typed or keyboard dictation |
| Recipes (build, servings, log) | HAVE | RecipeList/Build/Detail screens |
| Recipe URL import | PARTIAL | direct fetch + JSON-LD parse; code says "CORS will block most sites"; manual fallback |
| Custom foods | HAVE | `CustomFoodBuilder` |
| Meal templates / save-as-meal | HAVE (legacy FEED only) | `TEMPLATES` screen, `MealTemplateCard`, save-as-meal prompt |
| Copy yesterday / copy from any day | HAVE (legacy FEED only) | `CopyFromScreen` (copy meal type, single meal, entire day); `duplicateMeal` |
| Favourites / frequent foods | HAVE | favourites + `foodFrequency`; v7 shows frequent foods |
| Multi-add "plate" | HAVE | `plate` staging in LogMealScreen and in v7 FoodLogger |
| Quick add (calories/macros only) | HAVE | `QuickAddModal` (cal/P/C/F), `QuickAddBar` |
| Manual entry | HAVE | manual form in LogMealScreen and v7 |
| Serving units | PARTIAL | servings multiplier on the food's own serving; non-weight servings normalised to per-100 g; remembers last serving per food; no g/oz/cup/household picker found |
| Micronutrients | HAVE (data-dependent) | `MICRONUTRIENTS_54` field list; `MicronutrientDashboard`; full micros mainly from USDA records |
| Water | HAVE | `WaterScreen` (oz), target from `waterTargetOz` |
| Caffeine / supplements log | HAVE | `SupplementsScreen`; `CAFFEINE_LOG` key synced |
| Fasting timer | HAVE | `FastingTimer`, protocols table (16:8 …), fasting insights |
| Adaptive TDEE / weekly check-in | HAVE | MacroFactor-style engine, `WeeklyTDEECheckin` |
| Diet programs / calorie cycling | HAVE | "Diet" screen: program, dynamic cycling from training data, protein per lb |
| Diet breaks / metabolic adaptation | HAVE | `shouldRecommendDietBreak`, `detectMetabolicAdaptation`; activating sets `dietBreakActive` |
| Targets | HAVE | Coaching screen (goal, weekly rate, goal weight); Profile "Daily Targets (Auto-Calculated)" |
| Weight log / trend | HAVE | WeightScreen with EMA chart; weight projection |
| Import from MFP / Cronometer | HAVE (CSV, daily totals) | `parseMFPExport`, `parseCronometerExport` wired in DataExport |
| CSV export | HAVE | Meals CSV, Weight CSV, Workouts CSV, full JSON backup |
| Write nutrition to Apple Health | GAP | `WRITE_PERMISSIONS = []`; plist says "nütn never writes to Apple Health" |
| Period / cycle tracker | HAVE (in FEED) | `PeriodTracker` mounted on the `PERIOD` screen |

### Cited Findings
- FEED screen list: DASH, LOG, DETAIL, WATER, SUPPS, WEIGHT, COACHING, RECIPES, RECIPE_BUILD, RECIPE_DETAIL, AI_PHOTO, TEMPLATES, CALORIE_CYCLING, CHECKIN, CUSTOM_FOODS, MICROS, TRENDS, COPY_FROM, FASTING, VOICE_LOG, RECIPE_IMPORT, PERIOD, PROGRAM_STYLE. — [nutn-app/src/components/FeedModule.jsx:L401-417](/home/user/forged-worktrees/master-ro/nutn-app/src/components/FeedModule.jsx)
- Offline table comment: "300 most commonly logged foods … Used as the first search source before hitting the network". `grep "id: 'of_"` counts **82** entries. — [nutn-app/src/data/foodDatabase.js:L1-18](/home/user/forged-worktrees/master-ro/nutn-app/src/data/foodDatabase.js)
- `searchFoodsLive`: "The built-in offline table answers first", then remote results are merged in, and it returns `offline` / `usdaUnavailable` flags. — [nutn-app/src/services/foodApi.js:L1319-1411](/home/user/forged-worktrees/master-ro/nutn-app/src/services/foodApi.js)
- OFF base URL `https://world.openfoodfacts.org/api/v2`. The backend `/api/food/search`, `/api/food/detail/{fdcId}` and `/api/food/barcode/{code}` are used when `VITE_BACKEND_URL` is set. — [nutn-app/src/services/foodApi.js:L282, L836-1068, L1147-1268](/home/user/forged-worktrees/master-ro/nutn-app/src/services/foodApi.js); routes at [nutn-app/backend/routers/food.py:L50, L70, L87](/home/user/forged-worktrees/master-ro/nutn-app/backend/routers/food.py)
- Backend food proxy: "`USDA_API_KEY` (food proxy `/api/food/*`; `DEMO_KEY` with a logged warning if unset)", 7-day SQLite cache, per-user limit of `60/hour`. — [nutn-app/README.md](/home/user/forged-worktrees/master-ro/nutn-app/README.md)
- Barcode: "The MLKit scanner plugin is not linked into the shipped iOS build, so the 'Scan' button used to fail every time. When native scanning is unavailable the Log screen shows this field instead". Offline it says "barcode lookup needs a connection". — [nutn-app/src/components/feed/BarcodeEntry.jsx:L1-8](/home/user/forged-worktrees/master-ro/nutn-app/src/components/feed/BarcodeEntry.jsx); gate at [nutn-app/src/services/native.js:L381-404](/home/user/forged-worktrees/master-ro/nutn-app/src/services/native.js)
- Label scan: "POST it to the nütn backend (`/api/feed/scan-label`), which runs the owner's local vision model … the backend answers 503 `vision_model_not_configured` when no vision model is wired up". The fallback message is "Photo label scanning isn't available yet — type the label values instead". — [nutn-app/src/services/labelScanner.js:L1-27](/home/user/forged-worktrees/master-ro/nutn-app/src/services/labelScanner.js); route at [nutn-app/backend/routers/feed.py:L143](/home/user/forged-worktrees/master-ro/nutn-app/backend/routers/feed.py)
- The FEED "AI_PHOTO" screen calls `scanNutritionLabel` only, so it is a label scan and not dish recognition. — [nutn-app/src/components/FeedModule.jsx:L3691-3720](/home/user/forged-worktrees/master-ro/nutn-app/src/components/FeedModule.jsx)
- The aiMealAnalysis service holds "Pure parsers … Natural language logging — text → food search terms … nothing in this file talks to a network". — [nutn-app/src/services/aiMealAnalysis.js:L1-60](/home/user/forged-worktrees/master-ro/nutn-app/src/services/aiMealAnalysis.js)
- Voice: "Web Speech does not exist in WKWebView … on the native app the mic is hidden and this sheet is a typed-meal parser. No microphone / speech-recognition usage strings are declared for iOS". VoiceFoodLogger also carries its own hard-coded `COMMON_FOODS` macro table. — [nutn-app/src/components/VoiceFoodLogger.jsx:L1-40, L360-366](/home/user/forged-worktrees/master-ro/nutn-app/src/components/VoiceFoodLogger.jsx). The v7 describe flow says "Tip: your keyboard's mic dictates too." — [nutn-app/src/components/v7/screens/FoodLoggerWays.jsx:L180-251](/home/user/forged-worktrees/master-ro/nutn-app/src/components/v7/screens/FoodLoggerWays.jsx)
- Recipe import: "Capacitor / iOS: direct fetch (no backend). CORS will block most sites." It parses schema.org JSON-LD and falls back to "Enter details manually below". — [nutn-app/src/components/RecipeImporter.jsx:L203-232, L284](/home/user/forged-worktrees/master-ro/nutn-app/src/components/RecipeImporter.jsx)
- Copy-from: `CopyFromScreen({ … copyMealTypeToToday, copySingleMealToToday, copyEntireDayToToday })`. `MealDetailScreen` includes `duplicateMeal`. — [nutn-app/src/components/FeedModule.jsx:L3191, L3341](/home/user/forged-worktrees/master-ro/nutn-app/src/components/FeedModule.jsx)
- Quick add: `QuickAddModal` with cal/P/C/F fields, and `QuickAddBar` for NL text. — [nutn-app/src/components/FeedModule.jsx:L185, L311-316](/home/user/forged-worktrees/master-ro/nutn-app/src/components/FeedModule.jsx)
- Serving normalisation: non-weight servings "stay per 100 g and say so". Weight and volume servings are scaled. — [nutn-app/src/services/foodNormalize.js:L50-74](/home/user/forged-worktrees/master-ro/nutn-app/src/services/foodNormalize.js). The v7 logger steps `servings` by `SERVING_STEP`. — [nutn-app/src/components/v7/screens/FoodLogger.jsx:L142-161](/home/user/forged-worktrees/master-ro/nutn-app/src/components/v7/screens/FoodLogger.jsx)
- 54-field micronutrient list (vitamins, minerals, amino acids, omega-3/6, caffeine, alcohol, GI). — [nutn-app/src/services/foodApi.js:L29-43](/home/user/forged-worktrees/master-ro/nutn-app/src/services/foodApi.js)
- Adaptive TDEE: "MacroFactor-style reverse-engineered TDEE from food logs + weight trend … Week 1-2 Mifflin-St Jeor seed → Week 3+ trend-weight regression". It exports `detectMetabolicAdaptation`, `shouldRecommendDietBreak` and `generateWeeklyTDEECheckin`. — [nutn-app/src/engine/tdee.js:L1-13, L790, L847, L927](/home/user/forged-worktrees/master-ro/nutn-app/src/engine/tdee.js)
- Diet program screen "(calorie cycling from real training data, F10)" with `program`, `dynamic` and `proteinPerLb`. The diet break writes `dietBreakActive`, `dietBreakDays` and `dietBreakTarget: maintenanceCals`. — [nutn-app/src/components/FeedModule.jsx:L1748-1755, L4197-4200, L4573-4608](/home/user/forged-worktrees/master-ro/nutn-app/src/components/FeedModule.jsx)
- Fasting is one model with a `PROTOCOLS` table (16:8 …), persisted as `FASTING_SETTINGS` / `FASTING_LOG`. — [nutn-app/src/engine/fasting.js:L1-25](/home/user/forged-worktrees/master-ro/nutn-app/src/engine/fasting.js)
- Import and export: "Import: MFP CSV, Cronometer CSV, MacroFactor export; Export: Full FEED data as CSV + JSON". DataExport wires MFP and Cronometer CSV import (no MacroFactor button found), a Full Backup (JSON), per-module JSON, and Workouts/Meals/Weight CSV. — [nutn-app/src/services/dataPortability.js:L1-6](/home/user/forged-worktrees/master-ro/nutn-app/src/services/dataPortability.js), [nutn-app/src/components/DataExport.jsx:L4-5, L124-143, L209-210](/home/user/forged-worktrees/master-ro/nutn-app/src/components/DataExport.jsx)
- MFP import keeps per-meal daily totals (Date, Meal, Calories, Carbs, Fat, Protein, Sodium, Sugar) and does not carry individual foods. — [nutn-app/src/services/dataPortability.js:L9-48](/home/user/forged-worktrees/master-ro/nutn-app/src/services/dataPortability.js)

### Inferences
- If a user complains "barcode scanner doesn't work / is slow", nütn has the gap too: the shipping build has no camera barcode scanning. Linking the MLKit plugin is a known, nearly done fix, because the code path already exists in native.js.
- If a user complains "AI photo logging is inaccurate", nütn has nothing comparable (no photo meal recognition). If the complaint is about "voice logging", nütn's version is a rule-based text parser and is not AI.
- The offline database is small (82 foods). Offline search outside staples falls back to custom foods and recents.
- MFP/Cronometer import brings history in as macro totals and not food-level entries, which only partly answers "I can't take my data with me" complaints.

### Gaps
- I did not check how complete USDA/OFF micronutrient extraction is for branded foods, or how the UI presents missing micros.
- I did not verify whether the deployed backend has a USDA key or a vision model configured.

## 2. Workouts (IRON)

### Takeaway
IRON is deep. It has a 325-exercise database, ~21 named program templates plus "auto", a mesocycle generator, a progression/periodisation engine, deload detection, Smart Generate, warm-up sets, per-set RPE (6–10), per-exercise RIR, supersets/tri-sets/giant sets/circuits, a smart rest timer, previous-session reference ("MATCH LAST"), PRs/e1RM, MEV/MAV/MRV volume tracking, analytics, a calendar, cardio logging and CSV export. Gaps: **no exercise videos** (cue text only), **no drop-set entry** (read but never written), **no plate calculator** (only plate rounding), **no assisted-bodyweight mode**, **no rest-timer notification or Live Activity**, **no Apple Watch app**, and **no Apple Health workout write**.

### Status table
| Feature | Status | Evidence |
|---|---|---|
| Set logging (weight/reps, kg or lbs) | HAVE | lbs stored canonically, kg display; v7 logger too |
| Previous values | HAVE | "Last (date): …" line + "MATCH LAST" one-tap fill; `previousWeight/Reps` in WorkoutSetRow |
| Warm-up sets | HAVE | auto warm-ups at 50%/75% (or 55%) of target; `calculateWarmupSets`; excluded from volume/PRs |
| RPE | HAVE (per set, optional) | RPE selector 6–10 in WorkoutSetRow |
| RIR | PARTIAL | asked once per exercise/group at the end (`submitExertion(rir)`), not per set |
| Supersets / tri-sets / giant sets / circuits | HAVE | `GROUP_TYPES` with round model; v7 also |
| Drop sets | GAP for entry | `s.dr` is read by analytics/CSV but nothing creates `dr: true` |
| Bodyweight exercises | HAVE | `isBW` when equipment is bodyweight; `bw` flag on sets |
| Assisted / weighted-bodyweight | GAP | no "assisted" handling found |
| Cardio | HAVE (manual) | CardioTracker: run/walk/hike/cycle/row with distance/time/pace etc.; no GPS |
| Rest timer | HAVE (in-app) | smart defaults by exercise type, learns, ±30 s, skip, haptics, optional sound, timestamp-based `restEndsAt` |
| Rest timer when backgrounded / notification / Live Activity | GAP | no rest notification scheduled; no ActivityKit/Live Activity code |
| Plate calculator | GAP | only `roundToPlate` (2.5 kg / 5 lb rounding) |
| Exercise library | HAVE (325 entries) | `EX_DB` from data/exercises.js; substitutions |
| Exercise videos | GAP | "there are no demo videos, so this screen is the cue list per exercise" |
| Custom exercises | HAVE | `CustomExerciseCreator` mounted in IRON |
| Programs / templates | HAVE | starting_strength, stronglifts_5x5, greyskull_lp, ppl, ul, wendler_531, texas_method, nsuns_531, phul, phat, conjugate, dup, glute, home_gym, minimalist … |
| Mesocycles / progression engine | HAVE | `generateMesocycle`; linear/double/wave/RPE/DUP/block engine; mesocycle store |
| Deloads | HAVE | `shouldDeloadThisWeek`, `markDeloadComplete` |
| Workout generator ("Smart Generate") | HAVE | `workoutGenerator.js` (equipment, target muscles, MEV/MRV adjust, biometric readiness) |
| PRs / e1RM | HAVE | `estimate1RM`/`epley`, PR log, PRBoard, e1RM sparkline, PR celebration + local notification |
| Volume per muscle | HAVE | RP-style `VOLUME_LANDMARKS` MEV/MAV/MRV; VolumeTracker; PPL weekly targets |
| Analytics | HAVE | TrainingAnalytics, AnalyticsScreen, BodyTab, WorkoutCalendar, WeeklyReport, strength score/tiers |
| Strength rankings | HAVE (local only) | LeaderboardScreen: own PBs vs strength standards, local challenges |
| Form check | HAVE (self-check only) | FormChecker is a cue tick-list ("Nothing here is analysed") |
| Progress photos, body measurements | HAVE | ProgressPhotos, BodyMeasurements mounted in IRON |
| Gym profiles / equipment | HAVE | GymProfileEditor; `GYM_PROFILES` synced |
| Workout share card | HAVE | WorkoutShareCard after a session |
| Apple Watch | GAP | no watchOS/WatchKit target or code |
| Apple Health workout read | HAVE (HealthKit) | `getWorkouts(days)` in READ_PERMISSIONS |
| Apple Health workout write | GAP | `saveWorkout` exists but `WRITE_PERMISSIONS = []` and the plugin has no write API |
| CSV export of sets | HAVE | date, exercise, set, reps, weight_lb, bodyweight, rir, drop_set, session_seconds |

### Cited Findings
- Exercise DB: `EX_DB` evaluates to **325** entries (loaded with node). It also exports `calculateWarmupSets`, `estimate1RM`, `epley`, `getSubstitutions` and `getLastSets`. — [nutn-app/src/data/exercises.js:L36, L534](/home/user/forged-worktrees/master-ro/nutn-app/src/data/exercises.js)
- Videos: "Form Cues (audit S22): there are no demo videos, so this screen is the cue list per exercise — no player, no stub URLs". — [nutn-app/src/components/ExerciseVideoLibrary.jsx](/home/user/forged-worktrees/master-ro/nutn-app/src/components/ExerciseVideoLibrary.jsx)
- Program template ids include auto, starting_strength, stronglifts_5x5, greyskull_lp, full_body_3, ppl, ul, bro, arnold, wendler_531, texas_method, nsuns_531, phul, phat, conjugate, dup_program, metabolic_resistance, fat_loss_full, athletic_performance, glute_specialization, minimalist and home_gym. — [nutn-app/src/data/programTemplates.js:L110-953](/home/user/forged-worktrees/master-ro/nutn-app/src/data/programTemplates.js)
- The program engine "Supports linear progression, double progression, wave loading, RPE-based auto-regulation, undulating periodization, and block periodization". Deload helpers are imported by IRON. — [nutn-app/src/engine/workoutProgramEngine.js:L1-20](/home/user/forged-worktrees/master-ro/nutn-app/src/engine/workoutProgramEngine.js), [nutn-app/src/components/IronModule.jsx:L159](/home/user/forged-worktrees/master-ro/nutn-app/src/components/IronModule.jsx)
- `generateMesocycle(config)` and RP volume landmarks (Chest MEV 8 / MAV 16 / MRV 22, …). — [nutn-app/src/engine/progression.js:L1-25, L335](/home/user/forged-worktrees/master-ro/nutn-app/src/engine/progression.js)
- Group types: Superset (2), Tri-Set (3), Giant Set (2–6), Circuit (4–10), each with rest between rounds. — [nutn-app/src/components/IronModule.jsx:L256](/home/user/forged-worktrees/master-ro/nutn-app/src/components/IronModule.jsx)
- Warm-ups are auto-added at 50%×10 and 75%×5 of target (or 55%). Sets carry `{ w, r, bw?, rpe?, isWarmup? }`. — [nutn-app/src/components/IronModule.jsx:L1099-1102, L1358, L1381](/home/user/forged-worktrees/master-ro/nutn-app/src/components/IronModule.jsx)
- RIR: "One set per exercise per round; RIR asked once at the end". — [nutn-app/src/components/IronModule.jsx:L505, L1434, L1522](/home/user/forged-worktrees/master-ro/nutn-app/src/components/IronModule.jsx)
- RPE inline slider (6–10). Previous-value props `previousWeight` / `previousReps` ("last workout's weight for this exercise"). — [nutn-app/src/components/ds/WorkoutSetRow.jsx:L96-111, L317-318](/home/user/forged-worktrees/master-ro/nutn-app/src/components/ds/WorkoutSetRow.jsx)
- "MATCH LAST" button fills the last session's set. — [nutn-app/src/components/IronModule.jsx:L1690-1702, L2304-2313](/home/user/forged-worktrees/master-ro/nutn-app/src/components/IronModule.jsx)
- Drop sets: `s.dr` is only read (IronModule L909/L2194/L3466, BodyTab, TrainingAnalytics, strengthScore, DataExport). A grep for `dr: true` in components/engine/services finds no writer. — e.g. [nutn-app/src/components/DataExport.jsx:L138](/home/user/forged-worktrees/master-ro/nutn-app/src/components/DataExport.jsx)
- Rest timer features: "Smart defaults by exercise type (compound 3min, isolation 90s, superset 60s); Learns from user rest history; Auto-start option; +30s / -30s; Skip Rest; Haptic feedback at 10s warning and on completion; Optional audio cue … via Web Audio API". — [nutn-app/src/components/ds/RestTimerOverlay.jsx:L1-14](/home/user/forged-worktrees/master-ro/nutn-app/src/components/ds/RestTimerOverlay.jsx). The session stores `restEndsAt`. — [nutn-app/src/engine/activeWorkout.js:L5](/home/user/forged-worktrees/master-ro/nutn-app/src/engine/activeWorkout.js)
- Native local notifications are scheduled only for PR, streak milestone, achievement, and the daily 1001/1002/1003 set (morning, streak-risk 8 pm, wind-down). None is for rest timers. — [nutn-app/src/services/notifications.js:L442, L496, L525, L716-771](/home/user/forged-worktrees/master-ro/nutn-app/src/services/notifications.js)
- Plate: only `roundToPlate` is imported ("a kg lifter's prefill has to land on 2.5 kg plates"). A grep for plateCalc/calculatePlates found nothing. — [nutn-app/src/components/IronModule.jsx:L158, L893-895](/home/user/forged-worktrees/master-ro/nutn-app/src/components/IronModule.jsx)
- Cardio types: running, walking, hiking, cycling, rowing … with distance/time/pace/elevation/watts/split fields, entered manually. — [nutn-app/src/components/CardioTracker.jsx:L23-27](/home/user/forged-worktrees/master-ro/nutn-app/src/components/CardioTracker.jsx); engine in [nutn-app/src/engine/cardio.js](/home/user/forged-worktrees/master-ro/nutn-app/src/engine/cardio.js)
- IRON mounts PRBoard, ProgramScreen, AnalyticsScreen, BodyTab, BodyMeasurements, VolumeTracker, TrainingAnalytics, CustomExerciseCreator, WorkoutCalendar, WeeklyReport, ProgressPhotos, WorkoutShareCard, FormChecker ("Self-Check") and LeaderboardScreen ("Rankings"). — [nutn-app/src/components/IronModule.jsx:L138-156, L2748, L3151-3152, L3320-3612](/home/user/forged-worktrees/master-ro/nutn-app/src/components/IronModule.jsx)
- FormChecker: "The previous version claimed 'AI Form Analysis — 73/100' but never looked at the video … Nothing here is analysed." — [nutn-app/src/components/FormChecker.jsx](/home/user/forged-worktrees/master-ro/nutn-app/src/components/FormChecker.jsx)
- LeaderboardScreen: "Personal Best Leaderboard … Strength Standards … Challenge Mode — local bodyweight challenges". It reads local keys only. — [nutn-app/src/components/LeaderboardScreen.jsx:L1-13](/home/user/forged-worktrees/master-ro/nutn-app/src/components/LeaderboardScreen.jsx)
- HealthKit: `READ_PERMISSIONS` includes `workout`, and "`WRITE_PERMISSIONS = []` … @perfood/capacitor-healthkit has no write API". `saveWorkout` returns `write_unsupported` when `!hk.canWrite`. — [nutn-app/src/services/healthkit.js:L118-141, L1019-1025](/home/user/forged-worktrees/master-ro/nutn-app/src/services/healthkit.js). The plist says: "nütn never writes to Apple Health." — [nutn-app/ios/App/App/Info.plist:L30](/home/user/forged-worktrees/master-ro/nutn-app/ios/App/App/Info.plist)
- Apple Watch: `ios/App` contains only App, App.xcodeproj, App.xcworkspace and CapApp-SPM. A grep for watchOS/WatchKit/WatchConnectivity under ios/ and src/ found nothing. — [nutn-app/ios/App](/home/user/forged-worktrees/master-ro/nutn-app/ios/App)
- The v7 workout logger starts empty, from the next mesocycle day, from a recent session or from a favourite. It supports supersets/circuits and edits IRON's serialized session. — [nutn-app/V7-MIGRATION.md](/home/user/forged-worktrees/master-ro/nutn-app/V7-MIGRATION.md), [nutn-app/src/components/v7/screens/WorkoutLogger.jsx](/home/user/forged-worktrees/master-ro/nutn-app/src/components/v7/screens/WorkoutLogger.jsx)

### Inferences
- nütn already answers the common "Strong/Hevy lack programming/progression" complaints (programs, mesocycles, auto-progression, deloads, MEV/MRV). It is behind those apps on Watch support, rest-timer notifications when the app is backgrounded, videos, plate math, and drop-set logging.
- The rest timer is timestamp-based, so it probably shows the right remaining time after the app resumes. But nothing alerts the user while the phone is locked.

### Gaps
- I did not measure logging speed (taps per set). The code shows one-tap "MATCH LAST" and prefilled target weight/reps, but there are no timing data.
- I did not confirm whether `restEndsAt` survives a cold restart of an in-progress session in IRON's restore path. The v7 doc says sessions resume between v7 and IRON.

## 3. Recovery and sleep (REST)

### Takeaway
REST offers manual sleep logging (bed/wake, hours, quality, hygiene), HealthKit sleep import with conflict resolution, a readiness check-in scored by a multi-factor recovery engine, an HRV baseline chart, cold/heat exposure protocols, and supplements. Readiness shows up as a card and protocol in IRON, and Smart Generate scales volume by RHR/sleep. I found **no readiness-driven change to nutrition targets**. HealthKit HRV reading exists in code, while the plist text says HRV is not read in this version, so the two disagree. Oura/Whoop have only env-var placeholders.

### Status table
| Feature | Status | Evidence |
|---|---|---|
| Manual sleep logging | HAVE | `SleepView`, `SLEEP_LOG`, hygiene, stats |
| HealthKit sleep import (stages) | HAVE (iOS) | `getSleepData` maps Core/Deep/REM/InBed/Awake; manual vs HealthKit conflict prompt |
| HealthKit HRV / RHR / SpO2 / resp rate / BP / skin temp / ECG | PARTIAL / conflicting | readers exist + in READ_PERMISSIONS; plist says HRV/ECG/wrist temp "not read by this version" |
| Readiness score | HAVE | `calculateReadiness` (recovery engine) from logged HRV/RHR/hours + check-in; Readiness/Strain/Balance |
| Readiness → training | HAVE | `ReadinessModifierCard` in IRON (score + protocol actions); `biometricReadiness` in generator; recovery alert notification |
| Readiness → nutrition | GAP (not found) | no readiness reference in FeedModule/crosslink |
| v7 Today shows sleep/readiness | HAVE (v7 only) | "Up Next leads with recovery … Readiness 74 — Primed" |
| Oura / Whoop | GAP | only `VITE_OURA_CLIENT_ID` / `VITE_WHOOP_CLIENT_ID` in env docs; no code references |
| Cold/heat exposure, supplements | HAVE | REST tabs Exposure, Supplements |

### Cited Findings
- REST tabs: Sleep, Readiness, HRV, Exposure, Supplements, plus a Daily Recovery Brief card. — [nutn-app/src/components/RestModule.jsx:L1258-1275](/home/user/forged-worktrees/master-ro/nutn-app/src/components/RestModule.jsx)
- SleepView reads `SLEEP_LOG` and `SLEEP_HYGIENE` and checks HealthKit sleep for "conflict resolution". If both manual and healthkit entries exist for today, it flags a conflict and can adopt the HealthKit entry with stages. — [nutn-app/src/components/RestModule.jsx:L743-777, L949](/home/user/forged-worktrees/master-ro/nutn-app/src/components/RestModule.jsx)
- Sleep stage mapping covers AsleepCore/Deep/REM, InBed and Awake. — [nutn-app/src/services/healthkit.js:L467-531](/home/user/forged-worktrees/master-ro/nutn-app/src/services/healthkit.js)
- `READ_PERMISSIONS` lists stepCount, bodyMass, sleepAnalysis, heartRate, heartRateVariabilitySDNN, restingHeartRate, activeEnergyBurned, workout, bodyFatPercentage, oxygenSaturation, respiratoryRate, BP, electrocardiogramType and appleSleepingWristTemperature. — [nutn-app/src/services/healthkit.js:L121-137](/home/user/forged-worktrees/master-ro/nutn-app/src/services/healthkit.js). This contradicts the plist usage string: "Heart rate variability, ECG and wrist temperature are requested for a future update and are not read by this version." — [nutn-app/ios/App/App/Info.plist:L30](/home/user/forged-worktrees/master-ro/nutn-app/ios/App/App/Info.plist)
- The HealthKit store persists sleep, heartRate, hrv, steps, workouts, respiratory rate, spo2, body comp, active energy, BP, ECG and skin temp, each with source tags. — [nutn-app/src/services/healthkitStore.js:L1-40, L282-292](/home/user/forged-worktrees/master-ro/nutn-app/src/services/healthkitStore.js)
- The REST HRV chart uses `kn_hrv_log` and says "Log HRV readings to see your trend". Readiness is recalculated "from what was actually logged" via `calculateReadiness` and `computeBaselines`. — [nutn-app/src/components/RestModule.jsx:L121-193, L1013-1082](/home/user/forged-worktrees/master-ro/nutn-app/src/components/RestModule.jsx)
- Recovery engine model: "RecoveryScore = ParasympatheticReserve × (1 - AllostaticLoadFactor) × SleepRestorationFactor × NutritionalReadiness". — [nutn-app/src/engine/recovery.js:L1-25](/home/user/forged-worktrees/master-ro/nutn-app/src/engine/recovery.js)
- The REST pillar score has no fabricated defaults: "never a defaulted 7 h … no fabricated 93 % efficiency". — [nutn-app/src/engine/restScore.js:L1-14](/home/user/forged-worktrees/master-ro/nutn-app/src/engine/restScore.js)
- IRON readiness card: "today's REST readiness entry, or nothing". It also uses `biometricReadiness({ rhr, sleepHours })`. — [nutn-app/src/components/IronModule.jsx:L229-262, L718, L772-782](/home/user/forged-worktrees/master-ro/nutn-app/src/components/IronModule.jsx)
- Recovery alert notification: "Readiness is X. Consider a rest day or light activity only." — [nutn-app/src/services/notifications.js:L407-416](/home/user/forged-worktrees/master-ro/nutn-app/src/services/notifications.js)
- v7: "Folded into Today … Up Next leads with recovery (last night's sleep → morning check-in → Readiness 74 — Primed) … HRV, exposure and supplements are still REST-tab only." — [nutn-app/V7-MIGRATION.md](/home/user/forged-worktrees/master-ro/nutn-app/V7-MIGRATION.md)

### Inferences
- The HRV/RHR "readiness" input is mostly manual unless HealthKit data flows into `kn_hrv_log`. I did not trace a HealthKit → `HRV_LOG` writer, and the plist disclaimer suggests HRV is not used in this build. So "Whoop/Oura-style readiness from my watch" counts as PARTIAL at best.

### Gaps
- I could not confirm whether HealthKit HRV values feed `calculateReadiness` in the shipping flow (`pullRecoveryData` exists in healthkit.js but I found no UI caller outside the engine docstring).

## 4. Mood and mind (FORGE / MIND)

### Takeaway
The MIND module (mounted as "FORGE") is fully reachable. It has mood check-in, emotions check-in, free journal, guided journal, gratitude, breathwork patterns, meditation with synthesized audio, a well-being check-up, weekly theme, an Explore library, trends, PHQ-9, GAD-7 and ASRS screeners, a PHQ-9-driven safety protocol, crisis resources (US 988, Crisis Text Line, findahelpline.com), and mood-pattern analytics.

### Status table
| Feature | Status | Evidence |
|---|---|---|
| Mood check-in / emotions | HAVE | `MoodCheckin`, `EmotionsCheckin` |
| Journal (free, guided, gratitude) | HAVE | `JournalEntryScreen`, `GuidedJournal`, `GratitudeEntry`; v7 Reflect writes journal entries |
| Breathwork | HAVE | `BreathworkSession` (patterns with phases/cycles) |
| Meditation | HAVE (no recorded audio) | `MeditationSession`; audioEngine "Generates tones programmatically for offline use" |
| PHQ-9 / GAD-7 / ASRS | HAVE | ClinicalCheckin modes `daily / phq9 / asrs / gad7`; histories synced |
| Crisis resources | HAVE (US-centric + global link) | `CRISIS_LINES` |
| Safety escalation | HAVE | `forgeSafety` PHQ-9 bands; crisis card at ≥15/20 |
| Mood correlations / prediction | HAVE | `moodIntelligence` (Pearson r, effect size, EMA, regression); `predictTomorrow`; MindTrends; WeeklyReport |
| Well-being check-up, weekly theme, Explore | HAVE | MindModule screen switch |

### Cited Findings
- The MindModule screen switch includes home, coach, chat, explore, trends, mood-checkin, journal, breathwork, meditation, gratitude, clinical-checkin, phq9, asrs, guided-journal, wellbeing, crisis-resources, weekly-theme, explore-category and emotions-checkin. — [nutn-app/src/components/mind/MindModule.jsx:L564-705](/home/user/forged-worktrees/master-ro/nutn-app/src/components/mind/MindModule.jsx)
- `ForgeModule` is a "thin re-export of MindModule". — [nutn-app/src/components/ForgeModule.jsx:L1-4](/home/user/forged-worktrees/master-ro/nutn-app/src/components/ForgeModule.jsx)
- GAD-7 is implemented with `GAD7_ITEMS` and `scoreGAD7`, using Spitzer 2006 severity bands. "ClinicalCheckin — handles daily / phq9 / asrs / gad7 modes". PHQ9Assessment delegates to ClinicalCheckin with mode='phq9'. — [nutn-app/src/components/mind/ClinicalCheckin.jsx:L9-23, L71](/home/user/forged-worktrees/master-ro/nutn-app/src/components/mind/ClinicalCheckin.jsx), [nutn-app/src/components/mind/PHQ9Assessment.jsx](/home/user/forged-worktrees/master-ro/nutn-app/src/components/mind/PHQ9Assessment.jsx)
- Safety engine bands: 0–4 minimal … "15–19: Moderately Severe — active escalation, crisis resources surface; 20–27: Severe — crisis card always shown, scoring suppressed". — [nutn-app/src/engine/forgeSafety.js:L1-20](/home/user/forged-worktrees/master-ro/nutn-app/src/engine/forgeSafety.js)
- Crisis lines: 988 (call/text), Crisis Text Line (HOME to 741741), Find A Helpline (outside the US). "the app is not a crisis service". — [nutn-app/src/data/crisisLines.js](/home/user/forged-worktrees/master-ro/nutn-app/src/data/crisisLines.js)
- Mood Intelligence "Analyzes patterns in mood, behavior, and biometric data" using `calculatePearsonR`, `calculateEffectSize`, `exponentialMovingAverage` and `linearRegression` from correlations.js. It is used by MindTrends, MindModule (`predictTomorrow`) and WeeklyReport. — [nutn-app/src/engine/moodIntelligence.js:L1-25](/home/user/forged-worktrees/master-ro/nutn-app/src/engine/moodIntelligence.js)
- Audio: "Web Audio API wrapper for breathwork and meditation — Generates tones programmatically for offline use". — [nutn-app/src/services/audioEngine.js:L1-4](/home/user/forged-worktrees/master-ro/nutn-app/src/services/audioEngine.js)
- Synced mind keys include MOOD_HISTORY, ENTRIES_JOURNAL, PHQ/ASRS/GAD histories, CBT_HISTORY, BREATHWORK/MEDITATION counts, WELLBEING_HISTORY and EMOTIONS_CHECKIN. — [nutn-app/src/services/cloudSync.js:L22-28](/home/user/forged-worktrees/master-ro/nutn-app/src/services/cloudSync.js)

### Inferences
- Complaints about "meditation apps need content" map to PARTIAL: there are no recorded guided sessions, only timers and generated tones. The breathwork, journaling and screener coverage is broad for a fitness app.

### Gaps
- I did not inspect the Explore library's content volume or whether the guided journal prompts are static.

## 5. Cross-cutting: offline, sync, accounts, export, privacy, notifications, gamification, social, coach, insights, themes, a11y, units, monetization, platforms

### Takeaway
nütn is offline-first. Writes go to local storage, and Supabase sync runs on launch and every 15 minutes, last-write-wins per key. Accounts start anonymous, and email OTP links or signs in. Full JSON backup/restore and CSV exports exist. "Delete All Data" wipes cloud rows and local data but does **not delete the auth user**. There is **no paywall**. The AI coach chat and briefings go through the backend, defaulting to a local Qwen model, with a rule-based fallback for briefings. Gamification is extensive (streaks, XP, 27 badges, 9 day-count tiers that unlock themes). Community is flag-off. Light/dark/auto themes and lbs/kg, ft/cm and mi/km units are present. Native notifications are limited to a small daily set plus PR/milestone pings.

### Status table
| Feature | Status | Evidence |
|---|---|---|
| Offline-first | HAVE | local Preferences/localStorage; offline search fallback; service worker registered on web |
| Cloud sync | GATED (Supabase env) | `user_data` rows per key, last-write-wins, every 15 min + foreground |
| Accounts | HAVE / GATED | anonymous by default; email 6-digit OTP sign-in/link; no Apple/Google sign-in found |
| Backup / restore | HAVE | Full JSON backup, shape-checked restore (50 MB cap) |
| Export | HAVE | JSON per module; CSV meals/weight/workouts |
| Import from other apps | HAVE | MFP + Cronometer CSV |
| Delete data | HAVE | deletes cloud `user_data` first, signs out, wipes local |
| Delete account (auth user) | PARTIAL | no auth-user deletion call found; coach messages handled by separate retention migration |
| Privacy posture | HAVE | no model keys in client; Supabase RLS migrations; HealthKit read-only |
| Notifications | PARTIAL | native: daily 8 am check-in, 8 pm streak-risk, wind-down, PR, milestone, achievement; most other "smart" notifications are in-app banners/descriptors |
| Streaks / XP / badges / tiers | HAVE | streak engine, XP ledger, 27 badges, 9 Newton tiers unlocking themes |
| XP feature gating | UNMOUNTED/DEAD | `TIER_FEATURES` locks list not referenced outside tiers.js |
| Social / community | GATED OFF | `FEATURES.COMMUNITY=false`; social.js still creates a profile / emits events |
| Coach / AI chat | GATED (backend + model) | backend `/api/chat`, `/api/coach/*`; `MODEL_PROVIDER=local` (Qwen3.6-35B-A3B MLX) or `anthropic` (`claude-opus-5`) |
| Rule-based coach / daily briefing | HAVE | engine/coach.js "Rule-based engine — no API needed" |
| Insights / correlations | PARTIAL | mood intelligence, nutrition insights, fasting insights live; `engine/insights.js` has no importers |
| Weekly report | HAVE | Coach weekly/monthly (`weeklyReview.js`), IRON WeeklyReport, WeeklyNutrition, weekly TDEE check-in |
| Themes | HAVE | light / dark / auto (daylight cycle); tier themes |
| Accessibility | PARTIAL+ | 481 `aria-` usages in JSX; reduced-motion handling in 14 files; v7 tablist roles; some focus traps |
| Units | HAVE | weight lbs/kg, height ft/cm, distance mi/km; food water in oz |
| Monetization / paywall | NONE | "No subscription gate — the paywall is gone" |
| Platforms | iOS only (+ web build for tests/Pages) | Capacitor iOS; no Android project |
| Wearables beyond Apple Health | GAP | Oura/Whoop env placeholders only |
| Lab biomarkers | GATED | BiomarkerScreen + BiomarkerImport; backend `/parse-labs` |
| Biological age | HAVE | Profile card via `biologicalAge.js` |

### Cited Findings
- Sync design: "every key a user authored or would miss after a reinstall is synced … Last-write-wins per row, keyed on updated_at". It has three tiers: per-key, raw, and per-item (progress photos). — [nutn-app/src/services/cloudSync.js:L6-45](/home/user/forged-worktrees/master-ro/nutn-app/src/services/cloudSync.js)
- `startSyncSchedule` runs `syncToCloud` every 15 minutes. `clearCloud()` deletes `user_data` where `user_id = session.user.id`. — [nutn-app/src/services/cloudSync.js:L553-576](/home/user/forged-worktrees/master-ro/nutn-app/src/services/cloudSync.js)
- Auth: anonymous `signInAnonymously`, and "Email sign-in is a 6-digit OTP … An anonymous session is linked". `signOutDevice({ wipe })`. — [nutn-app/src/services/supabase.js:L7-18, L166-185, L256-348](/home/user/forged-worktrees/master-ro/nutn-app/src/services/supabase.js)
- Delete flow: "Cloud first … `clearCloud()` … `sb.auth.signOut()` … `clearAll()` … 'All data deleted'". No `auth.admin.deleteUser` or RPC exists. — [nutn-app/src/components/DataExport.jsx:L212-230](/home/user/forged-worktrees/master-ro/nutn-app/src/components/DataExport.jsx)
- Supabase migrations: community schema, user_data, cohort benchmark, RLS hardening, coach_messages, coach access cleanup, coach_messages retention, RLS insert tightening. — [nutn-app/supabase/migrations/](/home/user/forged-worktrees/master-ro/nutn-app/supabase/migrations)
- Backup import enforces a 50 MB max, device-only keys, and shape compatibility. — [nutn-app/src/services/backupImport.js:L18-141](/home/user/forged-worktrees/master-ro/nutn-app/src/services/backupImport.js)
- Notifications header: "All scheduling returns descriptor objects (no native push yet) … Max 5 notifications per day … Quiet hours: 10pm-7am … Progressive: Day 1-3 only Morning Check-In …". Native `LocalNotifications.schedule` is used for ids 1001 (daily morning), 1002 (8 pm "Don't break the chain."), 1003 ("Wind down." daily), PR, streak milestone and achievement. — [nutn-app/src/services/notifications.js:L1-26, L426-530, L716-771](/home/user/forged-worktrees/master-ro/nutn-app/src/services/notifications.js); called from [nutn-app/src/App.jsx:L813-830](/home/user/forged-worktrees/master-ro/nutn-app/src/App.jsx)
- Tiers: "Tiers are based on CUMULATIVE ACTIVE DAYS … 9 tiers, each unlocking a unique app theme". There is also an XP `TIER_FEATURES` map (Raw → Diamond) with `locked` lists, but nothing outside tiers.js references it. — [nutn-app/src/engine/tiers.js:L1-30, L111-157](/home/user/forged-worktrees/master-ro/nutn-app/src/engine/tiers.js)
- Badges: 27 `id:` entries. — [nutn-app/src/engine/badges.js](/home/user/forged-worktrees/master-ro/nutn-app/src/engine/badges.js). Streak/XP are wired in App. — [nutn-app/src/App.jsx:L38-42](/home/user/forged-worktrees/master-ro/nutn-app/src/App.jsx)
- Community gate: when `!FEATURES.COMMUNITY`, the tab renders "Community isn't part of this release." `createSocialProfile('nütn user')` and `emitFeedEvent(...)` are still called from App without a flag check, and social.js has no FEATURES reference. — [nutn-app/src/App.jsx:L914, L995, L1122, L1413-1427](/home/user/forged-worktrees/master-ro/nutn-app/src/App.jsx), [nutn-app/src/services/social.js](/home/user/forged-worktrees/master-ro/nutn-app/src/services/social.js)
- Coach model: "`local` (default) … `LOCAL_MODEL` (default `mlx-community/Qwen3.6-35B-A3B-4bit`) … `anthropic` … `claude-opus-5` … No OpenRouter, no other hosted provider". — [nutn-app/backend/services/llm.py:L1-55](/home/user/forged-worktrees/master-ro/nutn-app/backend/services/llm.py)
- Fly deploy: `MODEL_PROVIDER = "local"`, "The MLX server is not inside the machine: set LOCAL_MODEL_URL as a secret to a reachable MLX host, or switch the provider". — [nutn-app/backend/fly.toml](/home/user/forged-worktrees/master-ro/nutn-app/backend/fly.toml)
- Backend routes: `/chat`, `/history`, `/weekly-review`, `/daily-briefing`, `/explain-score`, `/predict-score`, `/scan-label`, `/parse-labs`, food search/detail/barcode. The README mentions a daily spend cap `COACH_DAILY_CAP_USD` and per-user hourly/daily rate limits. — [nutn-app/backend/routers/](/home/user/forged-worktrees/master-ro/nutn-app/backend/routers), [nutn-app/README.md](/home/user/forged-worktrees/master-ro/nutn-app/README.md)
- Client coach: briefing/weekly-review "return null on failure because every caller falls back to the rule engine in coach.js". On paywall: "No subscription gate — the paywall is gone". — [nutn-app/src/services/claudeCoach.js:L1-40, L204](/home/user/forged-worktrees/master-ro/nutn-app/src/services/claudeCoach.js)
- Rule-based coach: "Rule-based engine — no API needed for core recommendations." — [nutn-app/src/engine/coach.js:L1-5](/home/user/forged-worktrees/master-ro/nutn-app/src/engine/coach.js)
- `engine/insights.js` has zero non-test importers (import scan). `engine/correlations.js` is used only through moodIntelligence. — [nutn-app/src/engine/insights.js](/home/user/forged-worktrees/master-ro/nutn-app/src/engine/insights.js)
- Period review: "Computed on the fly … Below MIN_DAYS_WITH_DATA days … the review reports `enough: false`". — [nutn-app/src/engine/weeklyReview.js:L1-25](/home/user/forged-worktrees/master-ro/nutn-app/src/engine/weeklyReview.js)
- Theme modes are `'light' | 'dark' | 'auto'`, and auto uses suncalc daylight. Profile has an Appearance card with Theme and Daylight Cycle. — [nutn-app/src/components/ThemeProvider.jsx:L3-16, L112-126](/home/user/forged-worktrees/master-ro/nutn-app/src/components/ThemeProvider.jsx), [nutn-app/src/components/ProfileScreen.jsx:L919-950](/home/user/forged-worktrees/master-ro/nutn-app/src/components/ProfileScreen.jsx)
- Profile sections: nütn Score, Biological Age, Profile, Goal, Personal Assessment, Daily Targets (Auto-Calculated), Units, Appearance, Account, Data, Connected Devices (Apple Health only), About. — [nutn-app/src/components/ProfileScreen.jsx:L580-1219](/home/user/forged-worktrees/master-ro/nutn-app/src/components/ProfileScreen.jsx)
- Units: `WEIGHT_UNITS = ['lbs','kg']`, `HEIGHT_UNITS = ['ft','cm']`, `DISTANCE_UNITS = ['mi','km']`, default lbs/ft/mi. — [nutn-app/src/utils/units.js:L21-33](/home/user/forged-worktrees/master-ro/nutn-app/src/utils/units.js)
- Accessibility: the v7 TabBar is now `nav[role="tablist"]` with `role="tab"` and `aria-selected`. Ship-audit round 2 fixed "keyboard access and names across MIND", focus traps in v7 dialogs, and labelled inputs. Counts: 481 `aria-` occurrences in JSX and 14 files handling reduced motion (grep). — [nutn-app/V7-MIGRATION.md](/home/user/forged-worktrees/master-ro/nutn-app/V7-MIGRATION.md), [ship-audit/RUN-LEDGER.md](/home/user/forged-worktrees/master-ro/ship-audit/RUN-LEDGER.md)
- Offline cache: "All data writes to local storage immediately (offline-first). Sync to cloud when available". `registerSW` registers `./sw.js` when `serviceWorker` exists. — [nutn-app/src/services/offlineCache.js:L1-5, L100-120](/home/user/forged-worktrees/master-ro/nutn-app/src/services/offlineCache.js)
- Platform: Capacitor iOS config only (`ios` block, iOS 16). The web build has plugins mocked and is "used for Playwright and the Pages deploy". — [nutn-app/capacitor.config.ts](/home/user/forged-worktrees/master-ro/nutn-app/capacitor.config.ts), [nutn-app/README.md](/home/user/forged-worktrees/master-ro/nutn-app/README.md)
- Lab biomarkers: BiomarkerScreen mounts BiomarkerImport, and the backend route `POST /parse-labs` exists. — [nutn-app/src/components/BiomarkerScreen.jsx:L15, L187](/home/user/forged-worktrees/master-ro/nutn-app/src/components/BiomarkerScreen.jsx), [nutn-app/backend/routers/biomarkers.py:L130](/home/user/forged-worktrees/master-ro/nutn-app/backend/routers/biomarkers.py)

### Inferences
- "Paywall / subscription" complaints about competitors are a clear differentiator: nütn has no paywall code. The flip side is that the AI coach depends on a self-hosted model plus a spend cap, so reliability, not price, is nütn's risk.
- "Can't delete my account" complaints are only partly addressed. Data is wiped, but the Supabase auth identity remains. App Store guideline 5.1.1(v) expects account deletion, so this is worth flagging.
- Notifications are thin compared with apps users praise for reminders (no meal, workout or rest-timer reminders at the OS level), even though the in-app "smart" logic exists.
- Social features are off by design. Complaints about "toxic community" or "forced social" do not apply. Complaints about "no friends / accountability" are a gap.

### Gaps
- I found no explicit privacy policy text or in-app analytics/tracking SDK. None appears in package.json dependencies, but I did not audit the backend logging for PII.
- I did not verify how `coach_messages` are deleted on "Delete All Data". The migration `007_coach_messages_retention.sql` suggests time-based retention, but I did not read it.
- I did not test VoiceOver behaviour or Dynamic Type support. The a11y status rests on code signals only.
