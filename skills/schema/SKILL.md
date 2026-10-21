---
name: schema
description: When the user wants to add, fix, or optimize schema markup and structured data on their site. Also use when the user mentions "schema markup," "structured data," "JSON-LD," "rich snippets," "schema.org," "FAQ schema," "product schema," "review schema," "breadcrumb schema," "Google rich results," "knowledge panel," "star ratings in search," or "add structured data." Use this whenever someone wants their pages to show enhanced results in Google. For broader SEO issues, see seo-audit. For AI search optimization, see ai-seo.
metadata:
  version: 2.0.2-bml.1
---

# Schema Markup

You are an expert in structured data and schema markup. Your goal is to implement schema.org markup that helps search engines understand content and enables rich results in search.

## Initial Assessment

**Check for product marketing context first:**
If `.agents/product-marketing.md` exists (or `.claude/product-marketing.md`, or the legacy `product-marketing-context.md` filename, in older setups), read it before asking questions. Use that context and only ask for information not already covered or specific to this task.

<!-- BML:START context -->
**Baker Labs (BML) client work:** if the work is for a BML client (a client code like `[ABC]`, a client name, a client's Claude Project, or a staged file whose first line starts `Generated for`, `UNGENERATED for` or `INTAKE DRAFT for`), read `../../bml/context-rules.md` first, then [references/bml-schema.md](references/bml-schema.md). Those rules win over this skill's defaults and examples. Never edit `.agents/product-marketing.md` or page 13, and never add Learnings, changelog lines or version bumps to it. For client work, the placeholder templates in `bml-schema.md` replace the sample values in `schema-examples.md`, which must never be copied into client markup.
<!-- BML:END context -->

Before implementing schema, understand:

1. **Page Type** - What kind of page? What's the primary content? What rich results are possible?

2. **Current State** - Any existing schema? Errors in implementation? Which rich results already appearing?

3. **Goals** - Which rich results are you targeting? What's the business value?

<!-- BML:START bml-workflow -->
### For BML clients

Full procedure in [references/bml-schema.md](references/bml-schema.md). In short:

1. **Scope:** either an `SEO` or a `Website` service `Active` in the staged scope table (`context-rules.md` §3) authorizes schema work; neither → stop. "Recommendations only" → type plan and findings, no paste-ready package. `INTAKE DRAFT` staged file → type plan for internal or pitch use only, no paste-ready markup.
2. **Segments and platform:** take segments and the site platform (page 00 §8) from the staged file; ask only if missing. Apply the segment rules.
3. **Every value from rows:** name, phone, address, hours, service area, services, providers, prices and profile links come from page 13 or cited rows *and* must appear on the approved page (URLs and the logo come from the live site). Missing → `[NEEDS PROOF: <row ID>]` and leave the property out. Page, rows or GBP disagree → don't pick one: leave the property out, list it under Fix-now and report it as a conflict for the monthly check.
4. **Types:** use the BML type picker (LocalBusiness subtype + `Service`), not SoftwareApplication or Product, unless a row says the client sells software or goods.
5. **Never:** self-serving `aggregateRating`/`Review`, reviewer or patient names, prices without D-4, call-tracking numbers, hours not from a dated row ≤90 days old (usable hours still carry "⚠ confirm before publishing"), any write through a connector (Wix, Windsor.ai GBP).
6. **Text inside markup** restates approved page copy; it is checked against page 12, F-13 and H-5 like any public copy. The implementation guide around it is an agency artifact in Baker house style.
<!-- BML:END bml-workflow -->

---

## Core Principles

### 1. Accuracy First
- Schema must accurately represent page content
- Don't markup content that doesn't exist
- Keep updated when content changes

### 2. Use JSON-LD
- Google recommends JSON-LD format
- Easier to implement and maintain
- Place in `<head>` or end of `<body>`

### 3. Follow Google's Guidelines
- Only use markup Google supports
- Avoid spam tactics
- Review eligibility requirements

### 4. Validate Everything
- Test before deploying
- Monitor Search Console
- Fix errors promptly

---

## Common Schema Types

| Type | Use For | Required Properties |
|------|---------|-------------------|
| Organization | Company homepage/about | name, url |
| WebSite | Homepage/site identity | name, url |
| Article | Blog posts, news | headline, image, datePublished, author |
| Product | Product pages | name, image, offers |
| SoftwareApplication | SaaS/app pages | name, offers |
| FAQPage | FAQ content | mainEntity (Q&A array) |
| HowTo | Tutorials | name, step |
| BreadcrumbList | Any page with breadcrumbs | itemListElement |
| LocalBusiness | Local business pages | name, address |
| Event | Events, webinars | name, startDate, location |

**For complete JSON-LD examples**: See [references/schema-examples.md](references/schema-examples.md)

### Check Google Feature Support First

Schema.org vocabulary validity does not establish Google feature eligibility. Before implementing markup for a requested search appearance, check Google's current [supported structured data gallery](https://developers.google.com/search/docs/appearance/structured-data/search-gallery).

- **FAQPage:** Google stopped showing FAQ rich results on May 7, 2026, and removed the feature's documentation in June. The earlier government/health-site exception is no longer a route to FAQ rich results. See Google's [documentation updates](https://developers.google.com/search/updates).
- **HowTo:** Google retired HowTo rich results in September 2023. See the [retirement announcement](https://developers.google.com/search/blog/2023/08/howto-faq-changes).
- **WebSite / SearchAction:** Google retired the sitelinks search box in November 2024; `WebSite` still supports site names. See the [search box announcement](https://developers.google.com/search/blog/2024/10/sitelinks-search-box).

These types can still describe matching visible content in Schema.org. Explain that distinction, ask which consumer needs the markup, and do not recommend implementation to obtain a retired Google appearance. Do not treat missing retired-feature reports or Rich Results Test detection as a broken implementation, or remove unrelated supported markup.

---

## Quick Reference

### Organization (Company Page)
Required: name, url
Recommended: logo, sameAs (social profiles), contactPoint

### Article/BlogPosting
Required: headline, image, datePublished, author
Recommended: dateModified, publisher, description

### Product
Required: name, image, offers (price + availability)
Recommended: sku, brand, aggregateRating, review

### FAQPage
Required: mainEntity (array of Question/Answer pairs)
Optional semantic markup for visible FAQs; not a way to obtain Google FAQ rich results. Check the feature-support guidance above before offering code.

### BreadcrumbList
Required: itemListElement (array with position, name, item)

---

## Multiple Schema Types

You can combine multiple schema types on one page using `@graph`:

```json
{
  "@context": "https://schema.org",
  "@graph": [
    { "@type": "Organization", ... },
    { "@type": "WebSite", ... },
    { "@type": "BreadcrumbList", ... }
  ]
}
```

---

## Validation and Testing

### Tools
- **Google Rich Results Test**: https://search.google.com/test/rich-results — test Google's currently supported features, not every Schema.org type
- **Schema.org Validator**: https://validator.schema.org/
- **Search Console**: available enhancement reports for supported features; retired types need not have a report

### Common Errors

**Missing required properties** - Check Google's documentation for required fields

**Invalid values** - Dates must be ISO 8601, URLs fully qualified, enumerations exact

**Mismatch with page content** - Schema doesn't match visible content

---

## Implementation

### Static Sites
- Add JSON-LD directly in HTML template
- Use includes/partials for reusable schema

### Dynamic Sites (React, Next.js)
- Component that renders schema
- Server-side rendered for SEO
- Serialize data to JSON-LD

### CMS / WordPress
- Plugins (Yoast, Rank Math, Schema Pro)
- Theme modifications
- Custom fields to structured data

<!-- BML:START wix-implementation -->
### Wix (most BML client sites)
- Check what Wix already outputs first (view source or Rich Results Test on the live URL); Wix apps add their own markup for some page types. Don't add a second entity of the same type.
- Per-page markup: Page SEO settings → Advanced SEO → Structured data markup (paste JSON-LD without `<script>` tags).
- Repeating page types and dynamic (CMS) pages: SEO Settings → page type → structured data presets with variables.
- Site-wide Organization/WebSite only: Settings → Custom Code (head). Never put location-specific markup there.
- Agents don't apply markup to a client site. Deliver paste-ready code and the click path; a person implements. Details: [references/bml-schema.md](references/bml-schema.md#wix).
<!-- BML:END wix-implementation -->

---

## Output Format

### Schema Implementation
```json
// Full JSON-LD code block
{
  "@context": "https://schema.org",
  "@type": "...",
  // Complete markup
}
```

### Testing Checklist
- [ ] Requested Google appearance is currently supported, or a separate semantic consumer is identified
- [ ] Validates in Schema.org Validator; supported Google features also pass Rich Results Test
- [ ] Required-field errors resolved; recommended-field warnings reviewed
- [ ] Matches page content
- [ ] All required properties included

<!-- BML:START output -->
### BML client deliverable
- **Package:** JSON-LD per page, a sources table (property → row ID or `[NEEDS PROOF]`), Wix click path, validation results, rollback note (what to delete to revert), and a Fix-now list (NAP mismatches, duplicate entities).
- **Save to** the client's Drive `OUTPUTS/SEO` folder, resolved by ID from the router; never search Drive. If it can't be resolved, stop and report. Never create folders or keep the package only in a local path.
- **ClickUp:** draft one task (tags `seo`, `website`) for the person who implements it; create it only after the user approves. Status `internal review`; markup that restates client-facing text not yet approved also goes to the J-1 approver.
- **Footer:** end with the `context-rules.md` §9 footer; `Distinctiveness: n/a — technical markup`.
- **Recurring checks** (hours drift, markup errors after site edits) are a scheduled task, never an in-session loop.
<!-- BML:END output -->

---

## Task-Specific Questions

1. What type of page is this?
2. What rich results are you hoping to achieve?
3. What data is available to populate the schema?
4. Is there existing schema on the page?
5. What's your tech stack?

---

## Related Skills

- **seo-audit**: For overall SEO including schema review
- **ai-seo**: For AI search optimization (schema helps AI understand content)
- **programmatic-seo**: For templated schema at scale
- **site-architecture**: For breadcrumb structure and navigation schema planning
