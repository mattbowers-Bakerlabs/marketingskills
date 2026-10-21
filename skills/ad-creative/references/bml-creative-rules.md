<!-- BML:START creative-rules -->
# BML Creative Rules (ad-creative)

Ad-creative specifics for Baker Labs (BML) client work. Read this after `bml/context-rules.md` at the repo root (`../../../bml/context-rules.md` from this folder) and before the skill's own modes. Where this file or the rules file conflicts with SKILL.md or any other reference in this skill (its examples, templates, tool defaults or output paths), the BML files win. Not BML client work? Ignore this file.

## 0. What this overrides in SKILL.md

SKILL.md carries only a short BML mode list, to stay under its line limit. These rows replace the parts of SKILL.md named on the left.

| SKILL.md section | BML rule |
|---|---|
| Before Starting: the Learnings check | Learnings come only from page 13: read its Learnings section if it has one, and treat a missing one as normal. Never add, or offer to add, a Learnings entry or any other line to the staged file. A test result, a decision with a reason or a repeated correction becomes a drafted `context` task (rules file §1, §8) |
| Before Starting §2 Product & Offer (free trial, demo) | The offer is a D row (D-1, D-7, D-11) and the conversion a call, booking, quote or form (§3) |
| Mode 3 and Grounded Inputs (`inputs/`, `brand/`, `outputs/` folders; "ask the user to populate it") | The corpus is the client record (I-2, G-5 verbatim, page 03, Windsor data), not a folder on the machine. If it holds nothing usable, stop and name the rows to fill (§1). The daily-creative-drop loop is replaced by §9 cadence |
| Mode 3 awareness headlines ([awareness-headlines.md](awareness-headlines.md)) | Gate in that file's BML note and §4 (Conversation treatment) |
| Generating Ad Copy, Step 1 angle table | Social proof needs G rows, Outcome needs approved D-2 or G-2, Urgency needs a real D-11 promotion (never for clinical), Comparison and Contrarian lines that name a competitor need J-4 clearance. Missing fact → `[NEEDS PROOF: <row ID>]` (§2) |
| Step 4 Organize for Upload; Bulk CSV "direct upload" | A file for a person to upload. Nothing is uploaded by the skill (§9) |
| Writing Quality Standards: "Include numbers", "Add proof points", "Add urgency when genuine" | Numbers, proof points and urgency come only from rows (§2) |
| Descriptions That Convert ("No credit card required", "free trial", "signups"); No AI Tells ("No card required") | The client's page 01 CTA, plus a D-7 entry offer only if one is on file (§3). The AI-tells rules apply on top of H-5 never-use words |
| Shortened product names | Use the service and brand names exactly as the rows give them (D-1, B-1) |
| Test Hypotheses That Can Lose | Name the client's conversion (calls, bookings, forms, cost per lead) as the metric when A-12 says it is tracked; otherwise an upper-funnel metric, and say why. A magnitude needs a Windsor baseline; never invent one (§8) |
| Creative Review Page ("hostable anywhere") | Deliver to Drive `ASSETS/Ad-Creative` for a person to share with the approver (J-1). Never host it publicly; picks on the page aren't saved (§9) |
| Tool Integrations (CLIs, Magister, Supermetrics, Coupler) | Windsor.ai read-only; none of the others are used for BML clients, and no client account access or data goes to them (§8) |
| Related Skills | image for non-ad graphics (blog heroes, organic social, OG images); video for production tooling and non-ad video. Paid ad visuals, video ad concepts, hooks and scripts stay in ad-creative |

---

## 1. Inputs: what replaces the Grounded Inputs corpus

The upstream method (ground every concept in winning ads, reviews and comments) stays. For a BML client the corpus is the client record, not an `inputs/` folder.

| Upstream input | BML source |
|---|---|
| `inputs/winning-ads/` | I-2 (best past ads), Windsor.ai reads of the client's ad accounts (§8), approved `asset` records |
| `inputs/reviews/` | G-5 testimonials, verbatim with row ID, for quotes. Review themes (not quotes) from page 03 and any review-theme rows on file |
| `inputs/comments/` | Comments the user pastes or Windsor returns. Use themes and objections only; drop commenter names and handles |
| `brand/` | Page 01 voice (required CTA language, H-5 never-use words), page 02 style, A-17 brand assets, approved `asset` records |
| Product and offer facts | D-1 to D-11 (prices only where D-4 says publish; guarantees D-5; offers D-7; promotions D-11) |
| Proof | G-1 credentials, G-2 numbers, G-3 project stories, G-6 photo and video library |
| Customer language and objections | Page 03, D-6, E-8 (claims everyone makes: avoid as differentiators) |
| Local market | B-8, L-1, L-3, L-6, L-7 |

- Don't build a durable `inputs/`, `brand/` or `outputs/` corpus on the machine. Working files live in the session working directory; deliverables go to Drive (§9).
- A review the user pastes that isn't on G-5 can supply themes, never a quote. Suggest the account lead add it to G-5 with permission.
- Attribute a G-5 quote only in the form G-5 records as permitted. Never pull reviewer names, handles or photos from review sites or comments.
- Mode 3 stop rule: if I-2 and G-5 hold nothing usable and no performance data is available, stop and list the rows to fill. Don't ask the user to dump reviews into a folder, and don't generate ungrounded concepts.

## 2. Claims in ad copy

Every "be specific", "add numbers", "add proof" or "add urgency" step in this skill resolves to a row, or to `[NEEDS PROOF: <row ID>]`.

| Upstream move | BML rule |
|---|---|
| Numbers in headlines ("3x faster", "10,000+ teams") | G-2 or approved D-2 figures only; else `[NEEDS PROOF: G-2]` |
| Social-proof angle, review counts, star ratings | G-5 quotes; A-7 counts with "⚠ confirm before publishing" |
| Outcome angle ("Achieve Y in Z days") | D-2 approved outcome. Clinical: approved published copy only, flagged for provider review. Professional services: no outcome guarantees unless a row permits |
| Urgency ("Limited time", "ends tonight") | Only a real D-11 promotion with its dates. Never for clinical unless a page 12 row permits |
| Offers, promo codes, free estimates, financing | D-7, D-11; never invent a code or an offer |
| Prices | D-4, and only where it says the client approved publishing |
| Guarantees | D-5 |
| Awards, press, licenses | G-1; license details where J-3 requires them |
| Competitor names and comparisons | J-4 first; comparisons must be true and supportable |
| "Best", "#1", "leading" | J-2 check; needs substantiation on file |

The figures, brands and quotes in this skill's examples (SKILL.md, the static templates, the review-page sample) are illustrative. Never carry one into client copy.

## 3. Conversions and CTAs

Upstream examples assume trials, signups, demos, app downloads and promo codes. For a BML client the conversion is a call, booking, quote or estimate request, form or visit, per I-9 and I-4, unless the rows say otherwise.

| Upstream line | BML version |
|---|---|
| "Start your free trial" | The page 01 required CTA (book, call, request a quote) |
| "No credit card required" | An entry offer only if D-7 has one (free estimate, consultation) |
| "Limited to first 500 signups" | A real D-11 cap only |
| "what app is that?" reveal punchline | Re-cast for the service, or pick another format |

- Response promises ("we'll call back in 10 minutes") only within I-3.
- Meta lead (instant form) ads for a clinical client: flag for a compliance person (rules file §7); don't build them.

## 4. Format gates

Check the format before writing a brief. A format that fails its gate is skipped, with the reason in the footer.

| Format family | Gate for BML clients | Clinical |
|---|---|---|
| iOS-native reveals: iMessage, AirDrop, Apple Notes ([imessage-video-ads.md](imessage-video-ads.md)) | Only with the client approver's (J-1) explicit sign-off on a dramatized format before production. Every claim in the thread from rows. Generic chat skin, not Apple's UI or sounds. An on-screen "Dramatization" label. No sender or peer presented as a real customer. Apple Notes confessions are not "composite customer stories": a composite is a fabricated testimonial (G-5) | Not used |
| Awareness-headline Conversation treatment ([awareness-headlines.md](awareness-headlines.md)) | Lines from G-5 (verbatim, with permission) or page 03 / D-6 themes. Invented dialogue only as an on-screen "Dramatization", never attributed to a customer, peer or staff member, and never with mocked platform UI | No invented or dramatized dialogue |
| ChatGPT / AI-assistant reveal | Same gate, plus J-5. Never health, legal or financial advice | Never |
| Tweet/Reddit screenshot, Review Card, Testimonial Stack | Real, verbatim G-5 content with permission only. Never mock a review platform or social UI around invented or composite text | Written patient authorization (G-5, J-6) |
| UGC, creator, yapper, greenscreen, conversation, street interview ([short-form-video-specs.md](short-form-video-specs.md)) | Real customers only with a G-5 quote and a J-6 release. "Staged" or "recreated" means actors or staff presenting, never actors speaking as customers about an experience they didn't have: that is a fabricated testimonial. A staged or dramatized scene carries an on-screen "Dramatization" label | No staged or dramatized scenes. No patient stories without written authorization; never an actor as a patient |
| Authority (expert on camera) | A real credentialed person from G-1 with J-6 consent. Never an AI avatar or invented credential | Provider-fronted only, clinical claims flagged for provider review |
| Founder / owner content | B-12 (who appears on camera), I-8 (team time); story from B, F and G rows | Same, no patient details |
| Partnership ads, whitelisting, paid creators | Influencer work: only if page 00 includes it; otherwise offer a scope note | Same |
| Duet, stitch, reaction to someone's post | Written rights from the original creator; J-4 if it's a competitor | Same |
| Before/after | Real project photos from G-6 with a J-6 release. Never stock or AI images as the client's work | Only if a page 12 row permits; otherwise skip |
| Us vs. them, competitor callout, David & Goliath; contrast hooks that name a product or competitor (False assumption, Choice, Old vs. new) | J-4; true and supportable on file; a person reviews any named competitor before it runs | No fear framing; no health claims in the comparison |
| Press mention | G-1 coverage only, with logo rights | Same |
| Ugly / post-it / "ends tonight" | A real D-11 window only | Not used |
| AI animation, AI avatar, faceless motion ([motion-video-ads.md](motion-video-ads.md)) | J-5 at `APPROVED` or `PROVISIONAL`, disclosure per J-5; AI people generic and unidentifiable (§5) | No photorealistic AI people, digital twins or voice clones at all, consented ones included; abstract or illustrative motion only |

Clinical clients also follow rules file §7 throughout: no scarcity, urgency, fear or outcome-promise framing unless a page 12 row permits it. Use reassurance (credentials, process clarity, access, approved social proof). Curiosity-gap hooks that imply a hidden health risk count as fear framing.

## 5. Synthetic media: images, video and voice

1. **Assets before generation.** Before briefing new creative, look in the client's space for approved existing assets: ClickUp tasks tagged `asset`, status `approved`, Asset Type = the type you need (a targeted, read-only query, not a broad search). Then G-6 (photo and video library, who can shoot more) and A-17 (brand assets). Reuse or adapt first, or brief a shoot. Generate only for a gap, and say which gap.
2. **J-5 decides** whether AI-assisted creative is allowed and how it is disclosed. Its permission counts only at `APPROVED` or `PROVISIONAL`. At `OPEN` or `DRAFT`: concepts and prompts are fine, abstract or illustrative imagery is fine, but synthetic or photorealistic media is an internal preview only, J-5 is listed as a gap in the footer, and you ask before anything client-facing. A restriction on J-5 or J-6 binds at any status, including `DRAFT`.
3. **People and likeness.** AI-generated people only as generic, unidentifiable people, never presented as the client's customers, patients, staff, providers or owner. Clinical clients: no photorealistic AI people at all. A digital twin, voice clone or any real person's likeness only with that person's written consent recorded on J-6 and the person named on B-12. Clinical clients: no digital twins or voice clones at all, consented ones included. **Client hard line wins:** if a page 12 row (J-2, J-5 or J-6) rules out AI people or AI imagery, there are none at all, and a request that needs them stops and names the row.
4. **Never:** AI images of projects, before/afters, facilities or results presented as real; AI-generated, AI-voiced, composite or acted testimonials presented as real.
5. Apply the platform's AI-content label (Meta, TikTok, Google) where it requires one.
6. **Tools.** BML's stack (Figma connector included) is the default. The tools in [generative-tools.md](generative-tools.md) are options only "if BML or the client has an approved account". Don't send client photos of people, unreleased offers or anything from a clinical client to a tool that isn't approved for client work. No API keys or credentials pasted into chat or written into any file.
7. **Paid generations.** Write prompts and briefs freely; rendering a generation that costs money (image, video or voice credits) waits for a human checkpoint in this conversation naming what will be rendered.

## 6. Voice and style

- Ad copy, scripts and on-image text are client deliverables: page 01 voice, its required CTA language and H-5 never-use words. Visual direction, image prompts and the motion "brand slots" come from page 02 and A-17, not from a guess.
- Iteration reports, the roadmap, the retro and the review page's surrounding notes are agency artifacts: Baker house style. Only the ad copy quoted inside them (new variations, concept headlines) is written in client voice.
- Multi-location: parent brand voice, beliefs and guardrails; each location's ads use only that location's hours, providers, proof and service area.

## 7. Distinctiveness, capacity and local fit

- **Distinctiveness** is checked across the set or campaign: at least one belief (F) and one proof point (G, or a citable A row) carried by the set. If none is usable, mark the footer `Distinctiveness: FAIL — not client-ready` and list the rows to fill.
- **Capacity and season:** read B-6, I-10, D-11 and L-3 before choosing what to push. No creative for a service the client can't take on now; seasonal angles follow I-10.
- **Service area:** name only places within B-8 / L-1. Use L-6 (competitor offers and messaging) and L-7 (who bids, typical CPC) to differentiate, never to copy a competitor's ad.

## 8. Performance data

- Pull performance through **Windsor.ai, read-only** (Google Ads, Meta Ads, LinkedIn Ads, TikTok Ads, GA4), using the account IDs on A-13 / page 00 §8. The repo's ad platform CLIs, Magister and reporting connectors such as Supermetrics or Coupler are not used for BML clients, and no client account access or data goes to them.
- Check A-12 (tracking health) and A-9 before naming winners. If conversion tracking is broken, judge only on upper-funnel metrics (thumbstop, hold, CTR) and say so.
- Judge on the client's conversion (calls, bookings, forms, signed jobs; cost per lead), not ROAS, unless the rows say revenue is tracked.
- Pull aggregates only: no lead names, phone numbers or form contents. If data the user pastes includes personal data, don't copy it into any output.
- A test result or lesson worth keeping becomes a drafted `context` task (rules file §8), never a Learnings entry in the staged file.
- Competitor paid-search copy: Semrush `paid_search_research` (read-only) and the L-6 / L-7 rows. A finding that answers an `OPEN` row is staged as a `DRAFT` row (rules file §10), never written.
- **Windsor write actions** (ads, campaigns, budgets, bids, audiences): never run by an agent, even with approval. Launching is a person's job: hand over the approved, upload-ready file.
- Never upload customer lists or build audiences from customer, lead or patient data; that is a decision for a person (and, for clinical clients, a compliance question).

## 9. Outputs, approvals and cadence

| Output | Goes to |
|---|---|
| Copy sets, RSA sheets, bulk CSV, INDEX and concept briefs, hook matrix, iteration report | Client Drive `OUTPUTS/PAID-ADS` |
| Finished creative files (images, video), review page with its images | Client Drive `ASSETS/Ad-Creative` |
| Creative roadmap, monthly retro | Client Drive `OUTPUTS/PAID-ADS` (agency artifact) |
| Creative for a non-paid placement (blog, organic social, web, listings) | The folder the router maps for that placement; ask if none is mapped |

- Resolve folders by ID from the router. Never search Drive or create folders. If a folder can't be resolved, keep the files in the session's working directory and ask the user where they go. Prospects (`INTAKE DRAFT`) have no client folders: spec creative stays in the session's working directory, marked "from public research", for pitch use only.
- **ClickUp:** draft, don't create, a task tagged `paid-ads` for the work, with the client's approver (J-1) named. Once the client approves a piece, draft an `asset` record (Asset Type, file link) for the user to create. The skill writes nothing to ClickUp.
- **Approval path:** internal review → ready for client review → client review (J-1) → approved. Nothing publishes, posts, sends, uploads, renders a paid generation or changes budgets, bids or campaigns without a human checkpoint in this conversation (§5, §8). A bulk CSV is a file for a person.
- **Review page:** deliver the HTML file to `ASSETS/Ad-Creative` for a person to share with J-1. Never Vercel, Netlify, GitHub Pages or any public link. A private claude.ai artifact only if the user asks for one; never make it public or share its link outside the approver path. Picks made on the page aren't saved; the account lead records the client's choice on the ClickUp task. Only concepts with no open `[NEEDS PROOF]` gaps go on the page. Grounding lines are plain language starting "Real:", plus "Illustrative:" for imagery not yet shot or rendered; row IDs stay in INDEX.md. Leave the optional `likes` field out: a like count on an unpublished concept is invented social proof.
- **Cadence:** anything recurring (weekly refresh, monthly slate and retro, scheduled batches) is offered as a scheduled task, never an in-session loop, and created only when the user asks. BML default is a monthly slate and retro tied to the client's monthly session, sized to budget (A-9) and the client's approval time (I-8).
- **Footer:** every deliverable and agency artifact ends with the rules file §9 footer, stripped before it reaches the client (including from the review page).
<!-- BML:END creative-rules -->
