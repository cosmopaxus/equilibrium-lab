# Restructure lab · R4a · flat look everywhere (Oct 19, 2026)

Lab source: branch `restructure-lab`, commit `c55f1e1` (from Release 3.4 `ba408a8`). Build stamp `mvg0x4zd`.

- **No painted backgrounds anywhere**, Simple and Advanced. Cosmo: "lets get rid of the custom background images for now and keep it simple across the board."
- **One flat look**: Simple's Night navy / Day paper, Cinzel headings, plain cards, gold main buttons. Lessons, check-ins, Support, gems, Compass, onboarding, Rest and all of Advanced now match Simple.
- **Kept (small art):** the familiars, the school doors and the drawn World map (navy at Night). The grounds path map sits on a plain navy field. Home keeps its streak flame.
- The paintings stay in the source (switch `FLAT` in `src/lab.ts`) but aren't shown, preloaded or downloaded.
- Test data only (`companion.lab`). Next: R4b, the dose log and calendar, on this look.
- Earlier: R3 weekly check-in, P3a Simple shell, R2 evening check-in, R1 starting point and Support.

## For the build chats
- Published: `cosmopaxus/equilibrium-lab`. Source: `restructure-lab` `c55f1e1`. Live app untouched.
- No data change. No new library.
- Tests: 345 unit (5 new, `tests/flat.test.ts`); browser full run 245 pass / 15 skipped (9 painted-only checks pause while FLAT is on); new `e2e/flat.spec.ts`.
