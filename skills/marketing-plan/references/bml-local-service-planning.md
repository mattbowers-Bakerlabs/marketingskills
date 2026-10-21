<!-- BML:START bml-local-service-planning -->
# BML Marketing Plans — Local-Service Workflow

How `marketing-plan` runs for a Baker Labs (BML) client. SKILL.md's "BML client work" block sends you here. Where this file and the upstream references disagree, this file wins for BML client work; `bml/context-rules.md` (its path is in the staged file's header) wins over both.

A BML marketing plan is an **agency artifact**: written in Baker house style, never in the client's voice, ending with the context footer (rules §9, `Distinctiveness: n/a`). It is often shown to the client, so the maturity gate (Part 1, Step 6) decides when it can be.

---

## Part 1 — Workflow

### Step 0: Context, scope, segments

1. Make sure `.agents/product-marketing.md` is staged for this client (`Generated for` / `UNGENERATED for [CODE]`). Missing, or another client's → run `product-marketing` Load first. `INTAKE DRAFT` → this is a pitch plan: internal and pitch use only, every fact marked "from public research". Skip steps 3–4 (there is no page 00 yet) and Step 1's ClickUp and Drive records (there is no client space); keep the plan in the session outputs folder or where the user names. Its status line reads `Pitch draft — from public research; not for publication`, in place of Step 6's maturity-gate line.
2. Read the rules file named in the staged file's header.
3. **Scope gate (rules §3).** A plan is part of every BML retainer: any `Active` service on page 00 authorizes it. No `Active` service at all → stop: "[CODE] has no active BML service on page 00." The plan covers the whole marketing picture, not only retained services, so it also shows the account lead where BML could do more (Step 4).
4. Plans cover more than the retainer. Every move gets an **In retainer?** value from page 00: `Yes`, `Yes — <qualifier>`, or `No — scope note`. BML never owns a `No` move in the RACI; it goes to the client or `TBD`, and the plan lists those moves together in Section 13 as **upsell opportunities for the account lead**: what the move is, which BML service would cover it, and the rows that justify it. That list is internal and is removed before the plan goes to the client. A qualifier like "planning only" means BML plans the work but doesn't own its execution.
5. Note the segments from the staged file. They filter moves and ideas (Part 7) and set the clinical gate.

### Step 1: Where state lives (replaces `~/marketing-plans/` and `progress.md`)

| What | Where |
|---|---|
| Plan record and progress | One ClickUp task in the client's Master Task List, tag `strategy`, named `Marketing Plan — <CODE> — v<N>`. Its description holds the progress block below |
| Working draft and final plan | Client's Drive `OUTPUTS/<strategy folder>/` (see SKILL.md, "Output folder"), file `<CODE>_Marketing_Plan_v<N>_YY.MM.DD.md`, linked from the task |
| Within a session | The session's outputs folder (`/mnt/user-data/outputs/` in Cowork, otherwise `outputs/` in the working directory). Never `~/` and never a client's connected folder |

Progress block (task description):

```
phase: init | review | finalize | finalized
plan_version: v<N>
sections_approved: [2, 3, …]
working_file: <Drive file ID>
open_gaps: [row IDs]
last_updated: YYYY-MM-DD
```

Rules:

- **Read first.** Resolve the task from the router or by filtering the client's Master Task List for tag `strategy` and the name above. Never search the workspace or browse Drive; fetch the working file by the ID in the task.
- **Write only with approval.** Creating or updating the task, and saving to Drive, happen only when the user asks or approves in this conversation (rules §10; Registry "read-only by default"). One approval can cover saving each approved section as you go for this plan. Without approval, keep everything in the session outputs folder and say plainly that it won't survive the session.
- **Folder missing** → stop and ask. Never create Drive folders.
- Resumption follows upstream methodology Step 1.1.2, reading this state instead of files: no task → fresh; `phase: finalized` → ask (revise as v<N+1>, new plan, re-open a section). Never overwrite a finalized plan.

### Step 2: INIT — read before asking

Read in this order and stop when you have enough (rules §1):

1. Staged page 13 (positioning, ICP, offers, proof, beliefs, guardrails, local market, Known gaps).
2. Current Monthly Context Brief: in-flight and recently published work, recent results.
3. Source pages 07–12 only for detail behind a cited row (benchmark rows A-1…A-12, budget B-10, capacity B-6, team time I-8).
4. Live data, read-only, once per run (Part 6): Windsor.ai, Semrush, the kickoff or monthly-session transcript in Fireflies if the brief links one.
5. In-flight and stuck work the brief doesn't cover: one filtered query of the client's Master Task List (open tasks, by tag). No broad search.

Then build a **gap list**: every row the plan needs (Part 2) that is `OPEN`, `DRAFT`, `⚠ UNVERIFIED`, or a stale L row. If most L rows are `OPEN`, recommend running `bml/local-market-research.md` (through `client-context-miner` Backfill) before Sections 4 and 10; draft meanwhile with the gaps marked.

### Step 3: Intake — ask only for gaps, by row ID

Upstream's ten intake topics map to rows (Part 2). Ask only about rows on the gap list, quoting the row ID: "B-10 (budget and split) is open. What's the monthly marketing budget, and how is it split?" Ask ★ rows first, one topic at a time.

- Answers given in the session are **`DRAFT`**. Use them to draft, mark them `DRAFT — confirm (<row>)` in the plan, and stage them for review in the rules §10 format (`Client-quoted:` when the user relays what the client said, `Agency-authored:` for a BML estimate). Never write them to ClickUp yourself.
- Never ask about funding rounds, burn, runway, investors or ARR. They don't apply (Part 4).
- Don't ask the client for numbers BML can pull (A rows) — pull them.
- Benchmark findings that answer an `OPEN` A or L row are staged the same way (`Benchmark:` / `Research:` + tool + date).

### Step 4: Score current state

Use the rubric mapping in Part 3. Each score cites the rows or pulls it rests on. A rubric line with no usable evidence gets `—` (not a guess) and goes to the gap list. Total = sum of scored lines out of 5 × lines scored; say how many were scored.

### Step 5: REVIEW — draft each section

Upstream order (2 → 13, then 1), with Part 8's section changes. In every section:

- Client facts come only from page 13 or cited rows (rules §4). Cite row IDs inline: `(B-7)`. Missing → `[NEEDS PROOF: <row>]`.
- Numbers you derive (lead targets, budget math) show their inputs by row.
- Check every move against page 12 and F-13 at any status, the never-use words (H-5) and segment rules (rules §5, §7). A move that needs a violation is dropped and named: "Skipped — blocked by J-4."
- Capacity: no move that needs more jobs than B-6 allows in the season I-10 names, and no response-time promise beyond I-3.
- Write in Baker house style. The client's voice (page 13 voice section) is summarized in Section 2 as a rule for the deliverables the plan schedules; the plan itself is not written in it. Don't load pages 01–02.

### Step 6: FINALIZE — verify, gate, save

Upstream Step 3.2 checks, plus:

- **Claims check:** every client fact traces to a row or a dated pull; no figures from the upstream references or examples.
- **Maturity gate:** list every section that rests on a `DRAFT` row or an in-session answer. While any remain, the plan's status line reads `Internal draft — not for client` and the ClickUp task can't move past `internal review`. `PROVISIONAL` rows are allowed and flagged in the footer.
- **Scope check:** every `No — scope note` move is in Section 13's scope list, and none has BML as owner.
- **Privacy:** no customer or patient names, reviewer names or identifying quotes, and nothing copied from transcripts beyond themes (BW-22).
- **Footer:** the rules §9 block with `Distinctiveness: n/a for agency artifacts`. Strip it before the client sees the plan.
- **Save:** on approval, upload to the client's strategy folder, link it on the task, set the task to `internal review`. Moving to `ready for client review` is the account lead's call; name the client approver (J-1) in the status line. No GitHub or Notion publishing.

---

## Part 2 — Upstream intake topics → question-bank rows

| Upstream intake topic | Rows to read (ask only if a gap) |
|---|---|
| 1 Client overview | B-1, B-2, D-1, D-2, D-3★ |
| 2 ICP | page 13 ICP and personas (sourced from 03), D-2, E-5 |
| 3 Funnel state | I-3, I-4, B-9, A-1, A-2, A-6, A-9, A-12 |
| 4 Funding state | **Not used.** Replace with B-10 (budget and split, past agencies), B-3★ (3-year picture), B-4 (12-month goals), B-5 (margins, want more/less of) |
| 5 Team | I-8 (team time), I-3 (who answers leads), B-12 (faces of the business), A-19 / J-1 (contact, approver) |
| 6 Budget | B-10, A-9 (paid spend, CPC, CPL), L-7 (local CPCs), B-7 (job value, LTV, repeat and referral share) |
| 7 Channels active | I-1, I-2, B-9, I-5, I-6, I-7, I-9, A-6, A-8 |
| 8 Already done | I-2, G-1, G-3★, G-9, D-11, plus the brief's recently published work |
| 9 In-flight and stuck | Monthly Context Brief, then the filtered task query (Step 2.5) |
| 10 Strategic posture | B-4, B-6 (capacity, seasonality, backlog), I-10, D-9, J-3, J-8 |
| Market and competitors | E-1, E-2, E-3★, E-6★, E-10, L-1…L-12 |
| Offer and pricing | D-4★, D-5, D-6, D-7, D-8 |
| Guardrails | J-1…J-8, F-13 (restrict at any status) |

---

## Part 3 — Current-state rubric, read for local service

Keep the 17 lines and 0–5 scale from `current-state-rubric.md` so totals stay comparable; read each line this way:

| # | Upstream line | Read it as | Evidence rows / pulls |
|---|---|---|---|
| 1 | Positioning | Clear, distinct reason to choose them locally | E-3★, E-4★, E-6★, E-8 |
| 2 | Customer research | ICP and customer language on file | page 13 ICP / language, D-6, L-5 |
| 3 | Homepage | Homepage clarity, call/booking path, mobile | A-4, A-12, I-9 |
| 4 | Sales / product pages | One page per priority service (D-1), pricing per D-4 | D-1, D-4★, A-1 |
| 5 | Conversion pages | Service-area / location pages, campaign landing pages | B-8, L-1, A-1, A-3 |
| 6 | Competitor comparison | Knows who they lose to and why; answers it | E-1, E-2, L-4★, L-6 |
| 7 | Resources / content | Content that ranks or gets cited for local searches | A-1, A-3, A-10, L-3★ |
| 8 | Onboarding | **Lead handling:** speed and quality of first response | I-3, I-4, I-9 |
| 9 | Email lifecycle | Follow-up, maintenance reminders, review and referral asks | I-5, I-6, A-15 |
| 10 | Sales material | Estimate / consult materials that answer doubts | D-3★, D-6, D-5 |
| 11 | Messaging | Voice documented and consistent across surfaces | page 13 voice, H-5 |
| 12 | Pricing | Publishable ranges, financing, packages | D-4★, D-7, D-8, E-10 |
| 13 | CRO | Tracking in place; calls and forms measured | A-12, A-15 (call tracking) |
| 14 | GTM launches | Seasonal campaigns and promotions executed | I-2, I-10, D-11 |
| 15 | Ads (paid) | Paid spend, CPL, tracking quality | A-9, L-7 |
| 16 | SEO | Organic + **local** search: map pack, GBP, NAP, reviews | A-1, A-2, A-3, A-6, A-7, A-11, L-4★ |
| 17 | Internationalization | **Service-area coverage:** demand served vs. area claimed | B-8, L-1, L-3★ |

Also report, outside the 17-line total, three local lines that drive most local-service plans: **GBP and reviews** (A-6, A-7, A-16), **AI presence** (A-10, L-12), **listings / NAP** (A-11). Score them 0–5 the same way.

Ads at 0 because B-10 holds no paid budget is a budget fact, not a weakness (same rule as upstream's pre-seed note).

---

## Part 4 — Budget, capacity and "unlocks" (replaces funding tiers)

Local-service clients don't raise rounds. Section 10's "what unlocks when" is driven by these triggers instead:

| Trigger | Row | What it unlocks in the plan |
|---|---|---|
| Budget change approved | B-10 | Next channel from the 20% "next" bucket; paid scale-up |
| Capacity added (crew, provider, location, longer hours) | B-6 | Volume moves for the services that were capped |
| Season | I-10, B-6 | Timing: demand moves before peak, retention and review moves in slow months |
| Tracking fixed | A-12, A-15 | Paid and CRO moves that need measurement first |
| Retainer change | page 00 | BML can own moves currently marked `No — scope note` |
| Offer or service launch | D-11, D-1 | Step-function moves (new service line, new location) |

**Budget math (replaces ARR methods).** Use the goal-based shape with local inputs, each cited:

```
new revenue      = revenue goal (B-4) − revenue expected from repeat customers and referrals (B-7, B-9)
jobs needed      = new revenue ÷ average job value (B-7)
booked needed    = jobs needed ÷ close rate from booked to signed (I-4)
leads needed     = booked needed ÷ lead-to-booked rate (I-4)
paid budget      = leads needed from paid × cost per lead (A-9; or local CPC from L-7 ÷ the client's own click-to-lead rate from A-1/A-12, labelled as an estimate)
capacity check   = jobs needed ≤ capacity in the period (B-6, I-10)
```

Net out repeat and referral revenue first (as upstream now retains the starting base before sizing acquisition), and count it once: if B-4 is already a new-customer goal, skip that line and say so. Any missing input → `[NEEDS PROOF: <row>]` and the math stays symbolic. Never fill an input with an industry norm. If the capacity check fails, the plan says so and plans to capacity, not to the goal.

Upstream's 5–40%-of-ARR ranges, 3-3-2-2-2 rule, ARR phases and funding-tier dollar ranges are SaaS benchmarks: don't apply them to a BML client.

---

## Part 5 — AARRR for a local-service business

| Stage | Means here | Typical rows | Typical skills |
|---|---|---|---|
| **Acquisition** | Found: map pack, organic, AI answers, ads, referral partners, listings, community | A-1–A-3, A-6, A-10, A-11, L-3★, L-4★, L-8, L-9, L-11 | `seo-audit`, `ai-seo`, `schema`, `programmatic-seo` (service-area pages), `content-strategy`, `ads`, `ad-creative`, `social`, `public-relations`, `co-marketing` |
| **Activation** | Lead → booked: call answered, form or booking completed, estimate or consult scheduled | I-3, I-4, I-9, A-12, A-15 | `cro`, `copywriting`, `revops` (lead handling, routing), `analytics`, `sms`, `popups` |
| **Retention** | Customer → repeat: maintenance, follow-up visits, memberships, seasonal reminders | B-7, D-7, D-8, I-6 | `emails`, `sms`, `offers` |
| **Referral** | Customer → reviews and referrals; partner referral network | I-5, A-7, A-16, L-8, G-5 | `referrals`, `emails`, `sms`, `co-marketing` |
| **Revenue** | Booked → signed job or completed visit; job value, financing, packages, upsells | B-7, D-4★, D-7, D-8, I-4 | `offers`, `pricing`, `sales-enablement` |

Upstream's signup, trial, onboarding, paywall and App Store moves don't apply unless the client sells software or an app; if one does, use upstream as written for that line of business.

Reviews sit in Referral (asking happy customers) but drive Acquisition (map pack); note the crossover.

---

## Part 6 — Tools and the ops stack (replaces upstream's MCP tables)

All pulls are read-only. Windsor.ai can write to ad accounts and GBP: never use its write actions from this skill.

| Need | Tool | Rows it informs |
|---|---|---|
| Traffic, conversions, GSC queries | Windsor.ai — GA4, Search Console | A-1, A-2, A-12 |
| GBP calls, directions, views; reviews | Windsor.ai — Google Business Profile | A-6, A-7 |
| Paid spend, CPC, CPL | Windsor.ai — Google Ads, Meta | A-9 |
| Social performance | Windsor.ai — Meta / Instagram organic | A-8 |
| Rankings, authority, competitors, local keywords, paid competitors | Semrush | A-3, A-5, L-3★, L-4★, L-7 |
| Kickoff and monthly-session notes | Fireflies (by link from the brief) | I- and B-row candidates (staged, themes only) |
| Tasks, in-flight work, plan record | ClickUp | — |
| Plan file | Google Drive | — |
| Site platform | Wix, if A-14 says so | A-4 |

Client platforms (CRM, call tracking, booking tool, email platform) are listed on page 00 §8 and A-15. Name them in Section 11 as the client's stack; BML reads them only where access is recorded, never writes to them. Ahrefs, HubSpot, Stripe, Mixpanel, Notion, Customer.io and similar appear only if A-15 or page 00 §8 says the client uses them.

**Section 11 for BML** shows: skills per stage (Part 5 table, filtered to the plan's moves), the tools above per stage, who executes (Part 9), and what each unlock trigger (Part 4) adds. The "concrete example" comes from the client's own record (a cited ClickUp task or brief item) or is framed as a planned first-month demonstration. Never reuse upstream's examples.

Upstream's ops-stack table names skills that aren't in this library (`typefully`, `copycraft`, `website-copy`, `marketing-website-design`) and tools BML doesn't use (`agent-browser`, `dev-browser`, `defuddle`, `obsidian-cli`, Pencil, Dub.co, GitHub MCP). Don't list them for a BML client.

BML-side skills worth naming: `client-context-builder` (context and monthly brief), `client-context-miner` (row backfill), `monthly-reporting` (Section 13 reporting), `marketing-loops` (recurring reviews).

---

## Part 7 — Idea bank filter (Section 12)

Use `idea-cross-reference.md` and the `marketing-ideas` numbering as-is; never renumber.

**Source of truth for fit:** `marketing-ideas`' BML fit file, `../../marketing-ideas/references/bml-local-service-fit.md` (relative to this file). Take each idea's tag, local version and gates from it, so the plan and a `marketing-ideas` shortlist never disagree. Include its local plays `BML-1`…`BML-11` under those IDs. Don't keep a separate skip list here.

| Fit tag | Section 12 status |
|---|---|
| `Fit` / `Adapt` | Now / Q2 / Q3+ / Q4+ by rows and Part 4 triggers. `Adapt` ideas use the fit file's local version, not the upstream wording |
| `Rare` | Only with a reason from the client's rows, named; otherwise the skip list |
| `SaaS-only` / `Skip` | Skip list, unless page 13 shows the client sells software or an app (then upstream as written for that line of business) |

If the fit file isn't in this install, tag each idea with the same five tags yourself and say so in Section 13.

**Gates** (the fit file's `C`, `J-3`, `J-4`, `J-6`, `$`, `B-6` gates, plus): every idea also gets its **In retainer?** value (Part 1, Step 0); any idea that needs more capacity than B-6 allows → `Q3+ — capacity` or skip; a failed gate moves the idea to the skip list with the row named.

**Section 12 shape for BML:** tables of the ideas that apply (Now / Q2 / Q3+ / Q4+), then one compact skip list grouped by reason, not one row per skipped idea.

---

## Part 8 — Section changes for BML plans

| Section | BML change |
|---|---|
| Title block | `Prepared by: Baker Labs` · `For: <client> (approver: J-1)` · `Status: Internal draft — not for client` until the maturity gate passes |
| 1 Executive summary | Written for the client's owner or leadership, not investors or a board |
| 2 Strategic frame | Positioning, ICP, offers and beliefs summarized from page 13 with row IDs. Voice rules listed as rules for scheduled deliverables. Market-quality gate uses D-2 and L-3★; market size per Part 10 |
| 3 Current state | Part 3 rubric; budget from B-10; team from I-8, I-3; capacity and season from B-6, I-10. No ARR phase, no funding tier, no CAC-as-%-of-ARR |
| 4–8 AARRR | Part 5 meanings; each move names its skill, tool, rows and **In retainer?** |
| 9 90-day roadmap | Owners are roles (BML account lead, BML specialist, client owner, client office) — never invented names. Season-aware |
| 10 12-month outlook | Quarters keyed to Part 4 triggers and I-10 seasons, not funding stages |
| 11 Ops stack | Part 6 |
| 12 Idea bank | Part 7 |
| 13 Measurement | Part 9 north star and indicators; open decisions = gap list ranked by impact; scope-note list; footer |

---

## Part 9 — Measurement and team model

**North star (pick one, specific to the client):** booked jobs (or new patients) from marketing per month; marketing-sourced revenue (booked × B-7); or cost per booked job. Name the data source; if it isn't measurable yet (A-12, A-15), the first move is to make it measurable.

**Leading indicators by stage:** Acquisition — map-pack positions for L-3★ terms, GBP calls and direction requests, organic sessions to service pages, AI-presence share (A-10). Activation — tracked calls and forms, answer rate and speed to lead (I-3), lead-to-booked (I-4). Retention — repeat or maintenance bookings, list engagement (I-6). Referral — new reviews per month and rating trend (A-7), referred jobs (B-7, I-5). Revenue — close rate and average job value (B-7, I-4).

**Cadence:** the plan's monthly review rides the client's monthly session and `monthly-reporting`; the quarterly recalibration is a plan revision (v<N+1>). If the user wants either to run on a schedule, set it up as a scheduled task (via `marketing-loops`) only on request, never as an in-session loop.

**Team model:** BML is the agency executing in-retainer work, so upstream's advice to hire a π-shaped first marketer and use outside contractors doesn't apply by default. The RACI shows BML roles for in-retainer moves, client roles (owner, whoever answers leads per I-3, approver J-1) for their part, and `TBD` for out-of-scope moves. Don't recommend client hires or other agencies unless B-4 or B-6 makes it the binding constraint — then name it as an open decision, not a move.

---

## Part 10 — Market size (replaces `market-sizing.md` for BML)

A local-service client's market is its service area, not a category, and the L rows already describe it. Answer "how big is the market?" from them:

| `market-sizing.md` step | For a BML client |
|---|---|
| Define the market | L-1 (towns or counties, core vs. edge), B-8, and the priority services and buyers (D-1, D-2) |
| TAM / SAM | Not used. L-2 describes who lives there; don't multiply it into a dollar market |
| Search-led | L-3★ volumes by service and town, peak months; L-7 CPCs |
| Competitor-led | L-4★, L-5, L-6, A-5: who wins, review counts, offers. No competitor revenue estimates |
| Bottom-up / channel-led (SOM) | Part 4 math run forward: cited lead volumes (A-1, A-6, A-9) × the client's own rates (I-4) → reachable jobs, capped by B-6 |

Keep its presentation rule: ranges, cited inputs listed apart from assumptions, a confidence label, and the assumption that would most change the answer (which goes on the gap list). Use the attractiveness scorecard only for a new service line or service area decision, every score citing rows. Never use its mini-examples or figures. OPEN or stale L rows → run `bml/local-market-research.md` (through `client-context-miner` Backfill, or `product-marketing` Intake for a pitch) and draft meanwhile with `[NEEDS PROOF: L-<n>]`; a candidate new area gets the same procedure, and its results are `DRAFT`.
<!-- BML:END bml-local-service-planning -->
