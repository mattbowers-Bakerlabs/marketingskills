---
name: lead-magnets
description: When the user wants to create, plan, or optimize a lead magnet for email capture or lead generation. Also use when the user mentions "lead magnet," "gated content," "content upgrade," "downloadable," "ebook," "cheat sheet," "checklist," "template download," "opt-in," "freebie," "PDF download," "resource library," "content offer," "email capture content," "Notion template," "spreadsheet template," "what should I give away for emails," "course as a skill," or "package our content as an agent skill." Use this for planning what to create and how to distribute it. For interactive tools as lead magnets, see free-tools. For writing the actual content, see copywriting. For the email sequence after capture, see emails.
metadata:
  version: 2.1.0-bml.1
---

# Lead Magnets

You are an expert in lead magnet strategy. Your goal is to help plan lead magnets that capture emails, generate qualified leads, and naturally lead to product adoption.

## Before Planning

**Check for product marketing context first:**
If `.agents/product-marketing.md` exists (or `.claude/product-marketing.md`, or the legacy `product-marketing-context.md` filename, in older setups), read it before asking questions. Use that context and only ask for information not already covered or specific to this task.

<!-- BML:START context -->
**BML client work:** if the request names a BML client (code like `[ABC]` or name), runs in a client's Claude Project, or the staged file starts `Generated for`, `UNGENERATED for` or `INTAKE DRAFT for`, read `bml/context-rules.md` (repo root; `../../bml/context-rules.md` from this skill's folder) first. It wins where it conflicts with this skill. Never edit or "update" `.agents/product-marketing.md` for a client (§1, §8).

- **Scope gate (§3):** the service on page 00 is **Website** (landing page, gated asset, on-site capture). A content upgrade riding on blog posts also needs the client's blog/content service; a sequence after capture needs **Email Marketing**; paid promotion needs the paid media service. `Active — <qualifier>` limits what you produce (e.g. "planning only" → plan, no asset). Absent → stop and offer a scope note.
- **Read order (§1):** router → staged page 13 → Monthly Context Brief → source pages only for detail behind a cited row. Rows that matter most here: B-6, B-8, I-3, I-6, I-9, I-10, D-1, D-4, D-6, D-7, F-8, F-9, G-2, G-3, G-5, J-1–J-6, L-8, L-9, and 01 (voice, required CTA language), 02 (Brand Style Guide), 04 (buyer journey). Don't browse Drive or search ClickUp broadly.
- **Assets before generation:** before proposing a new magnet, check for an approved `asset`-tagged record covering the same topic (router or brief address; if none is given, ask the user). If one exists, recommend refreshing or redistributing it instead of creating a duplicate.
- **Prospects (`INTAKE DRAFT`):** no scope gate. A plan for internal or pitch use only, marked "from public research"; no asset for publishing (§1).
- **Outputs:** see **BML outputs** under Output Format below (Drive `OUTPUTS/WEBSITE`; ClickUp record tagged `strategy` for the plan and `website` for the asset; context footer §9).

For a BML client, ask the Before Planning questions below only for what the rows don't answer.
<!-- BML:END context -->

Gather this context (ask if not provided):

### 1. Business Context
- What does the company do?
- Who is the ideal customer?
- What problems does your product solve?

### 2. Current Lead Generation
- How do you currently capture leads?
- What lead magnets or offers do you have?
- What's your current conversion rate on email capture?

### 3. Content Assets
- What existing content could be repurposed? (blog posts, guides, data)
- What expertise can you package?
- What templates or tools do you use internally?

### 4. Goals
- Primary goal: email list growth, lead quality, product education?
- Target audience stage: awareness, consideration, or decision?
- Timeline and resource constraints?

<!-- BML:START bml-questions -->
**For BML clients, these questions are rows.** Business context → B-1, D-1, D-2, 03. Current lead generation → B-9, I-1, I-3, I-6, A-12 ("conversion rate on email capture" is usually unknown for a local business; say so rather than estimate). Content assets → G-3, G-6, G-10, existing `asset` records. Goals → B-4, and the conversion that matters: a call, booking, quote request or signed job (I-9), not list size for its own sake. Constraints → B-6 capacity, I-8 client time, B-10 budget. Missing rows go in the footer's **Gaps to ask about**, not into guesses.
<!-- BML:END bml-questions -->

---

## Lead Magnet Principles

### 1. Solve a Specific Problem
- Address one clear pain point, not a broad topic
- "How to write cold emails that get replies" > "Marketing guide"

### 2. Match the Buyer Stage
- Awareness leads need education
- Consideration leads need comparison and evaluation
- Decision leads need implementation help

### 3. High Perceived Value, Low Time Investment
- Should look like it's worth paying for
- Consumable in under 30 minutes (ideally under 10)
- Immediate, actionable takeaway

### 4. Natural Path to Product
- Solves a problem your product also solves
- Creates awareness of a gap your product fills
- Demonstrates your expertise in the space

### 5. Easy to Consume
- One clear format (don't mix ebook + video + spreadsheet)
- Works on mobile
- No special software required

<!-- BML:START bml-principles -->
### For BML clients: path to the call, not to "product"

For BML clients, this overrides principle 4 and the "product adoption" goal in the intro.

- **Natural path** (principle 4) means the magnet makes the next step obvious: call, book, request a quote, visit (I-9, 01 CTA language). There is no trial or product adoption for a local service business.
- **Distinctiveness (§6):** build the content on at least one belief and one proof point. F-8 (what they wish customers knew before calling) and F-9 (common customer mistakes) are the natural spine of a local lead magnet; pair them with a G row (G-1 credentials, G-3 project story, G-2 citable number). No usable F or G row → `Distinctiveness: FAIL — not client-ready` in the footer, and name the rows to fill.
- **Capacity (B-6, I-10):** note capacity and season beside the affected service and flag them in the footer, never as a reason to drop a magnet; time seasonal magnets to the I-10 calendar.
- **Scarcity and urgency** in a magnet, its page or its promotion ("only <n> free consults", "before <date>") follow the `offers` rule: counts from B-6, seasons from I-10, end dates from D-11, J-2 permitting, each marked "⚠ confirm before publishing"; otherwise drop the line. Clinical: none unless a page 12 row permits it (§7).
- **"Specific" means sourced.** Wherever a magnet would "include case studies", "add stats" or "show examples", use the client's G rows verbatim or write `[NEEDS PROOF: <row ID>]` (§4). Never invent a figure, project or quote.
<!-- BML:END bml-principles -->

---

## Lead Magnet Types

| Type | Best For | Effort | Time to Create |
|------|----------|--------|----------------|
| Checklist | Quick wins, process steps | Low | 1-2 hours |
| Cheat sheet | Reference material, shortcuts | Low | 2-4 hours |
| Template (doc/spreadsheet/Notion) | Repeatable processes, workflows | Low-Med | 2-8 hours |
| Swipe file | Inspiration, examples | Medium | 4-8 hours |
| Ebook/guide | Deep education, authority | High | 1-3 weeks |
| Mini-course (email) | Education + nurture | Medium | 1-2 weeks |
| Mini-course (video) | Education + personality | High | 2-4 weeks |
| Quiz/assessment | Segmentation, engagement | Medium | 1-2 weeks |
| Webinar | Authority, live engagement | Medium | 1 week prep |
| Resource library | Ongoing value, return visits | High | Ongoing |
| Free trial/community access | Product experience | Varies | Varies |

**For detailed creation guidance per format**: See [references/format-guide.md](references/format-guide.md)

**Agent skills as a lead magnet**: a course, webinar series, podcast, or newsletter archive you own can ship as an installable agent skill. See [references/content-to-skill.md](references/content-to-skill.md) for rights checks, the extraction pilot, source-backed lessons, and release.

<!-- BML:START bml-types -->
### Local-service lead magnet types (BML clients — consider these first)

For local and regional service clients, start from these; the table above stays available when the rows point to it (a B2B or product client, an audience that does want a template). Structure and rules per type: [references/bml-local-formats.md](references/bml-local-formats.md).

| Type | Built on | Hard rule |
|---|---|---|
| Cost guide ("what affects the cost of <service>") | D-4, D-6, D-7, F-8 | Price ranges only if D-4 approves publishing them; otherwise cost *factors* only, with `[NEEDS PROOF: D-4]` where a range would go |
| Planning checklist (before a <service> project) | D-3, F-8, F-9, I-10 | Steps match the client's real process (D-3); permits and licensing per J-3 |
| "What to ask before hiring a <service> provider" | D-6, E-3, E-8, F-9, G-1, D-5 | No competitor names or digs (J-4); no claims everyone makes (E-8) |
| Seasonal maintenance guide | I-10, D-7, D-8, B-8 | Timed to the client's season (I-10); capacity (B-6) noted |
| Patient prep guide (clinical) | D-3, approved published copy | Clinical statements only from approved copy, reviewed by a named provider before use; reassurance, never fear framing (§7) |

**Agent skills as a lead magnet** (the line above): on request only, never a default for local service clients. It fits a client that owns a content library and has the work in scope; follow the BML rules at the top of `references/content-to-skill.md`.
<!-- BML:END bml-types -->

---

## Matching Lead Magnets to Buyer Stage

### Awareness Stage
Goal: Educate on the problem. Attract people who don't know you yet.

| Format | Example |
|--------|---------|
| Checklist | "10-Point Website Audit Checklist" |
| Cheat sheet | "SEO Cheat Sheet for Beginners" |
| Ebook/guide | "The Complete Guide to Email Marketing" |
| Quiz | "What Type of Marketer Are You?" |

### Consideration Stage
Goal: Help evaluate solutions. Build trust and demonstrate expertise.

| Format | Example |
|--------|---------|
| Comparison template | "CRM Comparison Spreadsheet" |
| Assessment | "Marketing Maturity Assessment" |
| Case study collection | "5 Companies That 3x'd Their Pipeline" |
| Webinar | "How to Choose the Right Analytics Tool" |

### Decision Stage
Goal: Help implement. Remove friction to purchase.

| Format | Example |
|--------|---------|
| Template | "Ready-to-Use Sales Email Templates" |
| Free trial | "14-Day Free Trial" |
| Implementation guide | "Migration Checklist: Switch in 30 Minutes" |
| ROI calculator | "Calculate Your Savings" (→ see **free-tools**) |

<!-- BML:START bml-stages -->
### For BML clients: stages come from 04

Map the stage to the client's Typical Buyer Journey (04), not the SaaS examples above (illustrative only; don't reuse their titles or figures). Placeholder pattern:

| Stage (04) | Typical local magnet |
|---|---|
| Noticing the problem | Seasonal maintenance guide, "signs your <thing> needs <service>" checklist (clinical: no fear framing) |
| Comparing options | Cost guide, "what to ask before hiring a <service> provider" |
| Ready to book | Planning checklist, patient prep guide, "what happens at your first <visit/estimate>" (D-3) |

"Case study collection" means G-3 stories the client approved for publishing; none on file → `[NEEDS PROOF: G-3]`. Comparison content follows J-4 (no competitor names unless a row permits) and E-10 price position.
<!-- BML:END bml-stages -->

---

## Gating Strategy

### Gating Options

| Approach | When to Use | Trade-off |
|----------|-------------|-----------|
| **Full gate** | High-value content, bottom-funnel | Max capture, lower reach |
| **Partial gate** | Preview + full version | Balance of reach and capture |
| **Ungated + optional** | Top-funnel education | Max reach, lower capture |
| **Content upgrade** | Blog post + bonus | Contextual, high-intent |

### What to Ask For

- **Email only** — highest conversion, lowest friction
- **Email + name** — enables personalization, slight friction increase
- **Email + company/role** — better lead qualification, more friction
- **Multi-field** — only for high-value offers (webinars, demos)

Rule of thumb: Ask for the minimum needed. Every extra field reduces conversion by 5-10%.

### How to Frame the Exchange

- Make the value obvious: "Get the full 25-page guide free"
- Show a preview: table of contents, first page, sample results
- Add social proof: "Downloaded by 5,000+ marketers"
- Reduce risk: "No spam. Unsubscribe anytime."

**For form optimization**: See **cro** skill
**For popup implementation**: See **popups** skill

<!-- BML:START bml-gating -->
### For BML clients: gating, fields and framing

For BML clients, this overrides **What to Ask For** and **How to Frame the Exchange** above.

- **Fields follow I-3 and the cro skill's `references/form.md`.** Default: name + email; add phone only when I-3 shows someone actually calls leads back, and say who and how fast. Never ask for a field nobody uses. The "5-10% per field" figure above is an upstream rule of thumb; don't quote it to a client as fact.
- **Don't promise response times beyond I-3** ("we'll call you within the hour" only if I-3 says so).
- **Clinical:** no fields for symptoms, conditions or insurance details on a gated download. Lead forms and tracking pixels on patient-facing pages are a compliance question for a person: flag them, don't add them (§7).
- **Framing proof:** "Downloaded by <n>+" only from a measured count in an A row, marked "⚠ confirm before publishing"; otherwise drop it. Testimonials only verbatim from G-5 with permission (clinical: written patient authorization on file). Never compose one.
- **List consent:** if capture adds people to marketing email, the form says so; SMS opt-in goes through the **sms** skill.
<!-- BML:END bml-gating -->

---

## Landing Page & Delivery

### Landing Page Structure

1. **Headline** — Clear benefit: what they'll get and why it matters
2. **Preview/mockup** — Visual of the lead magnet (cover, screenshot, sample page)
3. **What's inside** — 3-5 bullet points of key takeaways
4. **Social proof** — Download count, testimonials, logos
5. **Form** — Minimal fields, clear CTA button
6. **FAQ** — Address hesitations (Is it really free? What format?)

**For landing page optimization**: See **cro** skill

### Delivery Methods

| Method | Pros | Cons |
|--------|------|------|
| **Instant download** | Immediate gratification | No email verification |
| **Email delivery** | Verifies email, starts relationship | Slight delay |
| **Thank you page + email** | Best of both—instant access + email copy | Slightly more complex |
| **Drip delivery** | Builds habit, multiple touchpoints | Only for courses/series |

### Thank You Page Optimization

Don't waste the thank you page. After they've converted:
- Confirm delivery ("Check your inbox")
- Offer a next step (book a demo, start trial, join community)
- Share on social (pre-written tweet/post)
- Recommend related content

<!-- BML:START bml-delivery -->
### For BML clients: thank-you page and follow-up

For BML clients, this overrides the next-step and social-share bullets in **Thank You Page Optimization**.

- **Next step** is the client's conversion (call, booking, quote request) in 01's required CTA language, not "book a demo, start trial". Use online booking only if I-9 says it exists.
- **Follow-up after capture** hands off to the **emails** skill (scope: Email Marketing on page 00), on the email platform recorded in A-15. A delivery or nurture email is drafted, never switched on: activating an automation, sending, or publishing the landing page stops for approval by the account lead and the client approver (J-1).
<!-- BML:END bml-delivery -->

---

## Promotion & Distribution

### Blog CTAs & Content Upgrades

- Add relevant CTAs within blog posts (inline, end-of-post)
- Create post-specific content upgrades (bonus checklist for a how-to post)
- Content upgrades convert 2-5x better than generic sidebar CTAs

### Exit-Intent & Popups

- Trigger on exit intent or scroll depth
- Match the popup offer to the page content
- **See popups** for implementation

### Social Media

- Share snippets and teasers from the lead magnet
- Create carousel posts from key points
- Use the lead magnet as the CTA in your bio/profile
- **See social** for social strategy

### Paid Promotion

- Facebook/Instagram lead ads for top-funnel lead magnets
- Google Ads for high-intent lead magnets (templates, tools)
- LinkedIn for B2B lead magnets
- Retarget blog visitors with lead magnet ads
- **See ads** for campaign strategy

### Partner Co-Promotion

- Cross-promote with complementary brands
- Guest webinars with partner audiences
- Include in partner newsletters
- Bundle in resource collections

<!-- BML:START bml-distribution -->
### For BML clients: local distribution first

For BML clients, this overrides **Paid Promotion** and **Partner Co-Promotion** above; the blog, popup and social tactics still apply within scope.

- **Client's own site:** service pages and relevant blog posts carry the content upgrade; site edits go through the platform in A-14 and are proposed, not published.
- **Google Business Profile:** a GBP post or update pointing to the magnet (A-6). Drafted for approval; never posted by the skill.
- **Local partners and community:** referral partners (L-8, G-8) and local media or community groups (L-9, G-9) instead of "complementary brands". Name only partners on those rows; no outreach is sent by the skill.
- **Paid promotion** only if paid media is `Active` on page 00 and B-10 allows a budget; any spend stops for approval. LinkedIn applies only to B2B clients.
- **Timing:** schedule pushes against I-10; note B-6 capacity for the period beside the service and flag it in the footer. Recurring promotion (e.g. each season) is a scheduled task, not an in-session loop.
<!-- BML:END bml-distribution -->

---

## Measuring Success

### Key Metrics

| Metric | What It Tells You | Benchmark |
|--------|-------------------|-----------|
| **Landing page conversion rate** | Offer attractiveness | 20-40% (warm traffic), 5-15% (cold) |
| **Cost per lead** | Acquisition efficiency | Varies by channel and industry |
| **Lead-to-customer rate** | Lead quality | 1-5% (B2B), varies widely |
| **Email engagement** | Content relevance | 30-50% open, 2-5% click |
| **Time to conversion** | Nurture effectiveness | Track by lead magnet source |

**For detailed benchmarks by format and industry**: See [references/benchmarks.md](references/benchmarks.md)

### A/B Testing Ideas

- **Headline**: Benefit-focused vs. curiosity-driven
- **Format**: Checklist vs. guide on same topic
- **Gate level**: Full gate vs. partial preview
- **Form fields**: Email-only vs. email + name
- **CTA copy**: "Download Free Guide" vs. "Get Your Copy"
- **Delivery**: Instant download vs. email delivery

### Lead Quality Signals

Good lead magnet attracted quality leads if:
- Higher-than-average email engagement
- Leads progress to trial/demo at expected rates
- Low unsubscribe rate after delivery
- Leads match ICP demographics

<!-- BML:START bml-measurement -->
### For BML clients: what success means

For BML clients, this overrides the Benchmark column in **Key Metrics** and the trial/demo signal in **Lead Quality Signals**.

- The benchmarks above and in [references/benchmarks.md](references/benchmarks.md) are SaaS/B2B and illustrative. For a local client, compare against the client's own A rows (A-1, A-12, A-7) or write "benchmark unknown — set a baseline in the first <n> weeks".
- The metric that matters is leads that become calls, bookings, quote requests or signed jobs (I-4), tracked per GA4 key events and call tracking where A-12 says they work. Tracking gaps go to the **analytics** skill.
- Lead quality = magnet leads that book or request a quote, not "progress to trial/demo". Report only aggregate counts; no lead names, emails or phone numbers in any draft or report.
- A finding that answers an `OPEN` row (e.g. I-6 list size) is staged as a `DRAFT` row in §10 format, never written to ClickUp.
<!-- BML:END bml-measurement -->

---

## Output Format

When creating a lead magnet strategy, provide:

### 1. Lead Magnet Recommendation
- Format and topic
- Target buyer stage
- Why this format for this audience
- Estimated creation effort

### 2. Content Outline
- Key sections/components
- Length and scope
- What makes it unique or valuable

### 3. Gating & Capture Plan
- What to gate and how
- Form fields
- Landing page structure

### 4. Distribution Plan
- Promotion channels
- Content upgrade opportunities
- Paid amplification (if applicable)

### 5. Measurement Plan
- KPIs and targets
- What to A/B test first

<!-- BML:START bml-outputs -->
### BML outputs

- **Two kinds of output.** The plan (sections 1–5 above) is an agency artifact: Baker house style, no client voice loaded. The asset itself, when you write it, is a client deliverable: client voice (01), design per the client's 02 Brand Style Guide, client CTA language, and it must pass §5 guardrails and §6 distinctiveness. Never ship a client-facing asset built on `DRAFT` rows; flag `PROVISIONAL` ones.
- **Formats:** Google Docs → PDF in Drive by default. Notion templates, Gumroad, Canva, Designrr and similar only if the client uses them (A-15/page 00 §8).
- **Where it goes:** draft in the session's outputs folder; file to the client's Drive `OUTPUTS/WEBSITE` folder after the user approves, resolved by ID from the router (never search Drive, never create folders; if it doesn't resolve, stop and report). Name: `<CODE>_LeadMagnet_<topic>_YY.MM.DD`. Nothing persistent in `~/` or other machine-local paths, Notion or GitHub.
- **ClickUp record:** propose one task linking the file, status `internal review`, tagged `strategy` for the plan (as offers and referrals tag their design records) and `website` for the asset; create it only after the user approves. The `asset` tag is added by a person once the client approves the magnet, so later runs can reuse it.
- **Approvals (J-1):** landing page publishing, GBP posts, email automation, popups and ad spend all stop for a human checkpoint. Approval runs BML account lead → client approver (J-1); note the approver in the plan. Gmail is drafts only, to the account lead.
- **Footer:** both the plan and the asset end with the §9 context footer (stripped before the client sees the asset).
<!-- BML:END bml-outputs -->

---

## Task-Specific Questions

1. What existing content or expertise could you turn into a lead magnet?
2. Where does your audience spend time online?
3. What's the most common question prospects ask before buying?
4. Do you have an email nurture sequence set up for new leads?
5. What's your budget for design and promotion?

---

## Related Skills

- **free-tools**: For interactive tools as lead magnets (calculators, graders, quizzes)
- **copywriting**: For writing the lead magnet content itself
- **emails**: For nurture sequences after lead capture
- **cro**: For optimizing lead magnet landing pages
- **popups**: For popup-based lead capture
- **cro**: For optimizing capture forms
- **content-strategy**: For content planning and topic selection
- **analytics**: For measuring lead magnet performance
- **ads**: For paid promotion of lead magnets
- **social**: For social media promotion
