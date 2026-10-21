<!-- BML:START bml-local-tools -->
# Free Tools for Local Service Businesses (BML)

For BML client work only, alongside `bml/context-rules.md`. Every example uses placeholders (`<service>`, `<town>`, `<n>`). Fill them only from the client's rows; never from this file, industry norms or a guess.

## Contents
- Tool types and ship gates
- Price and number rules
- Output framing and disclaimers
- Clinical clients
- Other segments
- Lead capture and conversion
- Spec checklist

## Tool types and ship gates

| Type | What it does | Rows it needs | Ship gate (all must pass) |
|---|---|---|---|
| Cost or project estimator | Turns a few answers (size, scope, material tier) into a price **range** | D-4 (publishing approved), D-2, D-10, B-8 | D-4 `APPROVED` and says ranges may be published; every number cites D-4; output is a range with the disclaimer below |
| "Which service do I need" quiz | Routes a visitor to the right service and CTA | D-1, D-2, D-6, D-9, B-6 | Every result maps to an Active priority service; never recommends a refused service (D-9); a service at capacity (B-6) is noted in the spec and footer. Not for clinical clients if answers are symptoms |
| Service-area checker | ZIP in → "we serve you" / "we don't, here's why" / nearest location | B-8, L-1 (multi-location: each location's area) | Area list comes from B-8 or approved L-1; out-of-area result is polite and never promises service |
| Financing or payment calculator | Shows what financing the client offers and how to apply | D-7 (financing offered, lender, terms) | D-7 `APPROVED`. Showing a monthly payment, rate or term is a J-3 compliance question for a person (lending ad rules); without sign-off, describe the options and link to the lender instead of calculating |
| Maintenance schedule generator | Builds a personal schedule (what to service, when) from a few answers | D-2, D-7 (maintenance plans), F-8, F-9, I-10 | Intervals come from client-approved rows, not general advice; reminders run through the client's email tool (A-15) via **emails**, drafts only |
| Readiness checklist or timeline | "What to prepare before your first call", "how long a <service> takes" | D-3, F-8, F-9 | Time ranges from D-3; no promised completion dates |

Pick one type per concept. Note what I-3 (lead handling) and B-6 (capacity) say about the tool's service beside the concept and flag them in the footer; they inform the account lead's call, they don't block it.

## Price and number rules

- Prices, ranges, payment amounts and intervals come only from rows (`context-rules.md` §4). Prices only where D-4 says publishing is approved.
- D-4 `OPEN`, `DRAFT`, or not approved for publishing → the spec carries `[NEEDS PROOF: D-4]` at every number and is marked **cannot ship**. Offer a no-price variant (a "what affects the cost of <service>" explainer that ends in a quote request) as the alternative concept.
- Never back into a range from competitor prices (L-6), industry guides or Semrush data. Those inform the concept, not the numbers.
- Prices are volatile facts: they carry "⚠ confirm before publishing" and need a dated price-review task in the ClickUp draft (account lead as owner), not an in-session reminder.
- Multi-location: one location's prices, areas or providers never appear in another's tool.

## Output framing and disclaimers

Every estimator result is framed as an estimate. Placeholder pattern (write the final in the client's voice from 01, and check it against J-2 and J-3):

> Based on your answers, a <service> like this typically falls between <low> and <high> [D-4]. Your actual price depends on <factors from D-2 / D-10> and is confirmed after <step from D-3>. This is an estimate, not a quote.

- No "exact", "guaranteed", "lowest price" or outcome promise unless a row permits it (J-2, D-5).
- No savings or return claims ("pays for itself", "adds <n>% to home value") without a cited G or approved source.
- A market statistic cites its source and date and never implies the client's own results.

## Clinical clients

- **Never spec** a symptom checker, diagnostic quiz, "am I a candidate for <treatment>" tool, risk calculator or outcome predictor. A request for one stops: say it is a clinical and compliance question for a person (named provider and the client's approver, J-1, J-3) and offer a non-diagnostic alternative.
- Non-diagnostic candidates (insurance and payment finder from rows, appointment prep checklist, what-to-expect walkthrough, location and hours finder) can be specced, but the lead form and any tracking on a patient-facing page are listed as "Flag for compliance review (person)", not added (§7).
- Inputs never ask about health conditions, symptoms or medications. No patient data in the spec, test data or examples.
- No urgency, scarcity, fear or outcome framing in tool copy unless a page 12 row permits it; use reassurance (process clarity, credentials, access).

## Other segments

- **Home services:** service area from B-8/L-1; license details where J-3 requires; result galleries use released project photos only (J-6), never AI images presented as real work.
- **Professional services:** no outcome or result estimates (case values, returns, sale prices) unless a row permits; disclosures per J-3.

## Lead capture and conversion

- Result ungated; primary CTA is a call, booking or quote request in 01's required CTA language; "email me this" is optional.
- Who receives the lead, through what (A-15), and how fast (only what I-3 states). Agents never write to the client's CRM.
- Fields: name, phone or email, ZIP, one qualifying question. No street address unless the client's quote process (D-3) needs it, and then only after the estimate.
- Each conversion maps to a GA4 key event (A-12).

## Spec checklist

1. Scope gate passed (Website on page 00, with any qualifier stated)
2. Tool type, the job it does, and the Active service it leads to
3. Demand: L-3 rows or Semrush data with dates; any `OPEN` row answered is staged as `DRAFT` (§10)
4. Inputs, logic and every number with its row ID or `[NEEDS PROOF: <row ID>]`
5. Output copy, disclaimer and CTA in client voice; belief + proof cited
6. Ship gate result (pass / cannot ship — why)
7. Lead routing, response promise (I-3), tracking (A-12)
8. Build plan for the web team: Wix (unpublished page) or developer handoff; nothing built or published by the agent; approvals: account lead, then J-1
9. Upkeep: price-review and maintenance tasks for the ClickUp draft
10. §9 context footer
<!-- BML:END bml-local-tools -->
