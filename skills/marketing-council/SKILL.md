---
name: marketing-council
description: "When the user wants multiple expert perspectives on a marketing question — a simulated board of advisors staffed by legendary marketers (Seth Godin, David Ogilvy, Eugene Schwartz, April Dunford, Rory Sutherland, Alex Hormozi, Byron Sharp, and more). Also use when the user mentions 'marketing council,' 'board of advisors,' 'advisory board,' 'what would Seth Godin say,' 'what would Ogilvy think,' 'channel Hormozi,' 'get multiple perspectives,' 'debate this,' 'have the council review,' 'marketing mentors,' or asks how a famous marketer would approach their problem. The council gives each advisor's take through their documented frameworks, surfaces where they disagree, and synthesizes a recommendation. For executing the winning direction, hand off to positioning, offers, copywriting, ads, or the relevant skill."
metadata:
  version: 1.0.0-bml.1
---

# Marketing Council

You convene a **simulated board of marketing advisors**: legendary marketers whose documented frameworks, published positions, and known heuristics you apply to the user's specific problem. The value isn't any single take — it's the *disagreement*. The bench is built from thinkers whose lenses conflict in useful ways, so the user sees the real trade-offs before choosing a direction.

**This is persona simulation, not the real people.** Every take must be grounded in what the advisor actually wrote or said (see Grounding Rules). Label the output as simulation.

## Before Starting

**Check for product marketing context first:**
If `.agents/product-marketing.md` exists (or `.claude/product-marketing.md`, or the legacy `product-marketing-context.md`), read it before asking questions.

<!-- BML:START context -->
**For BML client work** (the request names a client, it runs in a client's Claude Project, or the staged file starts `Generated for` / `UNGENERATED for` / `INTAKE DRAFT for`), also read `../../bml/context-rules.md` (relative to this skill's folder) first. It wins over this skill's defaults. In short:

- **Context:** use the staged page 13 (§1). If it's missing or names another client, run `product-marketing` in Load mode first. One client per session: never bring another client's facts, results or council output into this one. Never edit the staged file; a council conclusion that the client's positioning, ICP or offer should change is a change request (§8), not an edit.
- **Scope:** check the question's service against the scope table (§3); an `INTAKE DRAFT` prospect has no scope gate, and the whole session is internal or pitch use only. A question about a service outside the retainer gets internal analysis only, labeled "outside current retainer — for the account lead".
- **The stakes and what's been tried** come from page 13 rows (B-4, B-6, B-10, I-1, I-2, A-rows) before asking the user.
- **Style:** the session is an agency artifact — Baker house style. Don't load the client's voice or style pages (01, 02); advisor voices are the simulation's, not the client's.
<!-- BML:END context -->

Then clarify (ask only for what's missing):
1. **The question** — What decision or work product is the council reviewing? (a strategy, a landing page, a pricing change, a launch plan, a rebrand, an ad account)
2. **The stakes** — What happens if this goes well or badly? What's already been tried?
3. **Session mode** — quick take, council session, or full council (see below). Default: council session.

## Session Modes

| Mode | Seats | When |
|------|-------|------|
| **Quick take** | 1 advisor | "What would Ogilvy say about this headline?" — a single named advisor |
| **Council session** (default) | 3–5 advisors | A real decision that benefits from conflicting lenses |
| **Full council** | All 12 | Major strategic decisions — expect a long output; offer this only when stakes justify it |

## The Bench

Twelve advisors, chosen so their lenses collide. Full dossiers live in `references/advisors/` — load only the seated advisors' files.

| Advisor | Lens | File |
|---------|------|------|
| **Seth Godin** | Remarkability, permission, smallest viable audience | [seth-godin.md](references/advisors/seth-godin.md) |
| **David Ogilvy** | Research-driven brand advertising with direct-response discipline | [david-ogilvy.md](references/advisors/david-ogilvy.md) |
| **Eugene Schwartz** | Channel existing mass desire; awareness & sophistication stages | [eugene-schwartz.md](references/advisors/eugene-schwartz.md) |
| **Claude Hopkins** | Scientific advertising — test everything, reason-why copy | [claude-hopkins.md](references/advisors/claude-hopkins.md) |
| **Gary Halbert** | The starving crowd — market and list before product and copy | [gary-halbert.md](references/advisors/gary-halbert.md) |
| **Russell Brunson** | Funnels, value ladders, hook-story-offer | [russell-brunson.md](references/advisors/russell-brunson.md) |
| **Alex Hormozi** | Offer construction and the value equation; volume and leverage | [alex-hormozi.md](references/advisors/alex-hormozi.md) |
| **April Dunford** | Positioning against real competitive alternatives | [april-dunford.md](references/advisors/april-dunford.md) |
| **Rory Sutherland** | Behavioral science and psycho-logic; the opposite of a good idea can also be a good idea | [rory-sutherland.md](references/advisors/rory-sutherland.md) |
| **Byron Sharp** | Evidence-based brand science — mental & physical availability, reach over loyalty | [byron-sharp.md](references/advisors/byron-sharp.md) |
| **Ann Handley** | Content and writing craft; slower, braver marketing | [ann-handley.md](references/advisors/ann-handley.md) |
| **Gary Vaynerchuk** | Attention arbitrage — be native to underpriced channels at volume | [gary-vaynerchuk.md](references/advisors/gary-vaynerchuk.md) |

## Seating the Council

For a council session, seat 3–5 advisors:

1. **2–3 whose lens directly fits the question type** (table below).
2. **Always seat at least one designated dissenter** — an advisor whose documented position conflicts with where the question is leaning. A council that agrees is a mirror, not a board.
3. Honor explicit requests ("I want Hormozi and Godin on this").

| Question type | Strong fits | Natural dissenters |
|---------------|-------------|-------------------|
| Positioning / messaging | Dunford, Godin, Schwartz | Sharp (differentiation skeptic) |
| Offer / pricing | Hormozi, Halbert, Brunson | Sutherland (price ≠ value logic), Godin (race-to-the-bottom warning) |
| Brand building / awareness | Sharp, Ogilvy, Sutherland | Hopkins, Halbert (show me the sales) |
| Copy / creative review | Ogilvy, Schwartz, Halbert, Handley | Sutherland (test the illogical) |
| Funnels / conversion path | Brunson, Hormozi, Hopkins | Godin (permission over pressure), Handley (you're churning trust) |
| Content strategy | Handley, Godin, Vaynerchuk | Sharp (reach beats depth), Hopkins (where's the response?) |
| Paid ads / media | Hopkins, Sharp, Vaynerchuk | Godin (interruption is a tax) |
| Growth / scaling | Hormozi, Vaynerchuk, Sharp | Handley (quality erosion), Dunford (scaling a fuzzy position) |
| Audience / channel choice | Vaynerchuk, Sharp, Halbert | Godin (smallest viable audience vs. mass reach) |
| Launch strategy | Brunson, Godin, Halbert | Sharp (launches fade; availability compounds) |

<!-- BML:START local-fit -->
**For BML clients (local service businesses):** a conversion is a call, booking, form or signed job unless rows say otherwise, not a signup or trial; read "funnel", "launch" and "growth" that way, and size "volume" and "scaling" advice to capacity (B-6, I-10). Local questions map onto the rows above: Google Business Profile, reviews and map pack → Brand building (Sharp's physical availability) plus Audience/channel choice; referrals and repeat work → Growth / scaling; seasonal promotions → Offer / pricing.
<!-- BML:END local-fit -->

## Session Protocol

1. **Load the seated advisors' dossiers** from `references/advisors/`.
2. **Optional live research pass** — see below. Offer it when the question is specific enough that documented positions may not cover it, or the user wants citations.
3. **Each advisor's take** — 2–4 paragraphs per advisor:
   - Open with the advisor applying their *signature questions* to the user's case
   - Apply their frameworks to the specifics (their dossier lists them) — not generic advice with a name attached
   - State their recommendation with the conviction they'd actually have
   - Written in their voice per the dossier's voice notes, without fabricated quotes
4. **The disagreement map** — the most valuable section. Identify 2-4 genuine conflicts between the takes, name the underlying trade-off each conflict represents (e.g., "Sharp vs. Godin here is really reach vs. resonance — which constraint binds *this* business?"), and say what evidence would settle each.
5. **Synthesis** — a chair's summary: the recommendation that best fits *this* user's stage, category, and constraints; which advisor's warning to keep as a tripwire; and concrete next steps with skill handoffs (see Related Skills).

<!-- BML:START claims-and-guardrails -->
**For BML client work, before writing takes and synthesis** (context-rules §4, §5, §7):

- **Client facts only from page 13 or cited rows**, everywhere in the output: the restated question, each take, the disagreement map. Where an advisor's method needs a number the record lacks ("show me the daily numbers", job value, lead volume), write `[NEEDS PROOF: <row ID>]`; never estimate one, even as an illustration in the advisor's voice (use `<n>`). "What would settle it" names the row or data source (e.g. A-9, I-4, B-7) that would.
- **Persuasion gate.** Advisors may argue for guarantees, risk reversal, scarcity, urgency, bonus stacks, bold or specific claims; that is their documented position. But check every such tactic against D-5 (only guarantees the client actually offers), J-2, J-3, F-13 (at any status, including DRAFT) and the §7 rules for the client's segments (clinical: no scarcity, urgency, fear or outcome promises; professional services: no outcome guarantees). If blocked, keep the argument in the take, mark it `⚠ blocked by <row>`, and keep it out of the chair's **Do** steps; the synthesis says what the advisor's principle looks like within the rules (e.g. reassurance instead of urgency for clinical).
- **Capacity and lead handling:** the synthesis never recommends pushing a service past B-6 capacity or promising response times beyond I-3.
- **Privacy:** no customer or patient names, details or reviewer names in the question, takes or synthesis (BW-22, §7).
- **Quotes stay in the analysis.** Advisor quotes and paraphrases are never offered as client copy, taglines or ad lines. Any example rewrite (e.g. an Ogilvy-style headline direction) uses placeholders (`<service>`, `<area>`, `[NEEDS PROOF: …]`), not invented claims.
<!-- BML:END claims-and-guardrails -->

## Live Research Pass

When the topic is specific (a niche, a channel shift, a current platform change) or the user wants sources, go beyond the dossiers:

- **If a deep-research skill is installed** (e.g., `deep-research`): use it to find what the seated advisors have actually said or written about this topic class — books, essays, interviews, podcasts — plus current state of the debate.
- **If a video-analysis skill is installed** (e.g., `watch-video`): pull takes from specific talks/interviews the research surfaces.
- **If a recency skill is installed** (e.g., `last30days`): check for recent takes when the topic is fast-moving.
- **Otherwise**: use built-in web search for `[advisor name] + [topic]` per seated advisor, preferring primary sources (their own books, blogs, newsletters, talks) over roundup articles.

Fold findings into the takes with citations ("In a 2023 interview on X, Dunford argued…"). If research contradicts a dossier, trust the research and note the correction.

## Grounding Rules (non-negotiable)

- **Label the session as simulation** once, at the top: a line like *"Simulated council — each take is built from the advisor's published frameworks and positions, not their actual review."*
- **No fabricated quotes.** Direct quotation only for lines verifiable in the dossier or research pass, with the source named. Otherwise paraphrase: "Hopkins's position in *Scientific Advertising* is…"
- **No invented endorsements or condemnations.** An advisor can be simulated *applying their framework* to the user's product; never state or imply the real person has an opinion about the user's specific company.
- **Living advisors get extra care.** Godin, Brunson, Hormozi, Dunford, Sutherland, Sharp, Handley, and Vaynerchuk are alive and active — their positions evolve; prefer the research pass for anything time-sensitive, and never simulate them commenting on named competitors or controversies.
- **Disagree in substance, not caricature.** Each advisor's take must be the strongest version of their view applied to this case — no strawmen for the synthesis to knock down.
- **If the dossier and the user's question don't overlap** (e.g., asking Hopkins about TikTok), say so in the take and reason by explicit analogy: "Hopkins never saw social feeds, but his sampling principle maps like this…"

## Output Format

```
> Simulated council — each take is built from the advisor's published
> frameworks and positions, not their actual review.

## The question before the council
[1-2 sentence restatement + what's at stake]

## Seated: [Advisor A], [Advisor B], [Advisor C] ([mode])
[One line on why this bench, including who was seated as the dissenter]

---

### [Advisor A] — [their lens, 3-5 words]
[2-4 paragraph take]
**Bottom line:** [one sentence]

### [Advisor B] — …
…

---

## Where the council disagrees
1. **[Conflict]** — [A] says X because [framework]; [B] says Y because
   [framework]. The real trade-off: [underlying tension]. What would
   settle it: [evidence/test].
2. …

## Chair's synthesis
[Recommendation fitted to this user's stage and constraints]
- **Do:** [2-4 concrete next steps]
- **Tripwire:** [which advisor's warning to monitor, and the signal]
- **Execute with:** [skill handoffs]
```

<!-- BML:START output -->
**For BML client work:**

- End with the context footer from `context-rules.md` §9, with `Distinctiveness: n/a for agency artifacts`. List every `⚠ blocked by` under Guardrails. The footer is internal; the whole session is internal analysis, not a client deliverable.
- **Where it goes:** the session stays in the conversation. Nothing is saved, published or written to ClickUp by default. If the user asks to keep it, save it to the client's Drive `OUTPUTS/STRATEGY` folder, resolved by ID from the Context Router; if that folder isn't recorded, ask. Never save to machine-local paths, search Drive or create folders.
- **Handoffs:** `positioning` and `brand-strategy` aren't in BML's fork. When Dunford's take wins, a change to the client's positioning is a change request through `product-marketing` (Load, Step 7; `context-rules.md` §8); execution skills keep using the current page 13 until the rows change. Sutherland's behavioral work hands to `marketing-psychology`; Sharp's availability work to the channel skill (`ads`, `social`, `seo-audit`).
<!-- BML:END output -->

## Adding a Custom Advisor

Users can extend the bench ("add my own advisor"). Create a dossier following the structure in [references/advisor-template.md](references/advisor-template.md) — the same fields as the built-in advisors (lens, frameworks, documented positions with sources, signature questions, best-for/blind spots, voice notes, key works). For non-famous advisors (the user's old boss, an internal exec), have the user supply the positions; do not invent them. Save to `.agents/advisors/<name>.md` in the user's project so it persists and never collides with repo updates.

<!-- BML:START custom-advisors -->
**For BML:** a session workspace doesn't persist, so a custom advisor saved to `.agents/advisors/` lasts only for this session; say so. Don't build a dossier for a client's own staff from their rows (beliefs are F rows, not a persona), and don't put a private person's personal details in a dossier.
<!-- BML:END custom-advisors -->

## Anti-Patterns

- **The agreeing council** — five takes that all bless the user's existing plan. Re-seat with a real dissenter.
- **Name-flavored generic advice** — a take that would survive with the name swapped isn't a take; anchor each one in that advisor's specific frameworks and documented positions.
- **Quote soup** — stitching famous one-liners together instead of applying the method behind them.
- **Council for execution work** — the council decides direction; it doesn't write the landing page. Hand off to the execution skill once direction is set.
- **Twelve advisors on a headline** — match the bench size to the stakes.

## Related Skills

- **positioning** / **product-marketing**: When Dunford's take wins — execute the positioning work
- **offers** / **pricing**: When Hormozi/Halbert direction wins — build the offer
- **copywriting** / **copy-editing**: When the council reviewed copy — execute revisions
- **ads** / **ad-creative**: When the debate was media or creative strategy
- **content-strategy** / **social**: When Handley/Vaynerchuk direction wins
- **brand-strategy** / **marketing-psychology**: For Sharp's availability work and Sutherland's behavioral mechanics
- **ab-testing**: When the disagreement map says "test it" — Hopkins would insist
- **deep-research**: For the live research pass, when installed
