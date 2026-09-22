# Farmer Billing — final mobile prototype

Working sample-data implementation of the accepted Farmer Billing Mobile Final Figma screens. Mobile only: 375 × 812 at full size, with a shorter scrollable content viewport when needed to keep navigation visible. On phones, it fits the available viewport. The original Figma file is unchanged.

## Run

Run `npm start`, then open http://127.0.0.1:4174/#home. No installation or build step is required. `npm test` checks totals, draft ownership, validation, immutable saved items, save reconciliation, and independent receipt retries.

## Client walkthrough

1. Select Vidya Vikas, choose Stall A-12, tap Continue, and start a bill.
2. Add Tomato: 2.50 kg at ₹25/kg.
3. Add Coriander Bunch: 2 bunches. Explicitly apply the sample ₹12/bunch guidance.
4. Use Tomato’s three-dot menu to change its quantity to 3 kg. Remove Coriander using its confirmation sheet.
5. Add Potato: 1 kg at ₹18/kg. The draft is ₹93.
6. Review, enter an optional phone number, and confirm the save.
7. Open receipt status to send a simulated receipt. Open history and inspect the saved transaction.
8. Start another bill at the same market. Previously saved items remain unchanged.

The Review guide and Demo controls are outside the product screen. They provide clean starting samples, failed/unknown save outcomes, receipt retry, guidance states, and a sample scale photo. Demo data is dated 16 September 2026 to match the approved examples.

## Working operations

- Market → stall selection → explicit confirmation before billing. Selecting the same market/stall preserves the draft; changing either requires confirmation before discarding a populated draft.
- Selected stall persists through reload, new bills, checkout, saved snapshots, receipts and history. Existing saved demos migrate without losing data. A-13 and B-06 are additional illustrative assigned stalls for testing this choice. Market history includes all stalls and labels each bill with its original stall.
- Catalogue search, weight/count entry, quantity controls, editable rates, explicit benchmark suggestion application, and cancel without committing pending input.
- Compact item menus, edit, removal confirmation, running bill totals and the complete checkout flow.
- Optional receipt contact validation, save progress, failed-save retry, unknown-result reconciliation and duplicate-save guards.
- Separate saved bill snapshots, receipt ready/sending/sent/failed/retry, next bill, market-scoped history search and saved transaction details.
- Camera/file selection and image preview. AI analysis is simulated, uses the sample Tomato/2.50 kg result and always requires review. Files stay in the browser; no photo is uploaded.
- Browser-local persistence for drafts, editor input, contact and saved transactions. Reloaded pending saves go to status reconciliation.

## Demonstration limits

This is a client approval prototype. All amounts are sample data. No actual transaction service, SMS/WhatsApp delivery, AI recognition, live market feed, authentication or payment collection is connected. Each browser and site address has independent local progress; this is not shared or multi-user storage. Demo profile/customer counts mirror the approved example model, not verified unique customer identities. Uploaded photo previews are temporary and do not survive reload. Use Demo controls to reset the sample.

The main journeys are functional; the 92-state Figma atlas is a specification, not a claim that every provider condition has been implemented. Recovery controls exercise the core save, receipt, guidance and AI outcomes.

## Netlify

Import this project into a separate GitHub repository and connect it to Netlify, or upload the `dist` directory directly. `netlify.toml` sets the publish directory to `dist`. Leave the build command and base directory empty; no environment variables are needed. Hash navigation does not require redirects.

## Design source

Farmer Billing · Mobile · Final, page `1040:2` in Figma file `SlIauuoAz300IF73VZWAN8`. Stall selection follows M02-S `1215:10211` and selected state M02-T `1215:10408`. Reference nodes include M01 `1044:492`, editor `1044:706`, current bill `1045:32261`, removal `1045:31395`, review/contact/confirmation `1045:32501` / `1045:32741` / `1045:32928`, saved `1045:33283`, receipt `1045:33630`, history `1045:33803` and detail `1045:34032`. Additional AI and recovery references were read directly. Exported Figma icons and sample image are committed locally; fonts and style tokens reuse the Flamingo mobile prototype conventions.
