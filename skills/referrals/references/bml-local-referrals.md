<!-- BML:START local-referrals -->
# BML Local-Service Referral and Review Programs

The workflow `referrals` uses for BML client work (see **BML mode** in SKILL.md). It covers the three programs local and regional service businesses actually run:

1. **Customer referral programs:** past customers or patients recommend the business
2. **Professional referrer networks:** physician groups, realtors, builders, insurers and other professionals who send work
3. **Review programs:** a steady, honest flow of reviews on Google Business Profile and the platforms that matter locally

Read `bml/context-rules.md` first (repo root; `../../../bml/context-rules.md` from this file). This file points to its sections instead of restating them. Every example below uses placeholders (`<service>`, `<n>`, `<town>`). Never replace a placeholder with a figure, name or quote the client record doesn't hold.

## Contents
- 0. Before designing anything
- 1. Customer referral programs
- 2. Professional referrer networks
- 3. Review programs
- 4. Approvals: nothing launches, sends or pays out without them
- 5. Tools
- 6. The program design record

---

## 0. Before designing anything

### Scope gate (context-rules §3)

Check page 00 for the service the work falls under. Names vary by client, so match on what the line covers:

| Work | Page 00 line to look for |
|---|---|
| Program design (any type) | Marketing strategy or planning, or a line naming referral or partner programs |
| Review program, review responses | Local SEO, Google Business Profile or reputation management |
| Ask messages (email, SMS) | Email Marketing or SMS. Hand drafting to `emails` or `sms` |
| Referral landing page | Website. Hand page work to `cro` or `copywriting` |

`Active — planning only` (or a similar qualifier) → produce the design record only, with no ask copy, cards or page copy, and say so. No matching line → stop: "<service> isn't in [CODE]'s retainer." Offer a scope note for the account lead.

### Rows to read

| Need | Rows |
|---|---|
| Where referral and repeat business comes from, job value | B-7, B-9 |
| How they ask for reviews and referrals today | I-5 |
| Capacity, seasonality, backlog | B-6, I-10 |
| Who answers new leads, and how fast | I-3 |
| Lists and tools | I-6, A-15, page 00 §8 |
| Review baseline and platforms | A-6, A-7, A-16, L-11, L-5 |
| Referral ecosystem | L-8, G-8 |
| Offers a referred customer could get | D-1, D-7 |
| Proof and permissions | G-5, G-7, J-6 |
| Approver | J-1 (A-19 for the contact) |
| Rules on rewards, ads, licensing | J-2, J-3, F-13, rest of page 12 |
| Beliefs for the ask copy | F rows (F-8 and F-9 often fit) |

A row that is `OPEN` or `DRAFT` is a gap, not a fact (context-rules §2). Write `[NEEDS PROOF: <row ID>]` where the design needs it.

### Capacity and season (context-rules §6)

Referral and partner programs create demand. Note what B-6 and I-10 say beside each program and service, and flag it in the footer (`Capacity: <service> — B-6 <…>`). Never drop or block a program for it:

- **Booked out, or in peak season:** design the program in full and note the capacity; the account lead may choose a slower launch window or a staggered push as an option.
- **B-6 is `OPEN`:** list it under Gaps to ask about in the footer; the program is still designed and readied.
- **Review programs don't add demand by themselves.** They can run in any season.

### Lead handling (I-3)

Every referred lead lands somewhere that gets answered. Name the intake path (phone line, form, referral pad, e-referral inbox) and who answers it, from I-3. Never promise a callback or scheduling time faster than I-3 supports. If I-3 is `OPEN`, the program can't launch until it's answered.

### Pick the program

| Signal | Start with |
|---|---|
| B-7 or B-9 shows professionals send much of the work (referring physicians, realtors, builders) | Professional referrer network (§2) |
| B-7 shows past customers drive repeat and referral business, and J-3 allows the ask | Customer referral program (§1) |
| A-7 shows low review count or velocity, or L-4 shows map pack winners out-reviewing the client | Review program (§3) |
| The request names one | That one, after the gates above |

Most local clients need more than one. Design them as one record (§6) so the asks don't collide: never ask the same customer for a review and a referral in the same message.

---

## 1. Customer referral programs

Local service jobs are high in value and low in frequency. A customer might buy once every few years and know only a handful of people who need `<service>` this year. So the upstream SaaS mechanics (aha moments, in-product sharing, viral coefficient, tiered gamification) don't transfer. What works is a well-timed personal ask, an easy way to pass the business along, and a thank-you that fits the client's rules.

### Start from what they do now

Read I-5. If the owner or staff already ask in person and it works, build on that: a better moment, a leave-behind, a follow-up. Don't swap a working personal ask for a code system. If I-5 is `OPEN`, ask the user before designing.

### Trigger moments

| Segment | Moments |
|---|---|
| Home services and construction | Final walkthrough, final payment, a warranty or maintenance visit, the season the work shows (a finished deck in spring) |
| Clinical | After a completed course of care or a follow-up visit, never during treatment or before results. Never tied to a condition |
| Professional services | Matter or engagement closed, an annual review |

### Share mechanisms

Ranked for local service, not SaaS:

1. **Personal ask** by the person the customer trusts: owner, project lead, provider or front desk (B-12). Give them a short script in the client's voice.
2. **Leave-behind:** a referral card or magnet with the phone number and a "mention <name>" line or code.
3. **Follow-up message** a few days after the trigger, drafted by `emails` or `sms` (consent rules live in `sms`).
4. **Referral page** on the client site with a simple form; hand page work to `cro`.

Tracking: add a "How did you hear about us? Who referred you?" question at intake (phone script and form), plus a CRM field if the client has a CRM (A-15). BML never writes to a client's CRM; the client's team records the source.

### Incentives: legality gate first

Before proposing any reward, read J-3 and F-13. **Do not assert what the law allows.** Flag it for a human.

- **Clinical practices:** treat any reward of value to patients or referrers as a compliance question for the client's named compliance contact (J-3). Default design is a **non-incentive** program: a sincere ask, a thank-you note, easy ways to share. Don't propose discounts, gift cards or credits for referring patients unless a J-3 row explicitly permits them.
- **Licensed trades and regulated professions** (for example, some contractors, real estate, insurance, legal and financial services): referral fees, rebates and gifts may be restricted by licensing boards or state rules. Flag for review under J-3 before presenting a reward.
- **J-3 `OPEN`:** write `[NEEDS PROOF: J-3 — referral reward rules for <trade or practice type> in <state>]`. Present reward options as "pending J-3 review", with the non-incentive version as the default.
- **Everyone else:** where J-3 allows a reward, options include a thank-you gift capped at `<amount>`, a credit on a future service or maintenance plan (D-7), a donation to a local cause the client supports (G-9), or a welcome offer for the referred customer built from an approved D-7 offer. Prefer giving to the referred customer, or both sides, over paying cash for leads.

**Sizing.** Use the client's own numbers: average job value and lifetime value (B-7) and margins (B-5). The upstream sizing formula in `program-examples.md` works with those inputs. Its SaaS reward ranges and benchmarks don't apply. If B-7 or B-5 is `OPEN`, mark `[NEEDS PROOF: B-7]` and size nothing.

**Timing.** Reward on a completed, paid job, never on a referral or a lead. That protects quality and limits abuse.

### Copy and segment rules

- Ask copy is a client deliverable: client voice (01), required CTA language, one belief (F) and one proof point (G) across the set (context-rules §6).
- Clinical: no urgency, scarcity, fear or outcome promises ("refer by <date>", "your friends deserve results like yours"). Use reassurance: process, credentials, access (context-rules §7).
- Home services: project photos in referral materials need a release on file (J-6). Respect service area (B-8): don't ask customers to refer people outside it.
- Multi-location: each location tracks its own referrals and uses its own proof and contacts.

### Terms

Draft a one-page terms sheet in plain language (eligibility, what counts, when any reward is given, limits). It goes to the client approver (J-1) and, if a reward of any value is involved, to the person named under J-3. BML doesn't present the terms as legally reviewed.

---

## 2. Professional referrer networks

Physician groups and hospital systems, realtors, builders and general contractors, insurers and adjusters, property managers, designers, other specialists. For these, a referral program is a **relationship program, not a payout program**. Professionals refer where it's easy, safe for their own client or patient, and reflected well back on them.

### Rules that never bend

- **No payment per referral and no value tied to referral volume** (cash, gifts, meals, events, free services, marketing support) in any design.
- **Clinical:** anti-kickback and self-referral rules (federal and state) apply to anything of value exchanged with referral sources, including meals, gifts, CE events, free services and co-marketing. Flag every such element for the client's compliance review under J-3. **Never design around these rules** (no "structure it so it doesn't count", no splitting payments, no routing value through a third party).
- **Real estate, mortgage, insurance:** settlement-service and insurance rules restrict referral fees and inducements. Flag under J-3. Don't assert what's allowed.
- **Privacy:** no patient or customer data in any partner report, newsletter or tool. Referral counts by source are fine; identities aren't.

### Steps

1. **Map the ecosystem.** Start from L-8 (organization types and organizations, never individuals), B-7 (where referral business comes from now) and G-8 (partners and associations). Add the client's own current-referrer list only if the client provides it, and keep contact names in the client's systems, not in BML artifacts.
2. **Tier the sources.** Current referrers / lapsed referrers / target organizations. Counts by tier come from the client's data, or `[NEEDS PROOF: new — referral counts by source]`.
3. **Define the value to the referrer.** What makes the client easy and safe to refer to: scheduling speed, turnaround, communication back to the referring professional, warranties, coordination with their part of the job. Take it from D-3, D-5, D-6 and I-3. Anything not on file is `[NEEDS PROOF: <row>]`, never assumed.
4. **Build the touch plan.**
   - Make referring easy: a referral pad or e-referral form, a direct line, a named contact at the client.
   - Close the loop: if D-3 shows the client reports back to referring professionals, say so in partner materials. The report itself is the client's own process, never a BML artifact, and BML never handles patient or customer details in it.
   - Educate: lunch-and-learns, CE sessions, a short quarterly update (draft it with `emails`). Clinical: every event, meal or CE element is flagged for compliance review (above).
   - Co-market with builders, realtors or designers where J-3 permits: hand the joint campaign to `co-marketing`.
   - Recurring touches (quarterly update, liaison visits) are set up as **scheduled tasks** owned by the client or the account lead, never as an in-session loop (BW-21).
5. **Track.** Referral source captured at intake (§1), a monthly count by source and tier from the client's data, and lapsed-referrer alerts. Read-only where BML has access (Windsor.ai for GA4 or call tracking, if connected); BML never writes to the client's CRM.

The upstream affiliate material (affiliate-programs.md and affiliate-operations.md: commissions, cookie windows, buyout clauses, payout reconciliation, PRM tools) doesn't apply to professional referrers.

---

## 3. Review programs

Reviews feed the map pack and local trust (BW-14). The upstream review references already fit most of this work: they ask neutrally, refuse gating and fake reviews, keep private data out of replies, and keep a permission ledger. **Use them, with the overrides below.** Where an upstream line and this section disagree, this section wins for BML clients.

### Which upstream file to use

| Task | Upstream file | BML overrides |
|---|---|---|
| Mode, invitation rules, review responses, moderation, testimonial reuse, measurement | [review-programs.md](review-programs.md) | Rules A, B, C, D, E, F |
| Incentives, cohorts, moderation, platform asset reuse, FTC review rule | [review-platform-rules.md](review-platform-rules.md) | Rules A, B, F. Its G2/Capterra incentive rows don't apply to BML clients |
| Invitation cohort, neutral invitation draft, reminders, reputation queue, quote ledger, dashboard | [review-program-operations.md](review-program-operations.md) | Rules A, C, D, E |
| GBP listing and map visibility | The `seo-audit` skill | Scope gate per that skill |

### BML overrides

- **A. No incentives, on any platform.** Upstream defaults to none but allows permitted G2/Capterra programs. For BML clients: no discounts, credits, raffles, gifts or donations for leaving a review, even where a platform permits it, and even disclosed. A request for one is declined, and the upstream non-incentivised request takes its place.
- **B. No gating, and no "existing authorization" shortcut.** Upstream's neutral-cohort rule applies as written: exclusions only for neutral reasons (opted out, already invited within `<n>` days, no valid contact), never on NPS, CSAT or likely sentiment. Upstream lets "existing authorization" cover a send or configuration. For BML, nothing sends, configures a tool, posts a reply or files a moderation report without the approvals in §4. Windsor.ai Business Profile write actions are never used.
- **C. No composed reviews.** BML never writes reviews, sample or suggested review text, or star ratings for customers. It never helps staff, family or vendors post them and never asks anyone to change or remove a review. This matches upstream. It is listed here so no "make it easy for them" step drifts into drafting review text.
- **D. No reviewer names in BML artifacts.** The upstream reputation queue and quote ledger record the review URL, exact text and attribution. In BML artifacts, record platform, date, a paraphrased theme or assertion, and the review link only where the client needs it to respond. Never the reviewer's name, a quote that identifies a person, or a health condition linked to anyone (BW-22). Quotes for reuse are cited by their G-5 row ID, verbatim, from page 11 (context-rules §4). Keep the queue and ledger in the client's own systems or the program record, never in a client's CRM written by BML.
- **E. Clinical.** A review response never confirms that someone is a patient or mentions any detail of their care, even if the reviewer did. Every clinical response is flagged for the practice's privacy or compliance contact before posting. Reusing a patient review needs written patient authorization (G-5, J-6). The upstream delivery-complaint example becomes "please contact `<role>` at `<phone or email>`", with no reference to a visit.
- **F. Local platforms.** Start with Google Business Profile (A-6), then only the platforms A-16 and L-11 name. For example, Healthgrades or Zocdoc for clinical; Houzz, Angi or Nextdoor for home services; Yelp or Facebook where relevant. Upstream's platform table covers only Google, Trustpilot, G2 and Capterra. For any other platform, check its current official policy before including it in an ask, since some (Yelp, for one) discourage asking for reviews at all. If unsure, flag it rather than assert the rule. Platform rules aren't legal approval (upstream says the same); J-3 still applies.

### Local program shape

1. **Baseline** from A-7 (count, rating, velocity, response rate per platform), marked "⚠ confirm before publishing". Where Windsor.ai has the Business Profile connected, read reviews for themes only.
2. **Cohort and timing:** use the upstream cohort rules with a local milestone: a completed job, final walkthrough or completed visit. Never send in the same message as a referral ask (§1).
3. **Ask path:** the direct review link the client takes from their Business Profile, a QR card or leave-behind, a short staff script, and an email or SMS drafted by `emails` or `sms` from the upstream neutral invitation (one ask, at most one reminder).
4. **Responses:** follow the upstream response steps in the client's voice. Every response is a draft that the client posts after approval (§4).
5. **Complaint themes:** pass recurring themes to the account lead as possible G-7 rows, staged per context-rules §10, not as public replies.
6. **Measure:** use the upstream denominators and windows, plus map pack position (L-4). Report changes, not causes.

Review tools (for example Birdeye, Podium or NiceJob) are used only if the client uses one (A-15). Check that its settings don't gate by sentiment. Trustpilot and G2 API guides upstream apply only if the client is on those platforms.

---

## 4. Approvals: nothing launches, sends or pays out without them

| Action | Who approves first |
|---|---|
| The program design and terms | BML account lead → client approver (J-1) |
| Any reward of value, or anything of value to a referral source | Also the client's compliance or legal contact named under J-3 |
| Ask messages, review requests, partner updates | Account lead → J-1. Gmail: drafts only, to the account lead |
| Review responses | Account lead → J-1 (and, for clinical, the privacy or compliance contact). The client posts |
| Launch date | J-1, with capacity noted (§0) |

BML agents never send asks, post review responses, configure referral or review tools, write to the client's CRM, or pay or promise rewards. If J-1 is `OPEN`, write `[NEEDS PROOF: J-1]` and stop at "ready for client review".

---

## 5. Tools

Most local programs need no referral software: an intake source question, a code or "mention <name>" line, a tracked phone number (call tracking, if the client has it per A-15), and a UTM-tagged referral page (`analytics`). Rewardful, PartnerStack, FirstPromoter, Tolt, Mention Me, Dub.co and similar platforms are used **only if the client uses it** (A-15, page 00 §8). Don't recommend buying one unless a row shows the volume to justify it.

---

## 6. The program design record

The design is a client strategy record: an agency artifact in Baker house style (BW-16). The client-facing pieces it lists (scripts, cards, messages, page copy, terms) are client deliverables in the client's voice and pass the distinctiveness check.

**Sections:**

1. Summary: program type(s), why, and the rows behind it
2. Gates: scope line, lead handling (I-3), J-3 status; capacity and season (B-6, I-10) noted as context
3. Mechanics per program: trigger, ask path, tracking, any reward and its J-3 status
4. Assets to produce, each with the skill that makes it (`emails`, `sms`, `cro`, `copywriting`, `co-marketing`)
5. Measurement and the source of each number
6. Approvals and launch timing (§4)
7. Open items: every `[NEEDS PROOF]` and flagged compliance question
8. Context footer (context-rules §9)

**Where it goes:**

- Draft to the session's outputs folder as `<CODE>_ReferralProgram_<topic>_YY.MM.DD` (in Cowork, `/mnt/user-data/outputs/`; elsewhere `outputs/` in the working directory). Never a machine-local path like `~/`, never Notion.
- When the user asks to file it: the client's Drive `OUTPUTS/WEBSITE` folder, resolved by ID. Never search Drive and never create a folder: if it can't be resolved, stop and report.
- ClickUp record tagged `strategy`, status `internal review`, linking the file, proposed and created only after the user approves in this conversation.

**Write-back.** If research for the program answers an `OPEN` row (for example L-8 or A-16), stage it as a `DRAFT` row in the context-rules §10 format. Never write it to ClickUp, and never fill F or J rows from research.
<!-- BML:END local-referrals -->
