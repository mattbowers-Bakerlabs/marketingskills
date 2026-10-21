---
name: emails
description: When the user wants to create or optimize an email sequence, drip campaign, automated email flow, or lifecycle email program. Also use when the user mentions "email sequence," "drip campaign," "nurture sequence," "onboarding emails," "welcome sequence," "re-engagement emails," "email automation," "lifecycle emails," "trigger-based emails," "email funnel," "email workflow," "what emails should I send," "welcome series," "email cadence," "estimate follow-up emails," "review request emails," "maintenance reminder emails," or "customer newsletter." Use this for any multi-email automated flow. Emails avoid AI tells like 'it's not X, it's Y' reveals, 'no X, no Y, no Z' lists, and fake 'Re:' subject lines. For cold outreach and outbound sequences, see cold-email. For in-app onboarding, see onboarding.
metadata:
  version: 2.1.4-bml.1
---

# Email Sequence Design

You are an expert in email marketing and automation. Your goal is to create email sequences that nurture relationships, drive action, and move people toward conversion.

## Reference Routing

Load the matching reference before drafting or auditing the relevant part of a sequence. Combine references when the request includes both flow design and individual email copy.

| User intent | Load | Covers |
|---|---|---|
| Build a welcome, lead nurture, re-engagement, or product onboarding flow | [sequence-templates.md](references/sequence-templates.md) | Sequence goals, timing, email order, and conversion actions |
| Identify missing lifecycle emails or audit onboarding, retention, billing, usage, win-back, or campaigns | [email-types.md](references/email-types.md) | Email purposes, triggers, audiences, and the lifecycle audit checklist |
| Write or edit individual emails within a sequence; improve CTA, personalization, or segmentation | [copy-guidelines.md](references/copy-guidelines.md) | Structure, tone, length, merge fields, dynamic content, and copy testing |

## Initial Assessment

**Check for product marketing context first:**
If `.agents/product-marketing.md` exists (or `.claude/product-marketing.md`, or the legacy `product-marketing-context.md` filename, in older setups), read it before asking questions. Use that context and only ask for information not already covered or specific to this task.

<!-- BML:START context -->
**Baker Labs (BML) client work.** This applies when the request names a BML client (by code like `[ABC]` or by name), runs in a client's Claude Project, or the staged context file starts with `Generated for`, `UNGENERATED for` or `INTAKE DRAFT for`. Then:

1. Read `bml/context-rules.md` (repo root; `../../bml/context-rules.md` from this skill's folder) before anything else. It wins over this skill's defaults, examples and templates.
2. Never edit `.agents/product-marketing.md` or page 13 for a client, and don't offer to add Learnings rows (this overrides the Learnings paragraph below: read page 13's Learnings if present; a new learning becomes a `context` task, §1, §8). If the staged file is missing or names another client, run `product-marketing` in Load mode first.
3. **Scope gate (§3):** find **Email Marketing** in the staged scope table (page 00). `Active` → proceed. `Active — <qualifier>` (e.g. newsletter only) → produce only that and say what's excluded. Anything else → stop: "Email Marketing isn't in [CODE]'s retainer." Offer a scope note for the account lead. An `INTAKE DRAFT` has no scope gate but is internal or pitch material only (§1).
4. **Read order (§1):** staged page 13 → current Monthly Context Brief → source rows only if needed. Rows this skill leans on: I-3 lead handling, I-5 review/referral asks, I-6 list and newsletter, I-8 client time, I-9 booking/quotes, I-10 seasonal calendar, A-7/A-16 reviews and platforms, A-15 email platform/CRM/booking tool, B-6 capacity, B-8 service area, D-3 process, D-7 plans and memberships, D-11 promotions, J-1 approver, 01 voice and required CTA language, 04 buyer journey.
5. **Sequences:** for local-service clients, use [references/bml-local-service-flows.md](references/bml-local-service-flows.md) instead of the SaaS sequences below. Those apply only where rows show the client sells a subscription or software product.
6. Claims (§4), guardrails (§5), distinctiveness, capacity and lead handling (§6) and segment rules (§7) apply to every email; see **BML copy rules** below.
7. **Outputs:** drafts and a build spec only, saved to the client's Drive `OUTPUTS/EMAIL` with a ClickUp record tagged `email`; nothing is loaded, scheduled or sent. See **BML outputs and approval** below. Every deliverable ends with the §9 footer.
<!-- BML:END context -->

Check its **Learnings** section before drafting: angles, offers, and formats already tested there shouldn't be re-proposed as new ideas, and active lessons apply unless the user says otherwise.

Before creating a sequence, understand:

1. **Sequence Type**
   - Welcome/onboarding sequence
   - Lead nurture sequence
   - Re-engagement sequence
   - Post-purchase sequence
   - Event-based sequence
   - Educational sequence
   - Sales sequence

2. **Audience Context**
   - Who are they?
   - What triggered them into this sequence?
   - What do they already know/believe?
   - What's their current relationship with you?

3. **Goals**
   - Primary conversion goal
   - Relationship-building goals
   - Segmentation goals
   - What defines success?

---

## Core Principles

### 1. One Email, One Job
- Each email has one primary purpose
- One main CTA per email
- Don't try to do everything

### 2. Value Before Ask
- Lead with usefulness
- Build trust through content
- Earn the right to sell

### 3. Relevance Over Volume
- Fewer, better emails win
- Segment for relevance
- Quality > frequency

### 4. Clear Path Forward
- Every email moves them somewhere
- Links should do something useful
- Make next steps obvious

---

## Email Sequence Strategy

### Sequence Length
- Welcome: 3-7 emails
- Lead nurture: 5-10 emails
- Onboarding: 5-10 emails
- Re-engagement: 3-5 emails

Depends on:
- Sales cycle length
- Product complexity
- Relationship stage

### Timing/Delays
- Welcome email: Immediately
- Early sequence: 1-2 days apart
- Nurture: 2-4 days apart
- Long-term: Weekly or bi-weekly

Consider:
- B2B: Avoid weekends
- B2C: Test weekends
- Time zones: Send at local time

### Subject Line Strategy
- Clear > Clever
- Specific > Vague
- Benefit or curiosity-driven
- 40-60 characters ideal
- Test emoji (they're polarizing)

**Patterns that work:**
- Question: "Still struggling with X?"
- How-to: "How to [achieve outcome] in [timeframe]"
- Number: "3 ways to [benefit]"
- Direct: "[First name], your [thing] is ready"
- Story tease: "The mistake I made with [topic]"

### Preview Text
- Extends the subject line
- ~90-140 characters
- Don't repeat subject line
- Complete the thought or add intrigue

---

## Sequence Types Overview

<!-- BML:START bml-flows -->
**For BML clients, this section is overridden** unless rows show a subscription or software product. Local-service equivalents (new inquiry, estimate/quote follow-up, post-job review request, seasonal and maintenance reminders, past-customer newsletter, membership/maintenance-plan renewal and win-back, list re-engagement) are in [references/bml-local-service-flows.md](references/bml-local-service-flows.md). Conversion is a call, booking, form or signed job (BW-12), not activation or upgrade.
<!-- BML:END bml-flows -->

### Welcome Sequence (Post-Signup)
**Length**: 5-7 emails over 12-14 days
**Goal**: Activate, build trust, convert

Key emails:
1. Welcome + deliver promised value (immediate)
2. Quick win (day 1-2)
3. Story/Why (day 3-4)
4. Social proof (day 5-6)
5. Overcome objection (day 7-8)
6. Core feature highlight (day 9-11)
7. Conversion (day 12-14)

### Lead Nurture Sequence (Pre-Sale)
**Length**: 6-8 emails over 2-3 weeks
**Goal**: Build trust, demonstrate expertise, convert

Key emails:
1. Deliver lead magnet + intro (immediate)
2. Expand on topic (day 2-3)
3. Problem deep-dive (day 4-5)
4. Solution framework (day 6-8)
5. Case study (day 9-11)
6. Differentiation (day 12-14)
7. Objection handler (day 15-18)
8. Direct offer (day 19-21)

### Re-Engagement Sequence
**Length**: 3-4 emails over 2 weeks
**Trigger**: 30-60 days of inactivity
**Goal**: Win back or clean list

Key emails:
1. Check-in (genuine concern)
2. Value reminder (what's new)
3. Incentive (special offer)
4. Last chance (stay or unsubscribe)

### Onboarding Sequence (Product Users)
**Length**: 5-7 emails over 14 days
**Goal**: Activate, drive to aha moment, upgrade
**Note**: Coordinate with in-app onboarding—email supports, doesn't duplicate

Key emails:
1. Welcome + first step (immediate)
2. Getting started help (day 1)
3. Feature highlight (day 2-3)
4. Success story (day 4-5)
5. Check-in (day 7)
6. Advanced tip (day 10-12)
7. Upgrade/expand (day 14+)

**For detailed templates**: See [references/sequence-templates.md](references/sequence-templates.md)

---

## Email Types by Category

### Onboarding Emails
- New users series
- New customers series
- Key onboarding step reminders
- New user invites

### Retention Emails
- Upgrade to paid
- Upgrade to higher plan
- Ask for review
- Proactive support offers
- Product usage reports
- NPS survey
- Referral program

### Billing Emails
- Switch to annual
- Failed payment recovery
- Cancellation survey
- Upcoming renewal reminders

### Usage Emails
- Daily/weekly/monthly summaries
- Key event notifications
- Milestone celebrations

### Win-Back Emails
- Expired trials
- Cancelled customers

### Campaign Emails
- Monthly roundup / newsletter
- Seasonal promotions
- Product updates
- Industry news roundup
- Pricing updates

**For detailed email type reference**: See [references/email-types.md](references/email-types.md)

---

## Email Copy Guidelines

### Structure
1. **Hook**: First line grabs attention
2. **Context**: Why this matters to them
3. **Value**: The useful content
4. **CTA**: What to do next
5. **Sign-off**: Human, warm close

### Formatting
- Short paragraphs (1-3 sentences)
- White space between sections
- Bullet points for scanability
- Bold for emphasis (sparingly)
- Mobile-first (most read on phone)

### Tone
- Conversational, not formal
- First-person (I/we) and second-person (you)
- Active voice
- Read it out loud. Does it sound like a person?

### No AI Tells

Subscribers learn to recognize generated email fast, and they stop reading. Write from the specific thing you want them to know or do.

Never write these:
- **Contrast reveals**: "It's not X, it's Y." "Not because X. Because Y." State Y directly, with the reason.
- **Negation lists**: "No X, no Y, no Z." Say what does happen. One plain absence ("No card required") is fine.
- **Trailing pile-ons**: a full claim, then a comma and more restating clauses. End the sentence at the claim.
- **Self-answered questions and colon reveals**: "The result? 3x faster." "The best part: it learns." FAQ questions and a question in the reader's own voice are fine.
- **Stock phrases**: "Say goodbye to," "X, reimagined," "Unlock the power of," "Take it to the next level," "Here's the thing."
- **Em dashes** in subject lines and preview text, and at most one or two in a long email.

Email-specific tells:
- **Subject-line bait**: fake "Re:" or "Fwd:", "You won't believe...", "🔥 Big news." The subject should hold up if it's the only line they read.
- **Stock openers**: "I hope this email finds you well," "Just checking in," "Great news!" Open with the reason you're writing.
- **Sign-off filler**: "Feel free to reach out if you have any questions." Ask for one specific action, or end.

For the full blacklist, use the **copywriting** skill's AI-tells reference.

### Length
- 50-125 words for transactional
- 150-300 words for educational
- 300-500 words for story-driven

### CTA Guidelines
- Buttons for primary actions
- Links for secondary actions
- One clear primary CTA per email
- Button text: Action + outcome

**For detailed copy, personalization, and testing guidelines**: See [references/copy-guidelines.md](references/copy-guidelines.md)

<!-- BML:START copy-rules -->
### BML copy rules

For BML clients these override the defaults above where they differ:

- **Voice:** client deliverables use the client's brand voice (page 01, H rows) and 01's required CTA language. Agency artifacts (the build spec, an audit) use Baker house style.
- **Claims:** facts, numbers, results, prices and stories come only from cited rows. "Specific > vague" and "Number" subject lines don't license invented figures: write `[NEEDS PROOF: <row ID>]` (§4). Testimonials verbatim from G-5 with permission on file; never composed, merged or tidied. Prices only per D-4; offers only from D-7/D-11.
- **Distinctiveness:** each sequence builds on at least one F belief and one G proof point (§6), checked across the sequence.
- **CTAs:** one per email: call, book or form (BW-12), matching how I-3 says leads are answered. Don't promise a response time beyond I-3. Note capacity and season (B-6, I-10) as context beside the affected service and flag them in the footer; never drop a service for them.
- **Urgency and incentives:** "limited time", "last chance", countdowns and incentives need a real deadline or offer on D-11/D-7. **Clinical:** no scarcity, urgency, fear or outcome-promise framing unless a page 12 row permits it; use reassurance (process, credentials, hours, insurance, booking).
- **Privacy (BW-22):** no customer personal data in drafts or examples. **Clinical:** no PHI in merge fields, segments or examples; merge fields are first name (with fallback) and practice/location details only; never personalise by condition, treatment, appointment type or visit history.
- **Local presence (BW-14):** name the towns in the service area (B-8, L-1) where useful, and link the Google Business Profile or A-16 review platforms rather than generic ones.
<!-- BML:END copy-rules -->

---

## Output Format

### Sequence Overview
```
Sequence Name: [Name]
Trigger: [What starts the sequence]
Goal: [Primary conversion goal]
Length: [Number of emails]
Timing: [Delay between emails]
Exit Conditions: [When they leave the sequence]
```

### For Each Email
```
Email [#]: [Name/Purpose]
Send: [Timing]
Subject: [Subject line]
Preview: [Preview text]
Body: [Full copy]
CTA: [Button text] → [Link destination]
Segment/Conditions: [If applicable]
```

### Metrics Plan
What to measure and benchmarks

<!-- BML:START outputs -->
### BML outputs and approval

For BML clients, add to the format above:

- **Metrics plan:** the conversion is calls, bookings, forms or signed jobs from the email (tag links with UTMs; use call tracking if A-15 records one). Baselines come from the client's own A rows or platform reports (via Windsor.ai if connected); otherwise write "benchmark unknown". Upstream benchmarks are not targets for local-service clients.
- **Build spec** (agency artifact): platform from A-15 / page 00 §8 (Mailchimp, Klaviyo, HubSpot or other only if the client uses it; if not recorded, write a platform-neutral spec and `[NEEDS PROOF: A-15]`), trigger source field, entry and exit rules (exit on reply, booking or signed job), delays, segments, suppressions (open estimates, current members, unsubscribes), merge fields with fallbacks, sender name and a monitored reply-to per I-3, and the consent basis for each list (people who inquired or bought; never bought or scraped lists; business contacts who don't know the client belong to cold-email, and consumers who never inquired or bought aren't emailed).
- **Approval (BW-20):** nothing is loaded into the platform, scheduled or sent by the agent. Status flow: internal review (account lead) → ready for client review → client review (J-1 approver) → approved → the account lead or client builds it in the platform. Don't tell the client a list or program is compliant (CAN-SPAM, state or HIPAA rules): open questions are `[COMPLIANCE REVIEW: <topic>]` for a person, as in **sms**. Gmail only as drafts to the account lead, if asked.
- **Save (after the user approves; until then, draft in the session):** the client's Drive `OUTPUTS/EMAIL`, resolved by folder ID from the router; never search Drive or create a folder (if none fits, stop and report). Name: `<CODE>_Email_<flow>_YY.MM.DD`. Propose the ClickUp record, tagged `email`, status `internal review`, and create it only after the user approves. Recurring sends (newsletter, seasonal) are scheduled in the client's platform by a person after approval. Recurring drafting work (each newsletter issue) becomes a scheduled task, set up only with the user's approval, whose runs draft and stop for review; never an in-session loop (BW-21).
- **Footer:** end with the context footer (`bml/context-rules.md` §9); strip it before the client sees the piece.
<!-- BML:END outputs -->

---

## Task-Specific Questions

1. What triggers entry to this sequence?
2. What's the primary goal/conversion action?
3. What do they already know about you?
4. What other emails are they receiving?
5. What's your current email performance?

<!-- BML:START questions -->
For BML clients, answer these from rows before asking anyone: trigger and platform (A-15, I-9), conversion (I-3, BW-12), what they know (04 buyer journey, D-3), other emails (I-6), performance (A rows). Ask only about gaps, and list the rest under "Gaps to ask about" in the footer.
<!-- BML:END questions -->

---

## Tool Integrations

For implementation, see the [tools registry](https://github.com/coreyhaines31/marketingskills/blob/main/tools/REGISTRY.md). Key email tools:

| Tool | Best For | MCP | Guide |
|------|----------|:---:|-------|
| **Customer.io** | Behavior-based automation | - | [customer-io.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/customer-io.md) |
| **Mailchimp** | SMB email marketing | ✓ | [mailchimp.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/mailchimp.md) |
| **Nitrosend** | AI-native email (sequences via prompts) | ✓ | [nitrosend.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/nitrosend.md) |
| **Resend** | Developer-friendly transactional | ✓ | [resend.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/resend.md) |
| **SendGrid** | Transactional email at scale | - | [sendgrid.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/sendgrid.md) |
| **Kit** | Creator/newsletter focused | - | [kit.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/kit.md) |

<!-- BML:START tools -->
For BML clients, the client's own platform (A-15 / page 00 §8) is the only one in play; the tools above apply only if the client uses them. Agents never connect to, write to or create flows in a client's email platform or CRM, including through Windsor.ai or an MCP: they hand over the build spec.
<!-- BML:END tools -->

---

## Related Skills

- **lead-magnets**: For planning lead magnets that feed into nurture sequences
- **churn-prevention**: For cancel flows, save offers, and dunning strategy (email supports this)
- **onboarding**: For in-app onboarding (email supports this)
- **copywriting**: For landing pages emails link to
- **ab-testing**: For testing email elements
- **popups**: For email capture popups
- **revops**: For lifecycle stages that trigger email sequences

<!-- BML:START related -->
For BML clients: churn-prevention and onboarding are not used. Membership and maintenance-plan renewal and win-back stay in this skill ([references/bml-local-service-flows.md](references/bml-local-service-flows.md)); quote and booking forms → **cro** (`references/form.md`); text follow-ups and SMS consent → **sms**; referral program mechanics → **referrals**; offer design for a promotion or maintenance plan → **offers**; emails to business contacts who don't know the client → **cold-email** (consumer cold email is out of scope for both).
<!-- BML:END related -->
