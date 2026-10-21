<!-- BML:START local-service-flows -->
# BML Local-Service SMS Flows

The default flow set for Baker Labs (BML) clients: local and regional service businesses (home services and construction, clinical practices, professional services, multi-location brands). Use this instead of the ecommerce flows in `sequence-templates.md` unless page 13 says the client sells online and the scope covers it.

Every example here uses placeholders: `<Business>` (the sender name from page 13), `<service>`, `<day>`, `<time>`, `<town>`, `<link>`, `<phone>`, `<n>`. Replace them only with facts from page 13 or the rows it cites (`bml/context-rules.md` §4). No figure, offer, response time or review count in a draft unless a row holds it; otherwise write `[NEEDS PROOF: <row ID>]`.

---

## 1. Consent bucket: proposed, never decided

Each message gets a **proposed** consent bucket. The skill proposes; a person decides. Write `[COMPLIANCE REVIEW: consent bucket]` next to every proposal, and never tell the client a flow is "compliant", "TCPA-safe" or "HIPAA-compliant".

| Bucket (proposed) | Typical messages | Why it is only a proposal |
|---|---|---|
| Informational / transactional | Appointment confirmation and reminder, arrival window, missed-call reply that only answers the caller | Becomes marketing the moment it adds an offer, upsell, review ask or "book again" line |
| Marketing | Estimate follow-up that sells, seasonal or maintenance reminders, promotions, win-back, most review requests | Needs express written consent captured separately from the booking or estimate form |
| Unclear | Review requests, recall reminders at clinical practices, estimate follow-ups that only answer a question | Ask the compliance reviewer. Treat as marketing until told otherwise |

Rules that hold for every bucket:

- **Keep each message inside its bucket.** No promotional line in a transactional message.
- **Opt-in capture is separate.** A marketing-consent checkbox sits on its own next to the phone field, unchecked by default, with the disclosure from `compliance.md`. A booking or estimate form's phone field is not marketing consent.
- **Quiet hours.** Propose the conservative default from `compliance.md` (recipient-local) and flag state rules for the reviewer. Human replies to an inbound text are outside this rule only if the reviewer says so.
- **A2P 10DLC.** List the proposed campaign use case per flow (for example *Account Notification*, *Customer Care*, *Marketing*) and keep the drafted sample messages identical to what will be sent. Registration status comes from A-15 or 00 §8. If it isn't recorded, write `[NEEDS PROOF: A-15 — A2P 10DLC registration status]`.

## 2. Clinical clients: no PHI in a text

Applies whenever the staged file lists the clinical segment, or the client could be clinical (`bml/context-rules.md` §7).

- **Never put these in a message body:** a condition, procedure, test, imaging type, result, medication, or a provider specialty that reveals one. "Your appointment at <Business> on <day> at <time>" is the pattern. Not "your MRI", not "your consultation about <condition>".
- **Never ask for health information by text.** Missed-call and after-hours replies invite a call or a booking link. They don't ask "what is this about?"
- **Watch the sender name.** If the practice name itself reveals a condition, flag it: `[COMPLIANCE REVIEW: sender name may disclose condition]`.
- **No urgency, scarcity or fear** ("only <n> slots left", "don't wait", "before it gets worse"), unless a page 12 row permits it. Use reassurance: hours, location, parking, what to bring, how to reschedule.
- **No patient names, dates of service or examples drawn from real patients** in the spec, the drafts or test data. Use the placeholders above.
- **Every clinical flow carries `[COMPLIANCE REVIEW: HIPAA]`** in the spec, and the plan says it needs sign-off from the client's compliance contact before client review. Tracking links on patient-facing pages are a question for a person (context-rules §7). Flag them; don't add them.

## 3. Flows

Timing is a starting proposal. The client's I-3 (who answers, how fast), I-9 (online booking) and D-3 (process) rows override it. Each flow lists its exit conditions; every flow also exits on STOP.

### 3a. Missed-call text-back

- **Trigger:** an inbound call to the tracked line (A-15 call tracking) goes unanswered. **Bucket:** informational (proposed).
- **Timing:** within a few minutes of the missed call. One message. No follow-up unless the caller replies.
- **Promise only what I-3 supports.** If I-3 doesn't state a callback time, the message names none.

```
<Business>: Sorry we missed your call. Reply here or book at <link> and we'll get back to you. Reply STOP to opt out.
```
```
<Business>: Thanks for calling. We're closed right now and back <day> at <time>. Book anytime at <link>. Reply STOP to opt out.
```

**Exit:** caller replies (route to the person named in I-3), books, or calls again and is answered.

### 3b. Appointment or visit confirmation and reminder

- **Trigger:** booking created in the client's booking or scheduling tool (A-15). **Bucket:** informational (proposed).
- **Sends:** confirmation at booking; reminder `<n>` hours or days before (I-3 or D-3, else propose and mark `[NEEDS PROOF: D-3 — reminder timing]`); optional day-of arrival window for in-home services.
- **Content:** business name, day, time, location or arrival window, how to confirm or reschedule. Nothing else.

```
<Business>: You're booked for <day> at <time> at <address>. Reply C to confirm or call <phone> to reschedule. Reply STOP to opt out.
```
```
<Business>: Reminder: we'll see you <day> between <time> and <time>. Need to change it? Call <phone>. Reply STOP to opt out.
```

**Exit:** appointment cancelled, or the reminder has gone. Never add an upsell, review ask or promotion to these.

**Clinical clients:** appointment confirmations and reminders belong to the practice's own system (practice management or patient communication tool). BML doesn't draft them, matching the `emails` skill. If the practice asks for help, note it as a question for the account lead and the client's compliance contact.

### 3c. Estimate or quote follow-up (home services, professional services)

- **Trigger:** estimate sent and status still open in the client's CRM or field-service tool (A-15). **Bucket:** marketing (proposed) when it sells; flag if unsure.
- **Sends:** at most two, spaced `<n>` days apart (propose; D-3 overrides). Then stop. The client's team takes it from there (I-3).
- **Content:** answer a buyer doubt from D-6 or a belief from F-8, offer a call, and point to financing only if D-7 holds it. No invented deadlines, "prices going up" or "spots filling fast". Mention schedule openings only if B-6 says there is capacity and the client confirms the window.

```
<Business>: Hi, it's <Business> following up on your <service> estimate. Happy to walk through any questions: call <phone> or reply here. Reply STOP to opt out.
```
```
<Business>: One more note on your <service> estimate: [D-6 doubt, answered in one line from the row]. Questions? <phone>. Reply STOP to opt out.
```

**Exit:** job signed, estimate declined or closed, customer replies, or two sends done.

### 3d. Post-job or post-visit review request

- **Trigger:** job marked complete or visit checked out (A-15). **Bucket:** unclear (treat as marketing until the reviewer decides).
- **Sends:** one ask `<n>` days after completion, plus at most one reminder. Then stop.
- **Ask everyone the same way.** No gating: never ask "were you happy?" first and send only happy customers to the review site, or route unhappy ones elsewhere instead of the review link. A separate "tell us about a problem" contact may sit alongside the review link, never in place of it.
- **No incentives** of any kind for a review: no discount, entry, gift or credit, and nothing tied to a positive review. (Upstream `sequence-templates.md` Post-Purchase Send 4 offers a discount for a review. Never use it.)
- **No scripted wording:** don't suggest what to write, star counts or keywords, and never draft a review for anyone.
- **Link to the platform that matters** (A-16, A-6 Google Business Profile). Don't name a review count or rating in the message.
- **One ask across channels:** if the client also sends the request by email (**emails**), the customer gets one ask and at most one reminder in total, and a click or reply on either channel stops both. Referral asks are a separate message, never bundled with the review ask.
- **Clinical:** don't mention the visit type; `[COMPLIANCE REVIEW: HIPAA]`. Responding to reviews is out of scope here.

```
<Business>: Thanks for choosing us for your <service>. If you have a minute, we'd appreciate a review: <link>. Reply STOP to opt out.
```

**Exit:** review left (if the platform reports it), any reply (route to the I-3 owner and stop the flow; a complaint gets a person's answer, never a different ask), or both sends done.

### 3e. Seasonal or maintenance reminder

- **Trigger:** date-based, from the I-10 seasonal calendar or a maintenance interval in D-7. **Bucket:** marketing (proposed). Needs express written consent.
- **Capacity as context.** Note what B-6 and I-10 say about each service in that window beside it, and flag it in the footer (`Capacity: <service> — B-6 <…>`); an `OPEN` B-6 or I-10 goes under Gaps to ask about. Never drop a service for it. Suggest staggering large lists into batches the client's team can answer, so a reminder doesn't produce more calls than I-3 can handle.
- **Content:** the reason to act now that the season really gives (from I-10 or L-10), the service, and one CTA. Towns only from the service area (B-8). No fake scarcity. Offers and codes only from D-7 or D-11.
- **Clinical recall** ("time for your annual visit"): recall reminders stay in the practice's own system; BML doesn't draft them. A general seasonal text to the practice's whole opted-in list, or a service-line list it already keeps ("booking for `<service>` is open"), is allowed: no procedure named, no urgency, never segmented by an individual's visit history or condition, and `[COMPLIANCE REVIEW: HIPAA]`.
- **Cadence:** the client's platform runs the schedule. The skill drafts the spec. It never sets up a recurring send, an in-session loop or a reminder itself; recurring drafting work becomes a scheduled task only with the user's approval.

```
<Business>: It's that time of year for <service> in <town>. Book a visit at <link> or call <phone>. Reply STOP to opt out.
```

**Exit:** booked, opted out, or the season's window closes.

## 4. Opt-in capture points (local service)

Propose where consent is captured, using A-15 and the site's forms:

- Booking or estimate form: a separate, unchecked marketing-consent box next to the phone field, with the `compliance.md` disclosure text adapted to the client's legal name. Hand form changes to `cro` (`references/form.md`).
- In person or on the job: a keyword opt-in on a leave-behind or invoice. The keyword's confirmation message carries the full disclosure.
- Phone or front desk: verbal consent is not written consent. Flag it for the reviewer rather than counting it.

## 5. Flow spec format (one table per flow)

The spec is built for the client's platform (A-15 / 00 §8). If none is recorded, say "platform unknown" and keep the spec platform-neutral.

| Field | Content |
|---|---|
| Flow | Name and purpose |
| Platform | From A-15 / 00 §8, or "unknown" |
| Trigger event | The event in the client's tool that starts it |
| Audience and suppression | Who enters; who is excluded (opted out, active job, recent send) |
| Consent bucket | Proposed bucket + `[COMPLIANCE REVIEW: consent bucket]` |
| A2P campaign use case | Proposed |
| Messages | ID, delay, copy, character count, segments (GSM-7 or UCS-2) |
| Quiet hours | Proposed window, recipient-local, flagged for state rules |
| Reply handling | Who answers replies and how fast (I-3) |
| Exit conditions | As listed above, plus STOP |
| Rows used | IDs, plus any `[NEEDS PROOF]` |
| Flags | Compliance, clinical, capacity |

Character counts: count the final text with placeholders filled in at their likely length, and say which ones are estimates. Curly quotes, emoji and accented letters switch the message to UCS-2 (70 characters per segment).
<!-- BML:END local-service-flows -->
