<!-- BML:START bml-popups -->
# Popups for BML clients

Read after `../../bml/context-rules.md` (relative to the skill folder) whenever the popup is for a Baker Labs client. These rules override the upstream examples, offers, benchmarks, strategies and output steps in `SKILL.md`. Section numbers (§3, §4…) refer to `context-rules.md`.

## 1. How to treat the upstream content

- **Keep as method:** core principles, trigger types, design, close button, mobile, frequency capping, targeting, decline-copy rules, compliance and accessibility (GDPR/consent, Google's intrusive-interstitial guidance), the measurement metrics and the output structure.
- **Illustrative only:** every figure, offer and phrase in the upstream examples ("10% off", "$20", "free shipping", "Join [X] people", "Weekly tips in 5 min", "Wait! Before you go..."). Never copy them into client work.
- **Not targets:** the upstream Benchmarks (2–5% email popup, 3–10% exit intent, 10%+ click-triggered) come from ecommerce and SaaS list-building. For a local service client, report the client's own rate from A-1/A-12 if tracked, or say "benchmark unknown — set a baseline in the first <n> weeks".
- **Not defaults:** the E-commerce, B2B SaaS and Content/Media strategies. Use section 2 below unless the client is a product or ecommerce business (B-1 says so).

## 2. Goal map — local service popups

Pick the goal from the client's lead definition (page 13, I-3, I-9), not from list size. One primary goal per popup.

| Goal | Use when | Best trigger | CTA and destination | Rows to check |
|---|---|---|---|---|
| **Call** | Mobile visitors; someone answers the phone in business hours | Scroll on service pages; click-triggered from "Call" buttons | Click-to-call with the tracked number | I-3 (who answers, hours), A-15 call tracking, 01 CTA language |
| **Book** | Online booking exists or is wanted | Click-triggered or service-page scroll | Booking tool link or embedded widget | I-9, A-15 booking tool, B-6 open slots |
| **Quote / estimate request** | Jobs need a visit or a quote | Exit intent on service and gallery pages; page-count | Short form (route form detail to `cro` › `references/form.md`) | I-3 response time, D-3 process, B-8 service area |
| **Seasonal booking** | A season or promotion window is coming | Time-boxed banner or slide-in, on only for the window | Book or quote, with the dates from the row | I-10, D-11, B-6 (capacity in that window) |
| **Lead magnet download** | The client has (or approves) a guide, checklist or cost guide | Click-triggered or scroll on blog/guide pages | Download, then the follow-up the client can actually send | Lead magnet record (`lead-magnets`), I-6, A-15 email platform |
| **Email / newsletter capture** | Only if I-6 shows a list in use and A-15 names an email platform | Scroll on content pages | Subscribe | I-6, A-15; follow-up sequence via `emails` only if Email Marketing is in scope on page 00 |
| **Announcement** | New location, hours change, new service (D-11) | Top banner, time-limited | Learn more / book | D-11, volatile facts block |

**Ecommerce-style email-for-discount capture** is for product or ecommerce clients only, with an approved D-7/D-11 offer.

**Local service strategies** (replace the upstream Common Popup Strategies):

1. Service pages: quote or call slide-in on scroll; exit intent offers the quote form or a lead magnet, not a discount.
2. Blog and guides: click-triggered lead magnet; scroll slide-in to the related service.
3. Seasonal: one time-boxed banner during the I-10 window, removed when the window closes; capacity (B-6) noted in the spec and footer.

**Page rules for local service sites:** exclude contact, quote, booking, careers and thank-you pages; show service-area-specific popups only on pages for that area (B-8, L-1).

## 3. Offers gate

1. **Sources.** Offers, discounts, financing, packages and memberships come from D-7; promotions and seasonal offers from D-11 (with their dates); guarantees and warranties from D-5; any price only if D-4 says it may be published. Cite the row ID in the spec.
2. **Missing.** No row → write `[NEEDS PROOF: D-11]` (or D-7 / D-5) in the copy and list it in the footer. Never invent an amount, percent, deadline or guarantee, even as a placeholder that reads like a real figure.
3. **Status.** `DRAFT` offers are never stated (§2). Promotions are volatile: mark "⚠ confirm before publishing" and set the popup's end date to the offer's end date.
4. **Urgency and scarcity.**
   - Clinical clients: no discount, countdown, scarcity, urgency or fear framing unless a page 12 row permits it (§7). Use reassurance instead: approved social proof, credentials, process clarity, access (hours, insurance, online booking).
   - Every client: check J-2 (claims never to make) and J-3 (regulatory and licensing ad rules) before any offer copy.
   - Countdown timers only for a real, dated deadline from D-11 — never an evergreen timer that resets per visitor.
   - "Only <n> spots" style scarcity only if B-6 supports it and a row states the number.
   - No escalating offers across visits ("bigger discount on exit") unless the client approved each tier in D-7/D-11.
5. **A request that needs a violation** (e.g. a countdown discount for a clinical client with no permitting row) → stop before drafting and name the row (§5). Offer a compliant alternative.

## 4. Capacity and lead handling

- Note what B-6 (capacity, seasonality, backlog) and I-10 say about the promoted service in the spec and flag it in the footer (`Capacity: <service> — B-6 <…>`; an `OPEN` row goes under Gaps to ask about). Never drop or block the popup for it; at capacity or out of season, offer the account lead a waitlist or "book for <next season>" variant as an option.
- Never promise a response time beyond I-3 ("we'll call you within <time>" only if I-3 says so). Name who receives the leads and how (I-3) in the spec.
- Don't ask for fields the client can't act on; every field has a use in I-3.
- Privacy: no form submissions, customer details or reviewer names in the spec (a G-5 quote keeps only the attribution its permission allows).

## 5. Segment rules (on top of §7)

- **Clinical:** no fields asking about conditions, symptoms or treatment history; no patient stories without written authorization (G-5, J-6); tracking pixels and lead forms on patient-facing pages, including this popup's own form and tracking events, are a compliance question for a person — list them in the spec as "Flag for compliance review (person)", don't add them.
- **Home services and construction:** show license details where J-3 requires them; project photos only with a release on file (J-6); respect service area (B-8) in targeting and copy.
- **Multi-location:** one popup per location where offers, hours or booking differ; never show one location's offer, hours or providers on another's pages. Parent-brand guardrails apply to every location.
- **Professional services:** disclosures per J-3; no outcome guarantees unless a row permits them.

## 6. Copy (placeholders only)

Fill every `<…>` from a cited row, or leave `[NEEDS PROOF: <row ID>]`.

| Element | Placeholder pattern | Source |
|---|---|---|
| Headline — benefit | "Get your <service> <outcome> without <buyer doubt>" | D-2, D-6 |
| Headline — seasonal | "Book <service> before <date>" | I-10, D-11 |
| Headline — belief-led | "<what the client wishes customers knew>" | F-8, F-9 |
| Proof line | "<count> reviews on <platform> ⚠ confirm before publishing" or one verbatim quote with its row | A-7, G-5 |
| Offer line | "<offer from row>" or `[NEEDS PROOF: D-11]` | D-7, D-11, D-5 |
| CTA | The client's required CTA language | 01 |
| Decline | Neutral: "No thanks" / "Maybe later" | — |

Write in the client's voice (01) and style (02); this skill's own voice is not the client's. Short units are checked for distinctiveness across the popup set (§6): the set uses at least one F row and one G row, or the footer says `Distinctiveness: FAIL — not client-ready`.

## 7. Platform and implementation

- Read the site platform from page 00 §8 and A-14. BML-built sites are usually Wix (popups there are lightboxes); for other platforms, spec against what that platform supports.
- Confirm in the spec which triggers the platform supports natively. If one isn't (exit intent on mobile, page-count), spec a fallback rather than adding a third-party script.
- Popup or form tools (OptinMonster, Klaviyo forms, Privy, HubSpot forms…) only if the client uses one (page 00 §8, A-15). Don't recommend adding a tool as a default.
- **Never publish.** The skill does not edit the site, turn a popup on, or use any site-builder tool to do so. It stages a spec; the web team builds it after the client's approver (J-1) signs off.
- Tracking: list the events (view, submit, close, CTA click) and which become GA4 key events (A-12); route setup to `conversion-tracking` or `analytics`.
- A/B tests only if the platform or tool supports them; plan with `ab-testing`.

## 8. Spec and output

File name: `<CODE>_PopupSpec_<topic>_YY.MM.DD`. Agency artifact for the web team and client review; copy inside it is a client deliverable in client voice.

```
Popup spec · [CODE] · <short topic>
Status: DRAFT — not live. Approver: <J-1 name/role>
Platform: <page 00 §8 / A-14> · Tool: <only if client uses one>
Goal: <call / book / quote / seasonal booking / lead magnet / email capture / announcement>
Pages shown: <URLs or page types> · Excluded: <contact, booking, thank-you…>
Type and trigger: <type> · <trigger + fallback if not native>
Targeting and frequency: <audience> · <cap, dismissal memory>
Dates: start <date> · end <date from D-11 / I-10>
Capacity (context): <service — B-6 / I-10 note, or OPEN>
Offer: <text> (row <ID>) or [NEEDS PROOF: <row ID>]
Copy: headline · subhead · proof line · CTA · decline
Lead destination: <phone / booking tool / form recipient> (I-3)
Consent and privacy: <consent text, privacy policy link, no pre-checked boxes>
Mobile and Google interstitial check: <pass / notes>
Tracking events: <list> (A-12)
Segment flags: <clinical form/pixel flag, license line, location>
```

- **Where:** Drive `OUTPUTS/WEBSITE` in the client's folder, resolved by ID from the router. Never search Drive or create folders; if the folder can't be resolved, stop and report.
- **Record:** a ClickUp record tagged `website`, status `internal review`.
- **Approval:** save to Drive and create the ClickUp record only after the user approves in the conversation. The account lead reviews the spec; anything that goes live then waits for the client's approver (J-1).
- **Footer:** end with the context footer (§9). Strip it before the spec goes to the client.
<!-- BML:END bml-popups -->
