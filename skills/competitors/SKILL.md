---
name: competitors
description: "When the user wants to create competitor comparison or alternative pages for SEO and buyer-facing use. Also use when the user mentions 'alternative page,' 'vs page,' 'competitor comparison,' 'comparison page,' '[Product] vs [Product],' '[Product] alternative,' 'competitive landing pages,' 'how do we compare to X,' 'compare two options for buyers,' '[option] vs [option] page,' 'how to choose a [service],' 'competitor teardown,' 'audit our competitor pages,' 'are our comparison pages out of date,' or 'competitive asset audit.' Use this for any content that positions your product against competitors. Covers four formats: singular alternative, plural alternatives, you vs competitor, and competitor vs competitor. For auditing existing claims (not researching competitors from scratch, which is competitor-profiling; not technical SEO on these pages, which is seo-audit), use the asset audit here. For internal battle cards and sales-specific competitor docs, see sales-enablement."
metadata:
  version: 2.3.0-bml.1
---

# Competitor & Alternative Pages

You are an expert in creating competitor comparison and alternative pages. Your goal is to build pages that rank for competitive search terms, provide genuine value to evaluators, and position your product effectively.

## Initial Assessment

**Check for product marketing context first:**
If `.agents/product-marketing.md` exists (or `.claude/product-marketing.md`, or the legacy `product-marketing-context.md` filename, in older setups), read it before asking questions. Use that context and only ask for information not already covered or specific to this task.

<!-- BML:START context -->
**Baker Labs (BML) client work:** if the work is for a BML client (a client code like `[ABC]`, a client name, a client's Claude Project, or a staged file whose first line starts `Generated for`, `UNGENERATED for` or `INTAKE DRAFT for`), read `../../bml/context-rules.md` first, then [references/bml-competitors.md](references/bml-competitors.md). Those rules win over this skill's defaults and examples. Never edit `.agents/product-marketing.md` or page 13, and never add Learnings, changelog lines or version bumps to it. Run the BML gates below before drafting; for a BML client, "your product" means the client's service, practice or offer.
<!-- BML:END context -->

**Never guess the competitor.** If the request doesn't name one and the context file doesn't identify it, ask, and stop there. Don't draft a polished page around the most likely candidate.

<!-- BML:START gates -->
**BML gates. Run in order before drafting anything for a client:**

1. **Scope.** Find a Website or SEO line `Active` on page 00 (staged scope summary); either one authorizes this skill. "Planning only" means a page-set plan and no page copy. Absent: stop with "<service> isn't in [CODE]'s retainer" and offer a scope note. An `INTAKE DRAFT` file has no page 00: skip this gate, but the output is internal or pitch material only, never published (context-rules §1).
2. **Format.** Default to an option comparison (`<option A> vs <option B>`) or an unnamed buyer's guide (`how to choose a <service> in <town>`). Named-competitor formats (1–4 below) are gated by segment, and Format 4 is not for BML when the rivals are local businesses. See the format table in the BML reference.
3. **Guardrails.** Before drafting any page (named or not), check every page 12 row and F-13 (**at any status, including DRAFT**), the router's do-not-assert list and H-5. On a hit, stop before drafting: "Blocked by <row ID>: <rule>." If the row blocks naming competitors, offer the unnamed formats.
4. **Client conflict.** Confirm the named competitor is not a current BML client (Client Index, Baker Operations Manual). If it is, stop and escalate to the account lead.
5. **Demand.** Before recommending any page, check search demand for its exact term: reuse L-3, otherwise Semrush keyword research. Named-competitor pages need measurable demand; with none, say so and recommend an option-comparison term instead.
6. **Approval.** Named-competitor pages need the account lead's go-ahead recorded in the ClickUp task before drafting.
7. **Capacity.** Context, never a gate: if B-6 or I-10 marks a service as at capacity or out of season, note it beside the affected pages in the plan and in the footer; never drop or hold back a page for it.

Competitors to name come only from page 13 (E rows, L-4, L-6) or the request. If neither names one, ask and stop.
<!-- BML:END gates -->

Before creating competitor pages, understand:

1. **Your Product**
   - Core value proposition
   - Key differentiators
   - Ideal customer profile
   - Pricing model
   - Strengths and honest weaknesses

2. **Competitive Landscape**
   - Direct competitors
   - Indirect/adjacent competitors
   - Market positioning of each
   - Search volume for competitor terms

3. **Goals**
   - SEO traffic capture
   - Sales enablement
   - Conversion from competitor users
   - Brand positioning

---

## Core Principles

### 1. Honesty Builds Trust
- Acknowledge competitor strengths
- Be accurate about your limitations
- Don't misrepresent competitor features
- Readers are comparing—they'll verify claims

### 2. Depth Over Surface
- Go beyond feature checklists
- Explain *why* differences matter
- Include use cases and scenarios
- Show, don't just tell

### 3. Help Them Decide
- Different tools fit different needs
- Be clear about who you're best for
- Be clear about who competitor is best for
- Reduce evaluation friction

### 4. Modular Content Architecture
- Competitor data should be centralized
- Updates propagate to all pages
- Single source of truth per competitor

### 5. Evidence Discipline
Comparison pages are public claims about another company. Every one should survive the competitor's own team reading it.
- **"Not observed" is not "doesn't have."** A pricing page that doesn't list SSO is evidence about the page, not the product. Write "not listed on their pricing page (as of Mar 2026)" or drop the row. Use ✗ or "not available" only when their docs or a hands-on trial confirm the absence.
- **Date competitor facts.** Pricing and features change. Put an "as of" date on pricing tables and in the competitor data file, and re-verify before republishing.
- **One look is a snapshot.** A single visit can't support "they haven't changed pricing in years" or "no new features since 2024." That needs dated history (changelog, archived pages).
- **State what changed, not why.** "They moved SSO to the Enterprise tier" is a fact. "Because they're squeezing upmarket" is a guess. Leave motive out unless they've said it publicly.
- **Separate fact from interpretation.** Keep what their site says apart from what you think it means for the buyer, and keep both apart from what you recommend.

---

## Page Formats

### Format 1: [Competitor] Alternative (Singular)

**Search intent**: User is actively looking to switch from a specific competitor

**URL pattern**: `/alternatives/[competitor]` or `/[competitor]-alternative`

**Target keywords**: "[Competitor] alternative", "alternative to [Competitor]", "switch from [Competitor]"

**Page structure**:
1. Why people look for alternatives (validate their pain)
2. Summary: You as the alternative (quick positioning)
3. Detailed comparison (features, service, pricing)
4. Who should switch (and who shouldn't)
5. Migration path
6. Social proof from switchers
7. CTA

---

### Format 2: [Competitor] Alternatives (Plural)

**Search intent**: User is researching options, earlier in journey

**URL pattern**: `/alternatives/[competitor]-alternatives`

**Target keywords**: "[Competitor] alternatives", "best [Competitor] alternatives", "tools like [Competitor]"

**Page structure**:
1. Why people look for alternatives (common pain points)
2. What to look for in an alternative (criteria framework)
3. List of alternatives (you first, but include real options)
4. Comparison table (summary)
5. Detailed breakdown of each alternative
6. Recommendation by use case
7. CTA

**Important**: Include 4-7 real alternatives. Being genuinely helpful builds trust and ranks better.

**AI-answer expectations by stage**: these pages often earn *citations* in AI answers, but whether AI *recommends* your brand from them depends on offsite consensus (reviews, forums, analysts) — for emerging brands, a self-ranked list can surface the competitors in the AI answer while you get only the citation. Still publish for search intent and category framing, but set expectations accordingly — see ai-seo's citations-vs-recommendations reference for the data.

---

### Format 3: You vs [Competitor]

**Search intent**: User is directly comparing you to a specific competitor

**URL pattern**: `/vs/[competitor]` or `/compare/[you]-vs-[competitor]`

**Target keywords**: "[You] vs [Competitor]", "[Competitor] vs [You]"

**Page structure**:
1. TL;DR summary (key differences in 2-3 sentences)
2. At-a-glance comparison table
3. Detailed comparison by category (Features, Pricing, Support, Ease of use, Integrations)
4. Who [You] is best for
5. Who [Competitor] is best for (be honest)
6. What customers say (testimonials from switchers)
7. Migration support
8. CTA

---

### Format 4: [Competitor A] vs [Competitor B]

**Search intent**: User comparing two competitors (not you directly)

**URL pattern**: `/compare/[competitor-a]-vs-[competitor-b]`

**Page structure**:
1. Overview of both products
2. Comparison by category
3. Who each is best for
4. The third option (introduce yourself)
5. Comparison table (all three)
6. CTA

**Why this works**: Captures search traffic for competitor terms, positions you as knowledgeable.

---

## Essential Sections

### TL;DR Summary
Start every page with a quick summary for scanners—key differences in 2-3 sentences.

### Paragraph Comparisons
Go beyond tables. For each dimension, write a paragraph explaining the differences and when each matters.

### Feature Comparison
For each category: describe how each handles it, list strengths and limitations, give bottom line recommendation.

### Pricing Comparison
Include tier-by-tier comparison, what's included, hidden costs, and total cost calculation for sample team size.

### Who It's For
Be explicit about ideal customer for each option. Honest recommendations build trust.

### Migration Section
Cover what transfers, what needs reconfiguration, support offered, and quotes from customers who switched.

**For detailed templates**: See [references/templates.md](references/templates.md)

---

## Content Architecture

### Centralized Competitor Data
Create a single source of truth for each competitor with:
- Positioning and target audience
- Pricing (all tiers)
- Feature ratings
- Strengths and weaknesses
- Best for / not ideal for
- Common complaints (from reviews)
- Migration notes

**For data structure and examples**: See [references/content-architecture.md](references/content-architecture.md)

---

## Research Process

### Deep Competitor Research

For each competitor, gather:

1. **Product research**: Sign up, use it, document features/UX/limitations
2. **Pricing research**: Current pricing, what's included, hidden costs
3. **Review mining**: G2, Capterra, TrustRadius for common praise/complaint themes
4. **Customer feedback**: Talk to customers who switched (both directions)
5. **Content research**: Their positioning, their comparison pages, their changelog

<!-- BML:START research-sources -->
**For BML clients, research comes from these sources, in this order:** page 13 L rows (L-4 who wins, L-5 review themes, L-6 offers and claims, L-11 category platforms) and E rows → a competitor-profiling profile only if the task, brief or user links one and it is ≤90 days old (never browse Drive or the repo for one) → the competitor's own public pages, each fact dated. Semrush is the only SEO data tool. Never sign up for, call or pose as a customer of a competitor. Review input is themes only (no quotes, no reviewer names); G2, Capterra and TrustRadius don't apply to local businesses. Switcher input comes only from page 11 rows, verbatim. Findings that answer an OPEN row are staged as DRAFT rows (context-rules §10) and never written to ClickUp.
<!-- BML:END research-sources -->

### Ongoing Updates

- **Quarterly**: Verify pricing, check for major feature changes
- **When notified**: Customer mentions competitor change
- **Annually**: Full refresh of all competitor data

<!-- BML:START ongoing-updates -->
For BML clients, re-verification runs as a scheduled task (see marketing-loops; the quarterly market refresh already updates L-3, L-4, L-5 and L-7, but not L-6), never as an in-session loop. Propose the task; it is created only after the user approves. A page whose competitor facts are older than 90 days goes into the next asset audit.
<!-- BML:END ongoing-updates -->

### Competitive Asset Audit

When asked to check existing competitive content for stale or risky claims, audit every asset that makes claims about competitors: vs and alternative pages, battle cards, talk tracks, objection docs, and comparison tables in decks.

1. **List each claim** about a competitor, with the asset and line it lives in.
2. **Re-verify each claim** against the competitor's current site, docs, or changelog, and note the date you checked. If you can't browse, mark claims unchecked and list what to verify. Never mark one Current without a check date.
3. **Mark each one**:
   - **Current**: still true, source and date updated
   - **Changed**: now wrong, with what it says now
   - **Unverifiable**: had a source once, but nothing current confirms or rules it out. Soften to "not listed (as of date)" or remove
   - **Overclaimed**: stated as fact with no source behind it (an unconfirmed ✗, a guessed motive, a "why we win" with no evidence). Rewrite to what the evidence supports or remove
4. **Prioritize fixes**: public pages first (buyers and competitors read them), then anything reps say on calls, then internal docs.
5. **Report**: assets audited, claims checked, counts by status, and a fix list with the replacement wording.

Apply the Evidence Discipline rules above to every claim, including those in internal sales assets. Where several assets repeat one fact, fix it in the centralized competitor data so the fix carries through.

<!-- BML:START asset-audit -->
**BML asset audit.** The report is an agency artifact: Baker house style, no client voice or style pages (01/02). It also checks the client's own comparative claims ("best", "only", "#1", outcome promises) against rows, page 12 and the segment rules. Battle cards and talk tracks rarely exist for local clients; audit what does. Read-only: never edit the client's site. Save to the client's Drive OUTPUTS/SEO and end with the context footer.
<!-- BML:END asset-audit -->

---

## SEO Considerations

### Keyword Targeting

| Format | Primary Keywords |
|--------|-----------------|
| Alternative (singular) | [Competitor] alternative, alternative to [Competitor] |
| Alternatives (plural) | [Competitor] alternatives, best [Competitor] alternatives |
| You vs Competitor | [You] vs [Competitor], [Competitor] vs [You] |
| Competitor vs Competitor | [A] vs [B], [B] vs [A] |

### Internal Linking
- Link between related competitor pages
- Link from feature pages to relevant comparisons
- Create hub page linking to all competitor content

### Schema Markup
Consider FAQ schema for common questions like "What is the best alternative to [Competitor]?"

---

## Output Format

### Competitor Data File
Complete competitor profile in YAML format for use across all comparison pages.

### Page Content
For each page: URL, meta tags, full page copy organized by section, comparison tables, CTAs.

### Page Set Plan
Recommended pages to create with priority order based on search volume.

### Asset Audit Report
Claims checked per asset, status counts (current / changed / unverifiable / overclaimed), and a prioritized fix list with replacement wording.

<!-- BML:START output -->
**BML outputs.**
- **Style:** page copy is a client deliverable that uses the 01 voice and 02 style, builds on ≥1 F belief and ≥1 G proof point (otherwise the footer says `Distinctiveness: FAIL — not client-ready`), and uses 01's CTA language (call, booking or form) within I-3 response times. The page-set plan, data files and audit are agency artifacts in Baker house style.
- **Claims:** client facts only from page 13 or cited rows, otherwise `[NEEDS PROOF: <row ID>]`. Clinical and professional-services pages follow the claims rules in the BML reference (no outcome or superiority comparisons).
- **Where:** page copy to OUTPUTS/WEBSITE. Data files, page-set plan and audit to OUTPUTS/SEO. Resolve folders by ID, never create one; if none fits, stop and report. Draft the ClickUp record (`website` / `seo`) and create it only after the user approves.
- **Approval:** never publish to the client's site. Stop for a human, name the client approver (J-1), and flag any page that names a competitor for legal review.
- **Footer:** end every output with the context-rules §9 footer.
<!-- BML:END output -->

---

## Task-Specific Questions

1. What are common reasons people switch to you?
2. Do you have customer quotes about switching?
3. What's your pricing vs. competitors?
4. Do you offer migration support?

<!-- BML:START questions -->
For BML clients, answer these from page 13 first: switch reasons (G, E rows), quotes (page 11, verbatim), pricing (D-4 publish approval) and switching support (08). Ask only for true gaps, and mark the rest `[NEEDS PROOF: <row ID>]`.
<!-- BML:END questions -->

---

## Related Skills

- **programmatic-seo**: For building competitor pages at scale
- **copywriting**: For writing compelling comparison copy
- **seo-audit**: For optimizing competitor pages
- **schema**: For FAQ and comparison schema
- **sales-enablement**: For battle cards and internal sales collateral, decks, and objection docs
