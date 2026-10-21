> BML-owned file (Baker Labs fork): not part of upstream marketingskills; maintained by BML.

# Link Building for BML Clients

Read after [bml/context-rules.md](../../../bml/context-rules.md). These rules apply to Baker Labs client work only and win over the defaults in SKILL.md and the other references.

## Contents
- Scope gate
- Semrush and Windsor recipes
- Local tactic table
- Reviews and AI-citation targets
- Local linkable assets
- Segment rules
- Outreach drafts and approvals
- Paid placements and sponsorships
- Measurement targets
- Tracker, write-back and conflicts
- Disambiguation

## Scope gate

Link building is part of BML's SEO strategy work: `SEO — Active` on page 00 authorizes it, including outreach. There is no separate `Link building` service line. Qualifiers still narrow it.

| Page 00 says | Do | Don't |
|---|---|---|
| `SEO — Active` | Full plan, gap, citation audit, reclamation, prospects, and outreach drafts: cold outreach (local news, "best of" lists, editors, list owners) and relationship-based links (chamber, suppliers, associations, sponsorships the client already funds). Drafts go in BML Gmail when a named BML person sends, or a Drive doc when the client sends from their own address; either way, sent only after J-1 approval | Send anything |
| `SEO — Active — audit only` | Gap, citation audit, lost-link redirect list, unlinked-mention list | Any drafts |
| `SEO — Active — planning only` | Plan and targets | Prospect contacts, drafts |
| no `SEO — Active` | Stop; offer a scope note for the account lead | Anything else |
| `INTAKE DRAFT` staged file (prospect; no page 00) | Plan and targets for internal or pitch use, facts marked "from public research" | Prospect contacts, drafts, anything sent in the prospect's name |

## Semrush and Windsor recipes

Semrush is the only SEO data tool. Search Console, GA4 and Google Business Profile come through Windsor.ai, read only.

- **Page-level gap:** `backlinks_research` → `backlinks_refdomains` with the **target URL**, then the same for each of the 3–5 outranking URLs (from `organic_research` or L-4). Intersect: domains linking to 2 or more competitor pages but not the client = warm prospects. The MCP has no gap report; the Semrush UI Backlink Gap is fine when a person runs it.
- **Profile health:** `backlinks_overview`, `backlinks_anchors` (over-optimized anchors → risk notes).
- **Lost links to reclaim:** `backlinks` for the client's domain; match target URLs against 4xx and redirect-chain pages in Semrush `site_audit`. The output is a 301 list for a person to apply (e.g. the Wix redirect manager); the agent doesn't change the site.
- **Rankings:** Semrush `position_tracking` if the client has a project; otherwise Windsor `searchconsole` (page, query, position, clicks), 28-day windows.
- **Conversions:** Windsor `googleanalytics4`, referral source × key events (call, form, booking per I-3 and rows).
- **Google Business Profile:** Windsor `google_my_business`, **read only**. Never run its write actions (listing edits, posts, review replies).
- **Manual actions:** not available through Windsor. Ask the account lead to check Security & Manual Actions in the client's Search Console.
- **Mentions:** web search `"<business name>" -site:<domain>` and `"<owner/provider name>" "<town>"`. No paid mention monitors.
- Any other tool only if page 00 §8 lists it as the client's own. Pull each source once per run and record the pull date.

## Local tactic table (run before the upstream table)

| Tactic | Find it | Ask / action | Watch for |
|---|---|---|---|
| **Citation consistency with GBP** | GBP (Windsor) vs the record's name, address, phone, hours and categories (cite the row) vs data aggregators, Apple Business Connect, Bing Places, BBB, Yelp, Facebook and L-11 platforms | Fix-now list for the account lead: platform, field, current value, correct value (row ID) | Agent never claims, edits or submits listings. Multi-location: per location |
| **Chambers of commerce and business associations** | L-9; chamber member directories in L-1 towns | Member directory listing, new-member spotlight, event sponsor page | Membership fees = spend → checkpoint |
| **Trade and professional associations** | L-8/L-9; licensing and certification bodies (J-3) | "Find a member / certified pro" listing, member spotlight | Only credentials on file (J-3) |
| **Supplier / manufacturer dealer and installer pages** | Brands the client installs, carries or is certified for (rows; `[NEEDS PROOF: <row>]` if unknown); "find a dealer / installer / provider" pages | Listing on the locator; a featured-project or case-study page | Case-study photos need J-6; stories need G-5; no customer names or street addresses |
| **Referral partners** | L-8 (e.g. builders, realtors, physician groups) | "Preferred partners" or referral-resources page | Organizations only in the plan; the tracker holds only a public business contact for each |
| **Local sponsorships** | L-9 events, youth sports, charities, schools | Sponsor page link (rel=sponsored expected) | Spend → see "Paid placements"; note B-6/I-10 as context |
| **Local news** | L-9 outlets | Expert commentary, community story, seasonal tip; hand news pitching to **public-relations** | Clinical: provider review; no outcome claims |
| **Local "best of <town>" lists** | "best <service> in <town>" searches, local magazines and reader polls, L-12 cited pages | Honest-evaluation request with facts the writer can verify (license per J-3, years in business, service area, approved photos) | Pay-to-play awards and "badge packages" = paid placement; prices only where D-4 allows |
| **Unlinked mentions and lost links** | Recipes above | Upstream reclamation playbook | — |

The upstream "best X" offer of a free account or demo, integration marketplaces and G2/Capterra apply only when page 13 says the client sells software.

## Reviews and AI-citation targets

- **Reviews** (GBP, L-11 platforms) are reputation work, not link work. Note gaps for the account lead. Never quote reviewers or put reviewer names in any output.
- **AI-citation targets:** start from L-12 on page 13. Re-run the category prompts only if L-12 is `OPEN` or older than 90 days, and stage new results as DRAFT L-12 (see write-back).

## Local linkable assets

Build or point to: project or case-study pages, local guides (permits, seasons, what to expect), community involvement pages, provider or owner expertise pages, manufacturer-certified status. Rules:

- Facts, figures and prices only from rows; prices only where D-4 allows. Otherwise `[NEEDS PROOF: <row>]`.
- Project photos only with a release on file (J-6). Never present AI images as real projects.
- Patient or customer stories only with written authorization (G-5, J-6).
- Location as town or neighborhood only, never a customer's street address.
- Check for an approved existing asset (ClickUp tag `asset`) before proposing new content; new content goes to **content-strategy** or **copywriting**.

## Segment rules

| Segment | Rule |
|---|---|
| Clinical | No patient data anywhere. Case studies need G-5/J-6 and review by a named provider. No outcome or efficacy claims in pitches or guest content. Health directories (L-11) are listings: verify provider credentials from rows. |
| Home services | License details where J-3 requires. J-6 releases for photos. Prospects inside the service area (B-8, L-1). Capacity and season (B-6, I-10) are context to note beside the target, never a reason to drop a link target. |
| Multi-location | Citations, chambers, news and sponsorships per location. Never mix one location's name/address/phone, proof or providers into another's. Parent-brand guardrails (J-3) apply to all. |
| Professional services | Credentials and disclosures per J-3. No outcome guarantees in pitches. |

Target pages are D-1 priority services. Capacity and season (B-6, I-10) are noted beside affected targets as context, never used to drop one.

## Outreach drafts and approvals

- Agents create drafts only: Gmail `create_draft` (BML mailbox, for outreach a named BML person sends on the client's behalf) or a Drive doc (for the client to send from their own address). Use whichever fits who owns the relationship; both are allowed under `SEO — Active`. Never `send_message`, `reply` or `forward`, even after approval.
- Each batch has a summary (saved with the tracker in `OUTPUTS/SEO`): client code, approver (J-1), BML sender, prospects covered, tracker link. The summary, not the drafts, carries the context footer. Gmail drafts hold only the message; the `[CODE] Link outreach —` subject prefix is internal and the sender strips it.
- Drafts are client deliverables: client voice (01), CTA language, page 12 + F-13 checks, J-4 for competitor names (competitor names are fine in the internal plan). Pitches and guest content build on ≥1 F belief and ≥1 G proof.
- Never post, comment, submit contact or listing forms, or sign up for accounts on third-party sites; a person does that.
- Follow-up: one second draft, dated +7 days. Then stop. No agent-run sequences; sending limits and opt-out handling belong to the person who sends.

## Paid placements and sponsorships

- Local sponsorships, chamber memberships, pay-to-play "best of" awards and managed placement vendors are spend. Recommend them only with the cost as `[NEEDS PROOF: new — <cost>]`, rel=sponsored expected, and a stop for the account lead plus the client's approver (J-1). Never commit, pay or sign up.
- Value them for local relevance, mentions and community proof; don't promise ranking lift.
- Managed placement vendors (e.g. the one in SKILL.md's Tools table) are never a BML default. If one is proposed, run the vetting checks in [risk-policy.md](risk-policy.md).
- A disavow file (only after a manual action, per risk-policy.md) is prepared for a person to review and upload; the agent never submits it.

## Measurement targets

Baseline first: referring domains per target URL (Semrush), rankings (Semrush or Search Console via Windsor), referral conversions (GA4 via Windsor), each with its pull date. 30- and 90-day targets are ranges labeled as BML estimates in the agency plan, not promises to the client.

## Tracker, write-back and conflicts

- One tracker per client in Drive `OUTPUTS/SEO` (`<CODE>_Link_Tracker`, folder resolved by ID; never create one), using the upstream columns. Contacts are public business contacts from the site itself; no enrichment tools, no client customer data.
- Status moves past `drafted` only when a person records it (`approved`, `sent`, …).
- Findings that answer an OPEN row (L-8, L-9, L-11, L-12) are staged as DRAFT in the miner format (context-rules §10). Listing errors go under fix-now findings. Nothing is written to ClickUp without the user's approval.
- **Competing clients:** don't open another client's tracker or folders (one client per run). Before outreach, ask the account lead whether another BML client in the same category and market is pursuing the same prospects (lists, chamber spotlights, dealer pages), and note the answer in the batch summary. Never move one client's prospects, relationships or drafts into another's work.

## Disambiguation

- **link-building vs seo-audit:** off-site authority vs on-site and technical.
- **link-building vs directory-submissions:** local citation **audit** and earned local links here; startup/SaaS directory submission there. Submitting or claiming listings is a person's job, not an agent's.
- **link-building vs public-relations:** link and mention prospects here; news pitching there.
