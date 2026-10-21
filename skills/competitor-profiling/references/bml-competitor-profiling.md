<!-- BML file: Baker Labs overlay for competitor-profiling. Wholly BML; not part of upstream. -->
# BML Competitor Profiling

How `competitor-profiling` runs for a Baker Labs (BML) client. Read `../../../bml/context-rules.md` first; where the two conflict, context-rules wins. Not BML client work → ignore this file.

## 1. Before you start

- Staged `.agents/product-marketing.md` names this client (first line). Otherwise run `product-marketing` Load. Never write to that file or page 13.
- Scope gate on page 00 (context-rules §3): an Active **SEO** line authorizes competitor profiling. No SEO line → stop: "SEO isn't in [CODE]'s retainer." Offer a scope note. Respect qualifiers such as "planning only" or "audit only". `INTAKE DRAFT` context has no page 00: skip the gate (context-rules §1).
- Read from page 13: segment(s), service area (B-8, L-1), priority services (D-1), local search demand (L-3), map pack and organic winners (L-4), review themes (L-5), offers and messaging (L-6), paid bidders (L-7), category platforms (L-11), and the competitor rows (E rows) as page 13 cites them; open page 09 only if page 13 is stale or lacks the detail. Reuse them; don't re-pull what is on file and under 90 days old.
- This skill deepens individual competitors. It does not run the full L-1…L-12 procedure in [`bml/local-market-research.md`](../../../bml/local-market-research.md); that stays with Intake, the miner's Backfill and the quarterly refresh.
- Competitor list: URLs from the user → those. None → L-4 / E rows. Those `OPEN` → discover (§3) and say the list is BML research.
- This is an agency artifact: Baker house style (Ops Manual `02: Baker Style Guide`). Don't load pages 01/02. Page 03 only if comparing target audiences.
- One client per run. Never reuse another client's profiles, even for a shared competitor; re-pull.
- `INTAKE DRAFT` context → internal or pitch use only, marked "from public research".

## 2. Data sources

| Need | Source | Notes |
|---|---|---|
| Domain strength, organic keywords, est. traffic | Semrush `domain_overview` toolkit | Discover report → `get_report_schema` → `execute_report`; `database` = `us` unless stated |
| Ranking keywords and top pages | Semrush `organic_research` | Filter to L-3 terms ("<service> <town>", "<service> near me") |
| Organic competitors | Semrush `competitors_research` | Filter per §3 |
| Backlinks / referring domains (deep profile) | Semrush `backlinks_research` | Link-gap work goes to `link-building` |
| Paid bidding on local terms | Semrush `paid_search_research` | Feeds L-7 |
| Keyword volumes for L-3 terms | Semrush `keyword_research` | Only if L-3 is `OPEN` or stale; use in the profile, don't stage L-3 (owned by the L procedure) |
| Map pack, rating, review count, primary category, hours | Google Places search | Per priority service × core town |
| Site pages | WebFetch; browser tool for JS-heavy pages | Probe local paths (§4) |
| Client's own accounts (Search Console, GA4, Business Profile) | Windsor.ai | Only for the client, never for competitors; read only |

- Semrush is the only SEO data source. Firecrawl, DataForSEO, Ahrefs, Ubersuggest: only if the client uses them. Never recommend buying a tool.
- Semrush `no_data` is the final answer: write `—`, never estimate, don't hunt for another report. Note it in the profile.
- Map the upstream Phase 2 metrics: domain rank → Semrush Authority Score; ranked keywords / top pages → `organic_research`; backlinks summary / referring domains → `backlinks_research`; competitors domain → `competitors_research`.
- Scale sanity check for local competitors: compare claims ("<n> projects", "since <year>") with review count, years in business and locations, not organic traffic.
- Never call write actions on any connector (Windsor.ai listing or review actions, Wix, ad changes).

## 3. Discovering and prioritising competitors

- Keep businesses that serve the L-1 towns and offer the client's priority services.
- National directories and aggregators (category marketplaces, review sites) are not competitors to profile: list them as L-11 platforms.
- Out-of-area businesses that rank nationally are dropped unless they serve L-1 towns.
- Prioritise by: map pack top 3 on L-3 terms → organic top 3 → paid bidders (L-7) → service-area overlap. Profile the top 5 first.
- Multi-location clients: run per location; never mix one location's competitor set into another's. Suffix staged rows per location (L-4a, L-4b) as `bml/local-market-research.md` does.

## 4. What to extract (local service)

| Page | Extract |
|---|---|
| Homepage | Headline, subheadline, primary CTA type (call / book / form / estimate), phone/booking prominence, proof claims, audience signals |
| Services / service pages | Services offered, specialties, what they lead with |
| Locations / service area | Towns and counties named, number of locations |
| Pricing / offers / financing | Published prices verbatim, "free estimate/consult", financing, memberships or maintenance plans, promotions, guarantees and warranties |
| About / team | Years in business, licenses, certifications, associations, awards (clinical: credentials, insurance accepted) |
| Reviews / testimonials / gallery | Themes only (§5); whether project photos are labeled as their own work |
| Blog / resources | Topics, cadence, formats |

Common paths: `/services`, `/service-area`, `/locations`, `/areas-we-serve`, `/financing`, `/specials`, `/offers`, `/reviews`, `/testimonials`, `/gallery`, `/projects`, `/about`, `/insurance`, `/providers`. Read the homepage nav first.

Software or product competitors (e.g. for BML's own marketing) use the upstream extract table.

## 5. Reviews and privacy

- Sources by segment: Google reviews, Yelp, BBB; home services: Houzz, Angi, Nextdoor; clinical: Healthgrades, Zocdoc, Vitals; others per L-11.
- Output 3–5 praise and 3–5 complaint themes, paraphrased, each with source and date range.
- Never record reviewer names, initials, photos, profile links, or quotes that identify a person. Clinical: no condition, procedure or date tied to anyone. Don't copy patient testimonials from competitor sites. If asked for verbatim quotes, explain the rule and offer paraphrased language patterns.
- Ratings and review counts carry the date pulled and "⚠ confirm before publishing".
- Competitor clinical claims (outcomes, efficacy) are recorded as "competitor claim — observed <page>, <date> — never reuse".

## 6. Profile template and outputs

Use the upstream structure with these sections replaced:

- **At a Glance:** Locations · Service area · GBP primary category · Rating / review count (date, ⚠ confirm before publishing) · Semrush Authority Score · Organic keywords · Est. organic traffic · Map pack presence on L-3 terms · Paid bidding on L-3 terms (yes/no)
- **Services and Offer** (replaces Product & Features): services, specialties, CTA type, guarantees/warranties, financing
- **Price and Offer Signals** (replaces Pricing): published prices verbatim with page and date, or "no public pricing (pages checked, date)"; promotions; insurance (clinical). The client's own prices appear only where D-4 permits.
- **Reputation and Proof** (replaces Customers & Social Proof): ratings per platform, review themes (§5), licenses, associations, awards, years in business
- **Local SEO and Content:** L-3 term rankings, map pack results, top pages, content topics
- **Implications for [CODE]** (replaces Competitive Implications for [Your Product]): client-side strengths cite row IDs (A/D/G rows); anything without a row is `[NEEDS PROOF: <row ID>]` or labeled hypothesis. Frame as options for the strategist.

Positioning map axes for local markets: Budget ↔ Premium · Specialist ↔ Full-service · Emergency/fast ↔ Planned project · One town ↔ Regional · Independent ↔ Franchise · (clinical) Insurance-led ↔ Cash/elective.

**Files** (flat, in the client's Drive `OUTPUTS/RESEARCH`, or `OUTPUTS/SEO` if RESEARCH doesn't exist yet, resolved by ID from the router — never search Drive, never create folders; neither exists → stop and report):

- `<CODE>_Competitor_<slug>_YY.MM.DD.md` — one per competitor
- `<CODE>_Competitor_<slug>_Raw_YY.MM.DD.md` — deep profiles only: page excerpts used and Semrush outputs as tables. Quick scans keep raw data in session scratch only and cite sources (URL, date, Semrush report name) in the profile.
- `<CODE>_Competitor_Summary_YY.MM.DD.md` — summary
- `<CODE>_Competitor_Review_YY.MM.DD.md` — staged rows (§7)

Each profile and the summary end with the context footer (context-rules §9; Distinctiveness: n/a for agency artifacts). It is internal.

Refresh = new dated files linking the previous one; the Change Log compares against the previous dated file in the same folder. Never overwrite or delete.

**ClickUp:** draft one task for the account lead — name `Research — <CODE> — Competitor profiles — YY.MM.DD`, tag `research`, status `internal review`, Drive links in the description. Create it only after the user approves.

## 7. Staging findings for page 09

In `<CODE>_Competitor_Review_YY.MM.DD.md`, in the format `client-context-miner` uses (context-rules §10):

| ID | Answer (≤40 words, one fact) | Source | Confidence | Date |
|---|---|---|---|---|
| L-4 | <service> in <town>: map pack <competitor>, <competitor>, <competitor> | Research: Google Places search | High | <YY.MM.DD> |

- The table holds only L rows that are `OPEN` on page 13 (L-4, L-5, L-6, L-7, L-11). Source labels `Research:` or `Benchmark:`. Everything lands `DRAFT`.
- E rows (client rows, e.g. E-1, E-8 "claims everyone makes", which L-6 feeds) are never put in the table: list them under **Signals for other rows** as candidates for the client to confirm, only if `OPEN`.
- A finding that differs from a filled row: list it under **Conflicts for monthly check** with both versions and dates. Don't edit.
- Never draft F (beliefs) or J (guardrails) rows from research.
- **Signals for other rows** and **Fix-now findings** (problems spotted on the client's own listings) go in separate lists, as in [`bml/local-market-research.md`](../../../bml/local-market-research.md).
- Nothing is written to ClickUp; the account lead reviews and `client-context-miner` writes approved rows. A request to "add this to product-marketing.md" becomes staged rows or a `context` task (context-rules §8), created only on approval.

## 8. Guardrails and handoffs

- Internal dossiers may name competitors. Public material that names them (comparison pages, ads, copy) is subject to J-4 and every page 12 row at any status, including `DRAFT`; if the request requires a violation, stop and name the row.
- Before a "gap" is used publicly, confirm it (upstream rule) and route the work to `competitors`, `ads` or `copywriting`, which run their own guardrail checks and note the client's approver (J-1).
- Clinical clients: implications use reassurance (process, credentials, access), never fear, scarcity or outcome promises.
- Nothing from this skill publishes, sends or spends.
- Recurring refresh (quarterly with the L-row refresh, or a competitor watch if the retainer covers it) runs as a scheduled task, never an in-session loop.
