> **BML-owned file** (Baker Labs fork): the BML client layer for copy-editing. Not part of upstream; upstream syncs never touch it.

# Copy Editing — BML client layer

Read after `../../../bml/context-rules.md` whenever the edit is for a Baker Labs (BML) client. It changes *what may be said and where it goes*, not how the Seven Sweeps work. Where this file conflicts with SKILL.md, `checklist.md` or `content-refresh.md`, this file wins; `context-rules.md` wins over this file. The upstream examples in those files (figures, SaaS risk reducers, sample rewrites) are illustrative only: never reuse their numbers or wording in client copy.

## 1. Before the first sweep

1. **Context:** `.agents/product-marketing.md` must start with `Generated for [CODE]` (or `UNGENERATED for` / `INTAKE DRAFT for`) for this client. Missing or another client's → run `product-marketing` Load first. Read order: router → page 13 → Monthly Context Brief → source pages only if a cited row needs detail. Don't browse Drive or search ClickUp broadly. Read-only: never update the staged file, page 13 or a Learnings ledger (context-rules §1). One client per run.
2. **Scope gate (§3):** copy-editing is authorized by the **Blog content** line on page 00 being `Active`, for every piece it edits (site and landing-page copy, blog posts and articles, content refreshes). `Website` covers technical site changes and does not by itself authorize copy edits; `SEO` alone does not either: a SERP-driven refresh still needs Blog content, and SEO only supplies the gap data. Honor qualifiers. Under an "edits only" qualifier, a refresh may revise but not add **New** sections or pages. Out of scope → stop and say so. `INTAKE DRAFT` (prospect): no scope gate, but every fact counts as `DRAFT`, so the edit is internal or pitch material only, facts marked "from public research", never published.
3. **Answer the Task-Specific Questions from the record first:** the goal and action come from page 01 (required CTA language) and I-3, proof comes from G/A rows, and the audience comes from page 03 / the page 13 ICP section. Ask only for real gaps, listed as "Gaps to ask about".
4. **Mode pick** stays as upstream (A / B / C), with the BML split in §1a.

## 1a. Which skill owns which mode (BML clients)

- **Mode B: restore a rough draft.** copy-editing owns turning a client's or author's rough draft into finished copy, including drafts handed over from `copywriting`. Keep their argument and words (§3), run the full sweeps.
- **Mode C: point edit.** copy-editing owns edits to one headline, subhead, CTA, hero unit, line or section, including requests handed over from `copywriting`. Change only that unit.
- **Mode A: blank brief or slop that needs a rebuilt page or section** → hand to `copywriting`, which owns new copy and rebuilt pages and sections for BML clients. A content refresh stays here.
- Modes B and C follow every rule in this file with no shortcut: claims and `[NEEDS PROOF]` (§4), segment gates (§5), guardrails at any status (§7), distinctiveness reporting (§8), output and approvals (§12) and the full footer (§14).

## 2. Whose voice

| Piece | Voice | Load |
|---|---|---|
| Client deliverable (site page, blog post, landing page, email the client sends) | Client brand voice | Staged page 13 voice section (built from page 01); open page 01 only for detail behind a cited row; 02 only if formatting matters |
| Agency artifact (audit, report, plan, deck, the refresh gap grid) | Baker house style (Ops Manual `02: Baker Style Guide`) | Do **not** load the client's 01/02 or the page 13 voice section |

## 3. Voice and Tone sweep (Sweep 2)

- Hard rules from page 01 always win: never-use words (H-5), required CTA language, formality level.
- Mode B (author's own draft): keep the author's vocabulary and emphasis inside those hard rules. If the author's voice diverges consistently from page 01, don't edit it away. Draft it as a candidate `context` task (category: tone) per §10, created only after the user approves.

## 4. Claims: Prove It, Specificity, So What, AI-tell fixes

- Client facts come only from page 13 or the rows it cites, with the row ID. `APPROVED` → use. `PROVISIONAL` → use and flag in the footer. `DRAFT`/`OPEN`/`RETIRED`/`⚠ UNVERIFIED` → never assert. Never ship client-facing copy built on DRAFT rows.
- Wherever a sweep says add proof, add numbers, add a timeframe, name the customer, or "replace with the fact", use the row fact. If there is none, write `[NEEDS PROOF: <row ID>]` (or `[NEEDS PROOF: new — <what>]`). This replaces upstream's `[NEED: …]` marker for client work.
- A "so what" bridge may state a consequence the rows support. It never adds an outcome figure (time saved, % improvement) the rows lack.
- Testimonials: verbatim from page 11 with the row ID. Never compose, merge, trim into a new meaning or "tidy". No patient names or patient data, ever (§7). No reviewer or customer names, street addresses or other personal details beyond the attribution the page 11 row approves for publication.
- Review counts, ratings and other volatile facts carry `⚠ confirm before publishing`.
- Prices only where D-4 allows publishing them.
- Response-time or availability promises only as I-3 states them.

## 5. Segment gates (§7)

- **Clinical:** Sweep 6 becomes a reassurance sweep: approved social proof, process clarity, credentials, access (hours, insurance, booking). No fear, urgency, scarcity or outcome promises unless a page 12 row permits them. Clinical claims only from approved published copy, flagged for provider review. Patient stories need G-5/J-6 authorization. Don't add tracking or forms; flag them.
- **Multi-location:** parent-brand voice and guardrails. Proof, hours, providers and reviews belong only to the location the page is for.
- **Home services:** license details per J-3. Project photos only with a J-6 release. Respect service area (B-8, L-1). Seasonal availability (B-6, I-10) is context and an accuracy check, never a gate.
- **Professional services:** credentials and disclosures per J-3. No outcome guarantees unless a row permits them.

## 6. Zero Risk sweep (Sweep 7): local-service risk reducers

Use only what a row supports. Never add one because it would convert.

| Upstream (SaaS) | Local-service equivalent | Needs |
|---|---|---|
| Free trial | Free estimate / consultation / second opinion | D-row offering |
| No credit card required | No obligation; what the first visit or call involves | D- or I-row |
| Cancel anytime | Clear process steps and timeline | Page 08 process rows |
| Money-back guarantee | Warranty or guarantee **only if** a row states it | D/J row |
| Customer logos | Licenses, certifications, affiliations, insurance accepted | J-3 / A / G rows |
| "Response within X" | What happens after you call or submit the form | I-3 |

CTAs use page 01's required CTA language and the client's real conversion (call, booking, form, signed job). Don't promise availability or a seasonal offer that B-6/I-10 contradict (an accuracy check, not a capacity gate: capacity and season are noted as context, never a reason to drop a service or CTA).

## 7. Guardrails: every mode, any status

Check the edited copy against every page 12 row and F-13 (**including `DRAFT`**), the do-not-assert list, H-5 and the segment rules.
- In a line you are editing: fix it and note it in the footer.
- In a line you were told to leave alone (point edit): don't edit it. Report it in one line at the end, naming the row.
- A request that requires a violation (e.g. "add that we're cheaper than <competitor>" under J-4): stop before editing and name the row: "Blocked by <row>: <rule>."

## 8. Distinctiveness (§6)

- **Content refresh** (and a mode A rebuild, which goes to `copywriting` under the same rule): the result builds on ≥1 belief (F, APPROVED/PROVISIONAL) and ≥1 proof point (G, or a citable A). If the record has none for this topic, mark `Distinctiveness: FAIL — not client-ready` and list the rows to fill.
- **Modes B and C:** report what's present (`Distinctiveness: <IDs present>` or `FAIL — rows to fill`). This is informational for B and C, not a ship block. Don't inject a belief or proof the author didn't use.
- Agency artifacts: n/a.

## 9. Expert panel

The target-customer persona comes from page 03 / the page 13 ICP section, not an imagined one. A score never overrides `[NEEDS PROOF]`, guardrails or approval. "9–10 publish-ready" means ready for internal review, not for publishing. Panel critiques never reintroduce framing the segment rules or page 12 block (e.g. urgency from the direct-response persona for a clinical client).

## 10. Client edits and feedback (context-rules §8)

When the client has edited, rejected or commented on BML's copy (or the user pastes "the client changed it to this"):
1. Diff BML's version against the client's and list each meaningful change.
2. For each change, name the row it touches (or "no row") and a category: tone, accuracy, seriousness, belief, claim.
3. Draft one task per change, tagged `context`, named `Context — <CODE> — <row ID> — <short>`, with before/after, the client's words and the source link. Create it in ClickUp only after the user approves.
4. Apply the client's wording to the deliverable only after the claims (§4) and guardrail (§7) checks. A client edit that adds an unsourced claim gets `[NEEDS PROOF]` and a question back, not silent acceptance.
5. Never edit rows or page 13, and never add a Learnings entry.

## 11. Content refresh (with `content-refresh.md`)

- **Freshness and proof passes:** client stats, results, prices and testimonials are updated only from rows. An outdated client figure with no newer row → `[NEEDS PROOF: <row>]`; never estimate or pull a "current" number from the web. Market statistics come only from L rows or a public source with name and date, and never imply the client's own results.
- **Accuracy pass:** check services (page 08), service area (B-8, L-1), NAP, hours, providers and licenses against rows, not the live page. List mismatches as fix-now findings for the account lead. Never "correct" a row from the page.
- **Gap analysis tools:** Semrush is the only SEO data tool (organic research / keyword overview for the query, SERP features and organic competitors). Local competitors from L-4 (map pack + organic). The page's own queries from Search Console via Windsor.ai. Any other tool only if the client uses it.
- **Closing gaps:** a gap is closed with structure, subtopics and answers from the record. A gap that is proof or data (competitors show stats, case results, reviews) goes in the grid as `[NEEDS PROOF: <row>]`, even if every competitor has it. The **Uncovered** angle should come from an F row.
- **Competitor names** may appear in the internal gap grid (agency artifact). The refreshed copy follows J-4.
- **Write-back:** if L-4 is `OPEN` or older than 90 days, the Semrush competitor results may answer it: stage them in the context-rules §10 review format (lands as `DRAFT`). Never write the row or ClickUp yourself.
- Keep upstream's outline approval gate. Never promise a ranking or traffic outcome.

## 12. Output, records, publishing, approvals

- Save the edited piece to the client's Drive `OUTPUTS/WEBSITE` (site and landing copy) or `OUTPUTS/BLOG` (posts). The gap grid and outline go with the piece. Resolve the folder by ID from the router: never search Drive, never create a folder, and if none fits, stop and report. No local or project-root paths, no Notion/GitHub by default.
- Draft the ClickUp task (tag `website` or `blog-content`, plus `seo` for SERP-driven refreshes) and create it only after the user approves.
- Never publish to the client site, change URLs or set redirects, and never call write actions on connectors (Wix site changes, Windsor.ai Business Profile or listing edits, review replies, ad changes). The refresh handoff lists the meta description, schema, internal links, URL/301 plan and images for a human publisher.
- Images: check approved assets (ClickUp tag `asset`) first, list what's missing, require J-6 releases, and never present AI images as real projects.
- Nothing publishes, sends or spends without a human checkpoint. Client-facing work names the client's approver (J-1). A human moves the task to `ready for client review` after internal review; the skill never changes task status.

## 13. Recurring refreshes

Map cadence to local-service page types: service pages, location pages, blog posts, FAQ (not pricing/product pages). A refresh cadence is a scheduled task (or the `marketing-loops` content-refresh loop) proposed to the user, never an in-session loop.

## 14. Footer

End every client deliverable and agency artifact with the full context-rules §9 footer, including point edits (mode C). There is no short form.
