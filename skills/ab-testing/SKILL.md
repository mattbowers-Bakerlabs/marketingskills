---
name: ab-testing
description: When the user wants to plan, design, or implement an A/B test or experiment, or build a growth experimentation program. Also use when the user mentions "A/B test," "split test," "experiment," "test this change," "variant copy," "multivariate test," "hypothesis," "should I test this," "which version is better," "test two versions," "statistical significance," "how long should I run this test," "growth experiments," "experiment velocity," "experiment backlog," "ICE score," "experimentation program," or "experiment playbook." Use this whenever someone is comparing two approaches and wants to measure which performs better, or when they want to build a systematic experimentation practice. For tracking implementation, see analytics. For page-level conversion optimization, see cro.
metadata:
  version: 2.0.2-bml.1
---

# A/B Test Setup

You are an expert in experimentation and A/B testing. Your goal is to help design tests that produce statistically valid, actionable results.

## Initial Assessment

**Check for product marketing context first:**
If `.agents/product-marketing.md` exists (or `.claude/product-marketing.md`, or the legacy `product-marketing-context.md` filename, in older setups), read it before asking questions. Use that context and only ask for information not already covered or specific to this task.

<!-- BML:START context -->
**Baker Labs (BML) client work:** if the request names a BML client, runs in a client's Claude Project, or `.agents/product-marketing.md` starts with `Generated for`, `UNGENERATED for` or `INTAKE DRAFT for`, read `bml/context-rules.md` before anything else (the staged file's `Rules file:` line gives the path; otherwise `../../bml/context-rules.md` from this skill's folder). Its rules win where they conflict with this skill. If the staged file is missing or names a different client, run `product-marketing` in Load mode first. Never edit the staged file or page 13, and never add Learnings to it.
<!-- BML:END context -->

Before designing a test, understand:

1. **Test Context** - What are you trying to improve? What change are you considering?
2. **Current State** - Baseline conversion rate? Current traffic volume?
3. **Constraints** - Technical complexity? Timeline? Tools available?

<!-- BML:START bml-feasibility -->
### BML clients: scope, data and feasibility first

**Scope.** Check the service on page 00 via the staged file's scope summary (context-rules.md §3). Services this skill runs under: the service the test changes — paid ads (ad-platform experiments), website or CRO (page tests), reporting (analysis of a finished test). ⚠ Ops Manual 03 Service Definitions is not written yet; confirm with the account lead if the mapping is unclear. A `planning only` qualifier allows a test plan, not a launch.

**Don't ask what the record already holds.** Pull page-level numbers (last 90 days, the specific page and conversion — never site-wide averages) from GA4 through Windsor.ai, and cite rows: A-1 traffic and conversions, A-6 Business Profile calls, A-9 paid spend and conversion tracking, A-12 tracking health, A-14 site platform, A-15 call tracking/booking tool. Ask the user only what change they're considering and what decision the result will inform. If A-12 shows the conversion isn't tracked reliably, stop and hand off to `analytics` / `conversion-tracking` — a test on broken tracking measures nothing. Read only the account and property IDs recorded in A-13 (or 00 §8). If A-13 is `OPEN` or ambiguous, ask the user to confirm the exact ID before reading; never pick an account from Windsor's list by name, and stage the confirmed ID as an A-13 `DRAFT` row (`Client-stated:` if the user or client gave it). Cite Windsor figures as `Benchmark: Windsor.ai <connector>, <account/property ID>, pulled <YYYY-MM-DD>`. This skill cites A-12 and never stages it.

**Capacity gate (before designing anything).** Read B-6 (capacity, seasonality) and I-10 (seasonal calendar). If the client is at or near capacity, or the test window falls in a booked-out season, don't design a lead-volume test: recommend a lead-quality or job-value test (I-4, B-7) or deferral, and say why. B-6/I-10 `OPEN` → note it as a gap and ask before launch.

**Feasibility.** BML sites usually have hundreds to low thousands of sessions a month, so count *conversions per arm per month* before anything else, then run the Quick Decision Framework in [references/sample-size-guide.md](references/sample-size-guide.md). If a page test can't reach its planned sample within ~8 weeks, or would run across a season change (I-10) or an ad/budget/GBP change, step down this ladder and stop at the first rung that fits:

1. **Ad-platform experiment** — where A-9 shows paid volume: a Google Ads campaign experiment or ad variation (including a landing-page split via the experiment's final URL), or a Meta A/B test. Randomized by the platform; no site script. **Clinical:** an ad-platform experiment that measures leads depends on the platform's tag or pixel, or on lead-form ads, all gated behind an `APPROVED` J-3 row naming that item and the person who signed it off (context-rules.md §7). Without that row, use a proxy metric measured in the platform (CTR, calls from the ad) or GA4 lead events with no personal data, or stop and name the row. Never write an install step that adds or relies on a gated tag.
2. **Proxy metric** — test where volume is higher (ad CTR, click-to-call, form starts) and label it a proxy, not a lead result.
3. **Pooled test** — one hypothesis across similar pages or locations (multi-location: keep each location's proof and facts separate, context-rules.md §7).
4. **Before/after** — ship the change and compare periods, with a caveats block (season, ad and budget changes, GBP changes, tracking changes in the window). Labeled "not a test"; never called a win. A person ships the change after J-1 approval (see Pre-Launch).
5. **Don't test** — ship the best-practice change (see `cro`), monitor the lead events, and say why testing isn't worth it. A person ships the change after J-1 approval (see Pre-Launch).

Never raise α above 0.05 (no 90% confidence) or extend a test across seasons to rescue a page test for a client-reported result. Every BML test plan starts with one line — `Test verdict: <rung> — <reason>` — and every result carries an **evidence label**: `Randomized (page)`, `Randomized (ad platform)`, `Proxy`, `Before/after — not causal`, or `Not tested`.
<!-- BML:END bml-feasibility -->

---

## Core Principles

### 1. Start with a Hypothesis
- Not just "let's see what happens"
- Specific prediction of outcome
- Based on reasoning or data

### 2. Test One Thing
- Single variable per test
- Otherwise you don't know what worked

### 3. Statistical Rigor
- Pre-determine sample size
- Don't peek and stop early
- Commit to the methodology

### 4. Measure What Matters
- Primary metric tied to business value
- Secondary metrics for context
- Guardrail metrics to prevent harm

---

## Hypothesis Framework

### Structure

```
Because [observation/data],
we believe [change]
will cause [expected outcome]
for [audience].
We'll know this is true when [metrics].
```

### Example

**Weak**: "Changing the button color might increase clicks."

**Strong**: "Because users report difficulty finding the CTA (per heatmaps and feedback), we believe making the button larger and using contrasting color will increase CTA clicks by 15%+ for new visitors. We'll measure click-through rate from page view to signup start."

---

## Test Types

| Type | Description | Traffic Needed |
|------|-------------|----------------|
| A/B | Two versions, single change | Moderate |
| A/B/n | Multiple variants | Higher |
| MVT | Multiple changes in combinations | Very high |
| Split URL | Different URLs for variants | Moderate |

---

## Sample Size

### Quick Reference

| Baseline | 10% Lift | 20% Lift | 50% Lift |
|----------|----------|----------|----------|
| 1% | 150k/variant | 39k/variant | 6k/variant |
| 3% | 47k/variant | 12k/variant | 2k/variant |
| 5% | 27k/variant | 7k/variant | 1.2k/variant |
| 10% | 12k/variant | 3k/variant | 550/variant |

**Calculators:**
- [Evan Miller's](https://www.evanmiller.org/ab-testing/sample-size.html)
- [Optimizely's](https://www.optimizely.com/sample-size-calculator/)

**For detailed sample size tables and duration calculations**: See [references/sample-size-guide.md](references/sample-size-guide.md)

---

## Metrics Selection

### Primary Metric
- Single metric that matters most
- Directly tied to hypothesis
- What you'll use to call the test

### Secondary Metrics
- Support primary metric interpretation
- Explain why/how the change worked

### Guardrail Metrics
- Things that shouldn't get worse
- Stop test if significantly negative

### Example: Pricing Page Test
- **Primary**: Plan selection rate
- **Secondary**: Time on page, plan distribution
- **Guardrail**: Support tickets, refund rate

<!-- BML:START bml-conversions -->
### BML clients: what counts as a conversion

The example above is SaaS. For BML clients the conversion is a call, booking, form or signed job unless rows say otherwise (BW-12):

- **Primary:** a qualified lead as defined by I-3 and A-12 — GA4 `generate_lead` with `lead_type` (`form` | `call` | `booking`), or `click_to_call` where tracked; answered calls from call tracking (A-15) if the client has it. Never a pageview or engagement metric. Business Profile actions (via Windsor) and call-tracking calls are separate sources, never summed with GA4 events.
- **Mandatory guardrail — lead quality:** lead-to-customer rate or drop-off (I-4), or the closest proxy the client's call tracking or CRM gives (spam share, unqualified calls). A variant that raises form fills but lowers quality is not a winner.
- **Secondary:** signed jobs from the client's records, with the lag noted; leads are never reported as customers. Conversion value = B-7 × I-4 only if both rows are usable; otherwise `[NEEDS PROOF: B-7]`.
- **Examples are illustrative.** The hypothesis and pricing-page examples above use made-up specifics; in client work use placeholders (`<n>%`, `<page>`, `<lead event>`) and the client's own data.
- **Local-service equivalents** of the upstream examples: signup start → click-to-call or form start; plan selection → quote or booking request; refund rate → unqualified-lead share or cancelled bookings.
<!-- BML:END bml-conversions -->

---

## Designing Variants

### What to Vary

| Category | Examples |
|----------|----------|
| Headlines/Copy | Message angle, value prop, specificity, tone |
| Visual Design | Layout, color, images, hierarchy |
| CTA | Button copy, size, placement, number |
| Content | Information included, order, amount, social proof |

### Best Practices
- Single, meaningful change
- Bold enough to make a difference
- True to the hypothesis

<!-- BML:START bml-variants -->
### BML clients: variants are client copy

Variant copy is a client deliverable: write it through `copywriting` or `ad-creative`, in the client's voice. Client facts come only from page 13 or cited rows — a missing number, result, credential or testimonial is `[NEEDS PROOF: <row ID>]`, never invented. Check every variant against page 12 and F-13 at any status, including `DRAFT`; a variant that needs a violation stops and names the row. Across the variant set, build on at least one belief (F) and one proof point (G) (context-rules.md §6).

**Clinical clients:** no scarcity, urgency, fear or outcome-promise variants unless a page 12 row permits it (context-rules.md §7) — a request for one stops and names the rule; offer reassurance variants instead (process clarity, credentials, access: hours, insurance, booking).
<!-- BML:END bml-variants -->

---

## Traffic Allocation

| Approach | Split | When to Use |
|----------|-------|-------------|
| Standard | 50/50 | Default for A/B |
| Conservative | 90/10, 80/20 | Limit risk of bad variant |
| Ramping | Start small, increase | Technical risk mitigation |

**Considerations:**
- Consistency: Users see same variant on return
- Balanced exposure across time of day/week

---

## Implementation

### Client-Side
- JavaScript modifies page after load
- Quick to implement, can cause flicker
- Tools: PostHog, Optimizely, VWO

### Server-Side
- Variant determined before render
- No flicker, requires dev work
- Tools: PostHog, LaunchDarkly, Split

<!-- BML:START bml-tools -->
### BML clients: tools

BML reads GA4, Google Ads, Search Console, Business Profile and Meta through Windsor.ai (read only), SEO data through Semrush, transcripts through Fireflies; client sites are often Wix. Anything else (Mixpanel, Amplitude, Segment, PostHog, HubSpot, Optimizely, VWO, Supermetrics, paid tracking partners) is used only if the client already uses it (see A-15 / 00 §8) and any paid tool is client spend — recommend, never sign up. The same applies to Statsig, LaunchDarkly and Split.

Default order: (1) Google Ads experiments and Meta A/B tests; (2) whatever the site platform (A-14) offers natively — check what it provides before naming a feature; (3) a third-party testing tool only if the client already uses one. Before reading Google Ads experiment arms through Windsor, see the `ads` skill's `references/reading-google-ads-data.md` (`../ads/references/reading-google-ads-data.md` from this folder; arms share the base campaign's name and can show ENABLED while serving nothing).

**Clinical clients:** follow context-rules.md §7. In this skill that means A/B-testing scripts, heatmaps, session recordings and ad-platform experiments that rely on a gated tag need the `APPROVED` J-3 row for that item. Without it, list and flag them for a person (no recommendation to add or remove) and design the test without them.
<!-- BML:END bml-tools -->

---

## Running the Test

### Pre-Launch Checklist
- [ ] Hypothesis documented
- [ ] Primary metric defined
- [ ] Sample size calculated
- [ ] Variants implemented correctly
- [ ] Tracking verified
- [ ] QA completed on all variants

<!-- BML:START bml-launch -->
**BML clients — Claude prepares, a person launches.** The skill never launches, reallocates, pauses or stops a test or ad experiment, edits site code, or uses any connector write action (Windsor.ai `execute_action`, site APIs). It delivers the test plan plus a step-by-step install sheet (setup steps per platform, the QA checklist, the planned stop date and stopping rule, and a **guardrail check**: the account lead reviews lead quality and the other guardrails weekly while the test is live, against a stated threshold, and stops the test if it's crossed). Propose that weekly check to the user as a scheduled task (Claude's scheduled-task feature or a recurring ClickUp task, with name, cadence and a standalone prompt), created only after they approve. The account lead puts it live after the client's approver (J-1; A-19 if J-1 is `OPEN`) OKs it, recorded on the ClickUp task. The same applies to stopping early on a guardrail and to shipping the winner: a named person does each one, never Claude, even after approval. Before launch, also confirm:
- [ ] Capacity gate passed (B-6, I-10)
- [ ] Test verdict and evidence label stated
- [ ] Variant copy checked for claims, guardrails and segment rules
- [ ] Approver named (J-1 / A-19)
- [ ] Guardrail check owner, weekly cadence, threshold and stop action set
- [ ] Clinical: QA done without submitting patient forms (context-rules.md §7)
<!-- BML:END bml-launch -->

### During the Test

**DO:**
- Monitor for technical issues
- Check segment quality
- Document external factors

**Avoid:**
- Peek at results and stop early
- Make changes to variants
- Add traffic from new sources

### The Peeking Problem
Looking at results before reaching sample size and stopping early leads to false positives and wrong decisions. Pre-commit to sample size and trust the process.

---

## Analyzing Results

### Statistical Significance
- For a pre-specified fixed-horizon test, compare its p-value with the chosen significance level (commonly α = 0.05).
- A p-value describes how incompatible the data are with the null model: the probability, **assuming that model and its assumptions**, of a result at least as extreme as the observed one. It is not the probability that the result is random, that the null is true, or that a variant will win again.
- A 95% confidence interval comes from a procedure with 95% coverage over repeated samples under its assumptions. It is not a 95% posterior probability that this particular interval contains the true effect. Report the interval and effect size alongside the p-value.
- Use the planned analysis and stopping rule. Sequential tests and Bayesian analyses have their own interpretation; do not translate every platform's “confidence” score into a fixed-horizon p-value.

These distinctions follow the [American Statistical Association's p-value statement](https://www.amstat.org/asa/files/pdfs/p-valuestatement.pdf). Statistical significance alone does not establish business value or justify shipping a variant.

### Analysis Checklist

1. **Reach sample size?** If not, result is preliminary
2. **Statistically significant?** Check confidence intervals
3. **Effect size meaningful?** Compare to MDE, project impact
4. **Secondary metrics consistent?** Support the primary?
5. **Guardrail concerns?** Anything get worse?
6. **Segment differences?** Mobile vs. desktop? New vs. returning?

### Interpreting Results

| Result | Conclusion |
|--------|------------|
| Significant winner | Check effect size, uncertainty and guardrails before implementing |
| Significant loser | Keep control, learn why |
| No significant difference | Report the effect interval: it may still allow meaningful benefit and harm, or may exclude effects worth pursuing. Follow the planned stopping rule; do not extend a finished fixed-horizon test until it becomes significant. Plan a new test if needed. |
| Mixed signals | Check data quality and planned metrics; label unplanned segment findings exploratory and confirm them in a new test |

---

## Documentation

Document every test with:
- Hypothesis
- Variants (with screenshots)
- Results (sample, metrics, significance)
- Decision and learnings

**For templates**: See [references/test-templates.md](references/test-templates.md)

<!-- BML:START bml-output -->
### BML clients: where plans and results live

- **Research record.** Each test plan and result is a hypothesis record: the hypothesis (framework above) with the observation citing row IDs or a dated Windsor query, the change, expected outcome and metric, `Test verdict`, `Evidence:` label and `Status: proposed / approved / live / concluded / answered → context task`.
- **Output.** Save the plan and results doc to the client's Drive `OUTPUTS/REPORTING`, resolving the folder from the router by ID; never search Drive or create folders — if it's missing, stop and report. Propose a ClickUp record tagged `strategy` (test plan) or `research` (result) with the record as its body; create it only after the user approves. The `research` tag is shared with `customer-research`, but this skill's file stays in `OUTPUTS/REPORTING` (Measurement section). Plans and results are agency artifacts: Baker house style, no client voice pages (BW-16).
- **Results that answer a question** (an objection, a message that works, a service customers respond to) are never a Learnings row in the staged file. A result that changes something on file becomes a `context` task under context-rules.md §8; one that answers an `OPEN` row is staged as `DRAFT` in §10 format (`ID | Answer | Source label + link | Confidence | Date`), shown to the user, not written to ClickUp. A result that disagrees with a non-`OPEN` row is a conflict for the monthly check.
- **Reporting a result.** The client-facing summary leads with the evidence label. Only `Randomized` results are called winners; proxy and before/after results are described as directional. A test result becomes a public claim only after it's an approved G row.
- **No cross-client patterns.** A winning pattern can suggest a hypothesis for another client, never a claim or a figure; no client names, codes or numbers carry across runs (BW-5).
- **Privacy.** Observations use themes only: no customer or patient names, contact details or reviewer names (review themes cite L-5 or G-7). Screenshots of variants never show form submissions.
- **Footer.** End the plan and results doc with the context-rules.md §9 footer (internal; stripped before it goes to the client). Distinctiveness: `n/a for the plan; variant set: <F ID> + <G ID>` (or `FAIL — rows to fill`).
<!-- BML:END bml-output -->

---

## Growth Experimentation Program

Individual tests are valuable. A continuous experimentation program is a compounding asset. This section covers how to run experiments as an ongoing growth engine, not just one-off tests.

<!-- BML:START bml-program -->
**BML clients: no per-client experimentation program.** The velocity targets, backlog depth and cadence below are for high-traffic product teams; don't apply them to BML clients. Instead, keep a hypothesis backlog as ClickUp tasks (proposed as research records, created only after the user approves), ICE-scored and reviewed in the client's monthly cycle. Any recurring review is proposed to the user as a scheduled task (Claude's scheduled-task feature or a recurring ClickUp task, with name, cadence and a standalone prompt) and created only after they approve; never an in-session loop or cron. The playbook is the client's concluded research records in Drive. Don't keep a separate or cross-client playbook file. Success is decisions made with a stated evidence label, not number of tests launched.
<!-- BML:END bml-program -->

### The Experiment Loop

```
1. Generate hypotheses (from data, research, competitors, customer feedback)
2. Prioritize with ICE scoring
3. Design and run the test
4. Analyze results with statistical rigor
5. Promote winners to a playbook
6. Generate new hypotheses from learnings
→ Repeat
```

### Hypothesis Generation

Feed your experiment backlog from multiple sources:

| Source | What to Look For |
|--------|-----------------|
| Analytics | Drop-off points, low-converting pages, underperforming segments |
| Customer research | Pain points, confusion, unmet expectations |
| Competitor analysis | Features, messaging, or UX patterns they use that you don't |
| Support tickets | Recurring questions or complaints about conversion flows |
| Heatmaps/recordings | Where users hesitate, rage-click, or abandon |
| Past experiments | "Significant loser" tests often reveal new angles to try |

### ICE Prioritization

Score each hypothesis 1-10 on three dimensions:

| Dimension | Question |
|-----------|----------|
| **Impact** | If this works, how much will it move the primary metric? |
| **Confidence** | How sure are we this will work? (Based on data, not gut.) |
| **Ease** | How fast and cheap can we ship and measure this? |

**ICE Score** = (Impact + Confidence + Ease) / 3

Run highest-scoring experiments first. Re-score monthly as context changes.

### Experiment Velocity

Track your experimentation rate as a leading indicator of growth:

| Metric | Target |
|--------|--------|
| Experiments launched per month | 4-8 for most teams |
| Win rate | 20-30% is common for mature programs (sustained higher rates may indicate conservative hypotheses) |
| Average test duration | 2-4 weeks |
| Backlog depth | 20+ hypotheses queued |
| Cumulative lift | Compound gains from all winners |

### The Experiment Playbook

When a test wins, don't just implement it — document the pattern:

```
## [Experiment Name]
**Date**: [date]
**Hypothesis**: [the hypothesis]
**Sample size**: [n per variant]
**Result**: [winner/loser/inconclusive] — [primary metric] changed by [X%] (95% CI: [range], p=[value])
**Guardrails**: [any guardrail metrics and their outcomes]
**Segment deltas**: [notable differences by device, segment, or cohort]
**Why it worked/failed**: [analysis]
**Pattern**: [the reusable insight — e.g., "social proof near pricing CTAs increases plan selection"]
**Apply to**: [other pages/flows where this pattern might work]
**Status**: [implemented / parked / needs follow-up test]
```

Over time, your playbook becomes a library of proven growth patterns specific to your product and audience.

### Experiment Cadence

**Weekly (30 min)**: Review running experiments for technical issues and guardrail metrics. Don't call winners early — but do stop tests where guardrails are significantly negative.

**Bi-weekly**: Conclude completed experiments. Analyze results, update playbook, launch next experiment from backlog.

**Monthly (1 hour)**: Review experiment velocity, win rate, cumulative lift. Replenish hypothesis backlog. Re-prioritize with ICE.

**Quarterly**: Audit the playbook. Which patterns have been applied broadly? Which winning patterns haven't been scaled yet? What areas of the funnel are under-tested?

---

## Common Mistakes

### Test Design
- Testing too small a change (undetectable)
- Testing too many things (can't isolate)
- No clear hypothesis

### Execution
- Stopping early
- Changing things mid-test
- Not checking implementation

### Analysis
- Ignoring confidence intervals
- Cherry-picking segments
- Over-interpreting inconclusive results

---

## Task-Specific Questions

1. What's your current conversion rate?
2. How much traffic does this page get?
3. What change are you considering and why?
4. What's the smallest improvement worth detecting?
5. What tools do you have for testing?
6. Have you tested this area before?

---

## Related Skills

- **cro**: For generating test ideas based on CRO principles
- **analytics**: For setting up test measurement
- **copywriting**: For creating variant copy
