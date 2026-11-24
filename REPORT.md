# Report: ab-test-judge

| project | branch | tests | docker | CI | pushed | deployed | blockers |
|---|---|---|---|---|---|---|---|
| A/B Test Judge | ab-test-judge | 7 pass | builds, /health ok locally | workflow present | yes | no | deploy needs owner account |

Decisions: standard-library maths; pooled test with unpooled interval; peeking simulation. A test's expected z (2.39) was wrong; recomputed by hand to 2.50 and fixed the test, not the code.

---

# Final report

Stop time passed (target 07:30 IST, Nov 18, 2026). Work stopped at project 134; the repo was renamed from `brain-strome` to `brain-strom` afterwards, and `origin` was updated to the new name (pushes and `ls-remote` work).

## Built
About 134 projects, each on its own branch from `main`, each with README (problem, solution, architecture, setup, screenshot, design decisions, limitations), typed Python, pytest tests, Dockerfile, GitHub Actions CI (install, ruff, pytest, docker), a Render/Hugging Face deploy guide, and sample or synthetic data. The last batch (this session segment):

| project | branch | tests | docker | CI | pushed | deployed | blockers |
|---|---|---|---|---|---|---|---|
| Cron Explainer | cron-explainer | 10 pass | local build blocked by Docker Hub 429 | green | yes | no | deploy needs owner account |
| Word Ladder Solver | word-ladder-solver | 9 pass | CI builds it | green | yes | no | deploy needs owner account |
| Bloom Spellcheck | bloom-spellcheck | 9 pass | CI builds it | green | yes | no | deploy needs owner account |
| Text Diff Viewer | text-diff-viewer | 8 pass | CI builds it | green | yes | no | deploy needs owner account |
| Markov Name Maker | markov-name-maker | 8 pass | CI builds it | green | yes | no | deploy needs owner account |
| Dither Lab | dither-lab | 10 pass | builds in CI after a fix | green | yes | no | deploy needs owner account |
| Plant Watering Tree | plant-watering-tree | 9 pass | local build blocked by 429; CI builds it | green | yes | no | deploy needs owner account |
| Moon Phase Calendar | moon-phase-calendar | 9 pass | CI builds it | green | yes | no | deploy needs owner account |
| Gradient Descent Lab | gradient-descent-lab | 9 pass | local build blocked by 429 | green | yes | no | deploy needs owner account |
| Sorting Race | sorting-race | 9 pass | CI builds it | green | yes | no | deploy needs owner account |
| Town Bridge Finder | town-bridge-finder | 8 pass | local build blocked by 429 | green | yes | no | deploy needs owner account |
| Tournament Bracket Maker | tournament-bracket-maker | 9 pass | local build blocked by 429 | green | yes | no | deploy needs owner account |
| Check Digit Validator | check-digit-validator | 9 pass | local build blocked by 429 | green | yes | no | deploy needs owner account |
| Cellular Automata Lab | cellular-automata-lab | 10 pass | builds, /health ok locally | green | yes | no | deploy needs owner account |
| Maze Lab | maze-lab | 10 pass | local build blocked by 429; CI builds it | green | yes | no | deploy needs owner account |
| Huffman Squeeze | huffman-squeeze | 7 pass | local build blocked by 429; CI builds it | green | yes | no | deploy needs owner account |
| Rate Limiter Lab | rate-limiter-lab | 9 pass | builds, /health ok locally | green | yes | no | deploy needs owner account |
| Cache Policy Lab | cache-policy-lab | 9 pass | builds, /health ok locally | green | yes | no | deploy needs owner account |
| Password Strength Coach | password-strength-coach | 10 pass | builds, /health ok locally | green | yes | no | deploy needs owner account |
| Hash Table Lab | hash-table-lab | 10 pass | builds, /health ok locally | green | yes | no | deploy needs owner account |
| k-means Lab | kmeans-init-lab | 7 pass | builds, /health ok locally | green | yes | no | deploy needs owner account |
| Unbeatable Tic-Tac-Toe | tictactoe-minimax | 9 pass | builds, /health ok locally | green | yes | no | deploy needs owner account |
| PageRank Lab | pagerank-lab | 8 pass | builds, /health ok locally | green | yes | no | deploy needs owner account |
| Countdown Solver | countdown-solver | 9 pass | builds, /health ok locally | green | yes | no | deploy needs owner account |
| A/B Test Judge | ab-test-judge | 7 pass | builds, /health ok locally | green | yes | no | deploy needs owner account |

Earlier projects have the same row in their own branch's REPORT.md. All branch names on the remote are listed at the end of this file.

## Deployed
Nothing. Deploying to Render or Hugging Face Spaces needs the owner's account; every project has DEPLOY.md and a `render.yaml` ready.

## Blocked
- Docker Hub rate limit (429 Too Many Requests) stopped several local `docker build` runs. Each was retried once, then recorded, and the CI docker job covers the build. No claim of a local build was made without a passing `/health` curl.
- CI failed twice early (dither-lab, plant-watering-tree) because the Dockerfile copied a `data` folder that did not exist; fixed on both branches and CI went green.
- The repo rename from brain-strome to brain-strom happened mid-run; the `origin` remote was updated.

## Decisions
- Free, open-source, stateless FastAPI plus a static page per project, with invented or synthetic data (no personal data, no secrets).
- One branch per project, never touching `main` or existing branches; nothing deleted.
- Oracles and published results for tests (brute force, closed-form solutions, textbook figures); tests that disagreed with correct code were fixed by recomputing by hand, not by loosening asserts.
- Limitations are disclosed per project, including where results differ from theory.

## Next steps
1. Deploy the strongest projects (for example password-strength-coach, ab-test-judge, rate-limiter-lab, cache-policy-lab) to Render or Hugging Face Spaces and add the live links to their READMEs.
2. (Done) CI on ab-test-judge is green (run 180).
3. Fix stale pyproject descriptions on three early branches (table-seating-planner, bake-sale-pricer, timetable-builder).
4. Pick the 5 to 8 best projects for the resume instead of listing all of them.

## All project branches on the remote
- ab-test-judge
- appliance-power-cost
- autocomplete-trie-search
- bag-weight-balancer
- bake-sale-pricer
- bill-timing-planner
- birthday-countdown
- bloom-spellcheck
- board-game-dice-odds
- book-club-picker
- bookshelf-filler
- cache-policy-lab
- cafe-demand-forecaster
- campus-faq-search
- carry-on-capsule
- cellular-automata-lab
- chase-win-estimator
- check-digit-validator
- checkout-line-chooser
- chore-rota-planner
- cinema-seat-picker
- clinic-noshow-predictor
- coin-change-maker
- commute-leave-time
- contact-dedupe
- countdown-solver
- coupon-stack-chooser
- cron-explainer
- day-timebox-planner
- debt-payoff-strategist
- digit-sketchpad
- dinner-sync-planner
- dither-lab
- elevator-dispatch-sim
- elo-rating-league
- exam-runway
- fair-meeting-time
- fair-shift-roster
- fair-teams-picker
- final-grade-needed
- flashcard-review-scheduler
- flat-pack-packer
- flat-rent-estimator
- garden-planting-calendar
- gift-budget-splitter
- golden-hour-planner
- gradient-descent-lab
- grocery-aisle-route
- gym-week-planner
- habit-streak-keeper
- hall-booking-optimizer
- hash-table-lab
- heating-schedule-optimizer
- hike-time-estimator
- home-energy-anomaly
- homework-order-planner
- household-carbon-coach
- huffman-squeeze
- jet-lag-planner
- kitchen-stock-reorder
- kmeans-init-lab
- language-guesser
- laundry-slot-scheduler
- league-fixture-planner
- lost-and-found-matcher
- machine-anomaly-monitor
- markov-name-maker
- maze-lab
- meal-prep-budget-mixer
- meeting-notes-summarizer
- message-shrinker
- mini-spreadsheet
- moon-phase-calendar
- morning-routine-planner
- movie-night-recommender
- next-bus-finder
- pagerank-lab
- paint-can-planner
- palette-extractor
- pantry-saver
- parking-fee-comparator
- password-strength-coach
- photo-album-grouper
- pizza-order-planner
- plain-words-checker
- plank-cutting-planner
- plant-parent
- plant-watering-tree
- playlist-arc-builder
- playlist-fitter
- potluck-dish-matcher
- quick-event-parser
- race-pace-planner
- raffle-ticket-reality
- rate-limiter-lab
- reading-pace-planner
- receipt-line-reader
- recipe-scaler-shopping-list
- rent-check
- road-trip-stop-planner
- roommate-bill-settler
- savings-goal-planner
- school-bus-route-planner
- secret-santa-matcher
- shopping-typo-matcher
- sleep-cycle-planner
- sms-spam-shield
- sorting-race
- storage-cleanup-picker
- study-buddy-matcher
- subscription-sniffer
- sudoku-coach
- support-ticket-triage
- swim-lane-assigner
- table-seating-planner
- taxi-fare-splitter
- terrain-trail-pathfinder
- text-diff-viewer
- tictactoe-minimax
- tile-box-calculator
- timetable-builder
- tip-pool-splitter
- tournament-bracket-maker
- town-bridge-finder
- trail-pack-optimizer
- transit-pass-chooser
- typing-speed-coach
- unit-price-checker
- waiting-room-simulator
- waste-bin-sorter
- weather-outfit-picker
- wedding-seating-planner
- weekly-menu-planner
- word-hive-solver
- word-ladder-solver

## Timing note
All 134 project branches were pushed on Nov 17, 2026 (well before the Nov 18 07:30 IST stop). Only this final report section was pushed late, on Nov 24, because the repo rename (brain-strome to brain-strom) blocked pushes until the new name was added to the session. No project work was done after the stop time.
