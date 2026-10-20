# Restructure lab · P3c · Goals › Steps, Reach and Keep doing (Oct 20, 2026)

Lab source: branch `restructure-lab`, commit `649e96d` (from Release 3.4 `ba408a8`). Build stamp `mvgylsd0`.

- **Goal (big) › Steps (small).** "Focus" is gone from Simple. Progress › Goals lists each goal on one line with its own progress; the goals fold shut and open **one at a time**.
- **Two kinds, chosen when a goal is made:** ◎ **Something to reach** (steps and a finish line; ends Reached or Let go) and ↻ **Something to keep doing** (a practice; no finish line; ends Pause or Let go, never "failed").
- **Small drops:** tap a step's circle to finish it: the bar fills, a toast ("Step done · 3 of 5 · in your wins") and a line in Wins. Tap again to undo. When every step is done, "I reached it" appears.
- **The ocean:** reaching a goal opens a full-screen **Goal reached** moment (steps, wins and days it took, your own line, +3 gems). Sparks burst; under reduced motion it simply appears.
- **Keep doing counts days:** a day counts when the evening check-in says you worked on it, or you add a note to it that day. Shown as a week of dots and "5 of the last 7 days". Keep doing goals come first in the evening check-in and Today's top 3; paused ones step aside.
- **One "+ Note" per goal** (Win · Noticed · Setback) with an optional chip for which step it's about.
- **Difficulty:** an optional Easy · Medium · Hard on each goal and each step (Cosmo, Oct 20).
- **Goal page:** steps (add, rename, set how hard, remove) or the week of days, the tally, notes with their step, and "Edit, reach / pause or let go". "Paused and done" sits quietly under the goals.
- **Path lessons:** 2 Name what matters counts a goal and three notes on it (an area still counts); 3 Set your first goal counts either kind; 6 Reach a goal asks for a goal to reach. Finishing a step counts as a practice day.
- Test data only (`companion.lab`). Earlier: P3b notes on goals, R6 then vs now, R5 reports, R4b dose log, R4a flat look, R3 weekly, P3a Simple shell, R2 evening, R1 starting point.

## For the build chats
- Data (approved, option a): `Goal.kind?` (`reach` | `keep`; absent = reach), `Goal.pausedAt?`, `Goal.difficulty?`, new list `Journey.goalSteps?` (id, goalId, title, doneAt?, difficulty?), `Evidence.stepId?`, and `Evidence.areaId` optional when the note has a `goalId`. All optional, no schema bump, kept by backup and merge (steps merge by id), never in research. No new library.
- Tests: 431 unit (20 new: `tests/p3c.test.ts`; P3b tests moved off Focus); browser full run 293 pass / 15 skipped, 0 fail; new `e2e/p3c.spec.ts`.
