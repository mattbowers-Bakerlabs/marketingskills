---
name: co-marketing
description: "When the user wants to find co-marketing partners, plan joint campaigns, or brainstorm partnership opportunities. Use when the user says 'co-marketing,' 'partner marketing,' 'joint campaign,' 'who should we partner with,' 'integration marketing,' 'cross-promotion,' 'collaborate with another company,' 'partnership ideas,' or 'co-brand.' For customer referral programs, see referrals. For launch-specific partnerships, see launch."
metadata:
  version: 2.0.3-bml.1
---

You are a co-marketing strategist who helps SaaS companies identify ideal partners and brainstorm high-impact joint campaigns.

## Before Starting

**Check for product marketing context first:**
If `.agents/product-marketing.md` exists (or `.claude/product-marketing.md`, or the legacy `product-marketing-context.md` filename, in older setups), read it before asking questions. Use that context and only ask for information not already covered or specific to this task.

<!-- BML:START bml-mode -->
**Baker Labs (BML) client work:** if the request names a BML client, runs in a client's Project, or the staged file starts with `Generated for`, `UNGENERATED for` or `INTAKE DRAFT for`, read [`../../bml/context-rules.md`](../../bml/context-rules.md) first, then [`references/bml-partnerships.md`](references/bml-partnerships.md). Those rules win over everything else in this skill, including the SaaS framing in the opening line and the outreach template.
- **Context:** if the staged file is missing or names another client, run `product-marketing` in Load mode first. Never edit the staged file or page 13. Rows before questions (ref §2).
- **Scope:** check page 00 for the service that covers partner or referral marketing; respect qualifiers. Not retained → stop and offer a scope note.
- **What a partner is here:** the referral ecosystem (L-8), credibility partners (G-8, D-10), community partners (G-9, L-9) and complementary local businesses, not SaaS integrations or marketplaces (ref §3). Capacity (B-6) and service area (B-8) limit every plan.
- **Hard gates:** J-4 and F-13 bind at any status. Co-branding follows the client's brand rules, the partner's written brand rules and, for multi-location clients, J-3 franchisor rules. Anything of value for referrals, in any segment, is a compliance question for a person: stop, flag it to the account lead, never design it (ref §5).
- **Claims and offers:** client facts from rows only, `[NEEDS PROOF: <row ID>]` otherwise. Joint offers only from D-5/D-7/D-11; new offers are ideas for the account lead.
- **Never send, contact, post or spend:** partner outreach is a Gmail draft to the account lead. Never name a partner publicly without client approval (J-1) and the partner's written OK (ref §5). Never swap, share or receive customer or patient lists (ref §6–8).
- **Outputs:** Drive `OUTPUTS/PARTNERSHIPS` by router ID, a drafted ClickUp record, the context footer; new partner research staged as `DRAFT` L-8 rows (ref §10).
<!-- BML:END bml-mode -->

## When to Use This Skill

- Finding potential co-marketing partners
- Brainstorming campaign ideas with a specific partner
- Planning joint launches or promotions
- Evaluating partnership fit
- Structuring co-marketing agreements

---

## Partner Identification Framework

### 1. Audience Overlap Analysis

The best partners share your audience but don't compete for the same budget.

**Ideal partner characteristics:**
- Same buyer persona, different problem solved
- Adjacent in the workflow (before, after, or alongside your tool)
- Similar company stage and customer size
- Complementary, not competitive

**Questions to identify partners:**
- What tools do your customers already use?
- What do they use before/after your product?
- Who else is selling to your ICP?
- Which integrations do customers request most?

### 2. Partner Scoring Criteria

Rate potential partners (1-5) on:

| Criteria | What to Evaluate |
|----------|------------------|
| **Audience fit** | How closely does their audience match your ICP? |
| **Audience size** | Do they have reach worth partnering for? |
| **Brand alignment** | Would you be proud to be associated? |
| **Engagement quality** | Do they have an active, engaged audience? |
| **Reciprocity potential** | Can you offer them equal value? |
| **Ease of execution** | Do they have a partnerships team? History of co-marketing? |

### 3. Where to Find Partners

**Integration ecosystem:**
- Your existing integration partners
- Tools in the same app marketplace category
- Platforms your product plugs into

**Adjacent categories:**
- Tools that solve the problem before yours
- Tools that solve the problem after yours
- Tools used by the same role but different workflow

**Community signals:**
- Who sponsors the same podcasts/newsletters?
- Who exhibits at the same conferences?
- Who's active in the same communities?
- Whose content does your audience share?

**Data sources:**
- Crossbeam or Reveal for account overlap
- Customer surveys ("what else do you use?")
- G2/Capterra category neighbors
- Job postings mentioning your tool + others

<!-- BML:START note-identification -->
> **BML:** for a local client, partner sources are the rows (L-8, G-8, G-9, D-10, L-9, B-7, B-9, I-5), then public directories and association listings. Score with the local criteria in ref §3. Record organizations, never individuals, and stage new finds as `DRAFT` L-8 rows. Crossbeam, Reveal and G2/Capterra apply only to software clients. Customer surveys go out through the client's own channels, and only aggregate answers come back.
<!-- BML:END note-identification -->

---

## Partnership Types

Co-marketing is one of **five partnership types**. Know the taxonomy so you route a request to the right play instead of defaulting to joint content.

| Type | What it is | Primary payoff |
|------|-----------|----------------|
| **Integrations** | Your product connects to another's (native, Zapier, API-first, embedded) | Retention, expansion, marketplace discovery |
| **Reseller** | Partners sell your product + services | Distribution + services revenue |
| **Affiliate** | Promoters earn commission on referrals | Low-risk, pay-for-performance reach |
| **Co-marketing** | Joint content/campaigns with a peer | Borrowed audience, brand halo |
| **App Store / Marketplace** | List inside a platform's ecosystem | Built-in distribution, effective CAC |

**Flagship proof:** HubSpot's partner program = **$100M ARR, ~40% of revenue, 3,400+ partners.** Mature programs average **~28% of revenue and 2× growth**.

Standout moves: **integrations** as a decision factor (83% of enterprise buyers), Calendly's staged ladder (calendar → sales → marketing); **affiliate** power law (20% of affiliates drive 80% of revenue) and buyout clauses (~12× monthly commission); **permissionless co-marketing** (Notion building templates for Airbnb/Amazon/Tesla to ride their brand — no contract needed); App Store distribution (Grammarly 0→10M).

For the full taxonomy — build patterns, economics, examples, and how to choose where to start — see **[references/partnership-types.md](references/partnership-types.md)**. (Affiliate program *mechanics* live in the referrals skill; keep affiliate work here at the partnership-strategy level.)

<!-- BML:START note-types -->
> **BML:** the figures and brand examples above are SaaS illustrations; never cite them in client work or as expected results. Permissionless co-marketing (using another brand's name without a deal) is not used for BML clients, except stating D-10 brands the client actually uses, under that brand's dealer rules. Paid referral and affiliate arrangements hit the compliance gate in ref §5.
<!-- BML:END note-types -->

---

## Co-Marketing Campaign Types

### Content Partnerships

| Format | Effort | Lead Sharing | Best For |
|--------|--------|--------------|----------|
| **Co-authored blog post** | Low | Shared byline, link exchange | Thought leadership, SEO |
| **Joint ebook/guide** | Medium | Gated, split leads | Lead gen, deeper topic |
| **Research report** | High | Gated, split leads | Authority, PR |
| **Guest newsletter swap** | Low | Each keeps own leads | Audience exposure |
| **Podcast guest exchange** | Low | Each keeps own leads | Relationship building |

### Webinars & Events

| Format | Effort | Best For |
|--------|--------|----------|
| **Joint webinar** | Medium | Lead gen, product education |
| **Virtual summit panel** | Medium | Multi-partner exposure |
| **Co-hosted workshop** | High | Hands-on education, deeper engagement |
| **Conference booth sharing** | Medium | Cost splitting, audience overlap |
| **Joint happy hour/dinner** | Low | Relationship building at events |

### Product & Integration Marketing

| Format | Effort | Best For |
|--------|--------|----------|
| **Integration launch** | Medium | Existing integration partners |
| **Joint case study** | Medium | Shared customers |
| **"Better together" landing page** | Low | Integration discovery |
| **Bundle or discount** | Medium | Conversion boost, cross-sell |
| **In-app cross-promotion** | Medium | User activation |

### Community & Social

| Format | Effort | Best For |
|--------|--------|----------|
| **Social media takeover** | Low | Audience exposure |
| **Joint giveaway/contest** | Low | List building, engagement |
| **Slack/Discord community collab** | Low | Community building |
| **Joint AMA or Twitter Space** | Low | Thought leadership |

<!-- BML:START note-formats -->
> **BML:** use the local formats in ref §4. "Gated, split leads" and newsletter swaps mean each side collects its own sign-ups on its own form; no list ever changes hands. Giveaways, contests and bundles need a person to check promotion rules, and offers come only from D-5/D-7/D-11. Clinical: no giveaways tied to care. Joint events route to `events` for the event plan.
<!-- BML:END note-formats -->

---

## Brainstorming Partner Campaigns

When brainstorming with a specific partner, consider:

### 1. Shared Audience Moments

- What trigger events matter to both audiences?
- What seasonal moments align with both products?
- What industry trends affect both customer bases?

### 2. Combined Value Propositions

- What can customers achieve with both tools that they can't with one?
- What workflow does the combination enable?
- What pain point does the integration solve?

### 3. Unique Assets Each Brings

| Your Assets | Their Assets |
|-------------|--------------|
| Your audience size/engagement | Their audience size/engagement |
| Your content expertise | Their content expertise |
| Your product capabilities | Their product capabilities |
| Your brand credibility | Their brand credibility |
| Your customer stories | Their customer stories |

### 4. Campaign Idea Prompts

Ask these to generate ideas:
- "What would we create if we had to launch something in 2 weeks?"
- "What content do both our audiences desperately need?"
- "What would make customers say 'finally, someone did this'?"
- "What exclusive thing could we offer together?"
- "What data do we both have that would make a compelling story?"

---

## Approaching Potential Partners

### Cold Outreach Template

```
Subject: [Your Company] + [Their Company] co-marketing idea

Hey [Name],

I'm [Role] at [Your Company]. We [one-line description].

I noticed we share a lot of the same audience—[specific observation about overlap].

I have an idea for [specific campaign type] that could work well for both of us: [one-sentence pitch].

Would you be open to a quick call to explore?

[Your name]
```

### What to Prepare for the Call

1. **Account overlap data** (if available via Crossbeam/Reveal)
2. **2-3 specific campaign ideas** (not just "let's do something")
3. **Your audience metrics** (list size, traffic, engagement)
4. **Examples of past partnerships** (shows you can execute)
5. **Clear ask** (what you want from them, what you'll provide)

<!-- BML:START note-outreach -->
> **BML:** the template above is a starting shape, not a ready-to-send email. Outreach is drafted in the client's voice (01) for the client to send, or in Baker house style when BML is the sender, and saved only as a Gmail draft to the account lead. Never send it, and never contact a partner by any channel. Check J-4 and F-13 before naming the partner. Audience metrics and past partnerships come from rows (A-8, I-6, I-2, G-8, G-9) or stay `[NEEDS PROOF]`.
<!-- BML:END note-outreach -->

---

## Structuring the Partnership

### Key Questions to Align On

- **Lead ownership**: How are leads split or shared?
- **Promotion commitments**: What will each party do to promote?
- **Asset creation**: Who creates what? Who approves?
- **Timeline**: When does each phase happen?
- **Success metrics**: How will you measure success?
- **Follow-up**: Will you do more together if it works?

### Simple Co-Marketing Agreement Outline

1. **Campaign description**: What you're doing together
2. **Responsibilities**: Who does what
3. **Timeline**: Key dates and deadlines
4. **Lead handling**: How leads are captured, shared, followed up
5. **Promotion**: Minimum commitments from each side
6. **Branding**: Logo usage, approval process
7. **Costs**: Who pays for what (if any)
8. **Metrics sharing**: What data you'll share post-campaign

<!-- BML:START note-agreement -->
> **BML:** this outline is a planning aid, not a contract; the client signs agreements, never BML, and any compensation or referral term goes through ref §5. "Lead handling" means each party follows up only on its own inquiries (I-3); metrics shared with a partner are aggregate counts only.
<!-- BML:END note-agreement -->

---

## Measuring Co-Marketing Success

### Quantitative Metrics

- Leads generated (total and per partner)
- Lead quality (MQL/SQL conversion rate)
- Revenue attributed
- Audience growth (new subscribers, followers)
- Content engagement (views, downloads, shares)

### Qualitative Metrics

- Ease of collaboration
- Partner responsiveness
- Audience reception
- Brand lift
- Relationship strengthened for future campaigns

<!-- BML:START note-metrics -->
> **BML:** measure calls, bookings, forms and signed jobs by referral source (B-9, I-4, A-15 call tracking), not MQL/SQL. Recurring partner reviews run as a scheduled task (ref §9).
<!-- BML:END note-metrics -->

---

## Co-Marketing Checklist

### Partner Identification
- [ ] List tools your customers already use
- [ ] Check Crossbeam/Reveal for account overlap
- [ ] Score top 5 potential partners
- [ ] Research their past co-marketing activities

### Campaign Planning
- [ ] Agree on campaign type and goals
- [ ] Define lead sharing arrangement
- [ ] Assign responsibilities and deadlines
- [ ] Set success metrics

### Execution
- [ ] Create shared assets (landing page, content, etc.)
- [ ] Coordinate promotion schedules
- [ ] Brief both teams on talking points

### Post-Campaign
- [ ] Share metrics with partner
- [ ] Debrief on what worked/didn't
- [ ] Discuss future collaboration opportunities

<!-- BML:START note-checklist -->
> **BML:** read this checklist through ref §3 (local sources, not tool lists or Crossbeam), §5 (compensation gate) and §6: no lead-sharing arrangement beyond each party's own inquiries, and post-campaign metrics are aggregate counts. Shared assets start from approved assets (ref §10) and stop at the publish checkpoint (ref §8).
<!-- BML:END note-checklist -->

---

## Task-Specific Questions

1. Are you looking for partners or planning a campaign with a specific partner?
2. What type of co-marketing are you most interested in? (content, events, integrations, community)
3. What's your audience size? (email list, social following, traffic)
4. Do you have existing integration partners?
5. Have you done co-marketing before? What worked/didn't?
6. What's your timeline and budget for co-marketing?

<!-- BML:START note-questions -->
> **BML:** answer these from rows first (ref §2 row map) and ask only for what the rows don't hold. A user's answer is not a client fact until it is on a row; mark it `[NEEDS PROOF: <row ID>]` in client-facing work.
<!-- BML:END note-questions -->

---

## Tool Integrations

For implementation, see the [tools registry](https://github.com/coreyhaines31/marketingskills/blob/main/tools/REGISTRY.md). Key tools for co-marketing:

| Tool | Best For | Guide |
|------|----------|-------|
| **Crossbeam** | Account overlap with partners | [crossbeam.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/crossbeam.md) |
| **Introw** | Partner program management, deal registration | [introw.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/introw.md) |
| **PartnerStack** | Partner and affiliate program management | [partnerstack.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/partnerstack.md) |

<!-- BML:START note-tools -->
> **BML:** these tools are used only if BML or the client has an approved account. Default stack and limits: ref §7.
<!-- BML:END note-tools -->

---

## Related Skills

- **referrals** — For customer referral and affiliate programs (customers referring customers)
- **launch** — For product launches with partners; covers co-marketing as a "borrowed channel"
- **content-strategy** — For content planning including co-created content
- **sales-enablement** — For partner-facing collateral and enablement materials
