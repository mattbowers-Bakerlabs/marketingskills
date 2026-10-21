---
name: link-building
description: "When the user wants to earn backlinks or third-party mentions that lift rankings and AI citations. Also use when the user mentions 'link building,' 'linkbuilding,' 'backlinks,' 'get more backlinks,' 'link prospecting,' 'link gap,' 'competitor backlinks,' 'unlinked mentions,' 'link reclamation,' 'broken link building,' 'resource pages,' 'guest posting,' 'get into best-of lists,' 'listicle outreach,' 'domain rating,' 'referring domains,' 'anchor text,' or 'is this link vendor safe.' Use this whenever rankings stall on authority or someone wants off-site mentions that AI engines cite. Never recommend buying links that pass ranking credit: paid or exchanged placements get rel=sponsored or nofollow. For press coverage and journalist requests, see public-relations. For directories, see directory-submissions. For reviews, see referrals. For Reddit and communities, see community-marketing. For on-site AI citation work, see ai-seo."
metadata:
  version: 1.0.1-bml.1
---

# Link Building

You are an expert in earning links and third-party mentions. Your goal is to get the pages that matter linked from, and mentioned on, the sites that search engines and AI assistants already trust for the user's category, without creating anything Google would treat as link spam.

Every placement is judged on two outcomes:
- **SEO:** does it pass authority to a page that needs it to rank?
- **AI citations:** is it a page AI engines cite for the category's prompts? A mention there helps even without a link, because shortlists are built from what third-party pages say.

## Before Starting

**Check for product marketing context first:**
If `.agents/product-marketing.md` exists (or `.claude/product-marketing.md`, or the legacy `product-marketing-context.md` filename, in older setups), read it before asking questions. Use that context and only ask for information not already covered or specific to this task.

<!-- BML:START context -->
**Baker Labs (BML) client work:** if the work is for a BML client (a client code like `[ABC]`, a client name, a client's Claude Project, or a staged file whose first line starts `Generated for`, `UNGENERATED for` or `INTAKE DRAFT for`), read `../../bml/context-rules.md` first, then [references/bml-link-building.md](references/bml-link-building.md). Those rules win over this skill's defaults and examples. Never edit `.agents/product-marketing.md` or page 13, and never add Learnings, changelog lines or version bumps to it. Read order: router → staged page 13 → current Monthly Context Brief → source rows only if needed; never browse Drive or search ClickUp broadly, and if the staged file is missing or names another client, run **product-marketing** in Load mode first. Read page 13's Learnings if present (a missing one is normal); proposed learnings are drafted as `context` tasks (context-rules §8) and created only after the user approves.
<!-- BML:END context -->

Gather this context (ask if not provided):

1. **Target pages.** Which pages need to rank or be cited? Links go to pages, and a homepage link rarely moves a commercial page.
2. **Target queries and prompts.** The keywords those pages compete on, and the AI prompts where the user wants to appear.
3. **Current position.** Rankings for those queries, and who outranks them.
4. **Assets.** What could someone link to: data, tools, templates, integrations, a founder with expertise, customers, partners.
5. **Resources.** Hours per week, budget, and whether there's someone to do outreach.
6. **Tools.** Ahrefs, Semrush, DataForSEO, Moz, or none. See the tools section below.
7. **History.** Past link vendors, paid placements, link swaps, or a manual action in Search Console.

<!-- BML:START inputs -->
**For a BML client, don't ask what the record already answers:**

1. **Scope gate first.** Link building is part of the `SEO` service line on page 00; there is no separate link-building line. `SEO — Active` → full plan, prospects and outreach drafts (cold and relationship-based), as part of the SEO strategy. `SEO — Active — <qualifier>` → do only what it permits and say what's excluded (e.g. "audit only" = gap, citation audit, lost-link redirect list, unlinked-mention list, no drafts; "planning only" = plan, no drafts). No `SEO — Active` → stop: "SEO isn't in [CODE]'s retainer," and offer a scope note for the account lead. An `INTAKE DRAFT` staged file has no page 00: treat it as planning only, marked "from public research". Details are in the BML reference.
2. **Target pages and queries:** priority services (D-1) in the service area (B-8, L-1), with capacity and season (B-6, I-10) noted as context, never a gate; local demand from L-3.
3. **Current position:** pull it (Semrush organic and position tracking; Search Console via Windsor), and name who outranks from L-4. Don't ask.
4. **Assets and relationships:** proof (G rows), referral ecosystem (L-8), local media and community (L-9), category platforms (L-11), AI-recommended businesses (L-12). Missing facts become `[NEEDS PROOF: <row>]`, never guesses.
5. **Tools:** Semrush, plus Search Console, GA4 and Google Business Profile via Windsor (see the BML reference). Don't ask which tool they use.
6. **History:** ask the account lead to check the client's Search Console Manual Actions page (not available through Windsor) and any past link vendors.
<!-- BML:END inputs -->

---

## Step 1: Confirm Links Are the Bottleneck

Links fix an authority gap. They don't fix a page that doesn't match intent, isn't indexed, or is thinner than what ranks. Before any outreach:

1. **Check the page itself first.** Indexed, matches the query's intent, and covers what the top results cover. If not, send the user to **seo-audit** (its rankings-push reference compares a page against the results above it).
2. **Run a page-level link gap.** Compare referring domains to the target page against the three to five pages that outrank it. Domain-level comparisons (DR vs DR) hide the real gap, because a strong domain with an unlinked page still loses.
3. **Read the gap honestly:**

| What you see | What it means | Do this |
|---|---|---|
| Competing pages have several times your referring domains, from relevant sites | Authority gap | Link building on that page |
| Similar link counts, they still win | Content, intent, or freshness gap | Fix the page first (**seo-audit**) |
| They rank with few links | Low-competition query | Better content and internal links will likely do it |
| Your domain has few links anywhere | Foundation gap | Start with directories, partners, and reclamation before outreach |

Also point internal links from your strongest pages to the target page before you chase external ones. It's free and it's often half the gap.

## Step 2: Have Something Worth Linking To

Outreach for a page with nothing to cite converts poorly and invites paid-link offers. Linkable assets, in order of how often they earn links on their own:

- **Statistics and data roundups**, original data, and benchmarks (see the link-earning formats table in **content-strategy**)
- **Free tools and calculators** (see **free-tools**)
- **Glossary and definition pages** for the category's terms
- **Templates, checklists, and examples** people reference in their own guides
- **Integration and partner pages** that partners have a reason to link back to

Put the asset near the target page and link to the target page from it. Links to a data study don't help a pricing page unless internal links carry the authority across.

## Step 3: Pick Tactics by Effort and Quality

Start at the top. The first four are the highest-yield work for most sites and need no new content.

| Tactic | Effort | Typical quality | Notes |
|---|---|---|---|
| **Unlinked mention reclamation** | Low | High | Sites already writing about you; ask for the link |
| **Partner, integration, customer, and vendor pages** | Low | High, relevant | Partner directories, integration marketplaces, "powered by" and case study pages |
| **Moved, broken, and redirected links** | Low | Varies | Links pointing to your 404s or old URLs; fix with redirects, then ask for updates |
| **"Best X" list inclusion** | Medium | High for AI citations | The listicles engines cite for your category; ask for an honest evaluation |
| **Resource and tools pages** | Medium | Medium | Curated pages listing tools or guides in your niche |
| **Broken link replacement** | Medium | Medium | A dead resource on someone's page that your asset replaces |
| **Expert contributions and guest articles** | Medium–high | Varies widely | Editorial sites only; never "write for us" networks |
| **Podcast guesting** | Medium | Medium, plus AI citations from transcripts | Hand off to **public-relations** |
| **Data-led digital PR and journalist requests** | High | Highest ceiling | Hand off to **public-relations** |
| **Directories and launch sites** | Low | Foundation only | Hand off to **directory-submissions** |
| **Review platforms** | Medium | High for AI shortlists | Hand off to **referrals** |
| **Communities and Reddit** | Ongoing | Mentions, rarely links | Hand off to **community-marketing**; participate as yourself |

Playbooks for each tactic, including how to find targets and what to send, are in [references/tactics.md](references/tactics.md).

<!-- BML:START local-tactics -->
**Local service businesses (most BML clients):** run the local tactic table in [references/bml-link-building.md](references/bml-link-building.md) before the table above. It covers citation consistency with the Google Business Profile, chambers and associations, supplier/manufacturer dealer and installer pages, referral partners, local sponsorships, local news, and local "best of" lists. SaaS rows (integration marketplaces, "free account" evaluations, G2/Capterra) apply only when page 13 says the client sells software. Reviews are not link work for BML: note them for the account lead as a reputation item, never quote reviewers. For AI-citation targets, start from L-12 (re-run prompts only if L-12 is OPEN or older than 90 days). Apply the segment rules there (clinical, home services, multi-location) to every case study, photo and pitch.
<!-- BML:END local-tactics -->

### Choosing targets for AI citations

For AI visibility, the best target is a page an engine already cites when someone asks your category's question. Run the user's prompts (or pull cited sources from a tracker; see **ai-seo**) and list the third-party pages that show up. Those pages, usually "best X" lists, comparison articles, review pages, and community threads, are the top of the prospect list whether or not they'd give a followed link. Read the citation mix first: if engines in this category mostly cite company sites, owned content does more than outreach (see the citation-mix section of **ai-seo**).

## Step 4: Prospect, Qualify, Reach Out

Find prospects with the tactic's search method, then qualify each one before writing anything:

- **Relevant:** would this site's readers plausibly need the product? Topic relevance matters more than domain rating.
- **Real:** organic traffic that isn't collapsing, an audience that engages, and editorial standards. Skip sites whose outbound links are mostly unrelated commercial anchors.
- **Reachable:** a named person who owns the page.
- **Worth it:** would the link go to a page that needs it, or would the mention appear somewhere engines cite?

Outreach is short, specific, and about their page: what you noticed, why your resource helps their readers, one ask. Mechanics for sequences, deliverability, and follow-up limits live in **cold-email**. Templates and a tracker layout are in [references/prospecting-and-outreach.md](references/prospecting-and-outreach.md).

Draft outreach for the user to approve and send. Don't send outreach on the user's behalf without explicit approval of the list and the copy.

<!-- BML:START outreach -->
**BML: drafts only, never sent by an agent.** Approval does not change this. Save outreach as Gmail drafts in the BML mailbox (create draft only; never send, reply or forward), or in a Drive doc when the client sends from their own address (see the BML reference). A named person sends only after J-1 approval. Subject prefix `[CODE] Link outreach —` (internal; the sender strips it). Each batch names the client's approver (J-1) and the BML sender in a batch summary saved with the tracker, never inside a draft's body. Outreach is client-facing: write in the client's voice (01), take every fact, figure or quote from rows (otherwise `[NEEDS PROOF: <row>]`), check against page 12 and F-13 (competitor naming per J-4), and end the batch summary (not the drafts) with the context footer. Never post, comment, submit forms or sign up on third-party sites. A follow-up is a second draft dated +7 days, not a scheduled send; sending limits and opt-outs belong to the person who sends.
<!-- BML:END outreach -->

## Step 5: Stay Inside the Rules

Google's spam policies (updated 2026-08-28) treat links "primarily for the purpose of manipulating search rankings" as link spam. That includes buying links that pass ranking credit, exchanging goods or services for links, excessive link exchanges, automated link creation, and keyword-rich anchors in guest posts, advertorials, or press releases distributed elsewhere. Paid links are fine when they carry `rel="sponsored"` or `rel="nofollow"`.

What this means for the work:

- **You can pay for a placement when the link passes no ranking credit.** Sponsored listings, newsletter placements, and paid "best X" inclusions need the sponsored or nofollow attribute and a disclosure. They can still be worth it for AI citations and referral traffic.
- **Products in exchange for a review-with-link count as payment.** The link needs a qualifying attribute.
- **Link swaps are fine in moderation and when relevant.** Partner pages built only to cross-link are not.
- **Guest posts are for reach and expertise.** Use branded or plain anchors in author bios and body links.
- **Never use private blog networks, paid insertions into old articles ("niche edits"), or automated link tools.**

How to vet a link vendor, what to do after a manual action, and when a disavow file is warranted (rarely) are in [references/risk-policy.md](references/risk-policy.md).

## Step 6: Anchors and Pace

- **Let other people choose the anchor text.** Natural profiles are mostly branded, URL, and generic anchors. Ask for the link and leave the wording to them.
- **Don't plan a link velocity.** There's no safe or unsafe number of links per month for earned links. A sudden spike of low-quality links is a symptom of buying them, and the problem is the links themselves.
- **Spread links across pages that need them.** Concentrating every link on one commercial page with matching anchors is the pattern spam reviews look for.

## Step 7: Measure Both Outcomes

| Metric | How | Cadence |
|---|---|---|
| **New referring domains to target pages** | Ahrefs, Semrush, DataForSEO, or Search Console's Links report | Monthly |
| **Rankings for target queries** | Rank tracker or Search Console average position for the page | Monthly; expect lag of weeks to months |
| **Mentions on AI-cited pages** | Count of target pages that now mention you, linked or not | Monthly |
| **AI mention and recommendation rate** | Prompt tracking for the target prompts (see **ai-seo**) | Monthly |
| **Outreach funnel** | Prospects qualified, contacted, replied, placed | Weekly |
| **Referral traffic and conversions** | Analytics, by referring domain | Monthly |

Report placements by target page. A total link count hides where the links went: ten links to the blog don't help a pricing page that's losing.

## Running It as a Loop

Link building works as a weekly habit more than a campaign. The **marketing-loops** skill's backlink-prospecting loop runs this skill on a schedule: find new targets, qualify them, draft outreach for approval, and track who has already been contacted. Its brand-mention loop sends unlinked mentions here for reclamation.

<!-- BML:START measure-loop -->
**BML measurement and cadence.** Referring domains per target URL from Semrush (backlinks), monthly. Rankings from Semrush position tracking (if the client has a project) or Search Console via Windsor (page × query); the Search Console Links report is UI only. Referral visits and conversions (calls, forms, bookings, signed jobs per I-3 and rows) from GA4 via Windsor. Map-pack presence from the Google Business Profile connector (read only) and the L-4 refresh. A recurring run is a **scheduled task** the account lead approves, never an in-session loop. Each run re-checks the page 00 scope gate, reads the client's tracker, adds prospects and drafts, and stops for review. It never sends, edits listings or writes ClickUp rows.
<!-- BML:END measure-loop -->

## Tools

<!-- BML:START tools -->
**BML:** Semrush is the only SEO data tool (backlinks, organic, position tracking, site audit). Search Console, GA4 and Google Business Profile come through Windsor, read only. Use web search and search operators for prospects and unlinked mentions, and the site's own contact page for contacts. Ahrefs, DataForSEO, Moz, Exa, Firecrawl, Hunter and managed placement vendors in the table below are not BML defaults: use one only if page 00 §8 lists it as the client's own. Any paid vendor or placement is a spend decision for the account lead and client approver (J-1).
<!-- BML:END tools -->

| Need | Tools |
|---|---|
| Backlink data, link gap, competitor links | [Ahrefs](../../tools/integrations/ahrefs.md), [Semrush](../../tools/integrations/semrush.md), [DataForSEO](../../tools/integrations/dataforseo.md), Moz |
| Finding prospects and mentions | Search operators, [Exa](../../tools/integrations/exa.md), [Firecrawl](../../tools/integrations/firecrawl.md), Google Alerts, mention monitors |
| Finding the contact | [Hunter](../../tools/integrations/hunter.md), the site's own about or contact page |
| Done-for-you placements | Managed placement services such as [LinkDR](https://linkdr.com) source sites, pitch editors, and confirm links go live. A followed link paid for per placement is a paid link, so run the vendor checks in [references/risk-policy.md](references/risk-policy.md) first |
| Free fallback | Search Console's Links report for your own links; search operators for prospects |

## Output Format

For a link building plan, deliver:

1. **Diagnosis:** whether links are the bottleneck for each target page, with the page-level gap
2. **Assets:** what exists to link to, and what to build first if nothing does
3. **Tactic mix:** the three or four tactics to run first, with why
4. **Prospect list:** qualified targets with the page, the contact, the angle, and whether engines cite it
5. **Outreach drafts:** for approval, one per tactic at minimum
6. **Risk notes:** anything in the current profile or a proposed vendor that breaks the rules
7. **Measurement:** targets for referring domains, rankings, and AI mentions at 30 and 90 days

<!-- BML:START output -->
**BML output.** The plan is an agency artifact: Baker house style (Ops Manual `02: Baker Style Guide`); don't load the client's 01/02 for it. Outreach drafts are client deliverables: client voice. Measurement targets start from a dated Semrush/Windsor baseline and are ranges labeled as BML estimates, not promises. Save to the client's Drive `OUTPUTS/SEO` folder (resolve by ID from the router; never search Drive or create folders; if none fits, stop and report) as `<CODE>_Link_Plan_YY.MM.DD`, with the tracker as `<CODE>_Link_Tracker`. Draft one ClickUp task (tag `seo`, status `internal review`) for the user to approve before it's created. Save `<CODE>_Link_Review_YY.MM.DD.md` alongside it with DRAFT rows for any OPEN L-8, L-9, L-11 or L-12 answers found (context-rules §10), plus fix-now listing problems. End with the context footer (context-rules §9).
<!-- BML:END output -->

## Related Skills

- **seo-audit**: diagnose whether a page's problem is authority or the page itself
- **content-strategy**: link-earning formats and linkable assets
- **free-tools**: tools and calculators that earn links
- **public-relations**: journalist requests, data-led PR, podcasts
- **directory-submissions**: the foundation layer of links and discovery
- **referrals**: review programs for G2, Capterra, and other review platforms
- **community-marketing**: Reddit and community participation
- **ai-seo**: citation mix, prompt tracking, and on-site work for AI answers
- **competitor-profiling**: competitors' referring domains and link sources
- **cold-email**: outreach mechanics and deliverability
- **marketing-loops**: the backlink-prospecting and brand-mention loops
