# Restructure lab · P3b · goals by focus, Simple words, two-step evening check-in (Oct 20, 2026)

Lab source: branch `restructure-lab`, commit `2d9eefc` (from Release 3.4 `ba408a8`). Build stamp `mvgv7ev7`.

- **Goals by focus** (Progress › Goals): a *focus* is one thing you're practicing, like Sleep. Goals sit under their focus; goals without one sit under "No focus yet". Add a focus by name, or "Add a goal to Sleep".
- **Notes on each goal:** open a goal to add a note as things happen: **Win**, **Noticed** or **Setback**. Each goal shows its own tally ("2 wins · 1 setback · last Oct 18"). A goal with no focus asks for one first. Reach, let go and edit work as before.
- **Path lesson 2 (Name what matters)** now opens Goals in Simple, not the old Journey tab. It counts a focus and three notes, in either mode.
- **Simple words on shared screens:** lessons, the lesson list, the Begin card, the goal sheet and the gem ledger say focus and notes (no Journey, areas, evidence, quests, Grimoire or Compass). Shelf practices read plainly (no school tags); How stays open, Why folds; the last three days practiced show first.
- **Evening check-in in two short steps:** the five sliders, then the taps. The note is folded behind "Add a note for today". Same questions, same data.
- Test data only (`companion.lab`). Earlier: R6 then vs now, R5 reports, R4b dose log, R4a flat look, R3 weekly, P3a Simple shell, R2 evening, R1 starting point.

## For the build chats
- Data: approved addition `Evidence.goalId?` (optional; older notes untouched; kept by backup and merge; never in research). No schema bump. No new library.
- Tests: 414 unit (11 new: `tests/p3b.test.ts`); browser full run 287 pass / 15 skipped; new `e2e/p3b.spec.ts`; evening specs take two steps (`eveningNext` in `e2e/startingPoint.ts`).
