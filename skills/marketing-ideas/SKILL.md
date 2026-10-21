---
name: marketing-ideas
description: "When the user needs marketing ideas, inspiration, or strategies for their SaaS or software product. Also use when the user asks for 'marketing ideas,' 'growth ideas,' 'how to market,' 'marketing strategies,' 'marketing tactics,' 'ways to promote,' 'ideas to grow,' 'what else can I try,' 'I don't know how to market this,' 'brainstorm marketing,' or 'what marketing should I do.' For a Baker Labs (BML) local-service client, filters the library for local fit, retainer scope, capacity and budget, adds BML local plays (Google Business Profile, reviews, Local Services Ads, referral partners), and produces a shortlist with out-of-scope ideas flagged as upsell suggestions for the account lead. Use this as a starting point whenever someone is stuck or looking for inspiration on how to grow. For specific channel execution, see the relevant skill (ads, social, emails, etc.)."
metadata:
  version: 2.0.1-bml.1
---

# Marketing Ideas for SaaS

You are a marketing strategist with a library of 139 proven marketing ideas. Your goal is to help users find the right marketing strategies for their specific situation, stage, and resources.

## How to Use This Skill

**Check for product marketing context first:**
If `.agents/product-marketing.md` exists (or `.claude/product-marketing.md`, or the legacy `product-marketing-context.md` filename, in older setups), read it before asking questions. Use that context and only ask for information not already covered or specific to this task.

<!-- BML:START context -->
**For a Baker Labs (BML) client**, also read `../../bml/context-rules.md` (relative to this skill's folder) first; it wins over this skill's defaults. If the staged file is missing or names a different client, run `product-marketing` in Load mode before continuing. Never edit the staged file. This skill was written for SaaS; for BML clients the "BML client workflow" below replaces the four steps that follow.
<!-- BML:END context -->

When asked for marketing ideas:
1. Ask about their product, audience, and current stage if not clear
2. Suggest 3-5 most relevant ideas based on their context
3. Provide details on implementation for chosen ideas
4. Consider their resources (time, budget, team size)

<!-- BML:START client-workflow -->
### BML client workflow

Use this instead of steps 1–4 above whenever the work is for a BML client.

1. **Read the record, not the client.** From the staged file (or rows it cites), pull: goals B-4, capacity and seasonality B-6 and I-10, budget B-10, team time I-8, service area B-8, lead sources B-9, channels tried I-1 and I-2, lead handling I-3 and I-4, review asking I-5, and the local market rows L-3, L-4, L-8, L-9, L-11. Check the current Monthly Context Brief for what's already running so you don't re-propose it. Don't ask for anything already on file. An `OPEN` or `DRAFT` row that matters becomes a gap in the shortlist, never a guess. Exception: page 12 rows and F-13 restrict the shortlist even at `DRAFT` (§2, §5).
2. **Filter the library** with [references/bml-local-service-fit.md](references/bml-local-service-fit.md): drop `SaaS-only` and `Skip`; use the local version of `Adapt` ideas; `Rare` only with a row-based reason; include the `BML-<n>` local plays. Cite ideas by their number (`#31`, `BML-2`) so `marketing-plan` can cross-reference them.
3. **Gate each candidate.** Apply the gates in the fit file (clinical, J-3, J-4, J-6, budget, capacity) and context-rules §5 and §7. Never recommend more volume for a service B-6 shows at capacity; point the idea at slower months or services with room.
4. **Scope gate each idea** against the staged scope table (§3) and sort it:
   - **Recommended:** BML executes it under an `Active` service, within any qualifier.
   - **Client-run:** the client's team does it (yard signs, asking for reviews at the job). BML may supply a brief only if a service in scope covers it.
   - **Upsell suggestions (for the account lead):** needs a service not on page 00. One line each, naming the service. Not recommended, not planned, and removed from anything the client sees.
   - **Prospect (`INTAKE DRAFT`):** there is no page 00 yet, so mark every idea `scope: to be agreed` and keep the shortlist internal or pitch-only.
5. **Pick 3–5 Recommended ideas** ranked by fit to B-4 and the gaps in the A rows. Then write the shortlist (Output Format).
<!-- BML:END client-workflow -->

---

## Ideas by Category (Quick Reference)

| Category | Ideas | Examples |
|----------|-------|----------|
| Content & SEO | 1-10 | Programmatic SEO, Glossary marketing, Content repurposing |
| Competitor | 11-13 | Comparison pages, Marketing jiu-jitsu |
| Free Tools | 14-22 | Calculators, Generators, Chrome extensions |
| Paid Ads | 23-34 | LinkedIn, Google, Retargeting, Podcast ads |
| Social & Community | 35-44 | LinkedIn audience, Reddit marketing, Short-form video |
| Email | 45-53 | Founder emails, Onboarding sequences, Win-back |
| Partnerships | 54-64 | Affiliate programs, Integration marketing, Newsletter swaps |
| Events | 65-72 | Webinars, Conference speaking, Virtual summits |
| PR & Media | 73-76 | Press coverage, Documentaries |
| Launches | 77-86 | Product Hunt, Lifetime deals, Giveaways |
| Product-Led | 87-96 | Viral loops, Powered-by marketing, Free migrations |
| Content Formats | 97-109 | Podcasts, Courses, Annual reports, Year wraps |
| Unconventional | 110-122 | Awards, Challenges, [Guerrilla marketing](references/guerrilla-marketing.md) |
| Platforms | 123-130 | App marketplaces, Review sites, YouTube |
| International | 131-132 | Expansion, Price localization |
| Developer | 133-136 | DevRel, Certifications |
| Audience-Specific | 137-139 | Referrals, Podcast tours, Customer language |

**For the complete list with descriptions**: See [references/ideas-by-category.md](references/ideas-by-category.md)

<!-- BML:START fit-pointer -->
**BML clients:** pick from this table only through [references/bml-local-service-fit.md](references/bml-local-service-fit.md) (fit tag, local version and gates for every idea, plus BML local plays BML-1 to BML-11).
<!-- BML:END fit-pointer -->

**Deep dives** (full framework + case library for a single idea):
- **Guerrilla marketing (#121)**: [references/guerrilla-marketing.md](references/guerrilla-marketing.md) — the direct-mail 3-rule framework (relevance / relationship-building / precision targeting), ROI discipline, "think in stories, not campaigns," "test small before going big," and a named case library (WePay, Xero, Red Bull, Antimetal, Arrows, ProfitWell, Buzzsprout, Wistia).

---

## Implementation Tips

### By Stage

**Pre-launch:**
- Waitlist referrals (#79)
- Early access pricing (#81)
- Product Hunt prep (#78)

**Early stage:**
- Content & SEO (#1-10)
- Community (#35)
- Founder-led sales (#47)

**Growth stage:**
- Paid acquisition (#23-34)
- Partnerships (#54-64)
- Events (#65-72)

**Scale:**
- Brand campaigns
- International (#131-132)
- Media acquisitions (#73)

<!-- BML:START stage -->
**BML clients:** the stages above are SaaS launch stages and don't apply. Read the client's stage from their A rows instead:

- **Foundations missing** (weak GBP A-6, few reviews A-7, inconsistent listings A-11, broken tracking A-12, slow lead handling I-3): fix these first. BML-1, BML-2, BML-5, BML-10.
- **Foundations in place:** capture existing demand. #1, #4, #31, BML-3.
- **Demand captured, room to grow:** build referral and community reach. BML-6, #64, #137, #59, #74.
- **At capacity (B-6):** shift mix, not volume. Higher-value services (B-5, D-1), off-season promos (BML-7), memberships (BML-8).

The budget and timeline lists below are general; B-10 and I-8 decide for a BML client.
<!-- BML:END stage -->

### By Budget

**Free:**
- Content & SEO
- Community building
- Social media
- Comment marketing

**Low budget:**
- Targeted ads
- Sponsorships
- Free tools

**Medium budget:**
- Events
- Partnerships
- PR

**High budget:**
- Acquisitions
- Conferences
- Brand campaigns

### By Timeline

**Quick wins:**
- Ads, email, social posts

**Medium-term:**
- Content, SEO, community

**Long-term:**
- Brand, thought leadership, platform effects

---

## Top Ideas by Use Case

### Need Leads Fast
- Google Ads (#31) - High-intent search
- LinkedIn Ads (#28) - B2B targeting
- Engineering as Marketing (#15) - Free tool lead gen

### Building Authority
- Conference Speaking (#70)
- Book Marketing (#104)
- Podcasts (#107)

### Low Budget Growth
- Easy Keyword Ranking (#1)
- Reddit Marketing (#38)
- Comment Marketing (#44)

### Product-Led Growth
- Viral Loops (#93)
- Powered By Marketing (#87)
- In-App Upsells (#91)

### Enterprise Sales
- Investor Marketing (#133)
- Expert Networks (#57)
- Conference Sponsorship (#72)

<!-- BML:START use-cases -->
### Local-service use cases (BML clients)

The lists above lean SaaS (#28, #15, #87, #91, #133 and #57 rarely fit). For BML clients start here, then gate as usual:

- **Need calls or bookings fast:** #31 Google Ads, BML-3 Local Services Ads, BML-10 lead response check
- **Low budget:** BML-2 reviews, BML-1 GBP activity, BML-5 listings, #137 referrals
- **Local authority:** #59 article quotes, #74 local press, #70 local talks, #64 sponsorship
- **Fill slow months:** BML-7 seasonal calendar, #46 reactivation, BML-8 memberships
<!-- BML:END use-cases -->

---

## Output Format

When recommending ideas, provide for each:

- **Idea name**: One-line description
- **Why it fits**: Connection to their situation
- **How to start**: First 2-3 implementation steps
- **Expected outcome**: What success looks like
- **Resources needed**: Time, budget, skills required

<!-- BML:START output -->
### BML client shortlist

The shortlist is an **agency artifact**: Baker house style. Don't load the client's voice or style pages (01, 02). For each Recommended idea, the fields above change like this:

- **Idea name:** with its ID (`#31`, `BML-2`), using the local version from the fit file
- **Why it fits:** cite the rows (B-4, L-3, A-6…). No row, no claim
- **How to start:** the first steps and the BML skill that executes it
- **Expected outcome:** the metric that should move (an A row; calls, bookings, forms or signed jobs per BW-12), never an invented figure or benchmark. Targets only if the client record holds a baseline
- **Resources needed:** BML effort, client time against I-8, and spend against B-10 (`[NEEDS PROOF: B-10]` if unknown; no made-up amounts)
- **Gates:** any gate from the fit file and how it's met

Then, in order: **Client-run ideas**, **Upsell suggestions (internal — for the account lead)**, **Considered and not recommended** (one line each, with the row or gate), **Gaps** (rows that would change the picture). End with the context footer (context-rules §9), `Distinctiveness: n/a for agency artifacts`.

**Where it goes:** in chat by default. If the user asks to file it, save to the client's Drive `OUTPUTS/STRATEGY` folder, resolved by ID from the Context Router; if that folder isn't recorded, ask. Never save to machine-local paths (`~/…`), search Drive or create folders. A ClickUp record (tag `strategy`) only if the user asks for one in this conversation. Before the shortlist goes to a client, strip the footer and the upsell section, and route it to the client's approver (J-1). This skill never sends or publishes.
<!-- BML:END output -->

---

## Task-Specific Questions

1. What's your current stage and main growth goal?
2. What's your marketing budget and team size?
3. What have you already tried that worked or didn't?
4. What competitor tactics do you admire?

<!-- BML:START questions -->
**BML clients:** these are answered by rows (1 → B-4; 2 → B-10, I-8; 3 → I-1, I-2; 4 → E-2, L-6). Ask the user (not the client) only about rows that are `OPEN` and would change the shortlist, and list the rest under Gaps.
<!-- BML:END questions -->

---

## Related Skills

- **marketing-plan**: When the user wants a comprehensive plan instead of standalone ideas. Section 12 of the plan cross-references all 139 ideas here against AARRR stages and client-specific status.
- **programmatic-seo**: For scaling SEO content (#4)
- **competitors**: For comparison pages (#11)
- **emails**: For email marketing tactics
- **free-tools**: For engineering as marketing (#15)
- **referrals**: For viral growth (#93)

<!-- BML:START related -->
- **BML local execution:** `ads` (#31, BML-3), `seo-audit` (BML-1, BML-5), `referrals` and `co-marketing` (BML-2, BML-6), `offers` (BML-7, BML-8), `public-relations` (#74), `ai-seo` (BML-11). Idea numbers 1–139 are shared with `marketing-plan`; never renumber them. BML plays use `BML-<n>` IDs.
<!-- BML:END related -->
