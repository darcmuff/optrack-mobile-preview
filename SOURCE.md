# www/ source

This directory is a snapshot of `darcmuff/WheelHouse` `app/` at:

- Commit: `eb757f58e445d22521add01651bd0571b7fe03f0` (`eb757f5`)
- Message: Show onboarding and the first wheel at once after sign-up (sw v311)
- Taken: 22 November 2026 (Europe/London)

Phone layout changes were then applied on top of this snapshot, taken from WheelHouse commits `5a5cfde` and `6fad4ba` (`git diff eb757f5 6fad4ba -- app/index.html`). Those commits were later reverted on WheelHouse `dev`; they live only in this repo.

What that layout does:

- Phone tab bar (≤700px) shows only Home, Wheels and LEAPs (no Activity)
- Manual Add trade is a single column
- Home Options P&L chips wrap onto their own row
- Wheel and LEAP card headers wrap, with actions behind a ⋯ menu
- Content is padded above the tab bar, with safe-area insets
- Hit areas are at least 44px
- Create-account password placeholder is shortened to “Password, 6+ characters”

An extra CSS stacking fix, not in those WheelHouse commits, was added after checking the screenshots: on phones, `.lcw > .lc-h` is raised above the LEAP value tiles so the ⋯ menu is not covered or blurred by `.lc-hero`’s backdrop-filter. The same idea is applied to `.wc > .rot-header`. No financial formulas, calculations, parsers or business logic were changed.

`sw.js` is left at `optrack-v311`, matching the source commit. The WheelHouse service-worker bump to `optrack-v313` was not applied here.

Do not copy later WheelHouse changes back without recording the new source commit here.

A later phone-only layout pass (22 November 2026) added stacked trade cards at ≤700px for wheels and LEAPs, and two-line Monthly P&L / P&L by ticker rows. Desktop tables are unchanged above 700px. Still no financial formula, parser or business-logic changes.

A later phone-only presentation pass (22 November 2026) decluttered wheel and LEAP cards: dropped the redundant stage label, moved to-strike into the stepper sub-label, hid the Live pill when quotes are live, and removed the Profit % and “Assigned at” sub-lines. No financial formulas, parsers or business logic were changed, and the source WheelHouse commit is still eb757f5.

A later phone-only presentation pass (22 November 2026, round 2) hid PPD figures and earnings warning pills from the mobile UI, hid Fees on wheel and LEAP trade rows (fees remain in totals and data), and adjusted phone CSS so the card ⋯ button and “Called away” stepper label are not clipped at 390px. Calculation functions and stored values were not changed.

A later phone CSS pass (22 November 2026, round 3) keeps the “Called away” stepper label on one line and the header price change on one line with the ticker at 390px.

A later phone CSS pass (22 November 2026, round 4) tightens page and card side insets to ~8px from the screen edge on Home, Wheels and LEAPs, and keeps the Edit button visible on EXP trade rows.
