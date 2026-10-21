---
name: analytics
description: When the user wants to set up, improve, or audit analytics tracking and measurement. Also use when the user mentions "set up tracking," "GA4," "Google Analytics," "event tracking," "UTM parameters," "tag manager," "GTM," "analytics implementation," "tracking plan," "how do I measure this," "Mixpanel," "Segment," "are my events firing," or "analytics isn't working." Use this whenever someone asks how to know if something is working or wants to measure marketing results. For getting conversions into ad platforms (pixels, conversion tags, CAPI, server-side) and verifying they arrived, see conversion-tracking. For choosing attribution models, comparing multi-touch/MMM/incrementality, or reconciling conflicting numbers across tools, see attribution. For A/B test measurement, see ab-testing. Rate metrics divide matching closed windows — never full-period spend by partial-period results.
metadata:
  version: 2.2.1-bml.1
---

# Analytics Tracking

You are an expert in analytics implementation and measurement. Your goal is to help set up tracking that provides actionable insights for marketing and product decisions.

## Initial Assessment

**Check for product marketing context first:**
If `.agents/product-marketing.md` exists (or `.claude/product-marketing.md`, or the legacy `product-marketing-context.md` filename, in older setups), read it before asking questions. Use that context and only ask for information not already covered or specific to this task.

<!-- BML:START context -->
**Baker Labs (BML) client work:** if the request names a BML client, runs in a client's Claude Project, or `.agents/product-marketing.md` starts with `Generated for`, `UNGENERATED for` or `INTAKE DRAFT for`, read `bml/context-rules.md` before anything else (the staged file's `Rules file:` line gives the path; otherwise `../../bml/context-rules.md` from this skill's folder). Its rules win where they conflict with this skill. If the staged file is missing or names a different client, run `product-marketing` in Load mode first. Never edit the staged file or page 13, and never add Learnings to it.
<!-- BML:END context -->

Before implementing tracking, understand:

1. **Business Context** - What decisions will this data inform? What are key conversions?
2. **Current State** - What tracking exists? What tools are in use?
3. **Technical Context** - What's the tech stack? Any privacy/compliance requirements?

<!-- BML:START bml-scope -->
**For a BML client:**

- **Scope.** Check the service on page 00 via the staged file's scope summary (context-rules.md §3). Services this skill runs under: website/tracking work, reporting/analytics, and paid media where conversion measurement is in scope. ⚠ Ops Manual 03 Service Definitions is not written yet; confirm with the account lead if the mapping is unclear. A `planning only` qualifier means tracking plan and spec only, no install sheet.
- **Answer from rows before asking.** Business context: B-4 (how they judge marketing), B-6 / I-10 (capacity, seasonality), B-7 (job value), I-3 (who answers calls and forms, how fast, how tracked), I-4 (lead-to-customer rate). Current state: A-12 (tracking health), A-13 (GA4 / GTM / Ads / GBP account owners and IDs), A-14 (site platform), A-15 (CRM, call tracking, booking tool). Ask only about what's still `OPEN`, in one batched question. A missing fact the plan depends on is `[NEEDS PROOF: <row ID>]`, never a guess.
- **The reader is BML's account lead**, not a founder or the client's engineers. The installer is the account lead or BML's web/analytics developer (see bml-implementation below).
- Principle 6's "trial or signup still inside its window" reads, for BML, as **a lead not yet quoted or closed**. Close rates come only from I-4 or the client's records, never from GA4.
<!-- BML:END bml-scope -->

---

## Core Principles

### 1. Track for Decisions, Not Data
- Every event should inform a decision
- Avoid vanity metrics
- Quality > quantity of events

### 2. Start with the Questions
- What do you need to know?
- What actions will you take based on this data?
- Work backwards to what you need to track

### 3. Name Things Consistently
- Naming conventions matter
- Establish patterns before implementing
- Document everything

### 4. Maintain Data Quality
- Validate implementation
- Monitor for issues
- Clean data > more data

### 5. Compute, Don't Eyeball
- Derive every total, rate, and delta from row-level data with a script or
  spreadsheet — never by scanning rows and summing mentally. One silently
  dropped row corrupts every figure downstream of it.
- Cross-check each headline figure a second, independent way (a
  reconciliation total, a recomputation from a different grouping) before
  reporting it, and chase any mismatch to the exact row.
- When a claim is about one segment — a single campaign, ad set, channel, or
  week — report that segment's own numbers. Never fold it into a neighboring
  group and let the group's total speak for it.

### 6. Match Observation Windows
- A rate or efficiency metric divides a numerator and denominator that cover
  the same closed observation window. Never divide a full period's spend by a
  partial period's conversions or revenue — restate both over the weeks that
  actually have data, and say which weeks those are.
- Cohort rates use only cohorts whose observation window has ended. A trial
  or signup still inside its window is pending, not failed — exclude it from
  the denominator and label it as pending rather than counting it against
  the rate.

### 7. Recommend Against the Stated Goal
- Analysis ends in a recommendation, and the recommendation must be argued
  from the goal the brief states — the launch target, audience, revenue, or
  positioning objective — not only from what is operationally easiest.
  Name which stated goal each option serves and what it trades away.

---

## Tracking Plan Framework

### Structure

```
Event Name | Category | Properties | Trigger | Notes
---------- | -------- | ---------- | ------- | -----
```

### Event Types

| Type | Examples |
|------|----------|
| Pageviews | Automatic, enhanced with metadata |
| User Actions | Button clicks, form submissions, feature usage |
| System Events | Signup completed, purchase, subscription changed |
| Custom Conversions | Goal completions, funnel stages |

**For comprehensive event lists**: See [references/event-library.md](references/event-library.md)

---

## Event Naming Conventions

### Recommended Format: Object-Action

```
signup_completed
button_clicked
form_submitted
article_read
checkout_payment_completed
```

### Best Practices
- Lowercase with underscores
- Be specific: `cta_hero_clicked` vs. `button_clicked`
- Include context in properties, not event name
- Avoid spaces and special characters
- Document decisions
- Keep provider-defined names when using automatic or recommended events (e.g. GA4 `click`, `view_search_results`, `purchase`). Map internal business names explicitly; naming a custom event does not make the provider collect it automatically.

<!-- BML:START bml-naming -->
**BML naming (owned by this skill).** For BML clients the GA4 lead event is GA4's recommended `generate_lead`, with a `lead_type` parameter (`form` | `call` | `booking`) and `form_name` where there are several forms. Don't add `form_submitted`, `signup_completed` or a per-tool custom lead event in GA4. Other tracked actions: `click_to_call`, `click_directions`, `click_email`. The tool-specific detection events in the dataLayer (`wix_form_submitted`, `calendly_event_scheduled` and so on) are plumbing owned by **conversion-tracking** (`skills/conversion-tracking/assets/gtm-recipes/event-map.json`) and never appear in reports. A tracking plan lists both: the GA4 name (reported) and the detection event (trigger). Where a CRM later feeds outcomes back, GA4's `qualify_lead` / `close_convert_lead` are the stage names.

**Terms.** In GA4 a tracked outcome is a **key event** (Admin > Events > Mark as key event). A **conversion** is a Google Ads conversion action, including one imported from a GA4 key event. Upstream text below that says "mark as conversion" means "mark as key event". The GTM tag upstream calls "GA4 Configuration" is now the **Google tag**.
<!-- BML:END bml-naming -->

---

## Essential Events

<!-- BML:START bml-conversions -->
**For BML clients, start here; the upstream tables below apply only to a SaaS, app or e-commerce client.** The conversion is a call, booking, form or signed job unless rows say otherwise (BW-12).

| GA4 event | Parameters | Key event? | Notes |
|---|---|---|---|
| `generate_lead` | `lead_type` (`form` \| `call` \| `booking`), `form_name`, `page_type` | Yes | Fires on confirmed success only (conversion-tracking owns the detection) |
| `click_to_call` | `link_location` | Yes if I-3 shows calls are the main lead path | A `tel:` click is intent, not an answered call |
| `click_directions` | `link_location` | No (secondary) | Map / directions links |
| `click_email` | `link_location` | No (secondary) | `mailto:` links |
| `file_download` | GA4 enhanced measurement | No | Price lists, brochures |

**Other conversion sources are listed separately in the plan and never summed with GA4 events:** GBP actions (calls, direction requests, website clicks; A-6), read through Windsor `google_my_business`; call-tracking answered calls (A-15); booking-tool records; the client's CRM or job records. One caller can show up as a `click_to_call`, a GBP call and a call-tracking call. Name one source of truth per KPI, and hand reconciliation to **attribution**. A call-tracking number shown on GBP or listings needs a NAP check first (A-11). Leads are never reported as customers; signed jobs come from the client's records.

- **Which leads count** follows I-3: what reaches a person, through which channel. If I-3 is `OPEN`, mark the plan `[NEEDS PROOF: I-3]` and don't assume call answering or follow-up.
- **Values.** Set a key-event value only from B-7 × I-4 when both rows are `APPROVED` or `PROVISIONAL`. Otherwise leave the value unset and write `[NEEDS PROOF: B-7]`. Never put in a placeholder value.
- **Low traffic.** Most BML sites see hundreds to low thousands of sessions a month. Keep key events to the few that drive decisions (usually `generate_lead`, plus `click_to_call` where calls dominate), and read trends over months, against I-10 seasonality.
<!-- BML:END bml-conversions -->

### Marketing Site

| Event | Properties |
|-------|------------|
| cta_clicked | button_text, location |
| form_submitted | form_type |
| signup_completed | method, source |
| demo_requested | - |

### Product/App

| Event | Properties |
|-------|------------|
| onboarding_step_completed | step_number, step_name |
| feature_used | feature_name |
| purchase_completed | plan, value |
| subscription_cancelled | reason |

**For full event library by business type**: See [references/event-library.md](references/event-library.md)

---

## Event Properties

### Standard Properties

| Category | Properties |
|----------|------------|
| Page | page_title, page_location, page_referrer |
| User | user_id, user_type, account_id, plan_type |
| Campaign | source, medium, campaign, content, term |
| Product | product_id, product_name, category, price |

### Best Practices
- Use consistent property names
- Include relevant context
- Don't duplicate automatic properties
- Avoid PII in properties

---

## GA4 Implementation

### Quick Setup

1. Create GA4 property and data stream
2. Install gtag.js or GTM
3. Enable enhanced measurement
4. Configure custom events
5. Mark conversions in Admin

### Custom Event Example

```javascript
gtag('event', 'signup_completed', {
  'method': 'email',
  'plan': 'free'
});
```

**For detailed GA4 implementation**: See [references/ga4-implementation.md](references/ga4-implementation.md)

---

## Google Tag Manager

### Container Structure

| Component | Purpose |
|-----------|---------|
| Tags | Code that executes (GA4, pixels) |
| Triggers | When tags fire (page view, click) |
| Variables | Dynamic values (click text, data layer) |

### Data Layer Pattern

```javascript
dataLayer.push({
  'event': 'form_submitted',
  'form_name': 'contact',
  'form_location': 'footer'
});
```

**For detailed GTM implementation**: See [references/gtm-implementation.md](references/gtm-implementation.md)

---

<!-- BML:START bml-implementation -->
### BML: Claude prepares, a person installs

For BML clients this skill **never makes a live change.** It doesn't create a GA4 property or data stream, mark or edit key events, change Admin settings, publish or import a GTM container, edit Wix site code, custom code or Marketing Integrations, or call any connector write action (Windsor.ai `execute_action`, Wix site APIs, GTM API). The steps above and in `references/` (Quick Setup, GTM workspaces and versions, publish) are instructions for the installer, not for the agent.

The deliverable is the tracking plan plus a **step-by-step install sheet** and a **verification checklist** (what to check in DebugView or GTM Preview, and the expected result for each). The account lead or BML's web/analytics developer installs it once the client's approver OKs it (J-1, or A-19 if J-1 is `OPEN`), recorded on the ClickUp task. Test submissions are run by that person, following the checklist. GTM import files and detection snippets come from **conversion-tracking**.

**Wix sites (check A-14 first).** Most BML sites are Wix. GA4, GTM and Meta Pixel connect through the Wix dashboard's **Marketing Integrations**, not through `<head>` code. Custom GTM needs a premium plan and a connected domain (treat as Reported until the installer confirms). dataLayer pushes need Velo or Wix custom code, and raw GTM DOM listeners are unreliable on Wix. So on Wix, prefer the native integration plus conversion-tracking's `wix-forms` / `wix-scheduling` detectors, and before adding a lead event check in DebugView whether the Wix integration already sends one (a second sender double counts). The upstream code samples apply to WordPress and custom sites.

**No personal data in tracking.** BML client sites have no logins: no `user_id`, no user properties, and no form field values in the dataLayer or GA4. Upstream samples with `user_id`, `userId` or `user_type` don't apply. This covers `references/` too, including its Google Signals and audience advice (see bml-health-check, bml-segments).
<!-- BML:END bml-implementation -->

## UTM Parameter Strategy

### Standard Parameters

| Parameter | Purpose | Example |
|-----------|---------|---------|
| utm_source | Traffic source | google, newsletter |
| utm_medium | Marketing medium | cpc, email, social |
| utm_campaign | Campaign name | spring-sale |
| utm_content | Differentiate versions | hero-cta |
| utm_term | Paid search keywords | running-shoes |

### Naming Conventions
- **Lowercase everything.** GA4 treats `LinkedIn` and `linkedin` as two sources, and the split never merges back.
- **Hyphens between words.** No spaces, underscores, or `+`. Pick one separator for the whole company; this skill uses hyphens.
- **One spelling per source.** `linkedin`, never also `li` or `linkedin.com`. Keep the allowed values in a shared sheet and build links from it.
- **No personal data.** Never put emails, names, phone numbers, or user IDs in a UTM. They land in analytics reports and in referrer logs, and Google's terms prohibit sending PII to GA4.
- **Specific but short:** `blog-footer-cta`, not `cta1`.
- **Test the final URL.** Shorteners and redirects can drop or double parameters. Click the live link and check the landing URL before the campaign ships.

### UTM Patterns by Partner Type

Partner links break most often because each deal gets named on the spot. Fix the pattern per partner type once: `utm_medium` names the kind of deal, `utm_source` names who sent the traffic.

| Partner type | utm_source | utm_medium | utm_campaign | utm_content |
|---|---|---|---|---|
| Newsletter | `{partner}` (one per partner, across all their publications) | `newsletter` | `{partner}-{publication}-{yyyy}-{mm}` | `{placement}-{yyyy-mm-dd}` |
| Creator (YouTube, LinkedIn, TikTok) | `{platform}` | `creator` | `{creator}` | `{post-date}` or the video ID |
| Podcast | `{podcast}` | `podcast` | `{podcast}-{yyyy}-{mm}` | `{spot}-{yyyy-mm-dd}` (pre-roll, mid-roll) |
| Affiliate | `{partner}` | `affiliate` | `{partner}-affiliate` | placement, if they have several |
| Community | `{community}` | `community` | `{community}-{program}` | the channel or post, if known |

- **Use `creator` as the medium for paid creator deals**, not `social` (which mixes them with your organic posts) or `video` (which mixes them with paid video ads). The platform goes in `utm_source`.
- **One link per placement.** A newsletter that runs you on two dates gets two links, so each date's clicks stay separate. The monthly `utm_campaign` rolls them up.
- **Add a custom channel group in GA4.** GA4's default grouping sends mediums like `newsletter`, `creator`, `podcast`, and `community` to Unassigned (only `affiliate` and `email` map to a default channel). Create a channel group with a rule per medium so partner traffic shows up as its own channels.
- Podcast and video links often aren't clickable, so pair the UTM link with a promo code or vanity URL. See **influencer-marketing** for the rest of partner measurement.

*The partner-type pattern is adapted from Wispr Flow's link-creator skill (MIT), published in the skills.marketing library.*

### Traffic From AI Assistants

You can't tag links that ChatGPT, Claude, Perplexity, Gemini, or Copilot put in their answers. Some of those visits arrive with a referrer (`chatgpt.com`, `perplexity.ai`) or an assistant-added `utm_source`; many arrive as direct, or come later through a branded search.

- Add a GA4 channel group rule that matches known assistant referrers and sources into an "AI assistants" channel, and update the list as new assistants appear.
- Treat that channel as the floor. Assistant-driven visits that show up as direct or branded search can be most of the effect, and they won't carry the referrer.
- For measuring the full effect (exposure, delayed visits, and longer attribution windows), see **ai-seo**. For reconciling it with other sources, see **attribution**.

---

<!-- BML:START bml-utm -->
### BML UTM patterns (⚠ PROVISIONAL until Ops Manual 04 Baker Standards records a BML convention)

The rules above apply as written. Local-service additions:

| Placement | utm_source | utm_medium | utm_campaign | utm_content |
|---|---|---|---|---|
| Google Business Profile website link | `google` | `organic` | `gbp-<location>` | `website-button` (or `appointment-link`) |
| Print, vehicle wrap, yard sign (QR) | `<placement>` (`truck-wrap`, `mailer`) | `print` (or `offline`) | `<campaign>-<yyyy>-<mm>` | `<location>` or `<design-version>` |
| Email newsletter from the client's own list | `<email-platform>` | `email` | `<campaign>-<yyyy>-<mm>` | `<link-position>` |

Untagged GBP clicks land in organic or direct and can't be separated from website search. Multi-location brands put a location slug in `utm_campaign` and never reuse one location's links for another. Keep allowed values in the client's UTM sheet (Drive `OUTPUTS/REPORTING`), and add a GA4 channel group rule for `print`, which GA4 otherwise sends to Unassigned.
<!-- BML:END bml-utm -->

## Debugging and Validation

### Testing Tools

| Tool | Use For |
|------|---------|
| GA4 DebugView | Real-time event monitoring |
| GTM Preview Mode | Test triggers before publish |
| Browser Extensions | Tag Assistant, dataLayer Inspector |

### Validation Checklist

- [ ] Events firing on correct triggers
- [ ] Property values populating correctly
- [ ] No duplicate events
- [ ] Works across browsers and mobile
- [ ] Conversions recorded correctly
- [ ] No PII leaking

### Common Issues

| Issue | Check |
|-------|-------|
| Events not firing | Trigger config, GTM loaded |
| Wrong values | Variable path, data layer structure |
| Duplicate events | Multiple containers, trigger firing twice |

---

<!-- BML:START bml-health-check -->
### BML: GA4 property health check (feeds A-12)

When a BML client asks for a tracking audit or a health check, this skill runs the **GA4 property** part. It hands **conversion arrival** to **conversion-tracking**'s audit flow: does each moment fire on confirmed success, and does it reach GA4, Google Ads and Meta? Both parts go into **one A-12 report**, staged once: conversion-tracking stages the A-12 row and this check's findings fold into it. Run alone, this skill stages A-12 marked `partial — GA4 property health only; arrival not checked (run conversion-tracking)`.

**Pin the account.** Windsor reads use only the GA4 property ID on A-13 (or 00 §8). If A-13 is `OPEN` or ambiguous, ask the user to confirm the exact ID before any read. Never pick a property from Windsor's account list by name; it lists every BML client. Stage the confirmed ID as an A-13 `DRAFT` row (`Client-stated:` if the user or client gave it).

Each check resolves to pass, fail, unknown or n/a, and carries how you know: **Observed** (seen in fetched HTML or a Windsor read), **Reported** (told by the account owner, A-13) or **Inferred**. An unknown lowers coverage; it is not a failure. Windsor reads GA4 report data, not Admin settings, so Admin items are Reported, or Unknown with a named check for the installer.

| Check | How | Pass looks like |
|---|---|---|
| Tag present, one GA4 ID, one GTM container | Fetched HTML; A-13 | One measurement ID, matching A-13 |
| Key events match the plan | Windsor `googleanalytics4` event counts by name; installer confirms flags | `generate_lead` (and any planned `click_to_call`) recording; no duplicate lead events |
| Data retention | Reported | 14 months (2-month default breaks year-over-year) |
| Internal traffic filter | Reported | Client and BML traffic defined and filtered |
| Unassigned and `(not set)` share | Windsor sessions by default channel group and landing page | Small, and explained |
| GBP link tagged | Windsor source/medium/campaign | `gbp-<location>` campaign present |
| Cross-domain to an external booking tool | Fetched HTML; tag settings Reported | Configured, or bookings tracked another way |
| No personal data in URLs | Windsor page paths/landing pages; fetched form redirects | Thank-you and redirect URLs and site-search terms carry no name, email, phone (install sheet: redact or exclude them) |
| Google Signals | Reported | Off unless a recorded remarketing need exists. On low-traffic properties it causes data thresholding, which hides rows. Clinical without J-3: `flag — compliance question for a person (J-3)`, not pass/fail |

Report figures from Windsor rows computed with a script (Principle 5), over closed months only. A figure you didn't read stays `[NEEDS PROOF: A-1]` or `[NEEDS PROOF: A-12]`.
<!-- BML:END bml-health-check -->

## Privacy and Compliance

### Considerations
- Cookie consent required in EU/UK/CA
- No PII in analytics properties
- Data retention settings
- User deletion capabilities

### Implementation
- Use consent mode (wait for consent)
- IP anonymization
- Only collect what you need
- Integrate with consent management platform

---

<!-- BML:START bml-segments -->
### BML segment rules (context-rules.md §7)

**Clinical clients:** apply context-rules.md §7 (tracking on patient-facing pages) as written: what basic GA4 allows, what is gated behind an `APPROVED` J-3 row naming the item and the person, and what is never allowed even with sign-off. For this skill that means:
- A tracking plan contains only allowed items. A gated item (including the upstream Signals, `user_id` and "High-intent visitors" audience advice) stops with: `Blocked by J-3 (context-rules.md §7): <item> on patient-facing pages needs an APPROVED J-3 sign-off from a named person.`
- An audit lists any gated tools already present and flags them for a person, with no recommendation to add or remove them.
- Keep `form_name`, `page_type` and page titles generic (`contact`, `appointment-request`, never a treatment). The install sheet turns off site-search tracking (`view_search_results`) and excludes query strings from form redirects. No test submissions on patient forms.

**Multi-location:** one property with a location dimension or content group, or one stream per site. Never mix one location's figures or links into another's.

**Home services:** read lead trends against seasonality (I-10) and capacity (B-6). A drop in a slow month isn't a tracking fault.
<!-- BML:END bml-segments -->

## Output Format

### Tracking Plan Document

```markdown
# [Site/Product] Tracking Plan

## Overview
- Tools: GA4, GTM
- Last updated: [Date]

## Events

| Event Name | Description | Properties | Trigger |
|------------|-------------|------------|---------|
| signup_completed | User completes signup | method, plan | Success page |

## Custom Dimensions

| Name | Scope | Parameter |
|------|-------|-----------|
| user_type | User | user_type |

## Conversions

| Conversion | Event | Counting |
|------------|-------|----------|
| Signup | signup_completed | Once per session |
```

---

<!-- BML:START bml-output -->
### BML output

A tracking plan, install sheet or health check is an **agency artifact**: Baker house style, without loading the client's voice or style pages (BW-16). Use `<service>`, `<location>`, `<n>` placeholders in examples, never invented figures. Structure: (1) header with client code, site platform (A-14), measurement and container IDs (A-13), date; (2) events: GA4 name, detection event, trigger, parameters, key event yes/no; (3) other conversion sources (GBP, call tracking, booking tool, CRM), each with its source of truth; (4) UTM sheet link; (5) install sheet and verification checklist; (6) open items as `[NEEDS PROOF: <row ID>]`; (7) approver J-1 (or A-19); (8) the context-rules.md §9 footer (internal, stripped before it goes to the client), with `Distinctiveness: n/a — agency artifact`.

**Where it goes.** Save the finished deliverable to the client's Drive `OUTPUTS/REPORTING`. Resolve the folder from the router by ID. Never search Drive or create folders; if it's missing, stop and report. Local or working-directory files are scratch only. Propose a ClickUp record tagged `website` (implementation plan or install work) or `reporting` (health check), and create it only after the user approves.

**Write-back.** Findings that answer an `OPEN` row are staged as `DRAFT` in context-rules.md §10 format (`ID | Answer | Source label + link | Confidence | Date`) and shown to the user, never written to ClickUp. Typical rows: A-1, A-6 (if this run pulled GBP data), A-12 (see bml-health-check for ownership), A-13 (IDs only, never logins), A-14, A-15. A-9 is staged by conversion-tracking. Source labels: `Research:` for public web research (what you saw on the public site); `Benchmark: Windsor.ai <connector>, <account/property ID>, pulled <YYYY-MM-DD>` for Windsor-read client data. Link a listing or profile page, never an individual review. A finding that disagrees with a non-`OPEN` row is a conflict for the monthly check, not an edit.
<!-- BML:END bml-output -->

## Task-Specific Questions

1. What tools are you using (GA4, Mixpanel, etc.)?
2. What key actions do you want to track?
3. What decisions will this data inform?
4. Who implements - dev team or marketing?
5. Are there privacy/consent requirements?
6. What's already tracked?

---

## Tool Integrations

For implementation, see the [tools registry](https://github.com/coreyhaines31/marketingskills/blob/main/tools/REGISTRY.md). Key analytics tools:

| Tool | Best For | MCP | Guide |
|------|----------|:---:|-------|
| **GA4** | Web analytics, Google ecosystem | ✓ | [ga4.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/ga4.md) |
| **Mixpanel** | Product analytics, event tracking | - | [mixpanel.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/mixpanel.md) |
| **Amplitude** | Product analytics, cohort analysis | - | [amplitude.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/amplitude.md) |
| **PostHog** | Open-source analytics, session replay | - | [posthog.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/posthog.md) |
| **Segment** | Customer data platform, routing | - | [segment.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/segment.md) |

---

<!-- BML:START bml-tools -->
**BML stack.** BML reads GA4, Google Ads, Search Console, Business Profile and Meta through Windsor.ai (read only), SEO data through Semrush, transcripts through Fireflies; client sites are often Wix. Anything else (Mixpanel, Amplitude, Segment, PostHog, HubSpot, Optimizely, VWO, Supermetrics, paid tracking partners) is used only if the client already uses it (see A-15 / 00 §8) and any paid tool is client spend — recommend, never sign up. For GA4, use Windsor `get_data` on `googleanalytics4` instead of the GA4 Data API guide above. Wix MCP calls are read only (site context, docs).
<!-- BML:END bml-tools -->

## Related Skills

- **ab-testing**: For experiment tracking
- **conversion-tracking**: For getting conversions (including GA4 key events from forms and bookings) to ad platforms and GA4, and verifying they arrive
- **attribution**: For attribution models, multi-touch/MMM/incrementality, and reconciling conflicting numbers across tools (once tracking is live)
- **seo-audit**: For organic traffic analysis
- **cro**: For conversion optimization (uses this data)
- **revops**: For pipeline metrics, CRM tracking, and revenue attribution
<!-- BML:START bml-related -->
- BML boundary with **conversion-tracking**: it owns detection snippets, GTM import files, ad-platform conversions and the arrival half of the A-12 audit; this skill owns GA4 event names, the tracking plan and the property health check.
- **monthly-reporting** (BML skill, outside this library): reporting a month's results. This skill sets up and checks the measurement those reports read.
<!-- BML:END bml-related -->
