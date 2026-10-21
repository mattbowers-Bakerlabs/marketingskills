<!-- BML:START bml-local-service-flows -->
# BML Local-Service Email Flows

Local-service equivalents of the SaaS sequences in this skill, for Baker Labs (BML) clients: home services and construction, clinical practices, professional services, multi-location brands. Read `bml/context-rules.md` first (repo root; `../../../bml/context-rules.md` from this file). Every flow here is a **draft plus build spec**: nothing is loaded, scheduled or sent by the agent (SKILL.md, **BML outputs and approval**).

All examples use placeholders (`<service>`, `<town>`, `<n>`, `<client>`). Never replace a placeholder with a figure, name, quote or result that isn't in a cited row; write `[NEEDS PROOF: <row ID>]` instead.

## Contents
- Before you draft
- Flow catalogue
- Flow skeletons (inquiry, estimate follow-up, booked job, review request, seasonal/maintenance, newsletter, membership renewal and win-back, list re-engagement)
- Segment notes
- Local-service audit checklist

## Before you draft

| Check | Rows | If missing |
|---|---|---|
| Email Marketing is in scope | page 00 | Stop (§3) |
| Which platform, CRM, booking or estimate tool holds the trigger | A-15, page 00 §8, I-9 | Platform-neutral spec + `[NEEDS PROOF: A-15]` |
| Who answers inquiries, how fast, how leads are tracked | I-3 | Don't state a response time; flag I-3 |
| What the business wants more and less of, and capacity | B-5, B-6, I-10 | Don't promote any service as available "now" |
| Process from first call to finished job | D-3 | Keep "what happens next" generic and flag D-3 |
| Plans, memberships, promotions, seasonal offers | D-7, D-11 | No offer in the email |
| How they ask for reviews and referrals today; platforms that matter | I-5, A-7, A-16 | Ask for the platforms before drafting a review request |
| List size and current newsletter | I-6 | Ask; don't assume a list exists |
| Approver and turnaround | J-1 | Note "approver unknown" in the footer |

Email supports the people who answer the phone; it never replaces them. Every inquiry still gets a human reply per I-3, and every flow exits when the person replies, books or signs.

## Flow catalogue

| Flow | Trigger (from the client's tool) | Goal | Exit | Length |
|---|---|---|---|---|
| New inquiry | Form or quote request received | Confirm, set expectations, get the call or visit booked | Reply, booking, or staff marks contacted | 1–3 |
| Estimate / quote follow-up | Estimate sent, not signed | Answer doubts, get a decision either way | Signed, declined, or reply | 3–4 over 2–4 weeks |
| Booked job: what happens next | Job or consultation booked | Reduce no-shows and anxiety; explain the process | Job date passes | 1–2 |
| Post-job review request | Job marked complete | A public review on the A-16 platforms | Review link clicked or 2nd email sent | 1–2 |
| Seasonal / maintenance reminder | Calendar date from I-10 (whole list or service segment) | Book seasonal or maintenance work | Booking | 1–2 per season |
| Past-customer newsletter | Recurring (scheduled task) | Stay remembered; earn repeat and referral work (B-7) | Unsubscribe | Monthly or quarterly per I-8 |
| Membership / maintenance-plan renewal and win-back | Plan renewal date approaching; plan lapsed | Renew or rejoin | Renewed, or after final email | Renewal 2; win-back 2–3 over 60–90 days |
| List re-engagement | No opens or clicks for a long period | Keep or remove | Click, or removal | 2–3 |

## Flow skeletons

### New inquiry
1. **Immediate — "We got your request."** Who will contact them and how (I-3 wording only), what to have ready, one CTA: call `<tracked number>` or book a time (I-9). No sales pitch.
2. **Next business day, only if not contacted (staff field)** — short, from a named person (B-12 if approved), restate the one CTA.
3. **Optional, day 3–5** — answer one doubt from D-6 or a belief from F-8 ("what we wish people knew before calling"); one proof point (G-1/G-3). Then stop.

### Estimate / quote follow-up
1. **Day 2 — Questions about your estimate for `<service>`?** Restate what the estimate covers (D-3), how to reach the estimator, one CTA (call or reply).
2. **Day 7 — The doubt that stalls decisions.** One D-6 doubt and what reduces it (D-5 warranty, D-7 financing if listed); one G-3 story verbatim or `[NEEDS PROOF: G-3]`.
3. **Day 14 — Scheduling.** Only if B-6/I-10 rows support it: when the next openings are (from rows, never invented). No fake scarcity.
4. **Day 21–28 — Close the loop.** Ask for a decision either way ("still planning, went another direction, or ready to schedule?"). Exit on any reply.

Price talk follows D-4; ranges only if approved to publish. Never imply the estimate expires unless D-11 or the estimate itself says so.

### Booked job: what happens next
1. **On booking** — what happens on the day (D-3), how to prepare, who will arrive or whom they'll see, how to reschedule.
2. **Optional, day before** — only if the client's booking tool doesn't already send reminders (A-15). **Clinical:** appointment reminders belong to the practice's own system; BML doesn't draft them.

### Post-job review request
1. **Within a few days of completion — one ask.** Thank them, one sentence on why reviews help neighbours in `<town>` choose, direct link to the A-16 platform (Google Business Profile first unless rows say otherwise).
2. **One reminder, about a week later, to people who didn't click.** Then stop.

Rules (overrides any upstream review guidance):
- **No review gating:** every completed customer gets the same ask. No "were you happy?" step that sends happy customers to a review site and unhappy ones to a private form, and no segmenting the ask by score, sentiment or complaint history. A separate feedback survey is fine if it never decides who is asked to review.
- **No incentives** of any kind for a review (discounts, entries, gifts, donations per review), positive or not.
- **No scripted wording:** don't suggest what to write, star counts or keywords. Never draft a review for anyone.
- Ask on one or two platforms that matter (A-16), not every directory.
- **One ask across channels:** if the client also sends the request by text (**sms**), the customer gets one ask and at most one reminder in total, and a click or reply on either channel stops both.
- **Clinical:** don't mention the treatment, condition or visit; the ask is the same for every patient. Remind staff that responses to reviews must not confirm someone is a patient (a person decides this, not the skill).
- Referral asks are a separate email (or a **referrals** program), not bundled with the review ask.

### Seasonal / maintenance reminder
- Built from the I-10 calendar and D-7/D-11 offers; sent a few weeks before the season. Note B-6 capacity for the service beside it and flag it in the footer; if the client is booked out, offer the account lead a waitlist or later-date version as an option. An `OPEN` B-6 or I-10 is a footer gap to ask about, not a reason to hold the draft.
- One service per email; CTA to book or call. Name towns in the service area (B-8) when relevant.
- **Clinical:** general seasonal messages to the whole list or a service-line list the practice already maintains (e.g. "booking for `<service>` is open"). Never build a segment from an individual's visit history or condition; recall reminders stay in the practice's own system.

### Past-customer newsletter
- Cadence the client can sustain (I-6, I-8). The recurring send is scheduled in the client's platform by a person after approval; drafting each issue can be a scheduled task, set up only with the user's approval, whose runs draft and stop for review (BW-21).
- One primary CTA per issue. Content mix from rows: a belief or tip (F rows, F-9 customer mistakes), a project or client story (G-3, with release per J-6), a seasonal reminder (I-10), community news (G-9), a cross-sell (D-8).
- Photos only from the approved library (G-6, `asset` records) with releases on file; never AI images presented as real projects.

### Membership / maintenance-plan renewal and win-back
For clients with a plan on D-7 (maintenance agreement, service plan, membership). This replaces the SaaS churn-prevention material, which BML doesn't use.
1. **Renewal: 30 days before** — what the plan covered this term (only facts from the client's records; otherwise generic), renewal date, how to renew or change.
2. **Renewal: 7 days before** — short reminder, same CTA.
3. **Win-back: ~30 days after lapse** — what's included now; no guilt.
4. **Win-back: ~60 days** — answer one reason people let plans lapse (D-6) or ask why.
5. **Win-back: ~90 days (optional)** — rejoin offer only if D-7/D-11 lists one; then stop.
**Clinical memberships:** reassurance only, no "what you'll lose" or health-risk framing.

### List re-engagement
Upstream re-engagement fits, with two changes: the "Incentive" email needs a real D-11 offer or is dropped, and "Should we stop emailing you?" stays plain and honest (no guilt; for clinical clients no fear framing). Remove non-responders as the spec says; don't keep mailing them.

## Segment notes

- **Home services and construction:** license number where J-3 requires it; project photos only with a release (J-6); respect service area; note seasonal capacity (B-6, I-10) as context, never a gate.
- **Clinical:** no PHI anywhere (merge fields, segments, subject lines, examples); merge fields are first name with fallback and practice or location details only; no condition, treatment, appointment-type or visit-history personalisation; no urgency, scarcity, fear or outcome promises unless a page 12 row permits; patient stories only with written authorization (G-5, J-6). Whether the email platform is suitable for patient lists is a compliance question for a person: flag it `[COMPLIANCE REVIEW: HIPAA]`, don't decide it.
- **Multi-location:** one location's hours, providers, offers and proof never appear in another location's emails; voice and guardrails come from the parent brand.
- **Professional services:** required disclosures (J-3); no outcome guarantees.

## Local-service audit checklist

Use instead of the SaaS checklist in [email-types.md](email-types.md):

- [ ] New inquiry confirmation (and a not-yet-contacted nudge tied to I-3)
- [ ] Estimate / quote follow-up with a close-the-loop email
- [ ] Booked job "what happens next" (non-clinical; check the booking tool doesn't already send it)
- [ ] Post-job review request: everyone asked, no gating, no incentives, A-16 platforms
- [ ] Seasonal / maintenance reminders tied to I-10, with capacity (B-6) noted
- [ ] Past-customer newsletter at a sustainable cadence
- [ ] Membership / maintenance-plan renewal and win-back (if D-7 lists a plan)
- [ ] List re-engagement and removal of non-responders
- [ ] Every flow: exit on reply/booking, monitored reply-to, unsubscribe and postal address, consent basis recorded
<!-- BML:END bml-local-service-flows -->
