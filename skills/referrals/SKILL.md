---
name: referrals
description: "When the user wants to create, optimize, or analyze a referral program, affiliate program, or word-of-mouth strategy. Also use when the user mentions 'referral,' 'affiliate,' 'ambassador,' 'word of mouth,' 'viral loop,' 'refer a friend,' 'partner program,' 'referral incentive,' 'how to get referrals,' 'customers referring customers,' 'affiliate payout,' 'get more reviews,' 'G2 reviews,' 'review campaign,' 'respond to a bad review,' 'referral partners,' 'referring physicians,' 'review requests,' or 'get more Google reviews.' Use this whenever someone wants existing users or partners to bring in new customers. For launch-specific virality, see launch."
metadata:
  version: 2.2.1-bml.1
---

# Referral & Affiliate Programs

You are an expert in viral growth and referral marketing. Your goal is to help design and optimize programs that turn customers into growth engines.

<!-- BML:START modes -->
## BML mode: choose the workflow first

| Situation | Workflow |
|---|---|
| BML client work (signals in the context block below) | [references/bml-local-referrals.md](references/bml-local-referrals.md): customer referral programs, professional referrer networks, review programs. Use upstream sections only as the table below allows |
| BML client whose page 13 shows a product sold online with self-serve purchase (a B2B/product company) | Upstream workflow, plus every rule in the context block |
| BML's own marketing, or not BML work | Upstream workflow as written |

For BML client work, this overrides these upstream sections:

| Upstream section | For BML clients |
|---|---|
| Before Starting (LTV, CAC, shareable product, network effects) | Answer from rows (B-7, B-9, I-5, B-6, A-15). Ask only for gaps; a missing fact is `[NEEDS PROOF: <row ID>]` |
| Should You Engineer Virality First? | Skip. Local service sits at the limited end; no badges, watermarks or embeds |
| Referral Program Design, Steps 1–3 | Job-moment triggers, offline share paths and the J-3 legality gate in the BML file §1. Clinical default is a non-incentive program |
| Typical Findings, program-examples.md, affiliate-programs.md, affiliate-operations.md figures | Illustrative only. Never cite in client work; with no client row, say "benchmark unknown" |
| Launch Checklist, Email Sequences ("announce", "send reminder emails") | Drafts only. Nothing launches, sends or pays out before the approvals in the BML file §4 (client approver: J-1). Ask messages are drafted by `emails` or `sms` |
| Affiliate Programs, affiliate-operations.md | Only for the product-company case above, and outreach, terms changes and payouts stay drafts for approval. Professional referrers (L-8) get a relationship program (BML file §2), never per-referral pay |
| Review Programs | BML file §3: Google Business Profile and A-16 platforms, no gating, no incentives, no composed reviews, no reviewer names |
| Tool Integrations | Only if the client uses it (A-15, page 00 §8) |

Capacity is context, not a gate: note B-6 and I-10 beside the program and flag them in the footer (BML file §0).
<!-- BML:END modes -->

## Before Starting

**Check for product marketing context first:**
If `.agents/product-marketing.md` exists (or `.claude/product-marketing.md`, or the legacy `product-marketing-context.md` filename, in older setups), read it before asking questions. Use that context and only ask for information not already covered or specific to this task.

<!-- BML:START context -->
**BML client work:** if the request names a BML client (a code like `[ABC]` or a client name), runs in a client's Claude Project, or the staged file starts `Generated for`, `UNGENERATED for` or `INTAKE DRAFT for`, read `bml/context-rules.md` (repo root; `../../bml/context-rules.md` from this skill's folder) before anything else. Never edit `.agents/product-marketing.md` for a client, and never add a learning or changelog line to it (§1, §8).

- **Read order (§1):** router → staged page 13 → current Monthly Context Brief → source rows only for detail behind a cited row. Don't browse Drive or search ClickUp. The questions under "Gather this context" are answered from rows first.
- **Scope gate (§3):** the page 00 line covering the work: marketing strategy or planning (or a referral/partner program line) for program design; Local SEO, Google Business Profile or reputation management for review programs; Email Marketing or SMS for ask messages. A "planning only" qualifier means the design record only. No line → stop and offer a scope note.
- **Rules:** claims and `[NEEDS PROOF]` (§4), guardrails at any status incl. J-3 on rewards (§5), distinctiveness, capacity (B-6) and lead handling (I-3) (§6), segment rules (§7), client edits (§8), footer (§9), write-back of research as `DRAFT` rows (§10).
- **`INTAKE DRAFT`:** internal or pitch material only, marked "from public research". Nothing for launch.
- **Outputs:** the program design record goes to the session's outputs folder; filed on request to the client's Drive `OUTPUTS/WEBSITE` (resolved by ID, never created), with a ClickUp record tagged `strategy` created only after the user approves. Details: [references/bml-local-referrals.md](references/bml-local-referrals.md) §6.
<!-- BML:END context -->

Gather this context (ask if not provided):

### 1. Program Type
- Customer referral program, affiliate program, or both?
- B2B or B2C?
- What's the average customer LTV?
- What's your current CAC from other channels?

### 2. Current State
- Existing referral/affiliate program?
- Current referral rate (% who refer)?
- What incentives have you tried?

### 3. Product Fit
- Is your product shareable?
- Does it have network effects?
- Do customers naturally talk about it?

### 4. Resources
- Tools/platforms you use or consider?
- Budget for referral incentives?

---

## Should You Engineer Virality First?

Before building a reward-driven program, check whether virality can be **built into the product** — often cheaper and more durable than paid referrals. But **don't force virality where it doesn't naturally fit.**

Place the product on the **Viral Potential Spectrum**:
- **Natural** (build for it): collaboration tools, communication tools, user-facing outputs — every use exposes the product to non-users.
- **Limited** (don't force it): backend, competitive-advantage, internal-only, and infrastructure products. Invest in referral programs, content, and partnerships instead.

If the product is on the natural end, consider **product-embedded viral mechanisms** (Powered By badges, exposure loops, social sharing, embeds, watermarks) before or alongside a reward program.

**For the spectrum diagnostic, the 7 viral mechanisms, value-presentation and timing best practices, and affiliate power-law mechanics**: See [references/viral-mechanisms.md](references/viral-mechanisms.md)

---

## Referral vs. Affiliate

### Customer Referral Programs

**Best for:**
- Existing customers recommending to their network
- Products with natural word-of-mouth
- Lower-ticket or self-serve products

**Characteristics:**
- Referrer is an existing customer
- One-time or limited rewards
- Higher trust, lower volume

### Affiliate Programs

For partner recruitment/activation, cohort economics, executable terms, reconciliation, and measured incremental growth, load [the operating playbook](references/affiliate-operations.md). This expands the existing affiliate branch instead of creating an overlapping skill.

**Best for:**
- Reaching audiences you don't have access to
- Content creators, influencers, bloggers
- Higher-ticket products that justify commissions

**Characteristics:**
- Affiliates may not be customers
- Ongoing commission relationship
- Higher volume, variable trust

---

## Referral Program Design

### The Referral Loop

```
Trigger Moment → Share Action → Convert Referred → Reward → (Loop)
```

### Step 1: Identify Trigger Moments

**High-intent moments:**
- Right after first "aha" moment
- After achieving a milestone
- After exceptional support
- After renewing or upgrading

### Step 2: Design Share Mechanism

**Ranked by effectiveness:**
1. In-product sharing (highest conversion)
2. Personalized link
3. Email invitation
4. Social sharing
5. Referral code (works offline)

### Step 3: Choose Incentive Structure

**Single-sided rewards** (referrer only): Simpler, works for high-value products

**Double-sided rewards** (both parties): Higher conversion, win-win framing

**Tiered rewards**: Gamifies referral process, increases engagement

**Present the reward with the bigger-*feeling* number** — "lead with the larger number" (say "$10 off," not "40% off," on a low-priced product). Reward at the **aha moment or milestone**, not signup. Reduce friction: one-click share, pre-written messages.

**For examples and incentive sizing**: See [references/program-examples.md](references/program-examples.md)

**For product-embedded virality, value-presentation rules, and affiliate power-law mechanics**: See [references/viral-mechanisms.md](references/viral-mechanisms.md)

---

## Program Optimization

### Improving Referral Rate

**If few customers are referring:**
- Ask at better moments
- Simplify sharing process
- Test different incentive types
- Make referral prominent in product

**If referrals aren't converting:**
- Improve landing experience for referred users
- Strengthen incentive for new users
- Ensure referrer's endorsement is visible

### A/B Tests to Run

**Incentive tests:** Amount, type, single vs. double-sided, timing

**Messaging tests:** Program description, CTA copy, landing page copy

**Placement tests:** Where and when the referral prompt appears

### Common Problems & Fixes

| Problem | Fix |
|---------|-----|
| Low awareness | Add prominent in-app prompts |
| Low share rate | Simplify to one click |
| Low conversion | Optimize referred user experience |
| Fraud/abuse | Add verification, limits |
| One-time referrers | Add tiered/gamified rewards |

---

## Measuring Success

### Key Metrics

**Program health:**
- Active referrers (referred someone in last 30 days)
- Referral conversion rate
- Rewards earned/paid

**Business impact:**
- % of new customers from referrals
- CAC via referral vs. other channels
- LTV of referred customers
- Referral program ROI

### Typical Findings

- Referred customers have 16-25% higher LTV
- Referred customers have 18-37% lower churn
- Referred customers refer others at 2-3x rate

---

## Launch Checklist

### Before Launch
- [ ] Define program goals and success metrics
- [ ] Design incentive structure
- [ ] Build or configure referral tool
- [ ] Create referral landing page
- [ ] Set up tracking and attribution
- [ ] Define fraud prevention rules
- [ ] Create terms and conditions
- [ ] Test complete referral flow

### Launch
- [ ] Announce to existing customers
- [ ] Add in-app referral prompts
- [ ] Update website with program details
- [ ] Brief support team

### Post-Launch (First 30 Days)
- [ ] Review conversion funnel
- [ ] Identify top referrers
- [ ] Gather feedback
- [ ] Fix friction points
- [ ] Send reminder emails to non-referrers

---

## Email Sequences

### Referral Program Launch

```
Subject: You can now earn [reward] for sharing [Product]

We just launched our referral program!

Share [Product] with friends and earn [reward] for each signup.
They get [their reward] too.

[Unique referral link]

1. Share your link
2. Friend signs up
3. You both get [reward]
```

### Referral Nurture Sequence

- Day 7: Remind about referral program
- Day 30: "Know anyone who'd benefit?"
- Day 60: Success story + referral prompt
- After milestone: "You achieved [X]—know others who'd want this?"

---

## Affiliate Programs

**For detailed affiliate program design, commission structures, recruitment, and tools**: See [references/affiliate-programs.md](references/affiliate-programs.md)

**For affiliate power-law mechanics (buyout clauses ~12× monthly commission, the 20/80 super-promoter rule, launch-affiliate tactics)**: See [references/viral-mechanisms.md](references/viral-mechanisms.md)

---

## Review Programs

Reviews are the other half of customer advocacy. For review-request programs, responding to reviews, reputation triage, and reusing testimonials with permission (G2, Capterra, Trustpilot, Google, app stores), see [references/review-programs.md](references/review-programs.md). Platform rules differ, so check [references/review-platform-rules.md](references/review-platform-rules.md) before proposing incentives or automation.

<!-- BML:START review-programs -->
**BML clients:** read [references/bml-local-referrals.md](references/bml-local-referrals.md) §3 first. It routes to these three upstream files and overrides them for BML clients: no incentives on any platform, no gating or sends on "existing authorization", no composed reviews, no reviewer names in BML artifacts, clinical replies never confirm a patient, and Google Business Profile plus the A-16 platforms come first.
<!-- BML:END review-programs -->

## Task-Specific Questions

1. What type of program (referral, affiliate, or both)?
2. What's your customer LTV and current CAC?
3. Existing program or starting from scratch?
4. What tools/platforms are you considering?
5. What's your budget for rewards/commissions?
6. Is your product naturally shareable?

---

## Tool Integrations

For implementation, see the [tools registry](https://github.com/coreyhaines31/marketingskills/blob/main/tools/REGISTRY.md). Key tools for referral programs:

| Tool | Best For | Guide |
|------|----------|-------|
| **Rewardful** | Stripe-native affiliate programs | [rewardful.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/rewardful.md) |
| **Tolt** | SaaS affiliate programs | [tolt.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/tolt.md) |
| **Mention Me** | Enterprise referral programs | [mention-me.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/mention-me.md) |
| **Dub.co** | Link tracking and attribution | [dub-co.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/dub-co.md) |
| **Stripe** | Payment processing (for commission tracking) | [stripe.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/stripe.md) |
| **Introw** | Channel partner programs with tiers, deal registration, QBRs | [introw.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/introw.md) |
| **PartnerStack** | Enterprise partner and affiliate programs | [partnerstack.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/partnerstack.md) |

<!-- BML:START tools -->
**BML clients:** every tool above is "if the client uses it" (A-15, page 00 §8); don't assume Stripe or a referral platform. Most local programs need only an intake source question, a code, call tracking if the client has it, and a UTM-tagged page. BML never configures these tools, writes to a client's CRM, or pays rewards (BML file §4–5).
<!-- BML:END tools -->

---

## Related Skills

- **launch**: For launching referral program effectively
- **emails**: For referral nurture campaigns
- **marketing-psychology**: For understanding referral motivation
- **analytics**: For tracking referral attribution

<!-- BML:START related -->
- **BML clients:** `emails` and `sms` draft referral and review asks and partner updates (SMS consent lives in `sms`); `cro` or `copywriting` for a referral page; `co-marketing` for builder, realtor or designer partners; `offers` for a welcome offer built from D-7; `analytics` for source tracking.
<!-- BML:END related -->
