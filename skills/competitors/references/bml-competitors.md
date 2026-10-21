> BML-only file (Baker Labs fork). Not part of upstream marketingskills; no merge markers needed.

# BML: Comparison Pages for Local Service Clients

Use with [`bml/context-rules.md`](../../../bml/context-rules.md) for any Baker Labs client. Those rules decide what is true and what may be said; this file adapts the competitors skill to local service businesses.

## 1. Read order

1. Router → staged page 13 (`.agents/product-marketing.md`) → current Monthly Context Brief → source pages only if needed.
2. For competitors: E rows (positioning), L-4 (who wins locally), L-5 (review themes), L-6 (offers and claims), L-11 (category platforms), L-3 (search demand).
3. A competitor-profiling profile only if the ClickUp task, brief or user links one and it is ≤90 days old. Never browse Drive or the repo for one. If there is none and the gap matters, recommend running competitor-profiling first.
4. The competitor's own public pages for remaining gaps, each fact dated.

Do not browse Drive or search ClickUp broadly. One client per run: no facts, files or examples from another client. Never edit `.agents/product-marketing.md` or page 13; proposed learnings become `context` tasks (context-rules §1, §8).

## 2. Formats by segment

| Segment | Option comparison / buyer's guide | You vs named competitor; alternative(s) | Competitor A vs B (local businesses) |
|---|---|---|---|
| Home services | Default | Gated | Not for BML |
| Multi-location / franchise | Default (parent brand rules, J-3) | Gated, and only if the franchisor's brand rules allow it | Not for BML |
| Professional services | Default | Off by default; on only with a row that permits it, and then still Gated | Not for BML |
| Clinical | Default, with named-provider review of any clinical statement | Off unless a page 12 row explicitly permits it, and then still Gated | Not for BML |
| National or category comparisons (e.g. a franchise *type*, a national platform category) | Default | Allowed if J rows allow, under Evidence Discipline; the client-conflict check still applies (some BML clients are multi-location brands) | Allowed under Evidence Discipline when neither side is a local business; client-conflict check still applies |

**Gated** means all four hold: no page 12 / F-13 restriction (at any status, including DRAFT), the competitor is not a current BML client (Client Index, Baker Operations Manual), Semrush shows demand for the exact term, and the account lead's approval is recorded in the ClickUp task.

**Roundups (Format 2):** name only national or category options (for example "DIY vs contractor vs <franchise type>") unless J rows explicitly permit naming local businesses. Never list four to seven local rivals on a client's site by default.

## 3. Page shapes for local clients

**Option comparison** (`<option A> vs <option B>`; URL under the related service page)
1. TL;DR: when each option fits (2–3 sentences)
2. How each works (process from 08 rows)
3. Comparison by local dimensions (section 4)
4. Who each option is for, including when neither is right
5. How the client approaches this choice (≥1 F belief + ≥1 G proof point)
6. CTA in 01's language (call, booking or form)

**Buyer's guide** (`how to choose a <service> in <town>`)
1. What to check: criteria buyers can verify (licensing, credentials, warranty, process, reviews)
2. Questions to ask any provider
3. Red flags (general, never tied to a named business)
4. How the client meets each criterion (rows only)
5. Service area (B-8 / L-1) and CTA

Named formats, where allowed, keep the upstream structure but use these dimensions and drop "migration" unless 08 rows describe switching providers (records transfer, a project mid-way, effect on warranty).

## 4. Local comparison dimensions

| Dimension | Client side from | Competitor side from |
|---|---|---|
| Service area and travel | B-8, L-1 | Their published service-area page, dated |
| Licensing, credentials, disclosures | J-3, A rows | Their published license or credential info, dated |
| Warranty / guarantee | Rows only | Their published terms, dated; otherwise omit |
| Scheduling and response time | I-3 | Omit unless published |
| Pricing / financing / insurance accepted | D-4 (publish approval) and D rows | Dated L-6 or published page + "⚠ confirm before publishing"; otherwise no table |
| Process | 08 rows | Their published process, dated |
| Reviews | Volatile facts block + "⚠ confirm before publishing" | Public rating with source and date only; no quotes, no reviewer names |

These replace the SaaS dimensions (features, integrations, ease of use, security and compliance, per-seat pricing, "sample team size" totals). No self-assigned ratings of named businesses. "Not listed on <page> (as of <date>)", never "not available", unless their own page states it. Rival complaint themes are better used for positioning than printed in public copy.

## 5. Claims

- Client facts only from page 13 or cited rows; otherwise `[NEEDS PROOF: <row ID>]`.
- Quotes and switcher stories only verbatim from page 11, with the row ID; otherwise `[NEEDS PROOF: G-<n>]` or `[NEEDS PROOF: new — switcher quote]`. Clinical stories also need G-5/J-6 on file.
- No superiority or outcome claims ("better results", "#1", "most experienced") unless a row supports and permits them.
- **Clinical:** comparisons of treatments or procedures only from approved published copy, flagged for named-provider review; no efficacy, outcome or superiority comparisons, no urgency or fear framing.
- **Professional services:** no outcome comparisons unless a row permits them; credentials and disclosures per J-3.
- Local market statistics cite source and date and never imply the client's own results.
- Evidence Discipline (SKILL.md) applies in full. "Hands-on trial" means the competitor's own published page, dated. Never sign up, call or pose as a customer.
- Before naming or targeting any business, confirm it is not a current BML client. If it is, stop and escalate to the account lead.

## 6. Local competitor data file

One file per competitor per client, saved to that client's Drive OUTPUTS/SEO (never a project-root folder, never shared across clients):

    name: <competitor name>
    website: <domain>
    client: <CODE>
    last_verified: <YYYY-MM-DD>
    sources:
      - <URL or row ID> (<YYYY-MM-DD>)
    l_rows: [<L-4>, <L-6>]
    services_overlap: [<service>, <service>]
    service_area: "<towns, as published>"
    credentials_published: "<as published or —>"
    offers_published: "<offer, as of date, or —>"
    price_signals: "<as published, as of date, or —>"
    review_rating: "<n> (<source>, <date>) ⚠ confirm before publishing"
    review_themes_praise: [<theme>, <theme>]
    review_themes_complaint: [<theme>, <theme>]
    claims_they_repeat: [<claim>]
    notes: "<fact only; interpretation kept separate>"

Use `—` for unknowns. Never estimate.

## 7. Tools

- Semrush is the only SEO data tool (keyword demand, competitor domains). Search Console, GA4 and Google Business Profile come through Windsor.ai, read-only.
- Never call write actions on any connector: no Wix site changes, no Windsor.ai Business Profile or listing edits, no review replies, no ad changes.
- Other tools (review platforms, call tracking, CRMs) only "if the client uses it", per page 00 §8. Never write to a client CRM.
- Re-verification on a cadence is a scheduled task (marketing-loops), proposed and created only after the user approves, never an in-session loop. The quarterly market refresh covers L-3, L-4, L-5 and L-7; L-6 (offers and claims) is not refreshed by it, so re-check L-6 facts older than 90 days before reusing them.

## 8. Outputs

| Output | Kind | Voice | Location |
|---|---|---|---|
| Page copy | Client deliverable | 01 + 02 | OUTPUTS/WEBSITE |
| Page-set plan | Agency artifact | Baker house style (Ops Manual `02: Baker Style Guide`) | OUTPUTS/SEO |
| Competitor data files | Agency artifact | n/a | OUTPUTS/SEO |
| Asset audit | Agency artifact | Baker house style | OUTPUTS/SEO |

- Agency artifacts never load client pages 01/02.
- Resolve the OUTPUTS folder by ID from the router. Never search Drive and never create folders; if none fits, stop and report.
- A ClickUp task (tag `website` or `seo`) is drafted and created only after the user approves. Nothing is written to ClickUp otherwise.
- Nothing publishes, sends or spends without a human checkpoint. Name the client's approver (J-1). Any page that names a competitor is flagged for legal review.
- No competitor links in a local client's site footer; option-comparison pages link from the relevant service page (hand off to site-architecture).
- Rows found during research are staged as DRAFT in the context-rules §10 review format at the end of the output.
- Every output ends with the context-rules §9 footer (including `Distinctiveness: FAIL — not client-ready` when page copy lacks an F belief or G proof point).
