> Baker Labs (BML) file: everything here is BML-specific and not part of upstream marketing-skills.

# BML Site Architecture: Local Service Clients

Load for any Baker Labs client run, after `../../../bml/context-rules.md`. Facts (services, towns, locations, providers, licenses) come only from page 13 or cited rows; everything shown here in `<angle brackets>` is a placeholder. Missing facts are marked `[NEEDS PROOF: <row ID>]`, never guessed.

## Contents
- Where the inputs come from
- Gates: scope, services, guardrails
- Local templates (home services, clinical, professional services)
- Multi-location
- Locations and service areas
- Conversion paths, header and footer
- Internal linking priority
- Platform choice and Wix
- Inventory and migration with BML's tools
- Output, approvals and write-back

## Where the inputs come from

Read order: router → staged page 13 → Monthly Context Brief → source pages only if needed (detail behind a cited row, topic filtering, or a stale page 13; context-rules §1). Never browse Drive or search ClickUp broadly. One client per run: never carry another client's tree, towns, providers or proof into this plan.

| Planning question | Source |
|---|---|
| What the business does, segment(s) | Page 13 header, B-1 |
| Audiences and what they need on the site | 03, 04 |
| Services and which matter most | 08, D-1 |
| Capacity and seasons (context only, never a gate) | B-6, I-10 |
| Service area, towns | B-8, L-1 (core vs edge) |
| Locations, hours, NAP | 07 rows; "Volatile facts" → ⚠ confirm before publishing |
| Local demand by service and town | L-3 (Semrush) |
| Competitors' site patterns | L-4, L-6 (planning only; public pages follow page 12) |
| Current platform (starting point, not the default) | Page 00 §8 |
| Required CTA wording, lead handling | 01, I-3 |
| Approver | J-1 |

## Gates

1. **Scope** (context-rules §3). Either a Website or an SEO line `Active` on page 00 authorizes site-architecture: the full plan plus a build checklist for a person. A "planning only" qualifier → deliver the plan (trees, URL map, nav spec, linking plan, and any redirect map as old → new pairs), with no implementation or launch checklist, and say what the qualifier excludes. No covering line → stop: "<service> isn't in [CODE]'s retainer", and offer a scope note for the account lead. `INTAKE DRAFT` (prospect, no page 00): no scope gate; the plan is internal or pitch material marked "from public research", and the platform comes from public research, not page 00.
2. **Services.** Plan a page, with normal nav and dropdown placement, for every service on page 08; D-1 sets the order and priority. Capacity and seasons (B-6, I-10) are not a gate: they may be noted as context in the plan, but never remove a page, demote it from nav or hold it back. Never plan a page for a service not on page 08.
3. **Guardrails.** Page names, labels and sections pass page 12, F-13, H-5 and §7 at any status, including DRAFT (e.g. no urgency or "24/7 emergency" framing under clinical rules, no "guaranteed results"). Comparison or "vs" sections only if no page 12 row blocks naming competitors; otherwise stop and name the row. Comparison pages themselves → `competitors` skill.

## Local templates

Use these as starting trees; delete branches the record doesn't support. Depth: 2 levels for single-location, 3 for multi-location.

**Home services and construction**
```
Homepage (/)
├── Services (/services)
│   └── <Service> (/services/<service>)            ← every page 08 service; D-1 sets order
├── Projects (/projects)                           ← only with J-6 releases; no AI images as real work
│   └── <Service> projects (/projects/<service>)
├── Service Area (/service-area)                   ← B-8 / L-1
│   └── <Town> (/service-area/<town>)              ← only per the location rules below
├── Reviews (/reviews)                             ← G rows; no reviewer names
├── Process / Financing (/process, /financing)     ← only if 08 rows support them
├── About (/about)                                 ← license details per J-3
├── Blog (/blog)
└── Contact / <Request an estimate> (/contact)
```

**Clinical practice**
```
Homepage (/)
├── Services or Treatments (/services/<service>)   ← clinical claims only from approved copy
├── Conditions (/conditions/<condition>)           ← only if approved copy exists; never tied to a person
├── Providers (/providers/<provider-slug>)         ← one per provider on file; credentials per J-3
├── Patient Resources (/patients)
│   ├── Insurance and Payment (/patients/insurance)
│   ├── New Patients / Forms (/patients/new)       ← form handling: compliance review required
│   └── FAQ (/patients/faq)
├── Locations (/locations/<city>)                  ← see Multi-location
├── Reviews (/reviews)                             ← patient stories need G-5 / J-6
├── About (/about)
└── <Book / Request an appointment> (/book)        ← tracking and forms: flag for a person, don't add pixels
```

**Professional services**
```
Homepage (/)
├── Services (/services/<service>)
├── Industries or Clients served (/industries/<industry>)   ← only if 03 supports it
├── Team (/team/<person-slug>)                              ← credentials and disclosures per J-3
├── Results / Case studies (/results/<slug>)                ← no outcome guarantees unless a row permits; slug by topic, never a client name without permission
├── Insights (/insights)
├── About (/about)
└── Contact / <Schedule a consultation> (/contact)
```

- Slugs are by service, town or topic, never by a customer's or patient's name. Project pages never show a customer's street address.
- A Reviews or Projects section exists only if G rows carry the permission (G-5, J-6). No reviewer names, no patient details, no AI-generated imagery presented as real projects.
- Clinical booking, contact and form pages are marked "tracking and form handling: compliance review required". Don't specify pixels or third-party form tools.

## Multi-location

- Parent brand owns the hierarchy, voice and guardrails; locations hold only their own rows (context-rules §7). J-3 franchisor rules apply on every location page.
- Pattern: `/locations/` hub → `/locations/<city>` (one per staffed location with a Google Business Profile; the plan recommends that the GBP website link point here, and a person makes that change) → `/locations/<city>/<service>` only where the service offering or demand (L-3 per location) differs by location.
- Each location page carries only its own NAP, hours, providers/team, reviews and proof. Never reuse one location's providers, hours or testimonials on another's page.
- The services hub stays brand-level (`/services/<service>`) and links to the locations that offer it.
- Run the scope gate per location.

## Locations and service areas

- **Location page** = a real, staffed address with a GBP. NAP matches GBP exactly.
- **Service-area pages** only for B-8 / L-1 *core* towns where the record has local proof (a G row, a released project in that town, or a location-specific fact). Edge towns and towns without proof are listed on one `/service-area` page.
- No near-duplicate town pages with swapped names (doorway pages).
- More than about 10 town or town×service pages → plan the hub and URL pattern here and hand the page set to `programmatic-seo`.

## Conversion paths, header and footer

- Conversions: call, booking, form or signed job unless rows say otherwise. Header CTA rightmost, using 01's required CTA language; click-to-call visible in the sticky mobile header. Don't promise response times beyond I-3.
- Header (4–6 items): `<Services> | <Projects or Providers> | <Service Area or Locations> | <Reviews> | <About>` + CTA.
- Footer: NAP and hours per location (⚠ confirm before publishing), service-area list, license numbers where J-3 requires, privacy and accessibility links, social profiles on file. This replaces upstream's Product/Resources/Company footer columns.

## Internal linking priority

D-1 priority services → location / service-area pages → reviews and projects → contact/booking. Each blog post links up to the one service page it supports; service pages link to the matching projects or providers and the relevant location pages. The page each GBP links to gets strong internal links. This replaces upstream's "key feature pages, pricing" priority.

## Platform choice and Wix

- Platform questions follow upstream [platforms-and-migration.md](platforms-and-migration.md): reason through its questions and give a neutral shortlist of two or three options with what would tip the choice. No platform is the BML default; the current platform (page 00 §8) is a starting point, and Wix is one option among others. The shortlist is a recommendation; any platform change is decided by a person with the client's approver (J-1).
- Whenever a Verified Partner (◆) tool is named, keep the repository disclosure and name an alternative alongside it.
- Wix notes (information, for when the site is or would be on Wix): before proposing nested static-page URLs or changing blog or dynamic-page URL prefixes on Wix, check current Wix capability (Wix MCP documentation or help-centre search) and the site's existing URL patterns; prefer keeping existing URLs.
- Redirects are listed as one-to-one old → new pairs for a person to enter in Wix's 301 redirect manager.
- Wix MCP use, if any, is read-only (site and page lists, existing redirects). Never call write, publish or deploy tools.

## Inventory and migration with BML's tools

- Current-state inventory: the site's page list (Wix, read-only), Semrush Site Audit and Organic Research (Semrush is the only SEO data tool), and Search Console + GA4 via Windsor.ai for top pages by clicks and conversions. Other crawlers (Screaming Frog, Sitebulb) only if the client uses them.
- Migration and launch steps in `platforms-and-migration.md` become a checklist for a person, with the J-1 approver named (left out under a "planning only" qualifier; see Gates). Never call write actions on any connector (Wix site changes, Windsor.ai Business Profile or listing edits).
- Post-launch monitoring (Search Console 404s and coverage: daily for 14 days, then weekly for 6 weeks) is proposed as a scheduled task via `marketing-loops`, created only after the user approves. Never an in-session loop.

## Output, approvals and write-back

- The plan is an agency artifact: Baker house style (Ops Manual `02: Baker Style Guide`); don't load client pages 01/02 except 01's CTA and naming rows for labels.
- Save to the client's Drive `OUTPUTS/WEBSITE`, resolved by ID from the router. Never search Drive and never create folders; if none fits, stop and report.
- Draft a ClickUp task tagged `website` (status `internal review`); create it only after the user approves.
- Nothing publishes, sends or spends without a human checkpoint and the client's approver (J-1).
- Inventory facts that answer an `OPEN` row (services the site lists that D-1 doesn't, towns named on the site, locations) go in a "Proposed rows" table in context-rules §10 format, as `DRAFT`. Never written to ClickUp by the agent.
- End the deliverable with the context footer (context-rules §9).
