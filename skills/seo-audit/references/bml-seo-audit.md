*BML overlay: this whole file is Baker Labs (BML) material, not upstream. Merges never touch it.*

# SEO Audit for Baker Labs (BML) Clients

Read this after `bml/context-rules.md` (`../../../bml/context-rules.md` from this file; `bml/` paths below are from the repo root, so `bml/local-market-research.md` is `../../../bml/local-market-research.md`) whenever the audit is for a BML client. Where this file conflicts with the rest of the skill, this file wins. The rest of the skill still decides *how* to diagnose.

## 1. Before you start

1. **Context.** Read in this order: router → staged `.agents/product-marketing.md` (page 13) → current Monthly Context Brief → source pages only if a cited row needs detail. If the staged file is missing or names a different client, run `product-marketing` in Load mode. One client per run. Never browse Drive or search ClickUp broadly.
2. **Scope gate.** Find SEO in the page 00 summary at the top of the staged file. Only an `SEO` line authorizes this skill. A `Website` line covers technical site changes and doesn't authorize an SEO audit on its own, and neither does a `Blog content` line; if only those are present, treat SEO as absent.
   - `Active` → full audit.
   - `Active — <qualifier>` (for example "audit only", "local only", "no implementation") → produce only what the qualifier permits, and say what's excluded.
   - Absent → stop: "SEO isn't in [CODE]'s retainer." Offer a scope note for the account lead.
   - `INTAKE DRAFT` (prospect) → no scope gate. Use the audit only as internal or pitch material, labelled "from public research", never in anything published. `⚠ UNVERIFIED` items are never asserted.
3. **Inputs from the record, not the user.** Take these from page 13 and its rows before asking anything:

| Upstream question | Where it comes from |
|---|---|
| Site type / business goal | Segment(s) on the staged file; conversions are calls, bookings, forms or signed jobs unless rows say otherwise (I-3) |
| Priority keywords and pages | D-1 priority services × L-1 towns; L-3 local demand |
| Competitors | L-4 (map pack and organic winners), page 09 |
| Service area, locations, hours | B-8, L-1, page 07 location and hours rows |
| Capacity and season | B-6, I-10 |
| Platforms (CMS, GBP owner, call tracking, CRM) | page 00 §8 |
| Traffic baseline | Search Console and GA4 via Windsor (section 2) |

   Ask the user only for what's left: recent migrations or redesigns, known incidents, and pages the client is worried about.

## 2. Tools (BML stack)

Semrush is the only SEO data tool BML has. Search Console, GA4 and Business Profile come through Windsor.ai. Pull each source once per run and reuse it.

| Job | Tool | Notes |
|---|---|---|
| Crawl: status codes, redirects, canonicals, duplicate titles/metas, broken links, orphans | Semrush Site Audit (Semrush MCP `site_audit`) | Needs an existing Semrush project for the domain. None → don't create one. Say so, propose a task for the account lead to set it up, and label the audit "partial crawl" (built from Search Console, PageSpeed Insights and rendered spot checks) |
| Keywords, rankings, organic competitors | Semrush (`organic_research`, `keyword_research`, `position_tracking` where a project exists) | Label figures `Benchmark: Semrush <report>, <YY.MM.DD>` |
| Queries, pages, CTR, indexing, CWV report | Search Console via Windsor (`searchconsole`) | Check `get_connectors` first. Not connected → ask the account lead to connect it; don't guess |
| Conversions by landing page | GA4 via Windsor (`googleanalytics4`) | Key events: calls, forms, bookings. Use these instead of bounce rate or time on page |
| Profile actions, hours, categories | Business Profile via Windsor (`google_my_business`) | **Read only.** Never `execute_action` |
| Speed / Core Web Vitals | PageSpeed Insights, GSC CWV report | Free, no account |
| Structured data | Browser render (`document.querySelectorAll('script[type="application/ld+json"]')`), Rich Results Test | Never conclude "no schema" from a text fetch |
| Wix settings | Wix MCP read-only calls where the site is connected; otherwise list the settings to check | Never a write call |
| Screaming Frog, Ahrefs, Sitebulb, ContentKing, call tracking, CRM | Only if the client uses it (page 00 §8) or provides an export | Read only. Never write to a CRM |

## 3. Wix checks

Most BML client sites are on Wix (confirm on page 00 §8). Wix server-renders pages and handles hosting, HTTPS, CDN, image format conversion and the XML sitemap, so don't recommend server, caching-header or CDN changes there; mark them "not applicable on Wix". Point each fix at the Wix control that makes it.

- **SEO dashboard:** is Search Console connected through Wix? (It needs a Premium plan and a connected domain.) Note open SEO Assistant items as hints, not findings.
- **SEO Settings by page type** (main pages, blog posts, Bookings services, dynamic items, products): the default title is `{Page Name | Site Name}`, and the **meta description is blank by default**, so flag blanks in bulk. Check that variables produce unique titles.
- **Per page (SEO panel → Basics / Advanced SEO):** custom title and meta, slug (set from the *first* page name, so look for `/copy-of-…`, `/blank`, `/general-5`), the "Let search engines index this page" toggle, robots meta directives, canonical (self-referencing by default; changed only on purpose), and custom structured data.
- **Indexing hygiene:** hidden pages, lightboxes, password or member pages, thank-you pages, and Bookings `/booking-calendar/` or `/service-page/` duplicates. Flag thin blog tag, category and pagination pages.
- **Redirects:** the URL Redirect Manager covers old site URLs after a migration and renamed slugs. Look for chains and 404s from earlier rebuilds.
- **robots.txt editor:** unintentional blocks. Blocking or allowing AI crawlers is an `ai-seo` decision.
- **Speed:** installed apps, third-party embeds (review widgets, chat, maps, video), oversized hero images and galleries, too many fonts, and animations above the fold. Fixes are "remove or defer the app", not code changes.
- **Structured data:** Wix adds some markup itself (business info, blog posts, Bookings, products). Check what renders before proposing more, and route new markup to `schema`.
- **Multilingual:** Wix Multilingual generates hreflang. Verify its output; don't prescribe manual tags.
- **Business info:** the business name, address or service area and phone under the site's business info must match the canonical NAP record (section 4).

Verify any Wix control against the current Wix Help Center before naming it in a client report. Wix renames menus often.

## 4. Local presence

Treat the client as a local service business unless page 13 says otherwise. Run the upstream [local SEO reference](local-seo.md) with these overrides:

- **Canonical NAP record from rows:** name, phone, address or service area, hours and location URL, built from page 07 rows, B-8 and L-1. An `OPEN` row gets `[NEEDS PROOF: <row ID>]`; a `DRAFT` row isn't a fact, so a public mismatch with it is a conflict, not a fix-now finding. Where the GBP, the site or a listing disagrees with an approved row, that's a **fix-now finding**. If the public version might be the true one, it's also a conflict for the monthly check. Never "correct" the row.
- **Reuse BML research:** L-3 demand, L-4 map pack and organic winners, L-11 category platforms. If one is `OPEN` or older than 90 days, run that row's step in `bml/local-market-research.md` and stage the result (section 8). Read L-12 (AI recommendations) if present, but don't refresh it here; that belongs to `ai-seo`.
- **Reviews:** counts and ratings carry "⚠ confirm before publishing". No reviewer names in the audit, evidence or staged rows; summarize themes instead. Review request and reply drafts are client deliverables (section 6). They're never sent or posted, and they follow the segment rules. Replies never repeat customer, job, medical or financial details; for clinical clients a reply never confirms the reviewer is a patient or mentions treatment.
- **Citations:** this skill fixes existing listings and duplicates (the upstream cleanup table). Acquiring new citations and links belongs to `link-building`. AI visibility (L-12, Wix AI Visibility) belongs to `ai-seo`.
- **Service area pages:** only for towns in B-8 / L-1 core, and only with real local content. Never imply an office. Capacity and season (B-6, I-10) are context: note them beside the affected pages, never a reason to drop a page.
- **Measurement:** judge SEO pages by GA4 key events (calls, forms, bookings) by landing page and by profile actions. Read call tracking or a CRM only if page 00 §8 lists it, read-only.

### Local service sites by segment

Apply `bml/context-rules.md` §7 for the client's segment. Common issues to check:

- **All:** service pages thin or merged into one "Services" page; no page per D-1 service; CTAs that don't match the conversion path or I-3; GBP website link pointing at the homepage instead of the location page; phone not click-to-call on mobile.
- **Home services:** project galleries with no text or alt text; service-area pages that only swap town names; license details missing where J-3 requires them; project photos without a release (J-6); never AI images shown as real projects.
- **Clinical:** provider pages lacking credentials (from rows only); insurance, referral and booking information hard to find; clinical claims not traceable to approved copy (flag for a named provider's review); tracking pixels or lead forms on patient-facing pages (flag for a person; never recommend adding them); Search Console exports checked for anything identifying a patient before quoting.
- **Multi-location:** one GBP and one location page per real location; no location's hours, providers or proof on another's page; parent-brand rules (J-3) on every page.
- **Professional services:** credentials and disclosures per J-3; no outcome guarantees in proposed titles or metas.

### Title patterns for local service pages

Use these instead of the SaaS page types in [title-tags.md](title-tags.md). The rules in that file still apply.

| Page type | Pattern |
|---|---|
| Service | `<Service> in <Town> \| <Brand>` or `<Service> for <audience> \| <Brand>` |
| Service area | `<Service> in <Town>, <State> \| <Brand>` (real coverage only) |
| Location | `<Brand> <Town> - <Primary service>` |
| Provider (clinical) | `<Provider name>, <credential> - <specialty> in <Town>` (from rows) |
| Projects / gallery | `<Project type> in <Town> - <Brand> Projects` |
| Booking / contact | `Book <service> in <Town> \| <Brand>` |

## 5. Claims in the audit

- Client facts cite a row ID. Missing facts are `[NEEDS PROOF: <row ID>]`.
- No projected traffic, lead, revenue or ranking figures. Impact stays High/Medium/Low with a one-line reason.
- Market numbers are labelled `Research:` or `Benchmark:` with source and date, and never imply the client's own results.
- Naming competitors is fine in the audit (internal to BML and the client). Proposed on-site strings follow J-4.

## 6. Output

- **Style:** the audit is an agency artifact, so it's in Baker house style (Ops Manual `02: Baker Style Guide`). Don't load client pages 01/02 for the report body.
- **Proposed on-site strings** (titles, metas, GBP description, review request and reply drafts) are client deliverables inside the artifact: write them in client voice (page 13 / page 01, H-5 never-use words, required CTA language), check them against page 12 and F-13 at any status, and mark them "draft — for client approval (J-1)". A request that needs a guardrail violation stops and names the row.
- **Structure:** the upstream Audit Report Structure, plus an **Owner** on each finding (BML web team / client / Wix setting / Semrush / GBP owner), and these sections:
  - **Local presence**: NAP record, GBP, reviews, citations
  - **Wix fixes**: setting → current → proposed
  - **Human steps**: GSC indexing requests, profile edits, redirects, review requests
  - **Rows staged** (section 8)
  - Context footer from `bml/context-rules.md` §9 (Distinctiveness: n/a for agency artifacts)
- **Location:** the client's Drive `OUTPUTS/SEO`, resolved by folder ID from the router. Never search Drive and never create a folder; if none fits, stop and report. Name: `<CODE>_SEO_Audit_<YY.MM.DD>`. Nothing persistent in local paths.
- **Record:** draft a ClickUp task (tag `seo`, status `internal review`, link to the file). Create it only after the user approves.

## 7. Never

Change anything on the client's site, Business Profile, Search Console, robots.txt, redirects or Wix settings. No Windsor `execute_action`, no Wix write call, no indexing requests, no review requests sent, no listing submissions, no paid listing services, no Semrush project created. Nothing publishes, sends or spends without a human checkpoint and the client's approver (J-1). Fixes become proposed `website`/`seo` tasks for whoever implements. Every proposed task (fixes, Semrush project setup, connector requests) is drafted in the report and created only after the user approves. Anything on a cadence (rankings push, CWV watch, citation refresh) is proposed as a scheduled task for the user to approve, never an in-session loop.

## 8. Write-back

When a finding answers an `OPEN` row, stage it in the miner format (`bml/context-rules.md` §10). Never write to ClickUp.

| ID | Answer (≤40 words, one fact) | Source label + link | Confidence | Date |
|---|---|---|---|---|
| L-4 | Map pack for "<service> <town>": <competitor>, <competitor>, <competitor> | Research: Google Maps <link> | Medium | <YY.MM.DD> |

List separately: **conflicts** (a public fact that differs from a non-`OPEN` row) and **fix-now findings**. F and J rows are never filled from research.
