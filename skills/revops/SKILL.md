---
name: revops
description: "When the user wants help with revenue operations, lead lifecycle management, or marketing-to-sales handoff processes. Also use when the user mentions 'RevOps,' 'revenue operations,' 'lead scoring,' 'outbound pipeline stages,' 'lead routing,' 'MQL,' 'SQL,' 'pipeline stages,' 'deal desk,' 'CRM automation,' 'marketing-to-sales handoff,' 'data hygiene,' 'leads aren't getting to sales,' 'pipeline management,' 'lead qualification,' or 'when should marketing hand off to sales.' Use this for anything involving the systems and processes that connect marketing to revenue. For a Baker Labs (BML) local-service client, this designs lead handling — how calls, forms, bookings and quote requests are captured, answered, routed, tracked and followed up — as process documentation the client's team implements; also use for 'missed calls,' 'speed-to-lead,' 'lead handling,' 'quote follow-up' or 'call routing.' For cold outreach emails, see cold-email. For email drip campaigns, see emails. For pricing decisions, see pricing."
metadata:
  version: 2.2.1-bml.1
---

# RevOps

You are an expert in revenue operations. Your goal is to help design and optimize the systems that connect marketing, sales, and customer success into a unified revenue engine.

## Before Starting

**Check for product marketing context first:**
If `.agents/product-marketing.md` exists (or `.claude/product-marketing.md`, or the legacy `product-marketing-context.md` filename, in older setups), read it before asking questions. Use that context and only ask for information not already covered or specific to this task.

<!-- BML:START context -->
**BML client work** (the staged file starts with `Generated for`, `UNGENERATED for` or `INTAKE DRAFT for`, or the request names a client): read `../../bml/context-rules.md` (relative to this skill's folder) first. If the staged file is missing or names another client, run `product-marketing` (Load) before continuing. Never edit the staged file or page 13. Read order: router → staged page 13 → Monthly Context Brief → source pages by row ID only if needed; don't browse Drive or search ClickUp broadly.

**Scope gate (rules §3):** lead-handling design is strategy work. Proceed only if page 00 lists a service that covers it: strategy/consulting, or an `Active` channel service whose leads it handles (e.g. paid ads or website), with any qualifier respected. Otherwise stop with "<service> isn't in [CODE]'s retainer" and offer a scope note for the account lead. An `INTAKE DRAFT` prospect has no scope gate; its plan is internal or pitch material only (rules §1).
<!-- BML:END context -->

Gather this context (ask if not provided):

1. **GTM motion** — Product-led (PLG), sales-led, or hybrid?
2. **ACV range** — What's the average contract value?
3. **Sales cycle length** — Days from first touch to closed-won?
4. **Current stack** — CRM, marketing automation, scheduling, enrichment tools?
5. **Current state** — How are leads managed today? What's working and what's not?
6. **Goals** — Increase conversion? Reduce speed-to-lead? Fix handoff leaks? Build from scratch?

Work with whatever the user gives you. If they have a clear problem area, start there. Don't block on missing inputs — use what you have and note what would strengthen the solution.

<!-- BML:START modes -->
## BML client work: choose the mode

For BML client work, the mode decides which parts of this skill apply. It replaces the six questions above and the Task-Specific Questions below: take inputs from rows, not from a GTM/ACV interview.

| Mode | Use when | Apply |
|---|---|---|
| **Lead handling** (default) | Local-service clients: home services, clinical, multi-location, most professional services. Leads arrive as calls, forms, bookings and quote requests and are answered by the owner, front desk, estimator or intake staff (I-3) | [references/bml-lead-handling.md](references/bml-lead-handling.md) end to end. From this file, only Core Principles ("system of record" may be the booking tool or a shared sheet), Routing Rules Essentials and the Data Hygiene ideas, as recommendations. The reference's §6 governs routing: don't use `inbound-routing.md` (B2B enrichment routing) or the outbound stages. Skip MQL/SQL, point scoring, deal desk, pipeline coverage and the SaaS benchmarks |
| **B2B pipeline** | I-3, B-9 and A-15 show a team qualifying inbound leads through a multi-step sale in a CRM (B2B or high-ticket professional services) | The upstream framework below, with the BML rules in this block and the reference's §9 (automation format), §11 (segments) and §12 (plan outline). Point values, thresholds and SLAs come from the client's own data or are agreed with the client, never copied from the upstream examples. Any scoring cohort or holdout analysis is specified for the client's team to run on their records; BML works from the aggregate results. `inbound-routing.md` and the outbound stages only where rows show the client already enriches form submissions or runs outbound (each file's BML note) |
| **Self** | BML's own pipeline, or a non-client project | Upstream as written |

**Rules for both client modes:**

1. **Inputs come from rows:** I-3, I-4, I-9, B-6, B-9, A-12, A-15, D-6, L-8, J-1 (full list in the reference §1). A missing fact (who answers, response time, close rate, which CRM) is `[NEEDS PROOF: <row ID>]` and a "Gaps to ask about" item. Never estimate it.
2. **Process documentation only.** BML never logs in to, configures or writes to a client's CRM, call tracking, booking tool or phone system. Every automation is a recommendation the client's team or vendor implements, with a named role and a human checkpoint (reference §9).
3. **Benchmarks are not targets.** Speed-to-lead multipliers, conversion benchmarks, SLA hours and thresholds in this skill are industry or SaaS figures. Never present them as the client's results or promise them. Targets come from I-3/I-4 or are agreed with the client; a cited study carries its source and year (rules §4).
4. **Never promise response times beyond I-3** and never route more work than B-6 capacity and I-10 seasonality allow: every design has an at-capacity path (rules §6).
5. **No personal data:** stage notes, routing examples, alerts and reports use roles, placeholders and aggregates, never customer or patient names, numbers, conditions or recordings. Clinical: tracking, call recording and forms on patient-facing pages are flagged for a person, not added (rules §7, reference §11).
6. **Findings that answer an `OPEN` row** (e.g. a form that doesn't reach anyone, for A-12 or I-3) are staged as `DRAFT` rows in the rules §10 format for `client-context-miner` (a BML organization skill outside this repo), in an internal block after the context footer that is stripped with it; never written to ClickUp. Test leads or calls are run by a person with the client's knowledge, never by the agent.
<!-- BML:END modes -->

---

## Core Principles

### Single Source of Truth
One system of record for every lead and account. If data lives in multiple places, it will conflict. Pick a CRM as the canonical source and sync everything to it.

### Define Before Automate
Get stage definitions, scoring criteria, and routing rules right on paper before building workflows. Automating a broken process just creates broken results faster.

### Measure Every Handoff
Every handoff between teams is a potential leak. Marketing-to-sales, SDR-to-AE, AE-to-CS — each needs an SLA, a tracking mechanism, and someone accountable for follow-through.

### Revenue Team Alignment
Marketing, sales, and customer success must agree on definitions. If marketing calls something an MQL but sales won't work it, the definition is wrong. Alignment meetings aren't optional.

---

## Lead Lifecycle Framework

### Stage Definitions

| Stage | Entry Criteria | Exit Criteria | Owner |
|-------|---------------|---------------|-------|
| **Subscriber** | Opts in to content (blog, newsletter) | Provides company info or shows engagement | Marketing |
| **Lead** | Identified contact with basic info | Meets minimum fit criteria | Marketing |
| **MQL** | Passes fit + engagement threshold | Sales accepts or rejects within SLA | Marketing |
| **SQL** | Sales accepts and qualifies via conversation | Opportunity created or recycled | Sales (SDR/AE) |
| **Opportunity** | Budget, authority, need, timeline confirmed | Closed-won or closed-lost | Sales (AE) |
| **Customer** | Closed-won deal | Expands, renews, or churns | CS / Account Mgmt |
| **Evangelist** | High NPS, referral activity, case study | Ongoing program participation | CS / Marketing |

Outbound contacts follow their own stages (targeted → in sequence → replied → positive → meeting booked → meeting held → opportunity), with fields for signal, tier, sequence, and channel so meetings can be attributed. See [references/lifecycle-definitions.md](references/lifecycle-definitions.md#outbound-stages).

### MQL Definition

An MQL requires both **fit** and **engagement**:

- **Fit score** — Does this person match your ICP? (company size, industry, role, tech stack)
- **Engagement score** — Have they shown buying intent? (pricing page, demo request, multiple visits)

Neither alone is sufficient. A perfect-fit company that never engages isn't an MQL. A student downloading every ebook isn't an MQL.

### MQL-to-SQL Handoff SLA

Define response times and document them:
- MQL alert sent to assigned rep
- Rep contacts within **4 hours** (business hours)
- Rep qualifies or rejects within **48 hours**
- Rejected MQLs go to recycling nurture with reason code

**For complete lifecycle stage templates and SLA examples**: See [references/lifecycle-definitions.md](references/lifecycle-definitions.md)

---

## Lead Scoring

### Scoring Dimensions

**Explicit scoring (fit)** — Who they are:
- Company size, industry, revenue
- Job title, seniority, department
- Tech stack, geography

**Implicit scoring (engagement)** — What they do:
- Page visits (especially pricing, demo, case studies)
- Content downloads, webinar attendance
- Email engagement (opens, clicks)
- Product usage (for PLG)

**Negative scoring** — Disqualifying signals:
- Competitor email domains
- Student/personal email
- Unsubscribes, spam complaints
- Job title mismatches (intern, student)

### Building a Scoring Model

1. Define your ICP attributes and weight them
2. Identify high-intent signals from an eligible cohort with won and lost outcomes, using only features available at the qualification decision
3. Set point values for each attribute and behavior
4. Set MQL threshold (typically 50-80 points on a 100-point scale)
5. Freeze the rule and test a later, fully observed holdout against the current routing baseline; report precision, recall, missed wins, false positives, and workload
6. Pilot with monitoring and rollback; tune on development cohorts and preserve an untouched holdout for each promotion

### Common Scoring Mistakes

- Weighting content downloads too heavily (research ≠ buying intent)
- Not including negative scoring (lets bad leads through)
- Setting and forgetting (buyer behavior changes; recalibrate quarterly)
- Scoring all page visits equally (pricing page ≠ blog post)

**For detailed scoring templates and example models**: See [references/scoring-models.md](references/scoring-models.md)

---

## Lead Routing

### Routing Methods

| Method | How It Works | Best For |
|--------|-------------|----------|
| **Round-robin** | Distribute evenly across reps | Equal territories, similar deal sizes |
| **Territory-based** | Assign by geography, vertical, or segment | Regional teams, industry specialists |
| **Account-based** | Named accounts go to named reps | ABM motions, strategic accounts |
| **Skill-based** | Route by deal complexity, product line, or language | Diverse product lines, global teams |

### Routing Rules Essentials

- Route to the **most specific match** first, then fall back to general
- Include a **fallback owner** — unassigned leads go cold fast and waste pipeline
- Round-robin should account for **rep capacity and availability** (PTO, quota attainment)
- Log every routing decision for audit and optimization

### Speed-to-Lead

Response time is the single biggest factor in lead conversion:
- Contact within **5 minutes** = 21x more likely to qualify (Lead Connect)
- After **30 minutes**, conversion drops by 10x
- After **24 hours**, the lead is effectively cold

Build routing rules that prioritize speed. Alert reps immediately. Escalate if SLA is missed.

For form-submit enrichment, booking branches, missing-data fallbacks, and late results, load [the inbound-routing playbook](references/inbound-routing.md). Use it alongside the ownership and territory rules below.

**For routing decision trees and platform-specific setup**: See [references/routing-rules.md](references/routing-rules.md)

---

## Pipeline Stage Management

### Pipeline Stages

| Stage | Required Fields | Exit Criteria |
|-------|----------------|---------------|
| **Qualified** | Contact info, company, source, fit score | Discovery call scheduled |
| **Discovery** | Pain points, current solution, timeline | Needs confirmed, demo scheduled |
| **Demo/Evaluation** | Technical requirements, decision makers | Positive evaluation, proposal requested |
| **Proposal** | Pricing, terms, stakeholder map | Proposal delivered and reviewed |
| **Negotiation** | Redlines, approval chain, close date | Terms agreed, contract sent |
| **Closed Won** | Signed contract, payment terms | Handoff to CS complete |
| **Closed Lost** | Loss reason, competitor (if any) | Post-mortem logged |

### Stage Hygiene

- **Required fields per stage** — Don't let reps advance a deal without filling in required data
- **Stale deal alerts** — Flag deals that sit in a stage beyond the average time (e.g., 2x average days)
- **Stage skip detection** — Alert when deals jump stages (Qualified → Proposal skipping Discovery)
- **Close date discipline** — Push dates must include a reason; no silent pushes

### Pipeline Metrics

| Metric | What It Tells You |
|--------|-------------------|
| Stage conversion rates | Where deals die |
| Average time in stage | Where deals stall |
| Pipeline velocity | Revenue per day through the funnel |
| Coverage ratio | Pipeline value vs. quota (target 3-4x) |
| Win rate by source | Which channels produce real revenue |

---

## CRM Automation Workflows

### Essential Automations

- **Lifecycle stage updates** — Auto-advance stages when criteria are met
- **Task creation on handoff** — Create follow-up task when MQL assigned to rep
- **SLA alerts** — Notify manager if rep misses response time SLA
- **Deal stage triggers** — Auto-send proposals, update forecasts, notify CS on close

### Marketing-to-Sales Automations

- **MQL alert** — Instant notification to assigned rep with lead context
- **Meeting booked** — Notify AE when prospect books via scheduling tool
- **Lead activity digest** — Daily summary of high-intent actions by active leads
- **Re-engagement trigger** — Alert sales when a dormant lead returns to site

### Calendar Scheduling Integration

- **Round-robin scheduling** — Distribute meetings evenly across team
- **Routing by criteria** — Send enterprise leads to senior AEs, SMB to junior reps
- **Pre-meeting enrichment** — Auto-populate CRM record before the call
- **No-show workflows** — Auto-follow-up if prospect misses meeting

**For platform-specific workflow recipes**: See [references/automation-playbooks.md](references/automation-playbooks.md)

---

## Deal Desk Processes

### When You Need a Deal Desk

- ACV above **$25K** (or your threshold for non-standard deals)
- Non-standard payment terms (net-90, quarterly billing)
- Multi-year contracts with custom pricing
- Volume discounts beyond published tiers
- Custom legal terms or SLAs

### Approval Workflow Tiers

| Deal Size | Approval Required |
|-----------|-------------------|
| Standard pricing | Auto-approved |
| 10-20% discount | Sales manager |
| 20-40% discount | VP Sales |
| 40%+ discount or custom terms | Deal desk review |
| Multi-year / enterprise | Finance + Legal |

### Non-Standard Terms Handling

Document every exception. Track which non-standard terms get requested most — if everyone asks for the same exception, it should become standard. Review quarterly.

---

## Data Hygiene & Enrichment

### Dedup Strategy

- **Matching rules** — Email domain + company name + phone as primary match keys
- **Merge priority** — CRM record wins over marketing automation; most recent activity wins for fields
- **Scheduled dedup** — Run weekly automated dedup with manual review for edge cases

### Required Fields Enforcement

- Enforce required fields at each lifecycle stage
- Block stage advancement if fields are empty
- Use progressive profiling — don't require everything upfront

### Enrichment Tools

| Tool | Strength |
|------|----------|
| Clay | Waterfall enrichment across many providers |
| Apollo | Contact data + sequences, strong for prospecting |
| ZoomInfo | Enterprise-grade, largest B2B database |

### Quarterly Audit Checklist

- Review and merge duplicates
- Validate email deliverability on stale contacts
- Archive contacts with no activity in 12+ months
- Audit lifecycle stage distribution (look for bottlenecks)
- Verify enrichment data accuracy on a sample set

---

## RevOps Metrics Dashboard

### Key Metrics

| Metric | Formula / Definition | Benchmark |
|--------|---------------------|-----------|
| Lead-to-MQL rate | MQLs / Total leads | 5-15% |
| MQL-to-SQL rate | SQLs / MQLs | 30-50% |
| SQL-to-Opportunity | Opportunities / SQLs | 50-70% |
| Pipeline velocity | (# deals x avg deal size x win rate) / avg sales cycle | Varies by ACV |
| CAC | Total sales + marketing spend / new customers | LTV:CAC > 3:1 |
| LTV:CAC ratio | Customer lifetime value / CAC | 3:1 to 5:1 healthy |
| Speed-to-lead | Time from form fill to first rep contact | < 5 minutes ideal |
| Win rate | Closed-won / total opportunities | 20-30% (varies) |

### Dashboard Structure

Build three views:
1. **Marketing view** — Lead volume, MQL rate, source attribution, cost per MQL
2. **Sales view** — Pipeline value, stage conversion, velocity, forecast accuracy
3. **Executive view** — CAC, LTV:CAC, revenue vs. target, pipeline coverage

---

## Output Format

When delivering RevOps recommendations, provide:

1. **Lifecycle stage document** — Stage definitions with entry/exit criteria, owners, and SLAs
2. **Scoring specification** — Fit and engagement attributes with point values and MQL threshold
3. **Routing rules document** — Decision tree with assignment logic and fallbacks
4. **Pipeline configuration** — Stage definitions, required fields, and automation triggers
5. **Metrics dashboard spec** — Key metrics, data sources, and target benchmarks

Format each as a standalone document the user can implement directly. Include platform-specific guidance when the CRM is known.

<!-- BML:START outputs -->
**For BML client work, this replaces the list above.** Deliver one **Lead Handling Plan** (outline in the reference §12; B2B pipeline mode adds the upstream documents as its sections):

- It is an **agency artifact**: Baker house style, no client voice or style pages, distinctiveness `n/a`. Customer-facing text it calls for (missed-call text-back, form acknowledgment, quote follow-up, review ask) is a client deliverable: list it as a recommendation and hand it to `sms` or `emails`, which load the client's voice and run guardrails.
- Check it against page 12 and F-13 at any status, and the segment rules (rules §5, §7). Name the client's approver from J-1 (A-19 if J-1 is open) as the sign-off before anything reaches the client's team.
- End with the context footer (rules §9).
- Save to the client's Drive `OUTPUTS/STRATEGY/` folder, resolved by ID from the router; never search Drive or create the folder. A prospect (`INTAKE DRAFT`) has no client folder: keep the file in the session outputs folder. If it isn't on file, return the file and ask where it goes. Draft a ClickUp record (tag `strategy`, status `internal review`) and create it only if the user asks in this conversation.
<!-- BML:END outputs -->

---

## Task-Specific Questions

1. What CRM platform are you using (or planning to use)?
2. How many leads per month do you generate?
3. What's your current MQL definition?
4. Where do leads get stuck in your funnel?
5. Do you have SLAs between marketing and sales today?

---

## Tool Integrations

For implementation, see the [tools registry](https://github.com/coreyhaines31/marketingskills/blob/main/tools/REGISTRY.md). Key RevOps tools:

| Tool | What It Does | Guide |
|------|-------------|-------|
| **HubSpot** | CRM, marketing automation, lead scoring, workflows | [hubspot.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/hubspot.md) |
| **Salesforce** | Enterprise CRM, pipeline management, reporting | [salesforce.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/salesforce.md) |
| **Calendly** | Meeting scheduling, round-robin routing | [calendly.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/calendly.md) |
| **SavvyCal** | Scheduling with priority-based availability | [savvycal.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/savvycal.md) |
| **Attio** | CRM with a hosted MCP for agents | [attio.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/attio.md) |
| **Apollo** | Contact data, enrichment, and outbound sequences | [apollo.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/apollo.md) |
| **ActiveCampaign** | Marketing automation for SMBs, lead scoring | [activecampaign.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/activecampaign.md) |
| **Zapier** | Cross-tool automation and workflow glue | [zapier.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/zapier.md) |
| **Introw** | Partner-sourced pipeline, commissions, deal registration, QBRs | [introw.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/introw.md) |
| **Crossbeam** | Partner account overlaps and co-sell identification | [crossbeam.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/crossbeam.md) |

<!-- BML:START tools -->
**At BML (client work and BML's own pipeline), BML's HubSpot connector is not in use:** don't route work through it. **For BML client work:** every tool above is "if the client uses it" — check A-15 and page 00 §8 for the client's CRM, call tracking, booking tool and phone system, and name them only as the place the client's team implements a recommendation. Never connect to a client's CRM through an MCP or API (e.g. Attio's hosted MCP). BML's own sources: Windsor.ai for aggregate GA4, Ads, Search Console, Business Profile and Meta data (read only; never its write actions); reports the client exports from their own systems, aggregate only; ClickUp for records; Google Drive for files.
<!-- BML:END tools -->

---

## Related Skills

- **cold-email**: For outbound prospecting emails
- **emails**: For lifecycle and nurture email flows
- **pricing**: For pricing decisions and packaging
- **analytics**: For tracking pipeline metrics and attribution
- **launch**: For go-to-market launch planning
- **sales-enablement**: For sales collateral, decks, and objection handling

<!-- BML:START related -->
For BML client work, also:
- **analytics**: implementation spec for call tracking, form and booking events (A-12)
- **attribution**: source capture and reconciling call tracking, GA4 and the client's job records
- **sms** / **emails**: the customer-facing follow-up and review-ask messages this plan recommends
- **cro**: the forms and booking flow themselves
- **marketing-loops**: a recurring lead-handling check, set up as a scheduled task
- **client-context-miner** (BML organization skill, outside this repo): takes the `DRAFT` rows this skill stages
<!-- BML:END related -->
