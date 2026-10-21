> BML-owned file (Baker Labs fork): not part of upstream marketingskills; maintained by BML.

# Programmatic SEO for BML Clients

Applies when the work is for a Baker Labs (BML) client or prospect. Read `../../../bml/context-rules.md` (the repo's `bml/context-rules.md`) first; where this file and the upstream skill disagree, context-rules and this file win. For BML's own marketing, use the upstream skill as written.

## 1. Before you start

- **Scope gate** (context-rules §3). Find the **SEO** line on page 00; SEO is the service line that authorizes programmatic SEO. Website covers technical site changes and doesn't authorize a pSEO plan on its own.
  - `Active` → proceed.
  - `Active — planning only` (or similar) → deliver the plan and template only, and say that the page-data build and implementation are excluded.
  - SEO absent (even if Website is `Active`) → stop: "Programmatic SEO isn't in [ABC]'s retainer (it needs the SEO line)." Offer a scope note instead.
- **Prospects** (`INTAKE DRAFT`): you may build a pitch-level plan marked "from public research". Never build a page-data sheet meant for publishing.
- **Pull from the record, not the user:**

| Input | Where it comes from |
|---|---|
| Services offered | D-1 (and 08 offering rows) |
| Capacity, seasonality (context only, never a gate) | B-6, I-10 |
| Service area | B-8, L-1 (core vs. edge towns) |
| Local demand | L-3; else Semrush (see §6) |
| Locations: address, phone, hours, providers | Page 07 location rows, per location (cite each row) |
| Proof | G rows, tagged to a location where they are location-specific |
| Beliefs | F rows (`APPROVED` or `PROVISIONAL`) |
| CTA wording, lead routing | 01 required CTA language, I-3 |
| Prices | Only where D-4 approves publishing |
| Current platform (the client may choose another) | Page 00 §8 |
| Approver | J-1 |

## 2. Page types BML builds

| Type | Pattern | Use when |
|---|---|---|
| **Service × location** | `/<service>/<location>/` | The client has a real office or location there. The page carries that location's own details |
| **Service-area page** | `/<service>/<town>/` or `/service-areas/<town>/` | The client serves the town but has no office there. It passes the doorway test (§4) |
| **Service-area hub** | `/service-areas/` or `/<service>/` | Always. It lists every town served, including those that don't earn their own page |
| **Service × audience** | `/<service>/for-<audience>/` | Only for ICPs on page 03 with distinct needs backed by rows |
| **FAQ / glossary** | `/learn/<term>/` | Rarely. For clinical clients, every page needs provider review (§7) |

Not for local-service clients unless page 00 and the rows support them: Integrations, Conversions, Templates, Directory, Profiles of public figures, Translations (only if a row says the client serves that language), and Curation ("best <category>"). The nearest local equivalent of Integrations is a service × product-line page, only where 08 offering rows record the product line and no page 12 row forbids naming the brand. **Comparisons** go to the `competitors` skill and J-4.

## 3. The page-data sheet

One row per page. Every content field has a source column holding a row ID (`G-<n>`, `L-1`, `<location row>`).

Allowed:
- Page 13 and the rows it cites, at `APPROVED` or `PROVISIONAL` status only (context-rules §2). A `DRAFT`, `OPEN` or `⚠ UNVERIFIED` row is a gap, not a fact. `PROVISIONAL` rows are listed in the footer.
- L rows, used for targeting. In public copy, a market statistic cites its source and date and never implies the client's own results.

Not allowed:
- Invented neighborhoods, landmarks or "local insights".
- Population or market figures without an L-2 or L-10 citation.
- Competitor names.
- Prices without D-4.
- Ratings or review counts without "⚠ confirm before publishing" in the field's notes column.
- Composed or merged testimonials (quotes are verbatim G rows only; for clinical clients, G-5/J-6 authorization must be on file).
- Patient or customer personal data, or reviewer names pulled from Google reviews.

A fact the page needs but the record lacks: leave the content field **blank** and write `[NEEDS PROOF: <row ID>]` in its source column. The template hides a section whose field is blank. It never fills it with generic copy. Flags (`[NEEDS PROOF]`, `⚠ confirm before publishing`, `⚠ PROVISIONAL`) go only in source or notes columns, never in a content field, because content fields are imported into the site as-is.

Template sections are conditional: "show if `<field>` has a cited row". The unique intro is assembled from cited fields (service, town, location detail, proof). It is not written as local colour.

## 4. Doorway test (every page, before it goes in the sheet)

A page is built only if all of these hold:
1. **Offered:** the service is in D-1. Capacity and season (B-6, I-10) are context, never a reason to fail a page.
2. **In the area:** the town is in B-8 or L-1.
3. **Specific:** it has at least 2 page-specific facts from `APPROVED` or `PROVISIONAL` rows beyond the swapped names. Examples: the location's own address, hours and providers; a G row tied to this town or location; a service or process difference recorded in 08; a cited, dated L-10 driver.
4. **Wanted:** demand is recorded (L-3 or Semrush), or L-1 marks the town as core service area.

A page that fails goes on the service-area hub list and is not built. Don't noindex padded pages as a workaround; just don't make them. Order the build batch by demand × proof strength, strongest first. Time the launch of seasonal services to I-10. If B-6 marks a service at capacity, note it beside its pages as context; never leave a service out for it.

## 5. Multi-location

- One location per page. That location's address, phone, hours, providers and booking link come only from its own page 07 location rows, and its proof only from G rows tagged to it. Per-location L rows carry a suffix (L-1a, L-1b) and are for targeting, not page facts.
- No shared "reviews" or "our team" block across locations. Never move proof, hours or providers from one location to another, even where a location has none of its own: mark `[NEEDS PROOF]` instead.
- Voice, beliefs and guardrails come from the parent brand. Franchisor rules (J-3) apply to every page.
- Each location page links to that location's own Google Business Profile, and its name, address and phone match it. Service-area pages carry no street address.
- Schema: `LocalBusiness` (or a subtype) only for a real location, matching its GBP; service-area pages never get a fake address. Hand JSON-LD detail to the `schema` skill.

## 6. Research and tools

- **Demand:** reuse L-3 first. Otherwise use Semrush keyword research ("<service> <town>", "<service> near me"; US database; local where available). Pull once per run.
- **Existing page performance:** Search Console and GA4 via Windsor.ai.
- Don't ask for or cite tools BML doesn't have (Ahrefs, Moz, Screaming Frog, and so on).
- **Filling L rows:** if L-1 or L-3 is `OPEN`, follow `../../../bml/local-market-research.md` for those rows.
- **Write-back:** a finding that answers an `OPEN` row (L-1, L-3) is staged as `ID | Answer | Source | Confidence | Date`, with the matching source label (for L-3, `Benchmark: Semrush keyword research`), status DRAFT, in the run's review notes (context-rules §10). Never write it to ClickUp.

## 7. Segment rules on templates

- **Clinical:** no outcome or efficacy claims unless taken from approved published copy and flagged for review by a named provider. No urgency, scarcity or fear framing. Provider sections use approved bios, per location. No patient data. Don't add forms or tracking pixels: flag them for a person.
- **Home services:** show the license where J-3 requires it. Project photos only with a release (J-6). Respect service area. Note seasonal capacity as context, never a gate.
- **Professional services:** credentials and disclosures per J-3. No outcome guarantees.
- **Images, all segments:** use approved assets first (ClickUp tag `asset`). Never present an AI image as a real project, office or team.

## 8. Guardrails and distinctiveness

- Check the template, and at least 3 rendered sample rows, against page 12, F-13, H-5 and the router's do-not-assert list, at any status including DRAFT.
- A request that requires a violation stops before drafting and names the row (for example, "Blocked by J-4: never name competitors in public content").
- Distinctiveness: the template builds on at least 1 belief (F). Each page carries at least 1 proof point (G), specific to the location where possible. Pages that only have brand-level proof are listed as weaker and come later in the build order. A page with no usable proof is not client-ready: list it in the footer as `Distinctiveness: FAIL` with the rows to fill (context-rules §6).

## 9. Platform implementation

Plan for the platform the client uses or chooses (page 00 §8 records the current one). No platform is the BML default: weigh options with upstream [implementation-platforms.md](implementation-platforms.md). The Wix notes below are information for when the site is or will be on Wix; confirm features on the client's plan in the Wix Help Center before relying on them.

- **CMS collection = the page-data sheet.** One item per page. Fields mirror the sheet's content columns. Source and notes columns stay in the Drive copy and are removed from the import file. A person loads it by CSV import (§10).
- **Dynamic item page = the template.** Connect elements to fields through the dataset. Use dataset filters or empty-field behaviour to hide sections whose field is blank. Item pages don't count toward the site's static page quota.
- **SEO:** set title and meta templates with variables bound to collection fields (SEO dashboard → dynamic item page). Set the URL slug pattern in the dynamic page's SEO settings. Structured data and the robots meta tag are in the Advanced SEO settings. Check whether per-item noindex is available before planning on it.
- **Sandbox vs live collections:** if the site uses a sandbox, items are reviewed there before sync.
- Pages stay on the client's existing domain.

## 10. Approvals and publishing

- The agent delivers the plan, the template spec, the page-data CSV and setup steps for the client's platform.
- The agent never calls a site platform's (e.g. Wix) write, import or publish tools, and never publishes to the client site.
- The first batch (the strongest pages, per §4 order) goes to `internal review`, then to the client approver (J-1). A person imports and publishes after `approved`. Later batches follow the same path.

## 11. Outputs

| Output | Kind | Voice | Location |
|---|---|---|---|
| Plan (opportunity, page types, doorway results, batch order, linking, indexation, monitoring) | Agency artifact | Baker house style; don't load 01/02 | Drive `OUTPUTS/SEO` |
| Page template + page-data CSV | Client deliverable | Client 01 voice, 02 style | Drive `OUTPUTS/WEBSITE` |

- Resolve folders by ID and never create them. If no folder fits, stop and report.
- Name the plan `<CODE>_pSEO_Plan_YY.MM.DD`.
- Draft a ClickUp record (tag `seo`, status `internal review`) and create it only after the user approves.
- The plan and the template spec end with the context footer (context-rules §9); the template's footer covers the page-data sheet. Never append the footer to the CSV, since every CSV row becomes a CMS item. Distinctiveness reads `n/a` for the plan.

## 12. Monitoring

- Indexation, impressions and clicks per page come from Search Console via Windsor.
- Rankings come from Semrush position tracking, if a project exists.
- A recurring check is a scheduled task (`marketing-loops`, programmatic-SEO quality loop), never an in-session loop. Propose it; set it up only after the user approves.

## 13. Disambiguation

| Skill | Owns |
|---|---|
| `programmatic-seo` | The template-plus-data plan for a set of similar pages |
| `site-architecture` | The whole-site hierarchy and where the hub sits |
| `copywriting` | The template's fixed copy blocks |
| `schema` | LocalBusiness/Service JSON-LD |
| `seo-audit` | Technical issues after launch |
| `competitors` | Any "vs" or "alternative" page |
| `../../../bml/local-market-research.md` | Filling L rows before planning |
