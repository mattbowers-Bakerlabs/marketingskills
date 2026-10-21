---
name: cold-email
description: Write and run B2B cold outbound that gets replies, from cold emails and follow-ups to sending setup, LinkedIn, multichannel cadences, and reply handling. Use when the user mentions "cold email," "cold outreach," "outbound," "prospecting email," "SDR emails," "follow-up sequence," "nobody's replying," "email deliverability," "sending domains," "warm up inboxes," "LinkedIn outreach," "connection request message," "multichannel sequence," "cadence," "cold call," "voicemail," "handle replies," "AI SDR," "teardown outreach," or "product-led outbound." Send from secondary domains, verify lists first, turn off open tracking, and stop every channel when a prospect replies. Copy avoids AI tells like 'it's not X, it's Y' reveals. For building the list and account research, see prospecting. For lifecycle email, see emails. For call scripts and sales collateral, see sales-enablement.
metadata:
  version: 2.2.0-bml.1
---

# Cold Email Writing

You are an expert in cold outbound. Your goal is to write emails that sound like they came from a sharp, thoughtful human — not a sales machine following a template — and to make sure they reach the inbox, work alongside the other channels, and turn replies into meetings.

## Before Writing

**Check for product marketing context first:**
If `.agents/product-marketing.md` exists (or `.claude/product-marketing.md`, or the legacy `product-marketing-context.md` filename, in older setups), read it before asking questions. Use that context and only ask for information not already covered or specific to this task.

<!-- BML:START context -->

**Baker Labs (BML) work: decide who is sending first.** In cold email the sender sets the rules.

| Mode | Sender | Use when | Rules |
|---|---|---|---|
| **Client** | The client, written in the client's voice (page 01). A client deliverable | The request names a client code (`[ABC]`) or client name, runs in a client's Claude Project, or the staged `.agents/product-marketing.md` starts `Generated for` or `UNGENERATED for` | Read `bml/context-rules.md` (repo root) before anything else. Where it conflicts with this skill, it wins. Everything marked "Client mode" below applies |
| **Self** | BML, for its own new business. Also any non-client project | BML is the sender, including outreach to a prospect whose staged file starts `INTAKE DRAFT for` | Outside the client rules: no scope gate, footer or distinctiveness check. Use Baker house style and never load a client's voice. Still applies: nothing sends (Gmail drafts only), personal hooks only from sourced facts, business contact data only, opt-out line and postal address |

No signal → ask one question: "Who is sending this: a BML client, or BML itself?"

**Client mode:**
- **Context:** if the staged file is missing or names another client, run `product-marketing` (Load) first (§1). Never edit `.agents/product-marketing.md` or page 13, and decline any offer to update the context file or log a learning; changes become `context` tasks (§8).
- **Scope gate (§3):** the service is outbound / cold outreach on page 00. `Email Marketing` on its own covers people who already know the client (route that to `emails`). It covers cold outreach only if its qualifier names outbound, cold email or prospecting. If page 00 doesn't list outbound, stop: "Outbound email isn't in [CODE]'s retainer." Offer a scope note for the account lead. Respect qualifiers such as "copy only" (no list work) or "planning only" (a spec, no email copy).
- **Read order (§1):** router → staged page 13 → Monthly Context Brief → source rows only when needed: 03 ICPs and L-8 (referral ecosystem) for who; 01 for voice and required CTA language; 04 for the buyer journey; D and E rows for value; G for proof; F for beliefs; page 12 and F-13 for guardrails; A-15 and page 00 §8 for the client's sending tool and CRM; J-1 for the approver. Don't browse Drive or search ClickUp broadly.
- **Recipients:** business contacts only: referrers, partners and commercial buyers (a remodeler writing to builders and realtors; a radiology group writing to referring physicians). Cold email to consumers or patients is out of scope for this skill.
- **Output:** a sequence spec, saved after the user approves to the client's Drive `OUTPUTS/EMAIL` folder (by folder ID from the router; never search Drive or create folders; if the folder can't be resolved, stop and report). Name it as the template in [bml-referral-outreach.md](references/bml-referral-outreach.md) shows. Propose a ClickUp record tagged `email` with status `internal review`, and create it only after the user approves. Nothing sends (see "BML: nothing sends from an agent" below).

**Self mode:** never name a BML client, or use a client's results, stories or quotes, unless that client's record shows it approved the use in BML's own marketing. Facts about a prospect from an `INTAKE DRAFT` file are public research: use only sourced ones, and never assert a `⚠ UNVERIFIED` item (§1). BML's own outreach usually fits the value-first teardown in [outbound-plays.md](references/outbound-plays.md); a person reviews every teardown before it goes out.

<!-- BML:END context -->

Understand the situation (ask if not provided):

1. **Who are you writing to?** — Role, company, why them specifically
2. **What do you want?** — The outcome (meeting, reply, intro, demo)
3. **What's the value?** — The specific problem you solve for people like them
4. **What's your proof?** — A result, case study, or credibility signal
5. **Any research signals?** — Funding, hiring, LinkedIn posts, company news, tech stack changes

Work with whatever the user gives you. If they have a strong signal and a clear value prop, that's enough to write. Don't block on missing inputs — use what you have and note what would make it stronger.

<!-- BML:START inputs -->

**Client mode: answer the five questions from the record, not from guesses:**

1. **Who:** a segment from 03 (ICPs) or L-8 (referral ecosystem), inside the service area (B-8, L-1): for example <builders / realtors / property managers> in <town>, or <referring practice type> within <n> miles. The list comes from `prospecting` or from the client. This skill doesn't build lists or find contacts.
2. **What:** a reply, an intro call or a first referral, using 01's required CTA language. Don't use SDR, MQL, SQL or "pipeline" in client deliverables unless the client's rows do. The local-service chain is contacted → replied → intro call → first referral (B-9 records where referrals come from).
3. **Value:** from D-1 and D-2 (services; who, problem, outcome), D-3 (process) and E-3 / E-6 (what's unique). If B-6 or I-10 shows a service at capacity or out of season, note it beside that service and flag it in the footer; don't drop the service for it.
4. **Proof:** from G rows or citable A rows only. If the fact isn't there, write `[NEEDS PROOF: <row ID>]` (§4). This overrides "a result, case study, or credibility signal" here and every "add proof" step in the reference files. A resource to share in a follow-up comes from an approved `asset`-tagged record, not a new one made up for the email.
5. **Signals:** only facts that `prospecting` or the user supplied with a source link and date, such as a new <listing / permit / office opening / hire> at <prospect business>. No source means no personal hook: use the segment-level message ("no hook found"). Never write "I saw your post", "congrats on" or "loved your talk" without a sourced fact behind it.

"Don't block on missing inputs" still holds for the writing. Missing client facts become `[NEEDS PROOF]` markers, never plausible numbers.

<!-- BML:END inputs -->

---

## Writing Principles

### Write like a peer, not a vendor

The email should read like it came from someone who understands their world and isn't trying to sell them something. Use contractions. Read it aloud. If it sounds like marketing copy, rewrite it.

### Every sentence must earn its place

Cold email is ruthlessly short. If a sentence doesn't move the reader toward replying, cut it. The best cold emails feel like they could have been shorter, not longer.

### Personalization must connect to the problem

If you remove the personalized opening and the email still makes sense, the personalization isn't working. The observation should naturally lead into why you're reaching out.

See [personalization.md](references/personalization.md) for the 4-level system and research signals.

### Lead with their world, not yours

The reader should see their own situation reflected back. "You/your" should dominate over "I/we." Don't open with who you are or what your company does.

### One ask, low friction

Interest-based CTAs ("Worth exploring?" / "Would this be useful?") beat meeting requests. One CTA per email. Make it easy to say yes with a one-line reply.

---

## Voice & Tone

**The target voice:** A smart colleague who noticed something relevant and is sharing it. Conversational but not sloppy. Confident but not pushy.

**Calibrate to the audience:**

- C-suite: ultra-brief, peer-level, understated
- Mid-level: more specific value, slightly more detail
- Technical: precise, no fluff, respect their intelligence

**What it should NOT sound like:**

- A template with fields swapped in
- A pitch deck compressed into paragraph form
- A LinkedIn DM from someone you've never met
- An AI-generated email (avoid the telltale patterns: "I hope this email finds you well," "I came across your profile," "leverage," "synergy," "best-in-class")

---

## Structure

There's no single right structure. Choose a framework that fits the situation, or write freeform if the email flows naturally without one.

**Common shapes that work:**

- **Observation → Problem → Proof → Ask** — You noticed X, which usually means Y challenge. We helped Z with that. Interested?
- **Question → Value → Ask** — Struggling with X? We do Y. Company Z saw [result]. Worth a look?
- **Trigger → Insight → Ask** — Congrats on X. That usually creates Y challenge. We've helped similar companies with that. Curious?
- **Story → Bridge → Ask** — [Similar company] had [problem]. They [solved it this way]. Relevant to you?

For the full catalog of frameworks with examples, see [frameworks.md](references/frameworks.md).

---

## Subject Lines

Short, boring, internal-looking. The subject line's only job is to get the email opened.

- 2-4 words, lowercase, no punctuation tricks
- Should look like it came from a colleague ("reply rates," "hiring ops," "Q2 forecast")
- No product pitches, no urgency, no emojis, no prospect's first name

See [subject-lines.md](references/subject-lines.md) for the full data.

---

## Follow-Up Sequences

Each follow-up should add something new — a different angle, fresh proof, a useful resource. "Just checking in" gives the reader no reason to respond.

- 3-5 total emails, increasing gaps between them
- Each email should stand alone (they may not have read the previous ones)
- The breakup email is your last touch — honor it

See [follow-up-sequences.md](references/follow-up-sequences.md) for cadence, angle rotation, and breakup email templates.

---

## Before You Send

Copy only matters if it reaches the inbox. Before the first send:
- Send from **secondary domains**, never your primary one, with SPF, DKIM, and DMARC set up and mailboxes warmed for 3–4 weeks.
- **Verify every list** right before upload and keep bounces under 2%.
- **Turn off open and click tracking.** Measure replies.
- Include a plain-text **opt-out line and your postal address** in every email.

Domain and mailbox math, the Google, Yahoo, and Microsoft rules, monitoring, and stop-loss thresholds are in [deliverability.md](references/deliverability.md).

<!-- BML:START sending -->

**BML: nothing sends from an agent.** For all BML work, this overrides "Before the first send", "Beyond Email", "When They Reply" and the reference files wherever they imply that an agent sends, connects, calls, books or configures:

- Never send an email, connect or message on LinkedIn, place a call or start a sequence. Never configure a sending tool, buy domains, change DNS, warm mailboxes or upload lists. A person does these. Buying domains, mailboxes or tools is spend and needs explicit approval first.
- **Client mode deliverable:** a sequence spec, using the template in [bml-referral-outreach.md](references/bml-referral-outreach.md), for the client's sending tool as recorded on A-15 or page 00 §8. If no tool is recorded, say so; don't pick one. Gmail drafts only as review copies addressed to the account lead, never to prospects from a BML mailbox.
- **Self mode deliverable:** Gmail drafts in the user's mailbox, never sent, or the same spec.
- **Approval checkpoint (Client mode):** the copy and the list move through internal review (account lead) → ready for client review → client review (J-1 approver) → approved. Name the client's approver from J-1 in the handoff. Nothing goes into a sending tool before `approved`.
- Keep the deliverability and CAN-SPAM rules above as a checklist in the spec for whoever sends: opt-out line, the sender's postal address (from the record, else `[NEEDS PROOF: new — sender postal address]`), secondary domains, list verification and tracking off. Don't tell the client the program is compliant (CAN-SPAM, state rules, J-3): open questions are `[COMPLIANCE REVIEW: <topic>]` for a person, as in **sms**.
- Recurring outbound work (signal sweeps, reply triage, domain health checks) is set up as a scheduled task only with the user's approval; its runs draft and stop for review, never an in-session loop.

<!-- BML:END sending -->

---

## Beyond Email

Most outbound that works in 2026 runs on more than one channel:
- **LinkedIn**: profile, limits, the engage-then-connect sequence, message copy, and the automation decision. See [linkedin-outreach.md](references/linkedin-outreach.md).
- **Cadence**: how email, LinkedIn, calls, video, and ads fit together by tier, and the rule that a reply on any channel stops all of them. See [multichannel-cadence.md](references/multichannel-cadence.md). Call scripts are in the sales-enablement skill.
- **Plays**: value-first teardowns for services, product-led outbound for self-serve SaaS, problem-led outbound with a free sample, and founder-led outreach. See [outbound-plays.md](references/outbound-plays.md).

## When They Reply

Classify every reply (positive, information request, objection, not now, referral, out of office, unsubscribe), answer positive replies within minutes, and book with two proposed times plus a link. What an agent can handle alone and what needs a human is in [reply-handling.md](references/reply-handling.md).

<!-- BML:START replies -->

**BML replies:** the agent drafts suggested replies; a person sends them. For Client mode, "answer positive replies within minutes" becomes "within the response time I-3 records", and the handoff names who answers (I-3). Don't promise referrers anything faster. Book through the client's booking tool or call line (A-15, 01 CTA); never invent a booking link. Logging replies in the client's CRM is a person's step: agents never write to a client's CRM. Every unsubscribe or "please stop" goes on the suppression list the spec names, and stays there for later campaigns.

<!-- BML:END replies -->

---

## Quality Check

Before presenting, gut-check:

- Does it sound like a human wrote it? (Read it aloud, and check for the AI tells below)
- Would YOU reply to this if you received it?
- Does every sentence serve the reader, not the sender?
- Is the personalization connected to the problem?
- Is there one clear, low-friction ask?

<!-- BML:START guardrails -->

**Client mode: also check, before presenting (context-rules §4–§7):**

- **Guardrails:** every page 12 row and F-13, at any status including `DRAFT`. A request that needs a violation (naming a competitor J-4 forbids, a claim J-2 rules out) → stop before drafting and name the row.
- **Distinctiveness (§6):** the sequence as a whole builds on at least one F row and one G row. If it can't, mark the footer `Distinctiveness: FAIL` and list the rows to fill.
- **Capacity and lead handling (§6):** no promises to referrers of turnaround, response time or volume beyond B-6 and I-3. Leave out referrers outside the service area (B-8).
- **Segment rules (§7):**
  - *Clinical* (outreach to referring physicians and practices): professional outreach still follows J-3. No patient data, cases or stories in any email or list. No outcome or efficacy claims about patients unless approved published copy makes them and a named provider reviews them. No scarcity, urgency or fear: the breakup email is a polite close, not "loss aversion" or "last chance". Never offer gifts, payments or anything of value tied to referrals. Any referral incentive is a compliance question for a person: flag it, don't write it.
  - *Home services and construction:* license details where J-3 requires them; service area; seasonal capacity (B-6, I-10) noted as context, never a gate. A referral fee or gift to a realtor or builder is a compliance question for a person.
  - *Professional services and real estate:* disclosures per J-3; no outcome guarantees.
  - *Multi-location:* the sender is the location or the parent brand as the record says; never mix one location's proof into another's outreach.
- **Privacy:** prospect data is business contact information only (name, role, business email, business address) plus the sourced business fact. No personal phones, home addresses or notes about people's private lives. The list lives in the Drive file, not in ClickUp comments or the footer. One client per run: never reuse another client's list, copy or proof.
- **Footer:** end the deliverable with the §9 context footer (internal; strip it before the spec goes to the client).

<!-- BML:END guardrails -->

---

## What to Avoid

- Opening with "I hope this email finds you well" or "My name is X and I work at Y"
- Jargon: "synergy," "leverage," "circle back," "best-in-class," "leading provider"
- Feature dumps. One proof point beats ten features
- AI tells, which prospects spot in the first line and delete:
  - Contrast reveals ("It's not about X, it's about Y") and "no X, no Y, no Z" lists
  - A claim followed by a comma and more restating clauses
  - Self-answered questions ("The result? 40% more meetings.") and colon reveals. A real question you want them to answer is fine
  - Stock phrases: "Here's the thing," "I'll be honest," "Quick question" as an opener, "Say goodbye to," "Unlock," "Take it to the next level"
  - Em dashes
  - For the full blacklist, use the **copywriting** skill's AI-tells reference
- HTML, images, or multiple links
- Fake "Re:" or "Fwd:" subject lines
- Identical templates with only {{FirstName}} swapped
- Asking for 30-minute calls in first touch
- "Just checking in" follow-ups

---

## Data & Benchmarks

The references contain performance data if you need to make informed choices:

- [benchmarks.md](references/benchmarks.md) — Reply rates, conversion funnels, expert methods, common mistakes
- [deliverability.md](references/deliverability.md) — Sending domains, mailboxes, mailbox-provider rules, warmup, monitoring, stop-loss rules
- [linkedin-outreach.md](references/linkedin-outreach.md) — LinkedIn profile, limits, sequence, copy, automation risk
- [multichannel-cadence.md](references/multichannel-cadence.md) — Cadences by tier, cross-channel rules, calls, video, direct mail, ads
- [outbound-plays.md](references/outbound-plays.md) — Value-first teardown, product-led, problem-led, and founder-led plays
- [reply-handling.md](references/reply-handling.md) — Reply types, speed, booking, early objections, agent permissions
- [personalization.md](references/personalization.md) — 4-level personalization system, research signals
- [subject-lines.md](references/subject-lines.md) — Subject line data and optimization
- [follow-up-sequences.md](references/follow-up-sequences.md) — Cadence, angles, breakup emails
- [frameworks.md](references/frameworks.md) — All copywriting frameworks with examples

Use this data to inform your writing — not as a checklist to satisfy.

<!-- BML:START benchmarks -->

**BML: the reference data is SaaS and B2B-tech.** Every figure, company name, persona and example email in the references is illustrative. Never copy one into client work or quote one to a client as an expectation. There is no local-service benchmark on file for referrer outreach: use the client's own results (A rows, I-2) or say "benchmark unknown". The frameworks are fine as shapes; [bml-referral-outreach.md](references/bml-referral-outreach.md) has local-service shapes with placeholders and the sequence spec template.

deliverability.md, linkedin-outreach.md, multichannel-cadence.md and reply-handling.md describe actions an agent could take (buying domains, LinkedIn automation, autonomous replies, CRM logging). Each carries a BML header; for BML work, "BML: nothing sends from an agent" above overrides them. In outbound-plays.md, product-led outbound is SaaS-only, and the value-first teardown is the usual Self-mode play.

<!-- BML:END benchmarks -->

---

## Tool Integrations

For setup, see the [tools registry](https://github.com/coreyhaines31/marketingskills/blob/main/tools/REGISTRY.md), including its sales outbound quick start. Tools most used with this skill:

| Job | Tools | Guides |
|-----|-------|--------|
| Email sending and sequences | Instantly, lemlist, Outreach | [instantly.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/instantly.md), [lemlist.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/lemlist.md), [outreach.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/outreach.md) |
| LinkedIn steps | HeyReach, lemlist (both carry LinkedIn terms-of-service risk) | [heyreach.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/heyreach.md) |
| Verification before send | Truelist, Hunter | [truelist.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/truelist.md), [hunter.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/hunter.md) |
| CRM and reply logging | HubSpot, Attio, Close | [attio.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/attio.md), [close.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/close.md) |
| Booking | Calendly, SavvyCal | [calendly.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/calendly.md), [savvycal.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/savvycal.md) |

Instantly's webhooks (reply received, lead interested, bounced, unsubscribed) are the simplest way to drive the cross-channel stop and reply triage from an agent.

<!-- BML:START tools -->

**BML:** these tools are examples, not BML's stack. Name a sending, verification, LinkedIn, CRM or booking tool only if the client uses it (A-15, page 00 §8), and even then the agent writes the spec and a person loads and runs it. BML's own systems for this skill: Drive `OUTPUTS/EMAIL` for the deliverable, a ClickUp record tagged `email`, Gmail drafts only. Don't route work through connectors that are authorized but not in use (HubSpot and others). No credentials in specs or chats.

<!-- BML:END tools -->

---

## Related Skills

- **prospecting**: For building and qualifying the prospect list, signals, enrichment, verification, and account research — the natural upstream step before cold-email
- **copywriting**: For landing pages and web copy
- **emails**: For lifecycle/nurture email sequences (not cold outreach)
- **social**: For LinkedIn and social posts
- **product-marketing**: For establishing foundational positioning
- **revops**: For lead scoring, routing, pipeline management, and the outbound stage model
- **sales-enablement**: For cold call scripts, voicemails, and deal-stage objections
- **marketing-loops**: For running outbound on a schedule (signal sweeps, reply triage, domain health, sequence reviews)

<!-- BML:START related -->

**BML routing:**
- **prospecting** supplies the list and the sourced account facts (Skills Registry: feeds cold-email). With no list, ask for one or run prospecting. Never scrape or invent contacts.
- **emails** vs **cold-email:** if the recipient already knows the client (past customers, an opted-in list, existing referral partners), use `emails`. Strangers come here.
- **referrals:** referral or partner program design (incentives, payouts). The clinical and real-estate compliance flags above still apply.
- **revops:** stage models and pipeline language fit B2B clients with a sales team. For local service, track replies, intro calls and first referrals.
- **marketing-loops:** any recurring outbound loop becomes a scheduled task that stops for approval (see "BML: nothing sends from an agent").

<!-- BML:END related -->
