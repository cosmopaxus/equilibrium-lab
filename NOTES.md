# Restructure lab · Intake preview (Oct 20, 2026)

Lab source: branch `restructure-lab`, commit `6b14177` (on top of P3c `649e96d`). Lab only (`LAB = true`); the live app is untouched.

Cosmo: "i want to be able to have a reset so i can continue to show the intake beginning stages … or like a preview mode?"

- **Preview the intake:** Settings › *Show the app · preview only* › **Preview the intake** (in Simple, Settings sits at the bottom of Progress; in Advanced it's the You tab).
- **Or open the link:** `https://cosmopaxus.github.io/equilibrium-lab/?preview=intake` opens straight into the preview. The address cleans itself, so a reload goes back to the real journey.
- **What it shows:** the welcome → name and age → Space → directions → Safety & Path → the **starting point** survey → a brand-new member's Today. All of it works as a real member would see it.
- **Gold band on every screen:** "Intake preview · nothing is saved", with **Start again** (back to an empty welcome) and **Exit** (your own journey comes back exactly as it was).
- **Nothing is written to the device while it runs:** no saves, no drafts, no restore snapshot, no sync. "Erase" inside the preview only empties the preview. Reloading the page also ends it.
- **Full wipe** is still Settings › Your data › Erase this device's journey (permanent).

## For the build chats
- `src/state/store.tsx`: `preview`, `previewRun`, `startPreview`, `restartPreview`, `endPreview`. The sandbox swaps the journey and drafts for an empty journey in memory; `flush`, `schedule`, `setDraft`, `flushDrafts`, `replaceJourney`, `undoRestore` and `eraseDevice` stand aside while `previewRef` is on; `endPreview` reads the real journey back with `load`. `?preview=intake` is read once at start (`PREVIEW_ON_OPEN`, web + LAB only). `switchAccount` ends the preview first; `sync/account.tsx` never syncs during it.
- `App.tsx`: `<LabBand /> <PreviewBand /> <Shell />`; `Shell` keys `AppShell` on `previewRun`, so every start, restart and exit opens fresh screens. `src/ui/PreviewBand.tsx` (ink on gold, 44 px buttons). `You.tsx` gains the lab-only row. Rails say "Preview · nothing saved".
- No data change, no new library. Not in a live build (everything is behind `LAB`).
- Tests: 435 unit (`tests/preview.test.ts` guard rules; `tests/lab.test.ts` band order). Browser: new `e2e/preview.spec.ts` (4 × phone/desktop): the device's stored data is identical before, during and after a preview; Start again; reload; the link; erase inside the preview.

---

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
