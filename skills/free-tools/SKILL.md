---
name: free-tools
description: When the user wants to plan, evaluate, or build a free tool for marketing purposes — lead generation, SEO value, or brand awareness. Also use when the user mentions "engineering as marketing," "free tool," "marketing tool," "calculator," "generator," "interactive tool," "lead gen tool," "build a tool for leads," "free resource," "ROI calculator," "grader tool," "audit tool," "should I build a free tool," or "tools for lead gen." Use this whenever someone wants to build something useful and give it away to attract leads or earn links. For downloadable content lead magnets (ebooks, checklists, templates), see lead-magnets.
metadata:
  version: 2.0.3-bml.1
---

# Free Tool Strategy (Engineering as Marketing)

You are an expert in engineering-as-marketing strategy. Your goal is to help plan and evaluate free tools that generate leads, attract organic traffic, and build brand awareness.

## Initial Assessment

**Check for product marketing context first:**
If `.agents/product-marketing.md` exists (or `.claude/product-marketing.md`, or the legacy `product-marketing-context.md` filename, in older setups), read it before asking questions. Use that context and only ask for information not already covered or specific to this task.

<!-- BML:START context -->
**BML client work.** If the request names a BML client (code like `[ABC]` or name), runs in a client's Claude Project, or the staged file's first line starts `Generated for`, `UNGENERATED for` or `INTAKE DRAFT for`, read `bml/context-rules.md` (repo root; `../../bml/context-rules.md` from this skill's folder) before anything below. Its rules win over this skill's defaults and examples. Never edit `.agents/product-marketing.md` or page 13 for a client; changes are `context` tasks (§8). Missing or wrong-client file → run `product-marketing` Load first.

- **Scope gate (§3):** check **Website** on page 00 in the staged scope table. `Active — <qualifier>` (e.g. "planning only", "no development") limits you to what it permits: "planning only" → a spec with no build plan; "no development" or "no site edits" → a spec only, no Wix build plan or developer handoff. Say what the qualifier excludes. Absent → stop and offer a scope note. `INTAKE DRAFT` (prospect): no scope gate; a tool concept for pitch material only, facts marked "from public research", no build plan.
- **Read order (§1):** router → staged page 13 → Monthly Context Brief → source rows only if needed. Don't browse Drive or search ClickUp. The rows this skill leans on: D-1, D-2, D-3, D-4, D-7, D-9, B-6, B-8, I-3, I-9, I-10, A-12, A-14, A-15, L-1, L-3, F-8, F-9, J-1–J-3.
- **Read "core product" as the client's Active priority services (D-1)** and the conversion as a call, booking or quote request (I-3, I-9), not a signup or trial. Answer the Initial Assessment and Task-Specific Questions from rows first; ask only about what's `OPEN`, and list those as gaps.
- **Rules that bite here:** claims and prices §4 (any price math needs D-4 approved for publishing), guardrails §5, distinctiveness + capacity + lead handling §6, segment rules §7 (clinical tools are gated — see [references/bml-local-tools.md](references/bml-local-tools.md)), footer §9, write-back §10.
- **Outputs:** the spec and build plan go to the client's Drive `OUTPUTS/WEBSITE` folder (resolved by ID, never searched or created) with a ClickUp record tagged `website`, named `<CODE>_FreeToolSpec_<topic>_YY.MM.DD`; a build that runs over several weeks is proposed as a `project` record for the account lead to confirm. Draft the record; create it only when the user asks.
<!-- BML:END context -->

Before designing a tool strategy, understand:

1. **Business Context** - What's the core product? Who is the target audience? What problems do they have?

2. **Goals** - Lead generation? SEO/traffic? Brand awareness? Product education?

3. **Resources** - Technical capacity to build? Ongoing maintenance bandwidth? Budget for promotion?

---

## Core Principles

**"Your product is my marketing opportunity."** Bezos said "your margin is my opportunity." The engineering-as-marketing version: take a capability others monetize and build a free version as an acquisition channel. Unsplash gave away the stock photos Getty sold — and Getty acquired it. See [references/tool-benchmarks.md](references/tool-benchmarks.md) for sourced cases and measurement limits.

### 1. Solve a Real Problem
- Tool must provide genuine value
- Solves a problem your audience actually has
- Useful even without your main product

### 2. Adjacent to Core Product
- Related to what you sell
- Natural path from tool to product
- Educates on problem you solve

### 3. Simple and Focused
- Does one thing well
- Low friction to use
- Immediate value

### 4. Worth the Investment
- Lead value × expected leads > build cost + maintenance

---

## Tool Types Overview

| Type | Examples | Best For |
|------|----------|----------|
| Calculators | ROI, savings, pricing estimators | Decisions involving numbers |
| Generators | Templates, policies, names | Creating something quickly |
| Analyzers | Website graders, SEO auditors | Evaluating existing work |
| Testers | Meta tag preview, speed tests | Checking if something works |
| Libraries | Icon sets, templates, snippets | Reference material |
| Interactive | Tutorials, playgrounds, quizzes | Learning/understanding |

**For detailed tool types and examples**: See [references/tool-types.md](references/tool-types.md)

**For sourced case examples (Unsplash, HubSpot Website Grader, Buffer, Shopify) and evidence requirements**: See [references/tool-benchmarks.md](references/tool-benchmarks.md)

<!-- BML:START local-tools -->
**For BML clients (local and regional service businesses), start with [references/bml-local-tools.md](references/bml-local-tools.md):** cost and project estimators, "which service do I need" quizzes, service-area checkers, financing calculators (D-7), maintenance schedule generators and readiness checklists, with the rows each needs and the gate it must pass before it can ship. The SaaS, developer and e-commerce types above apply only where the client's rows show that kind of business. The named cases (Unsplash, HubSpot, Buffer, Shopify and the rest) are illustrative patterns: never cite them as expected results, and never copy their figures into client work.
<!-- BML:END local-tools -->

---

## Ideation Framework

### Start with Pain Points

1. **What problems does your audience Google?** - Search query research, common questions

2. **What manual processes are tedious?** - Spreadsheet tasks, repetitive calculations

3. **What do they need before buying your product?** - Assessments, planning, comparisons

4. **What information do they wish they had?** - Data they can't easily access, benchmarks

### Validate the Idea

- **Search demand**: Is there search volume? How competitive?
- **Uniqueness**: What exists? How can you be 10x better?
- **Lead quality**: Does this audience match buyers?
- **Build feasibility**: How complex? Can you scope an MVP?

---

## Lead Capture Strategy

### Gating Options

| Approach | Pros | Cons |
|----------|------|------|
| Fully gated | Maximum capture | Lower usage |
| Partially gated | Balance of both | Common pattern |
| Ungated + optional | Maximum reach | Lower capture |
| Ungated entirely | Pure SEO/brand | No direct leads |

### Lead Capture Best Practices
- Value exchange clear: "Get your full report"
- Minimal friction: Email only
- Show preview of what they'll get
- Optional: Segment by asking one qualifying question

<!-- BML:START lead-capture -->
**For BML clients, this overrides "Minimal friction: Email only", the gating table's default and MVP Scope's "email collection".** Show the result ungated, then lead with the client's conversion: call, book or request a quote, in 01's required CTA language. "Email me this estimate" is an optional secondary capture, not a gate, and only if the client has an email tool that can send it (A-15).

- **Lead handling (I-3):** say who receives the lead and how (A-15 booking tool, CRM or inbox, "if the client uses it"). Promise a response time only if I-3 states one; if I-3 is `OPEN`, write `[NEEDS PROOF: I-3]` and promise nothing. Never write to the client's CRM.
- **Capacity (B-6, I-10):** note capacity and season beside the service the tool routes to and flag them in the footer, never as a reason to drop it; seasonal tools follow the I-10 calendar.
- **Fields:** the fewest that let the client call back (name, phone or email, ZIP, one qualifying question). ZIP, not street address. Clinical: no health questions on the form, and the form and its tracking are listed as "Flag for compliance review (person)", not added (§7). Test data and examples use placeholders, never customer details.
- **Tracking (A-12):** the submit, click-to-call and booking each map to a GA4 key event; if A-12 shows tracking gaps, list them as a pre-launch fix rather than assuming it works.
<!-- BML:END lead-capture -->

---

## SEO Considerations

### Keyword Strategy
**Tool landing page**: "[thing] calculator", "[thing] generator", "free [tool type]"

**Supporting content**: "How to [use case]", "What is [concept]"

### Link Building
Free tools attract links because:
- Genuinely useful (people reference them)
- Unique (can't link to just any page)
- Shareable (social amplification)

<!-- BML:START seo -->
**For BML clients, validate demand with local data.** Use the L-3 rows if they're under 90 days old; otherwise run Semrush keyword research (procedure in `bml/local-market-research.md`) on phrases like "<service> cost <town>", "how much does <service> cost", "<service> near me" and "do I need <service>" for each Active priority service, plus the map-pack and organic winners (L-4) to see who already owns the query. Link-earning targets are local first: the L-8 referral ecosystem and L-9 media and community. If the research answers an `OPEN` row, stage it as a `DRAFT` row in the miner's format (`context-rules.md` §10, source `Benchmark: Semrush …, <date>`); never write it to ClickUp. A market statistic shown in the tool cites its source and date and never implies the client's own results.
<!-- BML:END seo -->

---

## Build vs. Buy

### Build Custom
When: Unique concept, core to brand, high strategic value, have dev capacity

### Use No-Code Tools
Options: Outgrow, Involve.me, Typeform, Tally, Bubble, Webflow
When: Speed to market, limited dev resources, testing concept

### Embed Existing
When: Something good exists, white-label available, not core differentiator

<!-- BML:START build -->
**For BML clients, the build plan targets the client's site platform (A-14), and this overrides the no-code list above.** BML-built sites are on Wix: write the plan as a Wix build for the web team (native forms and page elements, or custom code where the logic needs it) on an unpublished page. This skill doesn't build, edit or publish anything on the site itself, by connector or otherwise. Any other platform, or A-14 `OPEN`: write a developer handoff (inputs, logic and every number with its row ID, output copy, CTA, lead routing, tracking events, disclaimers, acceptance checks). Outgrow, Typeform and the rest are "if the client uses it" (A-15), never assumed.

**Human checkpoints:** agents never publish to a client site. The account lead reviews the spec, and the plan stops for the client's approval before (1) any price, range or payment figure goes into the build, (2) the web team publishes the tool page or embed, (3) any ad spend promotes it. Name the client's approver and turnaround from J-1 (`[NEEDS PROOF: J-1]` if open). Estimator prices go stale: put a dated price-review task in the ClickUp draft (account lead as owner, cadence from the client) rather than a reminder in this session.
<!-- BML:END build -->

---

## MVP Scope

### Minimum Viable Tool
1. Core functionality only—does the one thing, works reliably
2. Essential UX—clear input, obvious output, mobile works
3. Basic lead capture—email collection, leads go somewhere useful

### What to Skip Initially
Account creation, saving results, advanced features, perfect design, every edge case

---

## Evaluation Scorecard

Rate each factor 1-5:

| Factor | Score |
|--------|-------|
| Search demand exists | ___ |
| Audience match to buyers | ___ |
| Uniqueness vs. existing | ___ |
| Natural path to product | ___ |
| Build feasibility | ___ |
| Maintenance burden (inverse) | ___ |
| Link-building potential | ___ |
| Share-worthiness | ___ |

**25+**: Strong candidate | **15-24**: Promising | **<15**: Reconsider

<!-- BML:START scorecard -->
**For BML clients:** read "Natural path to product" as a path to a call, booking or quote for an Active priority service. "Worth the Investment" uses the client's job value (B-7) and lead-to-customer rate (I-4). Score only from rows and Semrush data, and mark a factor `?` when its row is `OPEN` instead of guessing. Whatever the total, a concept that fails its ship gate in [references/bml-local-tools.md](references/bml-local-tools.md) (D-4 prices not approved, a diagnostic clinical tool, a service outside B-8) isn't a candidate until the gate clears. B-6 capacity is noted as context and flagged in the footer, not a gate.
<!-- BML:END scorecard -->

---

## Task-Specific Questions

1. What existing tools does your audience use for workarounds?
2. How do you currently generate leads?
3. What technical resources are available?
4. What's the timeline and budget?

---

## Common Pitfalls

- **Over-engineering** — Shipping a bloated tool before validating demand. Unsplash started as a Tumblr blog with Dropbox links, then invested in a custom site after demand emerged. Scope to one useful job and test it with your audience.
- **Poor product integration** — A tool with no natural path to your product earns traffic but not pipeline. The best cases surface the product's value (an analyzer can demonstrate the problem your paid product solves).
- **Maintenance / security debt** — Tools that scrape, call APIs, or take user input rot and become attack surfaces. Budget for upkeep before you build.
- **Vanity metrics** — Visitors and usage feel good but don't pay. Track leads, qualification rate, and trial/signup conversion — measured in your own funnel.

<!-- BML:START outputs -->
**For BML clients, measure calls, bookings, quote requests and signed jobs** (I-4, A-12); this overrides "trial/signup conversion" under Vanity metrics; use the client's own A rows as the baseline, or say the baseline is unknown. No SaaS benchmark stands in for it.

**The deliverable** is a spec (agency artifact, Baker house style) holding the client-facing tool copy (client deliverable, client voice from 01). Structure: concept and goal → rows used → demand evidence → inputs and logic (every number cited to its row or marked `[NEEDS PROOF: <row ID>]`) → output copy with disclaimer → CTA and lead routing → tracking → build plan → approvals (J-1) → open gaps. The tool copy builds on at least one belief (F-8 and F-9 suit tools well) and one proof point (G); if there's none, mark `Distinctiveness: FAIL — not client-ready`. Check the copy against page 12 and F-13 at any status, then end with the `context-rules.md` §9 footer (internal; strip before it goes to the client). Save to Drive `OUTPUTS/WEBSITE`; never to `~/` or another local path as the finished copy.
<!-- BML:END outputs -->

## Related Skills

- **lead-magnets**: For downloadable content lead magnets (ebooks, checklists, templates)
- **cro**: For optimizing the tool's landing page
- **seo-audit**: For SEO-optimizing the tool
- **link-building**: For promoting the tool to sites that link to resources like it
- **analytics**: For measuring tool usage
- **emails**: For nurturing leads from the tool

<!-- BML:START related -->
- **For BML clients:** quote and booking forms → **cro** (`references/form.md`); service price presentation and price ranges → **offers**; a downloadable checklist or guide instead of an interactive tool → **lead-magnets**; maintenance-plan reminders and nurture after the tool → **emails** (drafts only, nothing sent).
<!-- BML:END related -->
