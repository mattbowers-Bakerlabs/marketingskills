<!-- BML:START bml-application -->
# Marketing psychology for BML client work

Read this before recommending any model for a Baker Labs (BML) client. It sits on top of `../../bml/context-rules.md` (path relative to this skill's folder), which wins on anything about client facts, guardrails and segments. Section numbers (§) below refer to that file.

This skill decides **which biases are in play and how to frame around them**. It does not decide what is true about the client: every fact it leans on comes from the staged page 13 (`.agents/product-marketing.md`) or the rows it cites.

---

## 1. Upstream examples are illustrations, not copy

The "Marketing application" lines in SKILL.md use SaaS examples and sample figures ($99 vs $100, "$3/day", "90% success rate", "80% done", "less than your morning coffee", an 80/20 budget split, "built by marketers for marketers"). They explain the principle. For client work:

- Never carry an upstream figure, phrase or ratio into a recommendation, brief or draft. Rebuild the example from the client's rows, or use placeholders (`<price from D-4>`, `<n> reviews`).
- Research findings used to explain a model ("losses weigh roughly twice as much as gains") are fine in an internal explanation, never as a claim in client copy.
- Budget splits come from B-10, not the Barbell 80/20. Touchpoint counts ("Rule of 7") are a heuristic, not a benchmark to quote to a client.

## 2. Gating table

Check the client's segments in the staged file (§7). If segments were inferred and the client could be clinical, use the Clinical column. **Row required** means: apply the model only when a row shows the thing is real and approved; otherwise drop it or write `[NEEDS PROOF: <row ID>]`. **Blocked** means: do not recommend it; say "Withheld: <model> — context-rules §7 (clinical)" unless a page 12 row explicitly permits it, in which case cite that row.

Page 12 and F-13 apply at any status, including `DRAFT`. If the user asks for a blocked tactic, stop before drafting and name the rule or row (§5), then offer the alternative.

| Model (SKILL.md name) | All clients | Clinical | Use instead |
|---|---|---|---|
| Scarcity / Urgency; "spots left", deadlines, countdowns | Row required: real capacity or backlog (B-6), a season (I-10), or a promotion with a real end date (D-11). Never invent counts or deadlines. Never push a service B-6 says is full | Blocked unless page 12 permits | Access: next available appointment or booking ease (I-9), hours, insurance and payment (D-7) |
| Loss Aversion / FOMO ("don't miss out", cost of waiting) | Row required for any stated cost of waiting (D-2, D-6). Cost or damage figures → `[NEEDS PROOF]` | Blocked unless page 12 permits | Gain framing tied to the process (D-3) and what to expect |
| Fear framing; Contrast Effect "before" state | Facts only from rows; check J-2, F-13. No invented damage, risk or cost figures | Blocked unless page 12 permits. Health-risk statements are clinical claims (approved copy only, named-provider review) | Credentials (G-1), process clarity (D-3), guarantees (D-5) |
| Mimetic Desire: waitlists, exclusivity | Row required: B-6 shows a real backlog | Blocked (it is scarcity) | Social proof, below |
| Zeigarnik: abandoned forms, cliffhangers; Rule of 7 retargeting | Allowed on the client's own forms and channels (I-1, A-9) | Don't recommend retargeting pixels or form tracking on patient-facing pages; flag as a compliance question for a person (§7) | A shorter booking form (Hick's Law, Activation Energy) |
| Anchoring: "was" price, competitor price, premium first | Prices only where D-4 says publishable. A "was" price only if it was actually charged (row). Competitor prices only with source and date, and only if J-4 allows naming competitors | Row required (D-4); no "was/now" discount urgency | Publishable range, financing (D-7) |
| Decoy; Good-Better-Best; Door-in-the-Face | Real packages only (D-1, D-7). Never invent a tier to act as a decoy or a "large first request" | Row required (D-7); never tier by promised outcome | One recommended option, explained |
| Charm / Rounded price / Rule of 100 / Mental Accounting ("$/day", "$/month") | Concrete prices only from D-4 publishable. Monthly framing only if D-7 lists financing, with any J-3 lending disclosures | Same | Ranges, "<price> starting at" per D-4 |
| Zero-Price Effect; Endowment (trials, samples): free estimate, consult, inspection | Row required: the free offer exists (D-5, D-7, D-11 or I-9) | Same; "free" must not imply a result | — |
| Regret Aversion: money-back guarantees, "no commitment" | Guarantees only as D-5 states them; "no commitment" only if D-3 / D-7 show it is true. Professional services: no outcome guarantees unless a row permits | No result or satisfaction-with-outcome guarantees unless page 12 permits | Process clarity (D-3), what happens if they change their mind (D-5) |
| Hyperbolic Discounting / Present Bias ("results today") | Immediate benefits only as D-2 / D-3 describe them; no timing promise not on a row | Blocked as an outcome promise unless page 12 permits | Immediate access: same-week booking or a call back, only as I-3 / I-9 support |
| Cobra Effect; Switching Costs (referral bonuses, lock-in) | Referral rewards need J-3 answered and a person to confirm. Never reward reviews (platform rules and FTC, every client). No contract or records lock-in as a retention tactic | Paying patients or providers for referrals is a J-3 question for a person; withhold until answered | Ask for referrals at the right moment (I-5) |
| Default Effect / Nudge | Pre-selecting a real recommended package is fine. Never pre-check consent to email or SMS, and never auto-enrol in a membership or plan | Same | — |
| Commitment & Consistency; Foot-in-the-Door | The small first step is the conversion in 01's required CTA language (call, booking, form). No follow-up pressure beyond what I-3 lead handling supports | Allowed as a low-pressure first step (book a consult); no pressure | — |
| Social Proof / Bandwagon; Availability Heuristic (case studies) | Numbers from G-2; ratings and review counts from A-7, marked "⚠ confirm before publishing"; testimonials verbatim from G-5 with consent; stories from G-3. No reviewer names. Missing → `[NEEDS PROOF: G-2]` / `A-7` / `G-5`. Multi-location: that location's proof only | Also needs written patient authorization (G-5, J-6); no condition tied to a person | — |
| Authority | Credentials G-1, partners and brands G-8 / D-10, experts G-11, community and media G-9. License or disclosure lines where J-3 requires. No endorsement, award or "featured in" that isn't on a row | Provider credentials as on approved copy; clinical claims flagged for named-provider review | — |
| Framing Effect: success rates, percentages | Any rate is a claim: G-2 / G-10 row or `[NEEDS PROOF]`. Professional services: no outcome guarantees unless a row permits | Outcome and efficacy figures only from approved published copy, flagged for provider review | Describe the process, not the result |
| Pratfall; Liking; Unity | An admitted weakness must match E-10 / E-1 and not cross F-13 or J-4. Faces and founder story from B-12 / B-2, with J-6 likeness permission. Shared-identity language builds on an F row | Same | — |
| Reciprocity (free content, tools) | Allowed; check team time (I-8) and capacity (B-6) | Educational content allowed; no clinical claims | — |

Models not listed (foundational thinking, Hick's Law, Fogg, EAST, COM-B, Peak-End, Goal-Gradient, IKEA, Curse of Knowledge, growth models after §3 translation) are allowed for every segment; any figure they produce still follows §4.

## 3. SaaS defaults → local-service equivalents

Upstream examples assume software. Translate before applying, and only to things the client's rows show they offer:

| Upstream | For a local-service client |
|---|---|
| Free trial, freemium, samples (Endowment, Zero-Price) | Free estimate, inspection or consultation (D-5, D-7, I-9) |
| Annual plan, subscription, upgrade path (Foot-in-the-Door) | Maintenance plan, membership or package (D-7); upsells (D-8) |
| Enterprise tier first (Door-in-the-Face, Anchoring) | Premium package or full-scope option (D-1, D-7) |
| Signup, activation, onboarding | Call, booking or form (01 CTA language); first visit or job; post-job follow-up (I-5) |
| Customer counts, logos | Reviews (A-7), years in business, jobs or patients served (G-2), local partners (G-8) |
| Churn, switching costs, network effects | Repeat and referral (B-7), review and referral asks (I-5), referral ecosystem (L-8) |
| North Star (active users) | Booked jobs or appointments; lead-to-customer rate (I-4) |
| "Import your data in one click" (Status-Quo) | "We handle the permits / insurance paperwork" — only if D-3 says so |
| Mere Exposure via content | Google Business Profile (A-6), listings (A-11, A-16), local media and community (L-9, G-9) |

Local competitors' messaging and review themes (L-5, L-6) show which frames are already crowded (Contrast, Unity). L rows are BML research: use them for targeting and framing, never as claims about the client.

## 4. Answering the skill's questions from rows

| SKILL.md question | Look here first |
|---|---|
| Behavior to influence | 01 required CTA, I-3 lead handling, I-9 booking |
| What the customer believes | Page 03 customers, D-6 buyer doubts, F rows |
| Journey stage | Page 04 journey |
| What blocks the action | D-6, I-4 drop-off, A-12 tracking health |
| Tested with real customers? | I-2 past campaigns, A-1 / A-9 results; otherwise hand testing to `ab-testing` |

Ask the user only about gaps, naming the row. If the user tells you something that answers an `OPEN` row (a buyer doubt, a capacity limit), don't treat it as fact: stage it as a `DRAFT` row in the §10 format in your reply (never written to ClickUp) and label it unconfirmed in your analysis.

## 5. Output

**Usually a hand-off.** Return a short psychology brief to the skill doing the work (`copywriting`, `cro`, `pricing`, `offers`, `ads`, `ad-creative`, `emails`). That skill loads the client's voice, writes the copy and adds the footer. Scarcity, urgency and guarantee *mechanics* belong to `offers`; price levels and tiers to `pricing`.

**Standalone** (the user asks for the psychology analysis itself): run the scope gate (§3) on the service the analysis supports; if none is Active, stop. A prospect (`INTAKE DRAFT`) has no scope gate: the brief is internal or pitch use only (§1). It is an agency artifact. Write in Baker house style; do not load the client's voice or style pages (01, 02); take the required CTA wording from page 13. End with the §9 footer, `Distinctiveness: n/a for agency artifacts`.

Brief format:

```
Psychology brief — [CODE] — <decision>  (internal)
Behavior: <conversion, per 01 / I-3>
Barrier: <what blocks it, with row IDs>
Build on: <F row> + <G row> for the downstream deliverable (§6), or "none on file"
| Model | Why it applies (rows) | How to apply | Gate (allowed / row required: ID / withheld: reason) |
Withheld: <model — rule or row>
Needs proof: <ID — what's missing>
Hand off to: <skill>
—— Context footer · [CODE] —— (per §9)
```

Every brief, hand-off or standalone, ends with the footer. Where it goes: return it in the conversation. Save it to the client's Drive only if the user asks, to `OUTPUTS/STRATEGY`, resolved by ID from the Context Router; if that folder isn't recorded, ask. Never search Drive. Never save to machine-local paths (`~/…`). Never create Drive folders or ClickUp tasks on your own; a ClickUp record (tag `strategy`) is created only when the user asks and approves.
<!-- BML:END bml-application -->
