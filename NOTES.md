# Restructure lab · R6 · then vs now, research copy, test export (Oct 19, 2026)

Lab source: branch `restructure-lab`, commit `d27b7c3` (from Release 3.4 `ba408a8`). Build stamp `mvg60qtn`.

- **Then vs now** (Progress, opens on day 28): your starting point (gray) beside your last four weeks (green) for Well-being, Calm, At ease, Brighter mood and Sleep. Dips stay gray: dips are normal. Tap a measure for its line: Week · Month · 3 mo · 6 mo · Year (ranges appear as your data grows).
- **Patterns** after four weeks, in plain numbers both ways (for example, evening mood on practice days vs other days). No praise words, so the feedback doesn't steer the answers.
- **What we share** (Settings › Research): what your research copy holds (numbers, the week, your age range, a random id) and what never leaves (your words, exact dates, dose amounts, name). The citizen science switch is there too.
- **Research tools** (hidden: tap the version line on About 5 times): download this device's research rows as CSV or JSON, in the same shape the research database takes. Nothing is sent anywhere.
- Test data only (`companion.lab`). Earlier: R5 reports, R4b dose log, R4a flat look, R3 weekly, P3a Simple shell, R2 evening, R1 starting point.

## For the build chats
- Data: approved addition `science.insightsFirstWeek` (set once; research rows carry `insights_seen` 0/1). Research ids map to a stable UUID at export (no stored change). No schema bump. No new library.
- Tests: 401 unit (30 new: `tests/research.test.ts`, `tests/thenVsNow.test.ts`); browser full run 273 pass / 15 skipped; new `e2e/research.spec.ts`.
