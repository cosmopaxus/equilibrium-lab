# Restructure lab · R5 · experience reports and integration scales (Oct 19, 2026)

Lab source: branch `restructure-lab`, commit `68a5e5f` (from Release 3.4 `ba408a8`). Build stamp `mvg44bn6`.

- **Plan a session** from the dose log: the day, plus prep days before and integration days after (you choose; 3 and 7 to start). The calendar marks them. Any logged dose day can also start a report.
- **The report, in five steps:** Before (intention, mood, what you expect, setting, who's with you) · The dose (from your dose log) · The experience (12 effects, none to strong; how long; an optional timeline; your story, private) · The day after (your next evening check-in links in) · **Integration check-ins at 1 week, 1 month and 3 months** (the Psychedelic Integration Scales, 24 sliders, about 5 minutes).
- Shows on **Today** when a step is due, in **Journal › Reports**, and on Advanced's Home as a card.
- Text stays private; only numbers can go to research later. No gems for answers. The integration scales' wording is a placeholder until the exact text from Frymann et al. (2022) goes in.
- Test data only (`companion.lab`). Earlier: R4b dose log, R4a flat look, R3 weekly, P3a Simple shell, R2 evening, R1 starting point.

## For the build chats
- Data: `Journey.reports` (approved shape plus `sessionDay`, `prepDays`, `integrationDays`, `followUps.month3`, Cosmo Oct 19) and `pis` scale sets. No schema bump. No new library.
- Tests: 371 unit (13 new, `tests/reports.test.ts`); browser full run 265 pass / 15 skipped; new `e2e/reports.spec.ts`.
