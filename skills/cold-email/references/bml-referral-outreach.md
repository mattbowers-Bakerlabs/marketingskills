<!-- BML:START bml-referral-outreach -->

# Local-Service B2B Outreach (BML)

For Client mode: a BML client writing, in its own voice, to businesses that send it work or buy from it. Read `bml/context-rules.md` (repo root) first. Everything in angle brackets is a placeholder: fill it from the client's rows or leave a `[NEEDS PROOF: <row ID>]` marker. Never replace a placeholder with a plausible number, name or quote.

## Who writes to whom

Pull recipients from 03 (ICPs) and L-8 (referral ecosystem), inside the service area (B-8, L-1).

| Client type | Typical recipients | What the recipient cares about | Value angles (rows) | Watch-outs |
|---|---|---|---|---|
| Home services and construction (remodeler, kitchens, carpentry) | <builders>, <realtors>, <property managers>, <designers> | Their own client's experience; a partner who shows up, communicates and finishes | D-3 process, D-5 warranty, B-8 area, E-3 / E-6 what's unique, G-3 projects | Capacity (B-6, I-10); license details (J-3); project photos only with a release (J-6); any referral fee or gift is a compliance question for a person |
| Clinical (radiology, medical groups, specialty clinics) | <referring physicians>, <practice managers>, <care coordinators> | Access for their patients, scheduling, report turnaround, clear communication with the office | Hours, locations, insurance and booking (access); D-3 process; G-1 credentials | J-3 applies; no patient data or stories; no outcome or efficacy claims unless approved published copy makes them and a named provider reviews; no urgency or fear; never anything of value tied to referrals |
| Professional services | <adjacent advisors>, <lenders>, <attorneys> | Looking good to their own client; a reliable hand-off | D-2, D-3, G-1, G-8 partners and associations | Disclosures per J-3; no outcome guarantees |
| Multi-location brand | Same as the segment, by location | Which location serves them | Location rows for local facts; parent rows for voice and beliefs | Sender is the location or parent as the record says; never mix locations' proof |

Professional recipients are still strangers: the cold-email principles in SKILL.md apply. The referrer's question is "will this make me look good to the people I send?" Write to that.

## Signals worth sourcing

Each one needs a source link and date from `prospecting` or the user. Business facts only.

- A new <listing / development / permit> in <town> (realtors, builders)
- A new <office / practice / location> opening, or a new <practice manager / partner> (from the business's own site or announcement)
- A <community event / association> the client also takes part in (L-9, G-9)
- A public change in the recipient's services that creates a hand-off need

No sourced signal → use the segment-level version of the email. Don't manufacture a hook.

## Shapes with placeholders

**Observation → Problem → Proof → Ask**

> <Sourced observation about the recipient's business>. When that happens, <recipient type> usually needs <problem from 03 or D-2>. <Client> <proof from a G row, or [NEEDS PROOF: G-3]>. <CTA in 01's required language>?

**Referrer value (make them look good)**

> When your <clients / patients> in <town> ask about <need from D-6 or F-8>, <what the client does about it, from D-3>. Would a short <intro call / visit> be useful before your next referral?

**Belief-led (distinctiveness)**

> <One-line belief from an F row, in the client's words>. That's why <process or guarantee from D-3 / D-5>. If that matches how you work, <CTA>?

Follow-ups rotate angle as in follow-up-sequences.md: a different value row, a G proof point, a useful resource the client already has (an `asset`-tagged record), then a polite close.

## Sequence spec template

After the user approves, save to the client's Drive `OUTPUTS/EMAIL` as `<CODE>_ColdOutreach_<segment>_YY.MM.DD`. Status starts at `internal review`.

```
Client: [CODE] · Segment: <recipient type> in <area> · Mode: Client
Scope: <page 00 line and qualifier>
Sender: <name and role from the record, or [NEEDS PROOF: new — sender]> · Sending tool: <A-15 / page 00 §8, or "not recorded">
List: <file name and source (prospecting run / client-supplied)>, <n> contacts, verified <date or "not yet">
Suppression list: <file name>; includes existing referral partners and past customers (route those to `emails`)

Touch 1 — day 0 — subject: <2–4 words> — body: <copy> — CTA: <01 language>
Touch 2 — day <n> — angle: <value row> — ...
Touch 3 — day <n> — angle: <proof row> — ...
Touch 4 — day <n> — polite close — ...

Stop rules: any reply on any channel stops every channel for that contact; "please stop" → suppression list
Replies: drafted by <agent / person>, sent by <I-3 owner> within <I-3 response time>
Compliance checklist for the sender: opt-out line · postal address <from record or [NEEDS PROOF: new — sender postal address]> · secondary domain with SPF, DKIM, DMARC · warmed mailboxes · list verified, bounces under 2% · open and click tracking off · J-3 items: <list>
Measure: replies, intro calls, first referrals (record new referral sources against B-9)
Approval: internal review (account lead) → ready for client review → client review (approver: J-1 <name / role>) → approved. Nothing is loaded before approved.

[context footer, context-rules §9 — strip before sending to the client]
```

<!-- BML:END bml-referral-outreach -->
