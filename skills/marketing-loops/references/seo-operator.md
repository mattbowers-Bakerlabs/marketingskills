# The SEO Operator

<!-- BML:START bml-seo-operator -->
> **BML client work: draft mode only.** This file assumes a SaaS owner, repo access and an agent that ships. For a BML client, these replace the matching parts below (all BML blocks in `SKILL.md`, `loop-state.md` and `loop-guardrails.md` still apply):
> - **Scope:** SEO `Active` on page 00 at setup and every run. Staged site changes stay within what that entry and its qualifier cover; anything beyond it (new templates, a redesign) is a scope note for the account lead. A qualifier like "reporting only" means the weekly report and nothing else.
> - **Ship mode is always "stage for approval."** No PRs, merges, deploys or edits through Wix or any site connector. "The output is changes to the site", "ship the top item" and "the first run ends with real changes" become: each run ends with ready-to-apply change sets in `OUTPUTS/SEO` or `OUTPUTS/WEBSITE`, applied by a person after the J-1 approver signs off. The first run is a dry run that records the baseline. Skip the repo steps (first run 1, lint/build).
> - **Settings:** conversion = calls, bookings, forms or signed jobs (I-3); competitors from E-1, E-2, L-4; data from Windsor.ai (`searchconsole`, `googleanalytics4`) and Semrush.
> - **Memory:** no `.agents/seo/`. The query map, queue and prompt panel live in the Drive loop file (`loop-state.md` BML block); snapshots and reports go to the client folders by ID. There is no `claims.md`: page 13 and the rows it cites are the claims source (never "learn the product from the code").
> - **Cadence:** "every run" items run weekly, as one Claude scheduled task (`SKILL.md` BML scheduling block).
> - **Writing gate:** "real numbers, the owner's opinions" means F and G rows; missing ones become `[NEEDS PROOF: <row ID>]` (`bml/context-rules.md` at the repo root, §4, §6). Comparison pages check J-4 first. Social posts only if Social is `Active`, as drafts. A free-tool idea is a recommendation for the account lead, not work.
> - **Weekly report:** `OUTPUTS/REPORTING`, Baker house style, context footer (§9).
<!-- BML:END bml-seo-operator -->

A recipe for handing an agent the whole SEO job for one site, run from the site's own repo on a schedule. It doesn't add new mechanics. It bundles the SEO loops from the catalog, gives them one shared memory, and sets the rules that keep an always-on agent useful instead of busy.

Use it when the user wants SEO run for them rather than advice about SEO, and the agent can work in the repo that builds the marketing site. If the site lives in a hosted builder with no repo access, run the same loops in draft mode and hand the changes to a human.

## Before the first run

Settle five things with the owner and write them at the top of the operator brief (below):

| Setting | What to capture |
|---------|-----------------|
| **Site** | The production URL |
| **Conversion** | The one action that counts (trial, demo request, purchase). Traffic that never reaches it isn't the goal |
| **Competitors** | 3–8 names, or permission to find them from the SERPs and AI answers |
| **Ship mode** | "Open a PR for review" (default) or "merge when checks pass." Auto-merge needs the owner's explicit say-so; see `loop-guardrails.md` |
| **Data access** | Which of Search Console, analytics, a rank or backlink tool, and an AI-visibility tool the agent can read |

Then confirm the foundation: tracking works (the tracking-QA loop), and `.agents/product-marketing.md` exists. If it doesn't, build it with the `product-marketing` skill first. The operator reads product facts from there; it doesn't keep a second copy.

## Shared memory

Agents start every run with no memory, so everything the operator knows lives in files. Use the loop-state convention (`.agents/loops/`) for run logs, plus one folder for SEO working files:

```
.agents/seo/
  brief.md          # the five settings above + any owner preferences
  claims.md         # claims ledger: each customer-facing fact, its source of truth, the pages that state it
  queries.csv       # query map: query, intent, page, status (live / planned / gap), position, last checked
  queue.md          # work queue, ranked by expected conversions per hour of effort
  prompts.md        # AI prompt panel by awareness stage, with each run's results
  snapshots/        # competitor sitemaps and key pages, for diffing
  reports/          # one file per weekly report
.agents/loops/seo-operator.log   # one line per run, acted or not
```

Two rules make the query map work. **Every page owns one primary query**, and **every query has at most one page.** Two pages chasing the same query is a defect: merge them and redirect the weaker one. A query with no page is a gap and goes in the queue.

Every fact in `claims.md` cites where it came from (a file in the product repo, the live pricing page). Facts from memory don't go in.

## Run schedule

| Every run (daily, or on each deploy) | Weekly | Monthly |
|---|---|---|
| Site health crawl | Striking-distance push | Rebuild the query map (keyword-gap) |
| Claim drift | Ranking-drop watch | Content decay |
| Ship the top item in the queue | Indexing check | Comparison-page review (`competitors` asset audit) |
| Append to the run log | Internal linking | Backlink prospecting + directory submissions |
| | AI-answer check | One free-tool candidate (`free-tools`) |
| | Competitor watch (sitemap diff) | |
| | Weekly report | |

Each cell is a catalog loop or a step defined below; run it with that loop's self-check, state, and stop rules. Skip any loop whose data isn't connected and say so in the report.

**Site health crawl.** Fetch the sitemap and request every URL. Flag non-200s, redirect chains, wrong canonicals, stray `noindex`, robots blocks, broken internal links, orphan pages, duplicate or missing titles and descriptions, and pages whose main content isn't in the server-rendered HTML. The `seo-audit` skill covers each check.

**Indexing check.** Compare the sitemap to what Search Console reports as indexed. For each unindexed URL, find the cause (thin, duplicate, orphaned, blocked, canonicalized elsewhere) and fix that, not the symptom. If indexing can't be verified, report "not verified." Never report a page as indexed without checking.

**Competitor watch.** Diff each competitor's sitemap against last week's snapshot to see what they published, then check which of those pages rank. Queue a response only where you can build a better page, not for every page they ship.

## The first run

1. **Learn the repo.** How routes and posts are created, and where titles, meta descriptions, canonicals, the sitemap, robots.txt, and structured data come from. Add pages the way the repo already does.
2. **Learn the product** from the code and the live site until you can explain it better than the homepage does. Fill `claims.md`.
3. **Build the query map** from buyers, not search volume: the problems they search, category terms, competitor names, "alternative" and "vs" queries, integrations, use cases, pre-purchase questions.
4. **Crawl the site** and log every problem.
5. **Write the queue**, then ship the top three fixes in the agreed ship mode, so the first run ends with real changes instead of a plan.

## Operating rules

- **The output is changes to the site.** A memo recommending a fix isn't progress; a PR with the fix is. Research earns its place only when it produces a change.
- **Finish before starting.** Ship the change in progress before opening the next one. Half-done drafts don't rank.
- **No guessing past missing data.** When a source isn't connected, note it in the report with what connecting it would make possible, then work with what exists. Don't fill gaps with estimates presented as data.
- **The product is the source of truth.** When a page and the product disagree, change the page. Never change the product, its pricing, or its claims to match marketing.
- **Escalate repeat failures.** If the same fix fails twice, stop, record what was tried, and raise it in the report.
- **Check before shipping.** Run the repo's lint, type check, and build, then load each changed page and look at it.
- **Don't break what earns.** Never delete, noindex, or redirect a page that gets traffic or has backlinks without the owner's approval.
- **Drafts only for anything outward-facing.** Outreach emails, directory listings, social posts, and new accounts are drafted for the owner to send. See `loop-guardrails.md`.

## The writing gate

Before writing any new page, read the current top results for its query and write one sentence on what the new page will have that none of them do: original data, a real example from the product, a working tool, a clearer answer. If you can't write that sentence, don't write the page. This is the same information-gain test as in `content-strategy`.

Then:
- Answer the query in the first two sentences, then add detail.
- Use what only this company has: product screenshots, real numbers, the owner's opinions. If none exist for a topic, ask for them in the report rather than writing around the gap.
- Never invent a statistic, quote, customer, review, price, or benchmark.
- Ship each new page with the checklist in `seo-audit`'s [rankings push reference](https://github.com/coreyhaines31/marketingskills/blob/main/skills/seo-audit/references/rankings-push.md): internal links from at least three existing pages, title, meta description, canonical, sitemap entry, structured data where it fits.
- Draft one social post per new article, built on its single most useful point (`social`).

## The weekly report

One screen, written to `.agents/seo/reports/YYYY-MM-DD.md`:

```markdown
## SEO week of [date]
**Shipped:** [each change, with its URL]
**Moved:** [clicks, impressions, positions, conversions vs last week, each with its source]
**Broken:** [open problems, worst first]
**Next:** [top 3 queue items]
**Need from you:** [at most 3 asks: data access, approvals, facts or screenshots only the owner has]
```

If a number can't be sourced, leave it out rather than estimating it.

## When not to run an operator

- **The site has almost no search demand to win** (a brand-new category, a tiny niche). Spend on positioning and distribution first.
- **No one will review the PRs.** An operator in PR mode with no reviewer just builds a backlog of stale branches. Use a weekly manual run instead.
- **Tracking is broken.** Fix it first. Every loop above reads from it.
