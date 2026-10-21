> BML addition: this whole file is Baker Labs (BML) text, not upstream. It is kept out of upstream merges.

# Content strategy for Baker Labs (BML) clients

Applies when the work is for a BML client: a client code like `[ABC]`, a client name, a client's Claude Project, or a staged `.agents/product-marketing.md` whose first line starts `Generated for`, `UNGENERATED for` or `INTAKE DRAFT for`. `../../../bml/context-rules.md` (cited as §n) wins over this file and over the skill's defaults and examples.

Never edit `.agents/product-marketing.md` or page 13, and never add Learnings, changelog lines or version bumps to it. One client per run: nothing from another client's rows, examples or files.

## 1. What this skill produces for BML

A topic plan: pillars, clusters, priority topics and an editorial calendar. It decides what gets written; it doesn't write it.
- Writing a piece → **copywriting**. Refreshing existing posts → **copy-editing**.
- Technical or ranking-drop diagnosis → **seo-audit**. AI-citation work → **ai-seo**.
- Service and location page gaps → name them with their L-1/L-3 evidence and hand off: hierarchy and URLs to **site-architecture**, many near-identical pages to **programmatic-seo**. Don't spec the page here.
- Links and citations → **link-building**.

## 2. Scope and scope note (§3)

Planning is in scope for every retained client: this skill never stops on scope. Page 00's **Blog content** line authorizes content-strategy; the **SEO** line adds the keyword/cluster side. Read both lines (scope summary at the top of the staged file) and plan for what's retained:

| Page 00 says | Do |
|---|---|
| Blog content and/or SEO `Active` | Full plan for the retained side (blog topics, SEO keyword/cluster plan, or both) |
| `Active — planning only` | Full plan. No drafts, no per-piece production tasks. State: "Planning only: drafting and production are outside the retainer." |
| `Active — <n> posts/month` | Calendar capped at n per month |
| `Active — local SEO only` | Topics limited to service and service-area intent |
| `Active — <other qualifier>` | Produce only what it permits. Name what it excludes |
| Neither line Active (absent, paused, anything else) | Still produce the plan. The scope note below says no content or SEO service is retained |

**Scope note (every plan, near the top):** "Covers: <retained services from page 00>. Producing anything in this plan outside the retainer (e.g. <writing posts / SEO pages / video>) needs a scope change: raise it with the account lead." Formats (video, podcast, email) and production the retainer doesn't cover stay in the plan, marked "outside the retainer" in the calendar.
`INTAKE DRAFT` (prospect): no scope note. The plan is pitch material, every fact is "from public research", and nothing is client-ready.

## 3. Row map: where the upstream questions are answered

| Upstream question | Take it from |
|---|---|
| What the company does, primary goal | Page 13 business and goals (page 07 rows) |
| Ideal customer, their questions and language | Page 13 audience (page 03) and buyer journey (page 04). Map buyer stages to page 04's stages |
| Problems solved, priority services | Offerings (page 08), D-1 |
| Competitors, content gaps | Positioning (page 09), E-8, L-4–L-6 |
| Customer stories, results | G rows (page 11). Else `[NEEDS PROOF: G-<n>]` |
| Opinions for thought leadership | F rows (page 10), APPROVED or PROVISIONAL only (flag PROVISIONAL) |
| Seasonality, service area (capacity as context only) | I-10, L-3, B-8, L-1, B-6 |
| Lead handling, CTA | I-3, required CTA language on page 13 |
| What's working, what's published | Monthly Context Brief (recent pieces, so nothing duplicates). Search Console/GA4 via Windsor.ai |
| What's been tried | Page 13 Learnings (if present) |
| Resources, formats | Page 00 retainer, not "writers, budget, time" questions |

Ask only about gaps that block the plan. List the others under "Gaps to ask about" in the footer. The upstream Task-Specific Questions become footer gaps too, not questions to the user.

## 4. Learnings

Read page 13's Learnings section if it has one. A missing section is normal; don't create it. Don't re-propose topics or angles it records as tried, failed or rejected unless the user asks. A result worth recording (a post that drove calls, a topic the client rejected) becomes a drafted task: `Context — [ABC] — <row ID or "no row"> — <short>`, created only after the user approves (§1, §8).

## 5. Topic and keyword sources, in this order

1. **L rows** (§4, for topics and planning): L-3 local search demand and peak months; L-4 who wins the map pack and organic results; L-5 competitor praise and complaint themes (unmet questions become topics); L-6 claims every competitor repeats (avoid echoing them); L-10 local demand drivers; L-11 category platforms; L-12 what AI assistants recommend. A row older than 90 days is stale: say so. Multi-location clients have per-location rows (L-4a, L-4b); use only the location's own.
2. **Semrush** (BML's only SEO data tool): `keyword_research` for "<service> <town>", "<service> near me", cost and how-to questions; `organic_research` for competitor ranking gaps. US database unless the client is elsewhere. Ahrefs, Moz and similar only if the client uses them.
3. **Search Console and GA4 via Windsor.ai**: queries with impressions but weak position (quick wins), and pages that drive calls, bookings or forms.
4. **Google Business Profile Q&A and review themes** (via Windsor.ai), and local communities (Nextdoor, local Facebook groups, Houzz/Angi for home services, Healthgrades/Zocdoc for clinical). These replace upstream's Indie Hackers / Hacker News / Product Hunt. Themes only: no reviewer names, no quotes that identify a person.
5. **Call transcripts (Fireflies)**: questions and phrases only. No names, conditions or dates of service. A phrase here is voice-of-customer, never a testimonial (testimonials only verbatim from page 11 with their row ID). Clinical clients: use only BML–client meeting transcripts, never recordings of patient calls.

Research that answers an OPEN row (most often L-3) is staged as DRAFT in the miner's format: `ID | Answer | Source label + link | Confidence | Date` (§10). A different answer from an existing row is flagged as a conflict, not overwritten. Never written to ClickUp.

## 6. Season, capacity context and scoring

**Seasonal timing:** publish searchable pieces for a seasonal service 8–12 weeks before its L-3/I-10 peak month, unless I-10 states a booking lead time; then use that.

**Capacity and season are context, not a gate:** if B-6 marks a service at capacity in a window, or I-10 notes a slow or peak season, say so next to the affected topics in the plan. Capacity never blocks, drops or moves a topic; only the seasonal timing above sets publish windows. If B-6 or I-10 is OPEN, plan normally and list the gap.

**Cadence:** the page 00 qualifier (`<n> posts/month`), else the current cadence in the Monthly Context Brief.

Then score with the upstream weights, read this way:
- **Customer Impact:** how often the question appears in page 03/04 rows, L-5 themes and Search Console queries; tie to a priority service (D-1), not LTV.
- **Content-Market Fit:** leads to a call, booking, form or signed job (I-3 handling). A usable F belief and G proof exist, or the gap is named.
- **Search Potential:** Semrush/L-3 intent and trend. Small local volumes are normal; judge by intent and fit, not raw volume.
- **Resources:** what the retainer covers and what proof or photos (with release) exist.

## 7. Topic checks (§5, §7)

- Check every proposed public title against page 12 and F-13 at any status (including DRAFT), and page 13's never-use words. A topic that needs a violation (e.g. "<competitor> vs [ABC]" under a J row that bars naming competitors) is dropped, with the row named. Competitor names may still appear in the plan's internal research section.
- **Shareable / thought leadership:** every opinion topic cites an F row. With no usable F row, list it as "needs belief: F-<n>"; don't invent a point of view.
- **Case studies and data pieces:** results come from G rows or are marked `[NEEDS PROOF: G-<n>]`. No customer or patient data in any analysis.
- **Clinical:** no fear, urgency or outcome-promise titles (no "warning signs you can't ignore"); prefer reassurance (process, access, insurance, credentials). Outcome topics are flagged for provider review. Patient-story topics need G-5/J-6 authorization.
- **Home services:** stay inside the service area (B-8, L-1). Project stories need a photo release (J-6). Never plan AI images as real projects.
- **Multi-location:** run per location. Never mix one location's L rows, proof or providers into another's topics. Voice, beliefs and guardrails come from the parent brand.
- **Professional services:** no outcome-guarantee topics unless a row permits.

## 8. Local translations of upstream defaults

| Upstream | For local service |
|---|---|
| Decision modifiers "demo, trial, pricing", "X vs Y", "alternatives" | "<service> cost in <town>", "near me", "reviews", "financing", "insurance accepted", "how long does <service> take", permits, before/after (prices only where D-4 allows; comparisons only after a page 12 check) |
| "[persona] + [use-case]" | "<service> for <situation / home type / patient need>" |
| Template libraries, product adoption | Checklists and guides that lead to a call or booking |
| Meta content ("$<n> MRR", "Debt Over VC") | Behind-the-scenes process content, built on F rows |
| Link-earning multipliers (B2B SaaS vendor study) | Not a local benchmark. Local links come from citations, community and sponsorships (L-9), via link-building |
| Distribution (X, LinkedIn, podcasts, "1 email to the owned list", repost schedule) | Site blog, GBP posts, Meta organic, the client's email list if they have one. Every post or send is a draft for human approval; social and emails execute |
| Headless CMS publish workflow (Sanity, Contentful, Strapi) | Most clients are on Wix. Headless guidance only if the client uses one. No step publishes: publishing is a human action after J-1 approval |

Never call write actions on any connector (Wix site changes, Windsor.ai GBP posts or listing edits, review replies, ad changes).

## 9. Distinctiveness

The plan is an agency artifact, so the §6 check is `n/a`. But each topic lists the F and G rows it can build on, so the copywriting draft can pass. Topics missing either are marked `needs belief: F-<n>` and/or `[NEEDS PROOF: G-<n>]` rather than given an invented angle.

## 10. Output

- **Style:** Baker house style (Baker Operations Manual, `02: Baker Style Guide`). Don't load the client's voice or style pages (01/02). Use page 03 (via page 13) for audience and page 13's never-use words (H-5) to screen titles. Titles are working titles; copywriting applies the client voice.
- **File:** `[ABC]_Content_Plan_YY.MM.DD`. Blog-led plan, or neither line retained → client Drive `OUTPUTS/BLOG`. SEO-retainer keyword/cluster plan → `OUTPUTS/SEO` (both retained: `OUTPUTS/SEO`, blog calendar as a section). Resolve the folder by ID from the router; never search Drive. If none fits, stop and report. Never create folders, never leave a machine-local path as the final copy, never publish to Notion/GitHub.
- **ClickUp:** draft one record tagged `strategy`, plus `blog-content` or `seo` for the retained side (neither retained: `strategy` only). Per-piece tasks from the calendar are a drafted list, only for production the retainer covers (none under `planning only`, and none for pieces marked "outside the retainer"). Create only after the user approves.
- **Scope note:** the §2 note sits near the top of every client plan.
- **Approvals:** note the client approver (J-1) if the plan goes to the client. Nothing in the plan publishes, posts, sends or spends.
- **Maturity (§2):** a plan that goes to the client never states a `DRAFT` row as fact and flags `PROVISIONAL` ones. `INTAKE DRAFT` plans are internal or pitch material only, marked "from public research".
- **Footer:** end with the §9 context footer (Distinctiveness: `n/a for agency artifacts`; when neither line is Active, `Scope: planning only — no content or SEO service retained`). Strip it before the client sees the plan.
- **Recurring:** monthly or quarterly plan refreshes are scheduled tasks (see marketing-loops), never an in-session loop.
