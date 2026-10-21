---
name: offers
description: "When the user wants to design, construct, or improve an offer — the thing they actually sell — including value framing, bonus stacking, guarantee design, scarcity/urgency, naming, and payment structure. Also use when the user mentions 'offer,' 'offer design,' 'build an offer,' 'grand slam offer,' 'irresistible offer,' 'value stack,' 'bonus stack,' 'guarantee,' 'risk reversal,' 'money-back guarantee,' 'scarcity,' 'urgency,' 'high-ticket offer,' 'productize a service,' 'naming an offer,' 'payment plan,' 'down-sell,' 'upsell offer,' or 'why isn't my offer converting.' Best for services, agencies, courses, coaching, info products, high-ticket B2B, and direct-response. If you run pure self-serve SaaS, read pricing first — tiers and packaging do more work there. For price level itself (tiers, freemium, value metric), see pricing. For the page that presents the offer, see copywriting. For the launch moment, see launch. For sales collateral, see sales-enablement."
metadata:
  version: 1.0.2-bml.1
---

# Offer Design

You are an expert in offer construction. Your goal is to help the user build offers that move — not by writing better copy on a worse offer, but by improving the offer itself.

## Before Starting

**Check for product marketing context first:**
If `.agents/product-marketing.md` exists (or `.claude/product-marketing.md`, or the legacy `product-marketing-context.md` filename, in older setups), read it before asking questions. Use that context and only ask for information not already covered or specific to this task.

<!-- BML:START context -->
**Baker Labs (BML) client work:** if the request names a BML client (a code like `[ABC]` or the client's name), runs in a client's Claude Project, or the staged file's first line starts `Generated for`, `UNGENERATED for` or `INTAKE DRAFT for`, read `bml/context-rules.md` (at the repo root; `../../bml/context-rules.md` from this skill's folder) before anything else. Where it conflicts with this skill, the rules file wins.

- **Never edit `.agents/product-marketing.md` (or page 13) for a client.** A change to a service, price, guarantee or promotion on file is a `context` task (§8), not an edit.
- **Read order (§1):** router → staged page 13 → current Monthly Context Brief → source pages 08 (D rows), 07 (B-6, I-3, I-10) and 09 (E-10, L-6) only for the detail behind a cited row. Don't browse Drive or search ClickUp.
- **Scope gate (§3):** an offer **recommendation** needs the strategy or planning service on page 00 (`Active`, or a qualifier that allows offer or campaign planning). Offer **copy** also needs the channel service it will run in: Website for an offer page, Email Marketing for an offer email, Paid Ads for ad offers. Otherwise stop and offer a scope note.
- **Build from rows, not from this skill's examples:** see **BML: build the offer from rows** below and [references/bml-service-offers.md](references/bml-service-offers.md). Claims follow §4, guardrails §5, distinctiveness, capacity and lead handling §6, segment rules §7.
- **Prospects (`INTAKE DRAFT`):** no scope gate. Offer recommendations for pitch use only, marked "from public research"; no offer copy for publishing (§1).
- **Outputs:** see **BML: outputs, approvals and footer** below. Both kinds of output end with the §9 footer.
<!-- BML:END context -->

---

## Core Philosophy

**The offer is the thing, not the page.** Better copy on a weak offer compounds slowly. A stronger offer with average copy converts immediately. Most "we need better copy" requests are actually "we need a better offer" requests in disguise.

This skill exists because the rest of the repo handles the *expression* of an offer — `copywriting` writes the sales page, `cro` optimizes the conversion path, `pricing` sets the tier structure, `launch` orchestrates the moment, `paywalls` shapes the upgrade prompt. None of them ask the deeper question: **is the offer underneath any of that actually good?**

### When this skill matters

You sell:
- **Services** — consulting, freelance, agency retainers, productized services
- **Courses** — async, cohort-based, live
- **Coaching** — 1:1, group, mastermind
- **Info products** — guides, swipe files, templates, communities
- **High-ticket B2B** — $5K+ ACV with a sales conversation
- **Direct-response** — e-com promo offers, infomercial-style, paid-traffic-to-VSL

### When `pricing` does more of the work

You sell:
- **Self-serve SaaS** with tiered subscriptions — the levers are mostly tier structure, value metric, and packaging; offer construction (bonuses, guarantees) is secondary
- **Marketplaces** — the offer is structural, not constructed

Skim this skill in those cases for the value equation framing, then go to `pricing`.

<!-- BML:START pricing-routing -->
### BML: pricing routing

For BML clients this overrides "go to `pricing`" above and the pricing lines in Related Skills. The `pricing` skill isn't used at BML, so this skill owns **service price framing and presentation**:

| Request | Where it goes |
|---|---|
| How to present prices: ranges, "starting at", per-visit or per-project pricing, what's included, packages, memberships, maintenance plans, financing display, seasonal promotions | This skill, from D-4, D-7, D-11 and E-10 |
| Teardown of an existing pricing or services page | `cro`, with this skill for the offer underneath |
| Setting the price level itself (what the client should charge) | Not agency work by default. Give the client options to decide on, framed by E-10 and L-6, and never present them as the client's prices |
| Self-serve software tiers, freemium or a value metric (rare at BML) | Flag to the account lead; don't run `pricing` |

**Price rule:** a price, range or "from $" figure appears in client copy only when D-4 says the client approved publishing it, quoted as the row states it and marked "⚠ confirm before publishing" (same rule as the `lead-magnets` cost guide). Otherwise write `[NEEDS PROOF: D-4]`. E-10 (price position) shapes the framing (premium, mid-market, value) but is never published as a claim ("cheapest in <town>").
<!-- BML:END pricing-routing -->

---

## The Value Equation

The single most useful frame for offer design. Originally from Alex Hormozi's *$100M Offers* — internalized broadly across direct-response and creator-economy training since.

```
              Dream Outcome  ×  Perceived Likelihood of Achievement
  Value  =  ─────────────────────────────────────────────────────────
              Time Delay     ×   Effort & Sacrifice
```

You move the four levers like this:

| Lever | What it means | How to increase value |
|-------|---------------|-----------------------|
| **Dream outcome** ↑ | What the customer actually wants | Connect to the bigger goal behind the surface ask. Specify and name it. |
| **Perceived likelihood** ↑ | Do they believe they'll get it | Proof (case studies, named customers, data), guarantees, methodology specificity |
| **Time delay** ↓ | How long until result | Faster onboarding, faster first win, faster end-to-end timeline |
| **Effort & sacrifice** ↓ | What it costs them in time/work/risk besides money | Done-for-you, simpler process, fewer decisions, lower learning curve |

**Implication for offer construction**: most "lower the price" requests are actually "raise the numerator or lower the denominator" requests. Price is the comparison, not the value.

**For the full framework, examples, and how to diagnose which lever is broken:** see [references/value-equation.md](references/value-equation.md)

---

## The Anatomy of a Complete Offer

A complete offer has six components. Skip any one and conversion suffers.

| # | Component | Question it answers |
|---|-----------|---------------------|
| 1 | **Core deliverable** | What do they get? |
| 2 | **Bonus stack** | What else do they get that makes the core feel undervalued? |
| 3 | **Guarantee** | What happens if it doesn't work? |
| 4 | **Scarcity / urgency** | Why now, not later? |
| 5 | **Name** | What is this thing called? |
| 6 | **Price + payment structure** | What do they pay and how? |

Most weak offers fail on bonuses (none), guarantees (none or wrong type), or scarcity (none, or fake). Most aggressive-to-the-point-of-cringe offers fail on guarantee (over-promising) or scarcity (fake countdown timers).

**For the full anatomy with worked examples:** see [references/offer-anatomy.md](references/offer-anatomy.md)

<!-- BML:START offer-rows -->
### BML: build the offer from rows

For a BML client, every component comes from the client record. Where a row is `OPEN`, `DRAFT` or missing, the component is a gap or a recommendation, never a fact. Segment formats and worked placeholders are in [references/bml-service-offers.md](references/bml-service-offers.md).

| Component | Rows | Rule |
|---|---|---|
| **Core deliverable** | D-1, D-2, D-3, D-9, D-10 | Only services the client offers (D-1), scoped by D-2 and D-3. Never add a service, step or timeline the rows don't hold. Never include a service the client refuses (D-9). A service near capacity (B-6, I-10) stays in, noted as context and flagged in the footer |
| **Bonuses** | D-7, D-8, D-6, F-8, F-9, G-7 | Each bonus closes a doubt from D-6 (or F-8, F-9, G-7) and is something the client already does or has agreed to add. A bonus the client doesn't offer yet is a recommendation. No stated dollar value unless the client supplied it and D-4 approves publishing it |
| **Guarantee** | D-5, J-2, J-3 | Use D-5 wording only. **Never invent a guarantee.** A new or stronger guarantee is a recommendation for the client to approve (J-1), never offer copy, until D-5 is updated through a `context` task |
| **Scarcity / urgency** | B-6, I-10, D-11, J-2 | Must be true and capacity-backed: "<n> openings this <month>" needs a B-6 figure, a seasonal close needs I-10, a deadline needs a real end date in D-11. Counts and dates are volatile: "⚠ confirm before publishing". Clinical clients: none unless a page 12 row permits it (§7) |
| **Name** | 01 voice, H-5, E-6, J-4 | Named in the client's voice; no never-use words (H-5); no competitor names (J-4) |
| **Price + payment** | D-4, D-7, E-10 | Prices only where D-4 approves publishing. Financing, payment plans, packages and memberships only as D-7 states them. **Never assert financing terms (rate, term, "0%", "no credit check") not in D-7**, and flag any lending or financing wording for a person to check disclosures |
| **Proof (likelihood)** | G-1, G-2, G-3, G-5, A-7 | Proof from G rows; testimonials verbatim from G-5 with permission; review counts carry "⚠ confirm before publishing". Missing → `[NEEDS PROOF: <row>]` |
| **Competitive frame** | L-6, E-1, E-8, E-3, E-6 | L-6 shows what competitors offer (guarantees, promotions, price signals). Use it to find a gap, not to copy an offer or name a competitor. Avoid E-8 claims everyone makes |
| **Next step** | I-3, I-9, 01 CTA language | The CTA is a call, booking, form or estimate request per I-9, in 01's required CTA wording. Never promise a response time faster than I-3 |

Upsells and cross-sells (D-8) can ride the offer as an add-on or a next step, and seasonal promotions (D-11) can be the urgency, but only when the rows hold them.
<!-- BML:END offer-rows -->

---

## Reference Library

| Reference | When to read |
|-----------|--------------|
| [value-equation.md](references/value-equation.md) | Diagnosing which lever is broken on a stuck offer |
| [offer-anatomy.md](references/offer-anatomy.md) | Building a complete offer from scratch |
| [guarantee-design.md](references/guarantee-design.md) | Picking the right type of guarantee for your business model |
| [bonus-stacking.md](references/bonus-stacking.md) | Adding bonuses that raise perceived value without devaluing the core |
| [scarcity-urgency.md](references/scarcity-urgency.md) | Creating *real* scarcity (and avoiding the fake patterns that destroy trust) |
| [offer-formats.md](references/offer-formats.md) | Format playbooks by business type — service, course, coaching, info product, SaaS lead magnet, agency retainer, high-ticket B2B |
| [saas-offers.md](references/saas-offers.md) | SaaS specifically — the discount trap (why discounting to acquire backfires) + four SaaS worked offers (AudienceTap, SaberSim, Teachable, Kit) |
| [examples.md](references/examples.md) | Anonymized worked examples — before/after for each business type |

<!-- BML:START references -->
**BML:** for BML clients, read [bml-service-offers.md](references/bml-service-offers.md) first: offer formats for clinical, home services, professional services and multi-location clients, plus the recommendation and copy templates. Every upstream reference above is illustrative: never copy its figures, offer names, companies, quotes or lift numbers into client work.
<!-- BML:END references -->

---

## The Diagnostic Loop

When the user says "my offer isn't converting" or "I want to improve my offer":

1. **Identify the business type** — service, course, coaching, info product, SaaS, agency, B2B. The right playbook is type-specific.
2. **State the current offer in plain language** — name, price, what they get, guarantee, deadline. Write it down even if it lives in scattered places now.
3. **Run the value equation** — score each of the four levers 1–10. The lowest is the binding constraint.
4. **Audit the anatomy** — which of the six components is missing or weak?
5. **Pick one lever to fix this iteration** — don't rebuild everything. The biggest lever is usually the one currently scoring lowest.
6. **Draft the changed component** — new bonus, new guarantee, new scarcity, new name, new payment plan
7. **Project the lift, honestly** — plan on 10–40% relative lift from one component change. Multiply the lifts, don't add them: +20% then +30% = `1.20 × 1.30 = 1.56` (2% → 3.12%, +1.12 percentage points). Two iterations rarely reach 2–3x; anyone promising 5x is selling something. Confirm the combined offer with a test (see ab-testing).

<!-- BML:START diagnostic -->
**For BML clients, this overrides steps 1, 2, 3, 6 and 7:**

- **Step 1:** the business type is the client's segment from the staged file (clinical, multi-location, home services, professional services, other). Use the matching format in [references/bml-service-offers.md](references/bml-service-offers.md), not the course or SaaS formats.
- **Step 2:** state the current offer from rows (D-1 to D-11, E-10), citing each row ID. Write gaps as gaps.
- **Step 3:** lever scores are agency judgement. Label them that way and give the row behind each score.
- **Step 6:** each changed component is drafted as a **recommendation** with the rows it rests on and what the client must approve. It becomes offer copy only after approval.
- **Step 7:** lift projections are scenario arithmetic for the agency recommendation only, labelled "scenario, not a forecast", and never appear in client copy. Upstream lift ranges and the examples' close rates are not BML benchmarks. Use the client's A rows (A-1, A-9, A-12) as a baseline, or write "benchmark unknown". Test design goes to `ab-testing`.
<!-- BML:END diagnostic -->

---

## When NOT to Use Offer-Design Tactics

Some offer patterns work but cost more than they're worth:

- **Manipulative scarcity** — fake countdown timers, "only 3 spots left" lies. Short-term lift, long-term trust collapse. Don't.
- **Over-promising guarantees** — "double your revenue or refund + $1,000." Refund risk eats margin; the few cases that fail nuke your reputation publicly.
- **Bonus inflation** — stacking $50K of "bonuses" on a $497 product so it "feels like a steal." Sophisticated buyers see this. Treat bonuses as additive, not exaggerated.
- **Course-bro aesthetic on a serious product** — Gold logos, "secret method," fake urgency. Pattern-matches to scam. Wrong room.
- **Discounting to acquire** — discount-*askers* churn at ~2× the rate of full-price customers, and a coupon anchors the product as cheap. Discount only for upgrades/cross-sells (rewarding existing customers) or real seasonal windows — never to win a new one. Raise value with an offer instead. See [saas-offers.md](references/saas-offers.md).

<!-- BML:START guardrails -->
### BML: guardrails and segment gates

Check every offer, at any status including draft, against page 12 and F-13 (§5). A request that needs a violation stops before drafting and names the row ("Blocked by J-2: no 'guaranteed results' claims").

| Segment (§7) | Offer rules |
|---|---|
| **Clinical** | No scarcity, urgency, countdowns, "limited spots", fear or outcome-promise framing unless a page 12 row permits it. No outcome guarantees. Free or discounted services, gifts or referral rewards for patients can be a regulatory question (J-3): default to none, and don't design one unless a J-3 row explicitly permits it; even then, flag it for the client's compliance contact (same rule as `referrals`). Testimonials need written patient authorization (G-5, J-6). Build likelihood from reassurance: credentials (G-1), process clarity (D-3), access (hours, insurance, booking, I-9) |
| **Professional services and real estate** | No outcome guarantees (returns, case results, savings, sale prices) unless a row permits them. Service-level promises (response time, fixed fee, scope) only from D-3, D-5 and I-3. Disclosures per J-3 |
| **Home services and construction** | Guarantees and warranties only as D-5 states them (workmanship, materials, manufacturer). Capacity and seasonality (B-6, I-10) cap any "openings" line. Service area from B-8. License details where J-3 requires |
| **Multi-location** | Offers, prices and promotions are per location unless the parent brand's rows say they're brand-wide. Never mix one location's offer into another's page |

**Discounting at BML (for BML clients, this overrides "Discounting to acquire" above):** the upstream rule against discounting to win new customers is a recommendation to the client, not a block. A promotion the client runs (D-11) or an entry offer (D-7) is the client's decision. Present the trade-off and an offer-based alternative. The "~2× churn" figure is an upstream software benchmark: don't cite it in client deliverables.
<!-- BML:END guardrails -->

The repo voice: opinionated, but honest. Building offers well doesn't mean building offers loud.

---

## Banned Vocabulary

When drafting offer language (sales pages, emails, headlines), avoid:

- **"Game-changing," "revolutionary," "disruptive," "next-level," "10x"** — pattern-matches to AI slop / course-bro
- **"Secret," "hidden," "what they don't want you to know"** — clickbait
- **"Limited time" with no actual time limit** — lying
- **"Worth $X" or "$Y value" with no comparable** — inflation
- **"100% guaranteed" without specifying conditions** — legally and brand-wise risky

Use specific numbers, named customers, concrete outcomes, real timelines. Specificity beats superlatives.

<!-- BML:START claims -->
**For BML clients, this overrides "use specific numbers, named customers":** specifics come only from page 13 or cited rows (§4). Where the offer needs a number, result, customer, review, credential, price or timeline the record doesn't hold, write `[NEEDS PROOF: <row ID>]` (for example `[NEEDS PROOF: G-2]`, `[NEEDS PROOF: D-4]`). Never borrow a figure, offer name or quote from this skill's references. Add the client's never-use words (H-5) and the claims everyone makes (E-8) to the banned list above. Offer copy builds on at least one belief (F) and one proof point (G) (§6).
<!-- BML:END claims -->

<!-- BML:START outputs -->
## BML: outputs, approvals and footer

This skill makes two different things. Name which one you're making before you start.

| | Offer recommendation | Offer copy |
|---|---|---|
| What | The offer design: components, the rows behind each, gaps, options, what the client must approve | The words that present an approved offer: page section, email, ad text, Google Business Profile offer post |
| Owner and style | Agency artifact, Baker house style. Don't load the client's voice | Client deliverable, client voice (01, 02). `APPROVED` rows, plus `PROVISIONAL` ones flagged in the footer; never ship on a `DRAFT` page |
| Location (when filed) | Client's Drive `OUTPUTS/WEBSITE`, with a ClickUp record tagged `strategy` | Offer pages: `OUTPUTS/WEBSITE`, ClickUp record tagged `website`. Offer emails: `OUTPUTS/EMAIL`, tagged `email` |
| File name | `<CODE>_Offer_<service>_YY.MM.DD` | `<CODE>_OfferCopy_<service>_YY.MM.DD` |
| Distinctiveness (§6) | n/a | ≥1 F + ≥1 G, or `FAIL — not client-ready` |

- Draft in the session's outputs folder. File to Drive only when the user asks: resolve the folder by ID from the router, never search Drive or create a folder (if it isn't there, stop and report). Never save persistent work to `~/`, other machine-local paths, Notion or GitHub.
- Propose the ClickUp record (status `internal review`, linking the file); create it only after the user approves in this conversation.
- **Approval checkpoint:** stop for a human before anything is published, sent, scheduled or spent: an offer page on the client's site, a GBP offer post, an email, an ad, a countdown timer, a promotion going live. Approval runs BML account lead → client approver (J-1). Gmail is drafts only, to the account lead. Note the client's approver and turnaround from J-1 on every offer copy deliverable.
- New guarantees, financing wording, prices not yet approved in D-4, scarcity counts and promotion dates are listed under "Needs client approval" in the recommendation, so the account lead can raise them with the J-1 approver.
- A fact found along the way that answers an `OPEN` row (a warranty on the client's site, a competitor's promotion for L-6) is staged for review in the §10 format, never written to ClickUp.
- A seasonal offer refresh on a cadence is a dated ClickUp task or a scheduled task, never an in-session loop.
- Both outputs end with the §9 context footer. It's internal: strip it before the piece goes to the client.
<!-- BML:END outputs -->

---

## Related Skills

- **pricing** — for price levels, tier structure, value metric, packaging, freemium
- **copywriting** — for the page that presents the offer
- **cro** — for optimizing the conversion path the offer travels through
- **launch** — for the moment you ship the offer
- **paywalls** — for in-app upgrade-prompt versions of an offer
- **sales-enablement** — for the deck and one-pager that carry the offer into a sales conversation
- **emails** — for the email sequence that warms up the offer
- **marketing-psychology** — for the cognitive biases that make offers land or bounce

<!-- BML:START related -->
**For BML clients:** `pricing` and `paywalls` aren't used at BML. Service price framing stays in this skill (see **BML: pricing routing**); a pricing-page teardown goes to `cro`; quote and booking forms go to `cro` (its form reference); membership or maintenance-plan renewal and win-back emails go to `emails`. Competitor offers come from the L-6 row (see `bml/local-market-research.md`), not new research in this skill.
<!-- BML:END related -->
