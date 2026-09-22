# Validation — 22 September 2026

- Eight state tests pass: approved sample totals, edit/remove arithmetic, draft isolation, immutable saved line snapshots, save retry/reconciliation without duplication, receipt retry independence, market discard guards, and input/contact validation.
- Browser walkthrough completed: select Vidya Vikas → Tomato 2.50 kg → Coriander 2 bunches with explicit ₹12 guidance → edit Tomato to 3 kg → remove Coriander → add Potato 1 kg → review → optional contact → confirm → save ₹93.
- Receipt ready → sending → sent, History search for 043 and saved details verified. Vidya Vikas history total was ₹373.50.
- Unknown save outcome survived reload; checking the save result reached a single saved snapshot.
- Receipt failure → retry → sent verified without saving another bill.
- AI sample photo → analysis → review verified; pending AI values did not enter the current bill before Add to bill.
- Invalid contact was rejected. Clearing the optional contact using normal keyboard input reached No receipt requested and saved without a receipt.
- Narrow viewport check found no horizontal content overflow and no broken rendered images. Browser viewport override reset after verification.
- WebMCP readback registered, returned the visible sample state and rejected unsupported input.
- Original sample reset before handoff. Local preview is left running at port 4174.

The prototype simulates provider outcomes. This is not validation of real AI recognition, network save services, actual receipt delivery or production concurrency. The complete Figma State Atlas has not been individually reproduced or tested.

## Stall selection follow-up

- Added explicit market → stall → confirmation flow, using the established mobile card and footer styles.
- Twelve state tests pass, including assigned-stall validation, same-stall preservation, discard protection, saved stall snapshots, next-bill context and migration of existing demos.
- Browser verification: choose A-13 → reload selection → confirm → add Potato → attempt A-12 switch → keep current bill → save → receipt and transaction detail retain A-13.
