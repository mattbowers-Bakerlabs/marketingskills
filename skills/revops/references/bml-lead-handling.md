<!-- BML:START lead-handling -->
# Lead Handling Design (BML local-service clients)

How a call, form, booking or quote request becomes a booked job or patient, and then a review or referral. Use this for BML client work in **Lead handling** mode (SKILL.md, "BML client work: choose the mode"). Rules come from `../../../bml/context-rules.md`, relative to this file (cited as "rules §n"); this file doesn't restate them.

Everything here is a template. Bracketed items are placeholders: fill them from the client's rows or leave `[NEEDS PROOF: <row ID>]`. Never fill one from this file, the upstream references or industry norms.

---

## 1. Inputs

Read these rows from the staged page 13, or from the source page by ID if page 13 doesn't carry them. `DRAFT` and `OPEN` rows are gaps, not facts (rules §2).

| Row | What it gives the design |
|---|---|
| I-3 | Who answers calls and forms, how fast, how leads are tracked today. The baseline for every response time |
| I-4 | Lead-to-customer rate and where leads drop off. Where to look first |
| I-9 | Online booking and quote tools, and what they collect |
| B-9 | Lead sources and their share. Which intake paths matter most |
| B-6, I-10 | Capacity, backlog and seasonality. Sets the at-capacity path and seasonal routing |
| A-15 | CRM, call tracking, booking tool, email platform. Where recommendations get implemented. "None" is a valid answer |
| A-12 | Tracking health. Whether calls and forms are counted at all |
| D-6 | Buyer doubts and what reduces them. Shapes follow-up content and the consult/estimate step |
| L-8 | Referral ecosystem. Referral intake and the referral-out path when at capacity |
| J-1 | Client approver and turnaround. Sign-off for the plan and every customer-facing message |
| Also | B-7 job value and repeat/referral rate · B-8 service area · D-1/D-9 services offered and refused · D-3 process · I-5 review and referral ask · A-6/A-7/A-16 Business Profile and review platforms · A-19 contacts · J-3 licensing and disclosures · G-8 partners |

Missing **lead definition** (what counts as a lead and a win: a call over a set length, a booked appointment, a signed contract)? Don't invent one. Propose a definition in the plan marked `[NEEDS PROOF: new — lead definition]` and list it under "Gaps to ask about".

## 2. Map the intake paths

One row per way a lead arrives. Fill from B-9, I-3, I-9, A-15 and A-6. Unknown cells stay `[NEEDS PROOF]`.

| Path | Where it lands | Who sees it first | Hours covered | How it's logged | Source captured? |
|---|---|---|---|---|---|
| Main phone line | | | | | |
| Tracking numbers (ads, GBP, site) | | | | | |
| Business Profile call / booking button | | | | | |
| Website form / quote request | | | | | |
| Online booking (I-9) | | | | | |
| Text / chat, if offered | | | | | |
| Local Services Ads or directory leads, if used | | | | | |
| Referrals (L-8, G-8) and walk-ins | | | | | |

Mark every path where a lead can sit unseen: after hours, weekends, a form inbox nobody owns, voicemail with no callback owner, a booking that never reaches the schedule. These are the main findings of the plan.

## 3. Stage definitions

The spine. Rename stages to the client's words (a clinic says "patient booked", a remodeler "signed contract"); keep the order.

| Stage | Enters when | Leaves when | Owner (role from I-3) | Where it's recorded (A-15) |
|---|---|---|---|---|
| **Inquiry** | A call, form, booking or message arrives on any path in §2 | Answered and screened, or closed as not a lead | [front desk / owner / intake] | |
| **Qualified** | Passes the §4 checks | Estimate or consult booked, or closed with a reason | | |
| **Estimate / consult booked** | A visit, call or appointment is scheduled | Held, or no-show → follow-up | | |
| **Proposal / quote** | Written quote, estimate or plan delivered (skip if the service is booked directly) | Accepted, declined or gone quiet → follow-up | [estimator / provider / owner] | |
| **Signed job / patient booked** | Customer commits: contract, deposit or appointment | Work completed, or cancelled with a reason | | |
| **Completed** | Job finished or visit held | Review / referral ask sent | | |
| **Review / referral ask** | Ask made per I-5 | Done; customer moves to repeat-service follow-up if B-7 shows repeat business | | |

**Closed reasons** (a short fixed list so I-4 drop-off can be measured): not a lead (spam, solicitor, job seeker, wrong number) · outside service area (B-8) · service not offered (D-9) · below minimum job · at capacity → waitlist or referred out · lost: price · lost: timing · lost: chose another provider · lost: no response. Adjust to the client; keep it under about ten.

Existing-customer service calls are not new leads. Route them separately so they don't inflate lead counts.

## 4. Qualification (replaces point scoring)

Local-service lead volume rarely supports a points model, and most clients have no marketing-automation platform. Use a short screen the person answering can run in under a minute:

1. Service we offer? (D-1, D-9)
2. Inside the service area? (B-8, L-1)
3. Can we take it on in the timeframe? (B-6, I-10)
4. Job size or type we want? (B-5, B-7)
5. Talking to the decision-maker, or who is?

Then a priority tier, with response times taken from I-3 or agreed with the client:

| Tier | Example triggers (adjust per client) | Response time |
|---|---|---|
| Respond now | Emergency or urgent service, booking requests, quote requests for priority services (D-1) | [from I-3 / agree with client] |
| Same day | Planned work, general questions | [from I-3 / agree with client] |
| Next business day | Low-fit or information-only | [from I-3 / agree with client] |

Use upstream point scoring only in B2B pipeline mode, built from the client's own won and lost jobs.

## 5. Answering and speed-to-lead

- **Coverage map:** for each path in §2, who answers in business hours, after hours, weekends and at lunch, and what happens on a miss (voicemail, answering service, call forwarding, auto text-back). Gaps here usually matter more than anything else in the plan.
- **Missed-call and form acknowledgment:** recommend an automatic acknowledgment only when someone will follow it up within the promised time. Its wording is a client deliverable (hand to `sms` or `emails`). It never promises a response time beyond I-3.
- **Benchmarks:** published speed-to-lead studies may support the argument in the plan, cited with source and year as industry research. Never present them as the client's numbers or a forecast (rules §4).
- **Measuring it:** first-response time comes from call tracking or the client's own logs (A-15). If neither exists, the measurement gap is the finding; recommend the tracking, don't estimate the time.

## 6. Routing

Route to the most specific match, then fall back. Every tree ends in a named fallback role and an at-capacity path.

```
New inquiry
├─ Existing customer / service request? → [service desk role], not the lead flow
├─ Outside service area (B-8)? → polite decline or referral partner (L-8), closed reason logged
├─ Location-specific? (multi-location) → that location's own line, hours and staff
├─ Service line needing a specialist? → [estimator / provider for <service>]
├─ At capacity for this service (B-6, I-10)? → waitlist with a date, or referral partner (L-8, G-8)
└─ Default → [first-response role]; if unanswered within [I-3 time] → [backup role]
```

Use roles, never staff or customer names, in the plan. Round-robin applies only when several people do the same job (e.g. multiple estimators).

Whatever the intake tool: every inquiry is recorded before any screening or lookup, so nothing is lost if a step fails; a resubmitted form or repeat call doesn't create a second lead, task or booking; a lead changes owner only by the agreed fallback rule, with the reason logged. This tree replaces upstream `inbound-routing.md` (B2B enrichment routing) in this mode.

## 7. Tracking

What the plan checks and recommends (implementation goes to `analytics`; source reconciliation to `attribution`):

- Call tracking numbers per source, with dynamic number insertion on the site if the client uses it (A-15)
- Form, booking and click-to-call events in GA4 (A-12)
- A source field captured at intake ("How did you hear about us?") alongside tracked source
- Booked and signed outcomes fed back to ad platforms only by the client's team or vendor; clinical: a compliance question (§11)
- The stage and closed reason recorded for every lead, so I-4 can be measured

**Data BML may read:** Windsor.ai aggregates (GA4 conversions, Ads calls and leads, Business Profile calls and bookings); summaries the client exports from their CRM or call tracking. Aggregates only: no caller names, numbers, recordings, transcripts or form contents in any output.

## 8. Follow-up

| Moment | Recommend | Rows |
|---|---|---|
| Inquiry not reached | Callback attempts and channels, then a closing message | I-3 |
| Estimate / consult no-show | Reschedule outreach by a named role | I-3 |
| Quote gone quiet | Follow-up sequence that answers the buyer doubts on file | D-6, D-7 |
| Lost on timing | Seasonal re-contact before the next busy window | I-10 |
| Completed | Review ask through the platforms on file, no incentives, no review gating | I-5, A-7, A-16 |
| Completed, repeat or referral business | Maintenance reminder or referral ask | B-7, I-5 |
| Referral received | Thank the referral source | L-8, G-8 |

Sequence content is a client deliverable: list the messages needed and hand them to `sms` or `emails`.

## 9. Automation recommendations

BML never builds these. Present each as:

| Recommendation | Fixes (finding / row) | Implemented by | Human checkpoint | Messages customers? |
|---|---|---|---|---|
| [e.g. missed-call text-back on tracking numbers] | [I-3 after-hours gap] | [client's office manager / vendor, A-15] | [who tests it before it goes live] | [Yes → wording approved by J-1] |

If the client has no CRM (A-15), recommend the simplest record that works (a shared inbox rule, the booking tool's own pipeline, a spreadsheet the front desk owns) before recommending software. Upstream `automation-playbooks.md` is a vocabulary for the client's vendor, not a build plan.

## 10. Metrics

Report against these without benchmarks; targets are agreed with the client.

| Metric | Source |
|---|---|
| Leads by path and source | Call tracking, GA4, Business Profile, booking tool |
| Answer rate and missed calls | Call tracking or phone system (A-15) |
| First-response time | Call tracking or client logs |
| Inquiry → booked rate | Client records (I-4) |
| Booked → signed / show rate | Client records |
| Cost per booked job | Ads spend (Windsor.ai) ÷ booked jobs from client records |
| Review asks sent and reviews received | Client records, review platforms (A-7) |

A recurring check (e.g. monthly answer rate and booked rate) goes to `marketing-loops` as a scheduled task, never a loop in this session. Monthly reporting picks the numbers up in `OUTPUTS/REPORTING`.

## 11. Segment notes

Apply on top of rules §7.

- **Clinical:** no patient data anywhere in the plan, examples, alerts or routing (no names, conditions, appointment details, insurance IDs). Stage notes and alerts carry only "new patient inquiry, [service line]". Intake forms that ask about conditions, call recording or transcription, dynamic number insertion and pixels on patient-facing pages, and sending leads back to ad platforms are compliance questions for a person: list them as flags, never as recommendations. Follow-up uses reassurance (access, insurance, booking, credentials), never urgency or outcome promises. Review asks follow the practice's approved process only.
- **Multi-location:** one intake map and routing branch per location; each location's numbers, hours and staff from its own rows. Never send one location's leads, proof or hours into another's flow. Shared call centers are fine if the plan shows how location is captured.
- **Home services:** service-area screening (B-8), seasonal capacity and waitlists (B-6, I-10), license details in quotes where J-3 requires them, emergency vs planned tiers.
- **Professional services:** disclosures and intake requirements per J-3; conflict checks and engagement terms are the firm's process, not BML's; no outcome promises in follow-ups. If the firm runs a true multi-step B2B sale, switch to B2B pipeline mode.

## 12. Lead Handling Plan outline

1. Summary: the three biggest leaks and what fixing them needs (in rows, not invented numbers)
2. Intake paths (§2) with gaps marked
3. Stage definitions and closed reasons (§3)
4. Qualification and priority tiers (§4)
5. Answering coverage and response times (§5)
6. Routing tree (§6)
7. Tracking (§7)
8. Follow-up map (§8)
9. Automation recommendations with owners and checkpoints (§9)
10. Metrics (§10)
11. Flags for a person (compliance, tracking on patient pages, anything needing the client's legal or vendor input)
12. Customer-facing messages to draft (handed to `sms` / `emails`)
13. Approver (J-1) and next steps
14. Context footer (rules §9)
15. Staged `DRAFT` rows for `client-context-miner` (rules §10), internal and stripped with the footer
<!-- BML:END lead-handling -->
