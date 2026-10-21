> BML file: this whole file is a Baker Labs (BML) addition to the upstream `schema` skill; it is not upstream content.

# Schema for BML clients

Read `../../../bml/context-rules.md` first. This file adds what schema work needs on top of it. Where it conflicts with `schema-examples.md`, this file wins for BML client work: the upstream examples contain sample values that must never be copied.

## Contents
- Step 0: gate and inputs
- Sources of truth
- Type picker
- Segment rules (clinical, home services, professional services, multi-location)
- Ratings and reviews
- Prices
- Hours and other volatile facts
- FAQPage
- Templates (placeholders only)
- Wix
- Validation with BML tools
- Deliverable, hand-off and write-back
- Disambiguation

## Step 0: gate and inputs

1. Staged file present and for this client (else run `product-marketing` Load). One client per run; never reuse another client's `@id`s, values or files. An `INTAKE DRAFT` file has no scope gate but every fact is `DRAFT`: deliver only a type plan for internal or pitch use, marked "from public research", never paste-ready markup.
2. Scope: schema is authorized by either page 00 service line — `SEO` or `Website` (Website usually covers technical site changes) — `Active` → full package. `Active — recommendations only` / `planning only` → a type plan and findings, no paste-ready code; say what the qualifier excludes. Neither line present → stop: "Neither SEO nor Website is in [ABC]'s retainer."
3. Segments and platform (page 00 §8) from the staged file. Ask only if missing.
4. The live page(s) to mark up. Read them; don't browse Drive or search ClickUp broadly.

## Sources of truth

A property is filled only when the value is (a) in page 13 or a cited row at `APPROVED` or `PROVISIONAL` and (b) visible on the approved live page. Exception: `url`, `logo` and `@id` values come from the live site. If either is missing, omit the property and list `[NEEDS PROOF: …]`. If the page, the row and GBP disagree, don't pick one: omit the property, list the mismatch under Fix-now, and report it as a conflict for the monthly check (`context-rules.md` §10). Never edit a row, the site or GBP to resolve it. GBP is checked read-only (Windsor.ai) and is a comparison point, never a source.

| Property | Source | Notes |
|---|---|---|
| `name`, `legalName` | page 07 business profile rows | Exactly as on GBP |
| `url`, `logo`, `image` | live site; images only with J-6 release | Never AI images presented as the business or real projects |
| `telephone` | location row (must match GBP) | Primary listing number, never a call-tracking number |
| `address` | location row (must match GBP) | Service-area business with hidden GBP address → locality and region only |
| `areaServed` | B-8, L-1 (core towns only) | L rows are research: use the core list the client confirmed |
| `openingHoursSpecification` | location hours row (proposed new row) | See Hours |
| `makesOffer` / `Service` | D-1 and page 08 offerings | Every service the client offers; capacity and season (B-6, I-10) are context, never a reason to leave one out |
| `offers.price`, `priceRange` | D-4 | See Prices |
| `sameAs` | profile/listing rows on page 07 | Only profiles the client controls |
| `employee` / provider `Person` | approved provider roster row | Credentials per J-3 |
| `hasCredential` (license) | J-3 | Home services: license number only where J-3 requires or allows |
| `description` | approved page copy, verbatim or trimmed | Checked against page 12, F-13, H-5; no new claims |
| `aggregateRating`, `review` | see Ratings and reviews | Default: omit |

Location, hours, phone and provider rows don't exist in the Master Question Bank yet. Until they do, use an `APPROVED` or `PROVISIONAL` value cited in page 13 or mark `[NEEDS PROOF: new — <fact>, <location>]`.

## Type picker

Pick the most specific Schema.org type that matches B-1 and the page. Check schema.org for the current hierarchy before using a type.

| Client | Homepage | Location page | Service page |
|---|---|---|---|
| Clinical | `MedicalOrganization` (or `Organization`) | `MedicalClinic`, `Dentist`, `Optician`, `DiagnosticLab` or another `MedicalBusiness` / `MedicalOrganization` subtype | `MedicalProcedure`/`Service` named as on the page, no outcome properties |
| Home services | `HomeAndConstructionBusiness` subtype (`GeneralContractor`, `RoofingContractor`, `Plumber`, `Electrician`, `HVACBusiness`, `HousePainter`) | same subtype per location | `Service` with `provider`, `areaServed`, `serviceType` |
| Professional services | specific type (`LegalService`, `AccountingService`, `FinancialService`, `InsuranceAgency`, `RealEstateAgent`) | same | `Service` |
| Other local business | closest `LocalBusiness` subtype | same | `Service` |

- Schema.org marks `ProfessionalService` and `Attorney` as deprecated; use a specific subtype, or `LocalBusiness` + `Service`.
- `SoftwareApplication` and `Product` are for clients a row says sell software or physical goods. A service package is a `Service` with an `Offer`, not a `Product`.
- Every page: `BreadcrumbList` where breadcrumbs are visible; `WebSite` (site name) on the homepage only.
- Blog posts: `BlogPosting` with `author` from the provider/staff roster or the Organization; never an invented person.
- For local clients the main value is entity clarity (business, locations, services, providers) for Google local and AI search. LocalBusiness markup by itself yields no stars or rich result; don't promise one.

## Segment rules

**Clinical** (`context-rules.md` §7 applies in full)
- No patient data anywhere: no patient names, stories, conditions or dates in markup or examples.
- No `MedicalCondition`/`MedicalTherapy` properties that state efficacy, outcomes or safety. Clinical claims only from approved published copy, flagged for provider review.
- Providers (`Person` / physician types) only from the approved roster; credentials and specialties per J-3; `isAcceptingNewPatients` only from a dated row.
- Medical review attribution on articles (`reviewedBy`) only for a named, row-backed provider who actually reviewed it.
- No rating or review markup.
- Tracking pixels and lead forms are not schema decisions; flag, don't add.

**Home services**
- License (`hasCredential`) per J-3.
- Service-area businesses: `areaServed` from B-8 / L-1 core; street address only if GBP shows it.
- Project images only with a J-6 release; never AI-generated images as projects.
- List every service the client offers; note capacity or season (B-6, I-10) as context in the notes, never drop a service from markup for it.

**Professional services and real estate**
- Credentials and disclosures per J-3. No outcome language (case results, returns, sale prices) in `description` unless a row permits it.

**Multi-location**
- Homepage: one parent `Organization` with `@id` `<site-root>/#organization`, built from the parent brand's rows.
- Each location page: one LocalBusiness subtype with `@id` `<location-page-url>#location`, `parentOrganization` → the parent `@id`, and only that location's rows (suffixed rows like L-4a).
- Never put two locations' NAP or hours in one entity, and never copy one location's providers, proof or hours into another.
- Franchisor rules (J-3) apply to every location's markup.
- Wix dynamic location pages: use a structured-data preset bound to collection fields, after checking every collection value against the rows.

## Ratings and reviews

- Google treats rating and review markup about a business on its own site (`LocalBusiness`, `Organization`, and services they offer) as self-serving: it isn't eligible for star snippets. Don't add it.
- Never mark up ratings or reviews copied from Google, Yelp, Healthgrades, Houzz or any third-party site.
- Allowed only on `Product`, `Course` or `Event` pages where the reviews were collected first-party and are visible on that page, the rating comes from a verified row, and the value carries "⚠ confirm before publishing".
- Never reviewer names, patient names or quotes that identify a person. Clinical clients: no review markup at all.
- A request for stars in Google for a local business gets this explanation, not markup.

## Prices

`offers.price`, `priceSpecification` and `priceRange` only for services where D-4 says the client approved publishing prices, with the value from that row. Otherwise omit the property and note `[NEEDS PROOF: D-4]`. Don't write "Call for pricing" into markup.

## Hours and other volatile facts

- Hours, providers accepting patients, prices, promotions and any rating are volatile. Use them only from the staged file's rows, ≤90 days old (the date is the row's source date or the staged file's Volatile facts as-of date; no date → treat as stale), and mark them "⚠ confirm before publishing" in the sources table.
- Hours must match GBP for that location. Holiday hours (`specialOpeningHoursSpecification`) only from a dated row.
- No usable row → omit the property and list `[NEEDS PROOF: new — hours, <location>]`. Never fill hours from the live site alone.
- Keeping hours in sync is a scheduled check, not something this skill repeats.

## FAQPage

Google no longer shows FAQ rich results. For BML clients, add FAQPage only when ai-seo or the content plan calls for it and the FAQ is approved, visible copy. Never offer it as a Google rich-result tactic. Answers are taken verbatim from the page and checked against guardrails; clinical answers are flagged for provider review; competitor names follow J-4.

## Templates (placeholders only)

Fill every `<…>` from rows. Remove any property whose row is missing rather than leaving the placeholder.

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "Organization",
      "@id": "<site-root>/#organization",
      "name": "<row: business name>",
      "url": "<site-root>",
      "logo": "<logo-url>",
      "sameAs": ["<row: profile-url>"]
    },
    {
      "@type": "<LocalBusiness subtype>",
      "@id": "<location-page-url>#location",
      "name": "<row: location name>",
      "parentOrganization": { "@id": "<site-root>/#organization" },
      "url": "<location-page-url>",
      "telephone": "<row: primary phone>",
      "address": {
        "@type": "PostalAddress",
        "streetAddress": "<row: street, only if shown on GBP>",
        "addressLocality": "<row: town>",
        "addressRegion": "<row: region>",
        "postalCode": "<row: postal code>",
        "addressCountry": "<row: country>"
      },
      "areaServed": [{ "@type": "City", "name": "<row: B-8 / L-1 town>" }],
      "openingHoursSpecification": [{
        "@type": "OpeningHoursSpecification",
        "dayOfWeek": ["<row: day>"],
        "opens": "<row: hh:mm>",
        "closes": "<row: hh:mm>"
      }]
    },
    {
      "@type": "Service",
      "@id": "<service-page-url>#service",
      "name": "<D-1 service name as on the page>",
      "serviceType": "<service>",
      "provider": { "@id": "<location-page-url>#location" },
      "areaServed": [{ "@type": "City", "name": "<row: town>" }]
    }
  ]
}
```

## Wix

Check Wix's current help center before giving click paths; menus change.

1. **See what's there.** Run Rich Results Test / Schema.org Validator on the live URL. Wix adds its own markup for some page types (for example blog posts and app pages). Note duplicates as Fix-now findings.
2. **Per-page markup:** page's SEO settings → Advanced SEO → Structured data markup → add markup, paste JSON-LD without `<script>` tags. Respect Wix's size and count limits.
3. **Page types and dynamic pages:** Dashboard → Marketing & SEO → SEO Settings → page type → structured data. Edit presets with variables; check that each bound field maps to a row-backed value.
4. **Site-wide:** Settings → Custom Code → head, all pages: Organization and WebSite only.
5. **Never** apply changes through a Wix connector or API, even when one is connected and the user asks. The agent may read the live page and validate; a person implements after internal review (and J-1 approval where markup restates client-facing text not yet approved).
6. **Rollback note:** list each markup item added and where, so a person can remove it.

Other platforms (WordPress, custom stacks) only if page 00 §8 says the client uses them; the upstream Implementation section covers them.

## Validation with BML tools

- Rich Results Test (supported Google features) and Schema.org Validator (vocabulary) on every page.
- Semrush Site Audit for a site-wide sweep of markup errors, read from the client's existing Site Audit project. Creating a project or starting a new crawl uses Semrush limits: ask first. Semrush is the only SEO data tool.
- Search Console enhancement reports are checked by a person; Windsor.ai's Search Console data covers performance, not markup validity.
- Other crawlers only if the client uses them.

## Deliverable, hand-off and write-back

Package (agency artifact in Baker house style, Ops Manual `02: Baker Style Guide`; don't load client pages 01/02 for it), saved to the client's Drive `OUTPUTS/SEO` resolved by ID from the router. Never search Drive or create folders; if no folder fits, stop and report.

1. Summary: pages covered, types used, what was left out and why.
2. Per page: JSON-LD, sources table (property → row ID, ⚠ flags, `[NEEDS PROOF]`), Wix click path, validation result.
3. Fix-now: NAP mismatches between site, schema and GBP; duplicate entities; markup that contradicts rows. Each is a fix for a person to make; never apply one through Wix, Windsor.ai (GBP or listing edits) or any other connector.
4. Rollback note.
5. Write-back: `DRAFT` rows for `OPEN` questions (see below).
6. Context footer (`context-rules.md` §9), `Distinctiveness: n/a — technical markup`.

Draft one ClickUp task (tags `seo`, `website`, status `internal review`) for the implementer; create it only after the user approves. Markup that restates client-facing text not yet approved also goes to the J-1 approver. Nothing publishes without that human checkpoint.

Recurring checks (hours drift against GBP, markup errors after site edits) are a scheduled task set up by the account lead (see `marketing-loops`), never an in-session loop.

Facts found while doing the work that answer an `OPEN` row (a profile URL, the primary phone) are listed in a Write-back section of the package in the miner review format (`ID | Answer | Source label + link | Confidence | Date`, all `DRAFT`). They are not used in the markup until the row is approved. Nothing is written to ClickUp, page 13 or the staged file.

## Disambiguation

- **schema** writes the markup and the implementation package.
- **seo-audit** finds markup errors among other technical and on-page issues.
- **ai-seo** decides what should be machine-readable for AI search (and may hand FAQPage or entity work to this skill).
