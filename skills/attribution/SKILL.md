---
name: attribution
description: When the user wants to figure out which marketing actually drives conversions and revenue, choose or interpret an attribution model, or reconcile conflicting numbers across tools. Also use when the user mentions "attribution," "attribution model," "first-touch vs last-touch," "multi-touch," "which channel drives revenue," "what's my real CAC," "my dashboards disagree," "Google/Meta says X but GA says Y," "media mix model," "MMM," "incrementality," "geo lift," "holdout test," "how did you hear about us," "self-reported attribution," "dark social," or wants to instrument attribution themselves — "stitch my bookings to their source," "SavvyCal/Calendly attribution," "close the identify gap," "track conversions on a third-party domain," "first-party / self-hosted attribution." For event tracking setup and UTMs, see analytics. For ad-platform pixels/CAPI and conversion tracking, see conversion-tracking. For pipeline and CRM revenue reporting, see revops. For the AI-search attribution blind spot, see ai-seo.
metadata:
  version: 1.1.6-bml.1
---

# Attribution

You help users answer the hardest question in marketing: **which of my efforts actually caused this conversion and this revenue?** Attribution is where marketers lose the most money — to channels that look good in one dashboard and terrible in another, to "direct" and "branded search" that hide the real source, and to models that quietly encode an opinion as if it were fact.

This skill has two pillars. Know which one the user needs before you dive in:

- **(A) Interpretation** — choosing an attribution model, picking a measurement approach, and *reconciling the conflicting numbers* your tools report. This applies to everyone, even with zero engineering.
- **(B) Own your attribution (first-party)** — instrumenting and stitching attribution *yourself* when you control the site/app. This is the build track. Use it when the user says "I want to track this myself" or is hitting a conversion that lives on a domain they don't own.

Most requests start with (A). Reach for (B) only when they control the surface and want to build.

Product context: check for `.agents/product-marketing.md` and read it if present — business type, sales cycle, and primary conversion drive almost every recommendation here.

<!-- BML:START context -->
**Baker Labs (BML) client work:** if the request names a BML client, runs in a client's Claude Project, or `.agents/product-marketing.md` starts with `Generated for`, `UNGENERATED for` or `INTAKE DRAFT for`, read `bml/context-rules.md` before anything else (the staged file's `Rules file:` line gives the path; otherwise `../../bml/context-rules.md` from this skill's folder). Its rules win where they conflict with this skill. If the staged file is missing or names a different client, run `product-marketing` in Load mode first. Never edit the staged file or page 13, and never add Learnings to it.
<!-- BML:END context -->

<!-- BML:START bml-scope -->
**BML client work — before you start:**

- **Scope gate.** Check the service on page 00 via the staged file's scope summary (context-rules.md §3). Services this skill runs under: reporting / analytics, and paid media where the retainer includes performance reporting — ⚠ Ops Manual 03 Service Definitions is not written yet; confirm with the account lead if the mapping is unclear.
- **Read order.** Router → staged page 13 → current Monthly Context Brief → this client's ClickUp tasks completed in the period (what launched, paused or changed — a new campaign, a booked-out month, a site change) → source pages only for a cited row. Never browse Drive or search ClickUp broadly. One client per run.
- **Which pillar.** BML clients are local service businesses: Pillar A is the job. Pillar B is gated (see the gate at the top of Pillar B). The business type is **local services** (`references/by-business-type.md`, BML block) unless page 13 says otherwise; the SaaS and DTC playbooks are for non-client work.
- **Leads are not customers.** GA4 `generate_lead` (`lead_type` = `form` | `call` | `booking`), `click_to_call`, `click_directions`, Ads/Meta conversions, GBP actions and call-tracking answered calls are *leads*, each from its own source — never summed with each other. Signed jobs or kept appointments come only from the client's records (I-4). Job value from B-7 × I-4 only if both rows are usable; otherwise `[NEEDS PROOF: B-7]`.
- **Example figures are illustrations.** Every number, company and journey in this skill and its references (survey shares, test lifts, deal values, platform counts) is a teaching example — never a client figure or a benchmark. Client numbers come only from a Windsor.ai read, a client-provided export or a cited row; otherwise `[NEEDS PROOF: <row ID>]`.
- **Segments.** Clinical: apply context-rules.md §7 (what's allowed, what's gated behind a J-3 row naming the item and the person, and what's never allowed). In this skill that means: aggregate counts by source only — never request, read or produce patient-level rows (names, contact details, dates of service, call recordings or transcripts with patient details), never tie a "how did you hear" answer to a named patient, and never join patient identity to browsing history, even with a J-3 sign-off. When a readout touches a §7 gated item (any ad-platform tag, advanced matching, Google Signals, `user_id`, session-recording or heatmap tools and the rest of the §7 list), list and flag it for a person with no recommendation to add or remove; if the request needs one, stop with `Blocked by J-3 (context-rules.md §7): <item> on patient-facing pages needs an APPROVED J-3 sign-off from a named person.` Multi-location: reconcile each location separately; never mix one location's numbers into another's.
<!-- BML:END bml-scope -->

## Boundaries — what this skill does NOT own

State these up front so you don't rebuild neighboring skills:

- **General event tracking, tracking plans, UTM setup, GA4/GTM** → **analytics**. Attribution *assumes tracking exists*. The line: analytics = "what events and how to fire them"; attribution = "how touches join to conversions and survive to revenue."
- **Ad-platform pixels, CAPI, server-side conversion tracking** → **conversion-tracking**. Attribution consumes platform-reported numbers and corrects for their bias; it doesn't set up the pixels.
- **Pipeline stages, lead lifecycle, CRM revenue dashboards** → **revops**. Attribution feeds pipeline data; it doesn't define stages.
- **Showing up in / measuring AI search** → **ai-seo**. Attribution names AI traffic as a blind spot only.

---

## Pillar A — Interpretation

### 1. What attribution can and can't tell you

Set expectations before touching a number:

- **Attribution is directional, not truth.** It's a model of causality built from incomplete data (cookies expire, sessions fragment, offline touches vanish, people research on one device and buy on another). Treat it as a strong hint, never a verdict.
- **Every model is an opinion.** "First-touch" says the first ad gets all the credit; "last-touch" says the closing click does. Both are wrong in opposite directions. Choosing a model is choosing whose story to believe — say so out loud.
- **The attribution gap is normal, so separate outcomes from credit.** The sum of channel-reported conversions almost always exceeds real conversions, because every platform claims the same sale under its own attribution window and view-through rules. Count real conversions once, deduplicated against one source of truth, and explain platform credit separately. The two won't tie out, and a modeled allocation never replaces the conversion ledger.

When a user demands one true number, reframe: "We can get you a *defensible, consistent* number and a read on which channels are trending up. A single objective truth doesn't exist — here's why, and here's what we use to make decisions anyway."

### 2. Attribution models

The classic rule-based set plus data-driven — and when each one lies. **Last non-direct** is a last-touch variant (skip the junk drawer), not a separate school of thought.

| Model | Credit rule | Best for | How it lies |
|---|---|---|---|
| **First-touch** | 100% to the first known touch | Top-of-funnel / demand-gen valuation; short cycles | Ignores everything that closed the deal; over-credits awareness channels |
| **Last-touch** | 100% to the last touch before conversion | Direct-response, quick e-comm | Over-credits bottom-funnel + branded search/direct; ignores what created demand |
| **Last non-direct** | 100% to last touch, skipping "direct" | A cheap fix for direct pollution | Still single-touch; just moves the blind spot |
| **Linear** | Equal credit to every touch | Long, multi-touch journeys where every step matters | Treats a throwaway visit like a demo; flatters high-frequency channels |
| **Time-decay** | More credit to touches nearer conversion | Longer cycles where recency matters | Under-credits the top of funnel; still an assumption, not a measurement |
| **Position-based (U-shaped)** | 40% first, 40% last, 20% middle | B2B with clear "created" + "closed" moments | The 40/40/20 split is arbitrary; middle touches get shortchanged |
| **Data-driven (algorithmic/Shapley)** | Credit from modeled marginal contribution | High-volume accounts with enough conversions | A black box; needs volume; can't see offline/dark touches it was never fed |

**Platform availability note:** Google Ads and GA4 retired first-click, linear, time-decay, and position-based as selectable reporting models (2023). Those UIs offer **data-driven** and **last-click** (plus GA4's paid-channels last-click variant). Teach the full table as *concepts* and as models you can compute on your own event path / CRM / warehouse — not as Google dropdown options.

**Rules of thumb:**
- Never report a single model in isolation for a long sales cycle. Show **first-touch and last-touch side by side** — the truth lives between them, and the gap between them *is* the insight.
- Data-driven attribution needs volume. Google Ads historically gated DDA behind ~3,000 ad interactions and ~300 conversions in 30 days; hard minimums are gone and DDA is the default, but Google still recommends ~**200 conversions and ~2,000 ad interactions** in 30 days for quality. Below that, DDA often collapses toward last-click priors — noise dressed as science. On Google/GA4 when thin: prefer last-click (or accept that DDA ≈ last-click). Elsewhere (first-party / CRM / warehouse): compute position-based or first+last side by side.
- The model matters far less than being **consistent** and pairing it with an out-of-model sanity check (Pillar A §4, self-reported).

For the model math, worked examples of one journey scored six rule-based ways, and Shapley explained plainly, see `references/attribution-models.md`.

### 3. The three measurement paradigms

Models split credit *within* your tracked data. Paradigms are how you get at *causality* — increasingly rigorous, increasingly expensive:

| Paradigm | What it is | Answers | Needs | Watch out |
|---|---|---|---|---|
| **MTA** (multi-touch attribution) | Stitch user-level touches, apply a model | "Which touchpoints appear on converting journeys?" | Clean cross-device user-level tracking | Cookie loss + privacy gut user-level data; click-paths systematically over-weight search/direct and under-weight impression channels |
| **MMM** (media/marketing mix modeling) | Top-down regression of spend vs. outcomes over time | "What's each channel's aggregate contribution, including offline/brand?" | 2–3 yrs of weekly data, spend variation | Correlational; slow to react; needs real budget swings to learn |
| **Incrementality** (geo holdout, PSA, ghost ads, on/off) | Controlled experiment: exposed vs. withheld | "Did this channel *cause* lift I wouldn't have gotten anyway?" | Ability to withhold; enough volume for significance | The gold standard, but you can only test a few things at a time |

**How to choose:** small budget / short cycle → good UTM + last-non-direct + a self-reported survey beats a fancy model. Mid budget, several channels → MTA for day-to-day + periodic incrementality tests on your biggest line items. Large budget, offline + brand spend → MMM for the portfolio + incrementality to validate MMM's coefficients. Incrementality is the tiebreaker whenever two channels both claim the same conversions.

Decision table by budget × sales cycle × channel count, and how to *read* a geo-holdout / PSA test (not a stats tutorial), in `references/measurement-paradigms.md`.

### 4. Self-reported attribution

The most underused signal, and often the most honest for long cycles and dark social. A post-conversion "How did you hear about us?" survey catches what tracking structurally cannot: podcasts, word of mouth, Slack communities, a founder's tweet, "a friend told me."

- **When it beats tracking:** long consideration cycles, high word-of-mouth, brand/community-led, or heavy dark-social (see §5). If a big slice of your journeys are "direct," you have a self-reported-shaped hole.
- **Ask at the moment of conversion** (signup, first purchase, demo request) — highest recall, before memory fades.
- **Wording:** open-ended ("How did you first hear about us?") captures dark social; a short pick-list is easier to quantify but pre-biases the answer. Best practice: pick-list of your known channels **plus a free-text "other/tell us more."**
- **Treat it as a triangulation input, not gospel** — recall is fuzzy and people credit the *memorable* touch, not the first. **Discount survey share when turning it into credit** (e.g. 22% recall of YouTube is evidence of awareness, not a claim that YouTube deserves 22% of conversions). Pair with incrementality / platform deltas before writing an allocation rule.
- On the build side, this is a form field written to your CRM/analytics as a person property — see Pillar B and `references/first-party-tracking.md`.

<!-- BML:START bml-self-reported -->
**BML local-service version.** The moments of conversion are the contact/quote form, the phone call (whoever answers per I-3) and the booking or job signing. Recommend asking "How did you hear about us?" at each, as a pick-list built from the client's own channels (B-9, I-1, L-11 category platforms, L-8 referral partners) plus "Other — tell us more". Write it as a recommendation for the approver (J-1; A-19 if J-1 is OPEN): a form change is a `website` task a person puts live, and a phone-intake question is a script line for the client's staff. BML never adds the field itself and never writes the answers into the client's CRM. Clinical: a form change on a patient-facing page is a compliance question for a person (context-rules.md §7) — flag it, don't recommend it; the phone-intake question is fine; answers are reported only as counts by source.
<!-- BML:END bml-self-reported -->

### 5. Reconciling conflicting sources

The request behind most attribution work: **"Google says 50, Meta says 40, GA says 60, my CRM says 35 — who's right?"** Nobody is. Here's the framework.

**Why each source systematically lies:**

| Source | Biased toward | Because |
|---|---|---|
| **Ad platforms** (Google/Meta/LinkedIn) | Over-counts *itself* | Claims view-through + click conversions in its own window; every platform counts the same sale; motivated to look good |
| **GA / web analytics** | Last non-direct click | Loses cross-device, loses cookie-blocked users, dumps the unknown into direct |
| **CRM** | Whatever the rep typed / the form captured | Human entry, lead-source overwrites, offline deals with no digital trail |
| **Self-reported survey** | The *memorable* touch | Recall bias; under-counts boring-but-real touches like retargeting |

**How to triangulate:**
1. **Pick one source of truth for the conversion count** — usually your CRM or backend (the system where money is real). Everything else explains *where those came from*, they don't get to redefine *how many*.
2. **Never sum across platforms.** If Google and Meta both claim a conversion, you have one conversion with two claimants, not two conversions. De-dupe against the source-of-truth total.
3. **Read directional agreement, not absolute match.** If every source says paid search is up and organic is down this quarter, that trend is trustworthy even though no two numbers match.
4. **Use self-reported as the tiebreaker** when platforms fight over the same conversions, and **incrementality** when the stakes justify a test. Do **not** turn a platform-vs-GA gap into a multiplier rule (Meta claims 2× GA ≠ "double Meta") — investigate windows and view-through, then ground any override in incrementality.
5. **Expect and budget for the gap.** Report "platforms claim N; we can verify M; the delta is over-claiming + view-through + untracked — here's our best allocation."
6. **Operationalize triangulation as rules when you can** — once you have a holdout or a trusted survey band for a channel, apply a documented **channel-level override** on reporting (shift credit from Direct/branded into the under-credited channel for the test window) rather than pretending raw MTA is truth. Details in `references/measurement-paradigms.md`.

The output is an honest allocation with confidence levels, not a false reconciliation to the decimal.

<!-- BML:START bml-source-of-truth -->
**BML source-of-truth ladder.** For a BML client, step 1 above ("usually your CRM") becomes the highest rung available. Name the rung in the readout and its confidence:

1. **The client's record of signed jobs / kept appointments** — the CRM, field-service or practice-management system named in A-15, read from an export or report the user provides (aggregate by source and month; for clinical, counts only). This is the count of customers.
2. **Call tracking (A-15) + the form/booking inbox** — answered calls and submissions. This is the count of *leads*, not customers; say so.
3. **Client-stated lead sources (B-9)** — the client's own view of where work comes from. Use it to sanity-check, not to count.

Platform and GA4 numbers (read through Windsor.ai) never define the count at any rung; they explain where it came from. BML is **read-only** on every client system: never write to, sync to or "fix" a client CRM, booking tool or call-tracking account, and never ask for login credentials — ask the user for an export. If no rung above 3 exists, the readout says the customer count is unknown and names the rows to fill (A-15, I-4).

A channel-level override (step 6) is a labeled adjustment in the readout, with the raw numbers shown beside it — never a change to a client dashboard or account.
<!-- BML:END bml-source-of-truth -->

### 6. The blind spots

Where conversions hide, making real channels look weak:

- **Direct** — the junk drawer. Bookmarks and typed URLs, yes, but also stripped referrers, app-to-web, dark social, and any touch your tracking dropped. A large direct share can include genuine direct visits, repeat users, and measurement loss. Investigate its composition before treating it as a tracking defect.
- **Branded search** — people who discovered you elsewhere and Googled your name. Last-touch hands the credit to paid/organic *branded* search; the real driver was whatever made them search. Segment branded vs. non-branded or you'll defund the top of funnel.
- **Dark social** — sharing that carries no referrer: DMs, Slack/Discord, podcasts, newsletters, screenshots. Structurally invisible to tracking; self-reported is the only way to see it (§4).
- **AI traffic** — assistants and AI search increasingly influence buyers, then send them via branded search or direct, so the AI touch is invisible in analytics. Name it and hand deeper work to **ai-seo**.

When direct and branded search dominate, the most common explanation is a top of funnel that's working while attribution hides it. Confirm before concluding: rule out existing customers, lost referrers, and offline discovery, then check self-reported attribution or run an incrementality test. It's the most common misread in marketing in both directions, so say which one the evidence supports.

<!-- BML:START bml-local-blind-spots -->
**Local-service blind spots** (add these before reading a BML client's numbers):

- **Google Business Profile** — calls, direction requests and website clicks from Maps and Search (A-6). Calls and directions never touch the site, so GA4 sees nothing. Report GBP as a channel in its own right from Windsor.ai (`google_my_business`); never fold it into "direct" or sum it with GA4 events.
- **Call extensions and call-only ads** — counted by Google Ads (or call tracking), not GA4.
- **Local Services Ads and directories** (Angi, Houzz, Zocdoc and the platforms in L-11) — leads reported only inside those platforms.
- **Referrals and word of mouth** (L-8), **yard signs, vehicle wraps, print** — no digital trail; only the "how did you hear" question (§4) sees them.
- **Walk-ins and repeat customers** — appear as direct or branded search, or not at all.
<!-- BML:END bml-local-blind-spots -->

### 7. Business-type fork

Defaults differ sharply. Summary here; full playbooks in `references/by-business-type.md`.

- **B2B SaaS (long cycle, sales-assisted):** journeys span weeks–months and multiple people, so single-touch models mislead badly. Anchor on the **CRM as source of truth**, use **first-touch + position-based** side by side, lean hard on **self-reported at demo/signup**, and treat **pipeline/revenue** attribution (→ revops) as the real scoreboard. Offline touches (events, sales convos) make MTA weakest and self-reported strongest here.
- **Ecommerce / DTC (short cycle, self-serve):** fast journeys, high volume, spend concentrated in paid social + search. Anchor on **platform ROAS but distrust it** (iOS/CAPI inflation), validate with **MMM once spend is material** and **incrementality/geo-holdouts** on your biggest channels, and use a **post-purchase survey** to catch what pixels miss. Last-touch is defensible for quick-turn SKUs; MMM+incrementality is how you allocate the real budget.

<!-- BML:START bml-local-services -->
- **Local services (BML clients — the default for client work):** the conversion is a call, booking or form; the outcome is a signed job or kept appointment closed offline (I-4); volume is low. Use **last-non-direct** (GA4: *Paid and organic last click*) plus the "how did you hear" question and GBP as its own channel; in Google Ads/GA4 report last-click and say data-driven ≈ last-click at this volume — don't sell a model change as a lever. **No MMM.** Incrementality only as reading past natural pauses (booked out, seasonal shutdown) or as a written on/off proposal for the approver. Vocabulary: CAC → cost per signed job; pipeline → leads → estimates/consults → signed jobs; MRR/LTV → B-7 job value and LTV. Revops hand-offs don't apply — note them for the account lead. Full playbook: `references/by-business-type.md`, BML block.
<!-- BML:END bml-local-services -->

---

## Pillar B — Own your attribution (first-party)

Use this when the user **controls the site/app** and wants to instrument attribution themselves — especially for a conversion that happens on a **domain they don't own** (a SavvyCal/Calendly/Cal.com booking, a Stripe Checkout page). This pillar is grounded in real production builds; the full runbook with code patterns is in `references/first-party-tracking.md`. The essentials:

<!-- BML:START bml-pillar-b-gate -->
**BML gate — advisory only.** For BML client work, Pillar B is explanation, not implementation:

- **Deliver a plain-language brief for the client's developer or platform vendor:** what is un-joined (e.g. bookings on `<booking tool>` lose their source), the pattern that would close it, what it needs (metadata passthrough + webhook), the privacy guard, and how to verify it. Claude writes no code to install, deploys nothing, edits no site code or settings (Wix included), and uses no connector write action. A person puts any change live after the approver (J-1; A-19 if J-1 is OPEN) OKs it, recorded on the ClickUp task.
- **Never write to a client CRM** — the "last mile" CRM sync below and account rollup are for the client's own team to decide; BML may describe them, not build or run them.
- **One recommendation worth making:** the first-touch data-quality fix (exclude booking, payment and login domains as unwanted referrals in GA4). It is a config change, so Claude doesn't make it: write the steps as a recommended `website` (tracking work) task, handed to `analytics` / `conversion-tracking`, for a named person with A-13 access to apply after approval.
- **Clinical clients: stop.** Joining a known identity (email, phone, `user_id`) to browsing history is patient data, which context-rules.md §7 never allows — a J-3 sign-off doesn't change this. Say "Blocked by context-rules.md §7: patient identity is never joined to browsing history" and offer aggregate source reporting instead.
- **No visitor de-anonymization** (RB2B and similar) for any BML client.
<!-- BML:END bml-pillar-b-gate -->

### The identity graph

First-party attribution is one idea: **join anonymous browsing to the eventual conversion.**

1. A visitor arrives anonymously; your analytics tool assigns an **anonymous `distinct_id`** and stamps **first-touch properties** (`$initial_referrer`, `$initial_utm_*`) on their events.
2. At conversion (signup, booking, purchase) you call **`identify()`** with a stable id (email or user UUID). This **merges** the anonymous history into a known person — first-touch now survives all the way to the conversion.
3. Every conversion event can now be broken down by first-touch channel. That's the whole game.

### Closing the `identify()` gap

The most common first-party failure: **nothing ever calls `identify()`**, so conversions never join to browsing history and every customer looks like they appeared from nowhere. (Framing adapted from Tessa Kriesel's PostHog approach.) The fix is to call identify at each real conversion. **Audit first** — many SaaS apps already identify at signup; don't rebuild what works. Find the *specific* un-instrumented conversions and close only those.

### Stitching conversions on a third-party domain

The one case that needs real machinery: a conversion that completes on a domain you don't control (a booking tool, a hosted checkout). You can't run your analytics there, so:

1. **At click time**, a capture-phase link decorator appends the visitor's anonymous `distinct_id` to the outbound URL via the tool's **metadata passthrough** (e.g. `?metadata[ph_distinct_id]=<id>`). One document-level listener covers every CTA — no per-link edits.
2. The third-party tool stores that metadata and returns it in its **webhook**.
3. Your **webhook handler** fires an **identity merge** (`$identify` with the booking email as `distinct_id` and the smuggled anonymous id as `$anon_distinct_id`) plus a **conversion event** — joining the booking back onto the marketing journey.

### Guardrails (do not skip)

- **Anonymity guard — fail closed.** Only ever smuggle the *anonymous* id. After `identify()`, the current id becomes the user's email/UUID; leaking that into a third-party URL or merging on it corrupts profiles (person A's email folds into whoever books). Reject ids that look like PII (contain `@`), cap length, and when identity is ambiguous, **send nothing**. If the app identifies by UUID, test `distinct_id === device_id` rather than an `@` check.
- **First-touch data quality.** Redirects overwrite the true first touch. Exclude OAuth/checkout referrers (`accounts.google.com`, `checkout.stripe.com`, `login.*`), your own subdomains (self-referrals), and dev hosts (`localhost`) from referrer classification. This is usually a settings change, not code, and it's the highest-trust-per-effort fix.
- **Cross-subdomain stitching.** Marketing site → app on a subdomain must share one analytics project + a cross-subdomain cookie, or the journey breaks at the handoff. Expect **near-zero numbers until the stitch is verified in prod** — don't panic at empty data; use a campaign-window heuristic fallback and backfill the pre-stitch cohort in the meantime (details in the reference).

### Reporting and the last mile

The first payoff is one insight: your **conversion event broken down by first-touch channel** (`$initial_utm_source` / `$initial_referring_domain`), and — joined to revenue — **channel → conversion → revenue**. Confirm first-touch vs. last-touch config in the tool (many default to last-touch; first-party attribution wants `$initial_*`).

But first-touch alone can't run the multi-touch models from §2. **Store the full ordered touch path** (not just `$initial_*`) and the build track feeds the interpretation track — you can score your own journeys position-based / linear / time-decay instead of only reading about them.

**The last mile — get it into the CRM** (production refinement from Tessa Kriesel). A breakdown in an analytics tool is a report; sales and lifecycle act on attribution *written onto the record*. Sync a **`source` field with `confidence` and `basis`** (journey-linked vs self-reported vs campaign-window fallback) plus a **Paid-vs-Organic read** off the medium, **rolled up to the account** (not just the contact — one B2B org is several people with mixed work/personal emails). How pipeline/lifecycle then *use* it is **revops**' job.

The pattern is tool-agnostic: identify + merge exists in PostHog, Segment, Amplitude, and via user-id in GA4; the third-party stitch works with any tool that has a metadata passthrough + webhook. PostHog + SavvyCal are the worked example in `references/first-party-tracking.md`.

---

## Output format

Deliver an **attribution readout**, not a data dump:

```markdown
# Attribution Readout — [date]

## The question
[What decision this informs — e.g. "where should next quarter's budget go?"]

## Source of truth
[Which system defines the conversion count, and why]

## What each source says
| Channel | Platform-reported | GA | CRM | Self-reported | Our read |
|---------|------------------|----|----|--------------|----------|
[De-duped against source of truth; not summed]

## Model comparison (for long cycles)
[First-touch vs last-touch side by side; the gap is the insight]

## Confidence & gaps
[The attribution gap, the blind spots, what we can't see]

## Recommendation
[Allocation call with confidence levels; the tiebreaker test worth running]
```

<!-- BML:START bml-output -->
**BML client readouts:**

- **Title:** `Attribution Readout — [CODE] — [period]`. It's an agency artifact: Baker house style; do not load the client's voice or style pages; Distinctiveness `n/a — agency artifact`.
- **Source table columns:** Channel · Windsor.ai (Google Ads / Meta / GA4 `generate_lead` by `lead_type` / GBP actions — each its own column, never summed) · Call tracking · Forms/bookings · Client job log · "How did you hear" · Our read. Add a **lead → signed job** row from I-4 or the client export; if missing, `[NEEDS PROOF: I-4]`.
- **Model comparison:** for local services, show last-click vs. the self-reported split instead of a long-cycle first/last table.
- **Recommendation:** any test that pauses, cuts or shifts spend is a recommendation for the approver (J-1; A-19 if J-1 is OPEN), with B-6 capacity and I-10 season noted — never executed. Any pause or spend change is made by a named person (the account lead or the client), never Claude, even after approval. Tracking defects found along the way (the tracking-health part of A-9, A-12) go to `conversion-tracking` / `analytics` as a recommended `website` task, not a fix.
- **Where it goes:** the client's Drive `OUTPUTS/REPORTING`, resolved from the router by folder ID — never search Drive or create folders; if the folder is missing, stop and report. Propose a ClickUp record tagged `reporting`; create it only after the user approves. Anything written to the working directory is scratch only.
- **Write-back:** a finding that answers an `OPEN` A-6 row (when this run pulled the GBP data) or the spend/CPL part of an `OPEN` A-9 row is staged as `DRAFT` in context-rules.md §10 format (`ID | Answer | Benchmark: Windsor.ai <connector>, <account/property ID>, pulled <YYYY-MM-DD> + link to the platform report or listing page | Confidence | Date`), shown to the user, never written to ClickUp. Attribution never stages A-12 or the tracking-health part of A-9 — cite them, or list them under "Gaps to ask about". Measured lead-source shares and lead-to-job rates do **not** fill B-9 or I-4 (those are the client's own answers); put them under "Gaps to ask about" in the footer. A finding that disagrees with a non-OPEN row is a conflict for the monthly check, not an edit.
- **Footer:** end with the context-rules.md §9 footer (internal; stripped before the piece goes to the client).
<!-- BML:END bml-output -->

## Tool Integrations

For implementation, see the [tools registry](https://github.com/coreyhaines31/marketingskills/blob/main/tools/REGISTRY.md). Key tools:

| Tool | Best For | MCP | Guide |
|------|----------|:---:|-------|
| **PostHog** | First-party attribution, identify/merge, funnels | - | [posthog.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/posthog.md) |
| **GA4** | Web analytics, model comparison, user-id stitching | ✓ | [ga4.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/ga4.md) |
| **Dub** | Short-link + click attribution | ✓ | [dub-co.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/dub-co.md) |
| **Segment** | CDP — route identify/track to every destination | - | [segment.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/segment.md) |
| **HubSpot** | CRM lead-source + self-reported fields | ✓ | [hubspot.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/hubspot.md) |
| **Salesforce** | CRM as revenue source of truth | - | [salesforce.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/salesforce.md) |
| **Supermetrics** | Pull platform numbers into one place to reconcile | ✓ | [supermetrics.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/supermetrics.md) |
| **RB2B** | De-anonymize B2B website visitors | - | [rb2b.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/rb2b.md) |

<!-- BML:START bml-tools -->
**BML tools.** BML reads GA4, Google Ads, Search Console, Business Profile and Meta through Windsor.ai (read only), SEO data through Semrush, transcripts through Fireflies; client sites are often Wix. Anything else (Mixpanel, Amplitude, Segment, PostHog, HubSpot, Optimizely, VWO, Supermetrics, paid tracking partners) is used only if the client already uses it (see A-15 / 00 §8) and any paid tool is client spend — recommend, never sign up.

- **Windsor.ai:** `get_data` on `googleanalytics4`, `google_ads`, `facebook`, `google_my_business`, `searchconsole`, using only the account/property IDs on A-13 (or 00 §8). If A-13 is OPEN or ambiguous, ask the user to confirm the exact ID before reading — never pick an account from Windsor's list by name — and stage the confirmed ID as an A-13 `DRAFT` row (`Client-stated:` if the user or client gave it). Never call `execute_action` — it changes budgets, bids and listings.
- **Fireflies (A-18):** intake and sales-call transcripts can show how customers say they found the client — count mentions by source; never quote or name a customer. Clinical: use only the meetings the account lead has pre-screened and given you by meeting ID — never search or browse transcripts — and report a `SENSITIVE` source by ID, never by title.
- **Call tracking, CRM, booking tool (A-15):** read from an export the user provides; no logins, no writes.
- **RB2B:** not for BML client work.
<!-- BML:END bml-tools -->

---

## Related Skills

- **analytics** — event tracking, tracking plans, UTMs, GA4/GTM setup. Do this *before* attribution.
- **conversion-tracking** — ad-platform pixels, CAPI, server-side conversion tracking, and tracking audits.
- **revops** — pipeline stages, lead lifecycle, CRM revenue reporting. Attribution feeds it.
- **ai-seo** — the AI-search attribution blind spot in depth.
- **ab-testing** — controlled experiments; the incrementality mindset applied to on-site changes.
