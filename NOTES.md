# Restructure lab · R4b · dose log and calendar (Oct 19, 2026)

Lab source: branch `restructure-lab` (from Release 3.4 `ba408a8`). Build stamp `mvg26bpn`.

- **Dose log** (Today › Dose log in Simple; Home › rhythm card › Dose log in Advanced): today at the top with one tap (Took it, Skipped, Off day), a month calendar with your rhythm (dose days ringed in gold, taken filled, skipped marked –, off days dotted), and your rhythm one tap away.
- **Logging a day:** the ǝvōke offering (in its own unit: Harmony in drops, Therapeutic Line in mL, Shots in servings) or Other (your name and unit), **your own amount** (never suggested or converted), time, intention, and a note. "Start low, go slow" is always shown.
- **Rhythms:** ǝvōke's protocol library now has slots (2-Day Personal Minordose, Intuitive, ǝvōke Protocol), with placeholder rhythms until the ǝvōke team fills them in. The ǝvōke Protocol asks for an intention on each dose day.
- The evening check-in starts from what you logged. Skipped days are kept. Amounts stay private (not in research for now). No dosing tools for under 18 or when the safety answers pause them.
- Test data only (`companion.lab`). Earlier: R4a flat look, R3 weekly check-in, P3a Simple shell, R2 evening check-in, R1 starting point and Support.

## For the build chats
- Data: the approved optional `DayNote` fields (`offeringId`, `unit`, `amountValue`, `takenAt`, `intention`). No schema bump. No new library.
- Tests: 358 unit (13 new, `tests/doseLog.test.ts`); browser full run 257 pass / 15 skipped; new `e2e/doseLog.spec.ts`.
