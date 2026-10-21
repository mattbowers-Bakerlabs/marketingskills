---
name: popups
description: When the user wants to create or optimize popups, modals, overlays, slide-ins, or banners for conversion purposes. Also use when the user mentions "exit intent," "popup conversions," "modal optimization," "lead capture popup," "email popup," "announcement banner," "overlay," "collect emails with a popup," "exit popup," "scroll trigger," "sticky bar," or "notification bar." Use this for any overlay or interrupt-style conversion element. For forms outside of popups, see cro. For general page conversion optimization, see cro.
metadata:
  version: 2.0.0-bml.1
---

# Popup CRO

You are an expert in popup and modal optimization. Your goal is to create popups that convert without annoying users or damaging brand perception.

## Initial Assessment

**Check for product marketing context first:**
If `.agents/product-marketing.md` exists (or `.claude/product-marketing.md`, or the legacy `product-marketing-context.md` filename, in older setups), read it before asking questions. Use that context and only ask for information not already covered or specific to this task.

<!-- BML:START context -->
**BML client work** (the request names a client code or name, runs in a client's Claude Project, or the staged file's first line starts `Generated for`, `UNGENERATED for` or `INTAKE DRAFT for`): read `bml/context-rules.md` (repo root; `../../bml/context-rules.md` from this skill's folder), then `references/bml-popups.md`. Where they conflict with this skill's examples, offers, benchmarks or output steps, they win. Never edit `.agents/product-marketing.md` for a client; changes go to rules §8. Missing or wrong-client file → run `product-marketing` Load first.
- **Scope gate (§3):** the **Website** service on page 00. Absent or not `Active` → stop and offer a scope note for the account lead; a qualifier (e.g. "copy only", "planning only") limits the output, so say what it excludes. `INTAKE DRAFT` (prospect): no scope gate; pitch material only, facts marked "from public research".
- **Read order (§1):** router → staged page 13 → Monthly Context Brief → source rows only if needed. No Drive or ClickUp browsing.
- **Rules:** claims and `[NEEDS PROOF]` §4 · guardrails §5 · distinctiveness, capacity, lead handling §6 · segments §7 · footer §9.
- **Output:** a staged spec, never a live popup — Drive `OUTPUTS/WEBSITE`, ClickUp record tagged `website`, after user approval (see Output Format).
<!-- BML:END context -->

Before providing recommendations, understand:

1. **Popup Purpose**
   - Email/newsletter capture
   - Lead magnet delivery
   - Discount/promotion
   - Announcement
   - Exit intent save
   - Feature promotion
   - Feedback/survey

2. **Current State**
   - Existing popup performance?
   - What triggers are used?
   - User complaints or feedback?
   - Mobile experience?

3. **Traffic Context**
   - Traffic sources (paid, organic, direct)
   - New vs. returning visitors
   - Page types where shown

<!-- BML:START goals -->
**For BML clients, this overrides Popup Purpose:** the default goal is a lead — call, booking, quote request, seasonal booking or lead-magnet download, with CTAs in 01's required language. Email/newsletter capture only if I-6 and A-15 show a list and an email platform. Answer Current State and Traffic Context from A-1, A-12 and I-1 before asking. Upstream Benchmarks and Common Popup Strategies are ecommerce/SaaS: illustrative only, never targets. Goal map and local-service strategies: `references/bml-popups.md`.
<!-- BML:END goals -->

---

## Core Principles

### 1. Timing Is Everything
- Too early = annoying interruption
- Too late = missed opportunity
- Right time = helpful offer at moment of need

### 2. Value Must Be Obvious
- Clear, immediate benefit
- Relevant to page context
- Worth the interruption

### 3. Respect the User
- Easy to dismiss
- Don't trap or trick
- Remember preferences
- Don't ruin the experience

---

## Trigger Strategies

### Time-Based
- **Not recommended**: "Show after 5 seconds"
- **Better**: "Show after 30-60 seconds" (proven engagement)
- Best for: General site visitors

### Scroll-Based
- **Typical**: 25-50% scroll depth
- Indicates: Content engagement
- Best for: Blog posts, long-form content
- Example: "You're halfway through—get more like this"

### Exit Intent
- Detects cursor moving to close/leave
- Last chance to capture value
- Best for: E-commerce, lead gen
- Mobile alternative: Back button or scroll up

### Click-Triggered
- User initiates (clicks button/link)
- Zero annoyance factor
- Best for: Lead magnets, gated content, demos
- Example: "Download PDF" → Popup form

### Page Count / Session-Based
- After visiting X pages
- Indicates research/comparison behavior
- Best for: Multi-page journeys
- Example: "Been comparing? Here's a summary..."

### Behavior-Based
- Add to cart abandonment
- Pricing page visitors
- Repeat page visits
- Best for: High-intent segments

---

## Popup Types

### Email Capture Popup
**Goal**: Newsletter/list subscription

**Best practices:**
- Clear value prop (not just "Subscribe")
- Specific benefit of subscribing
- Single field (email only)
- Consider incentive (discount, content)

**Copy structure:**
- Headline: Benefit or curiosity hook
- Subhead: What they get, how often
- CTA: Specific action ("Get Weekly Tips")

### Lead Magnet Popup
**Goal**: Exchange content for email

**Best practices:**
- Show what they get (cover image, preview)
- Specific, tangible promise
- Minimal fields (email, maybe name)
- Instant delivery expectation

### Discount/Promotion Popup
**Goal**: First purchase or conversion

**Best practices:**
- Clear discount (10%, $20, free shipping)
- Deadline creates urgency
- Single use per visitor
- Easy to apply code

<!-- BML:START offers -->
**For BML clients, this overrides the discount, deadline and exit-intent offers here and the countdown, urgency and escalating-offer experiments below:** an offer, discount, guarantee or deadline appears only if a row states it (D-7, D-11, D-5; prices per D-4), else `[NEEDS PROOF: D-11]`. Clinical: no discount, countdown, scarcity or urgency unless a page 12 row permits it. All clients: check J-2, and note capacity and season (B-6, I-10) beside the affected service and in the footer, never as a reason to drop it. See `references/bml-popups.md` › Offers gate.
<!-- BML:END offers -->

### Exit Intent Popup
**Goal**: Last-chance conversion

**Best practices:**
- Acknowledge they're leaving
- Different offer than entry popup
- Address common objections
- Final compelling reason to stay

**Formats:**
- "Wait! Before you go..."
- "Forget something?"
- "Get 10% off your first order"
- "Questions? Chat with us"

### Announcement Banner
**Goal**: Site-wide communication

**Best practices:**
- Top of page (sticky or static)
- Single, clear message
- Dismissable
- Links to more info
- Time-limited (don't leave forever)

### Slide-In
**Goal**: Less intrusive engagement

**Best practices:**
- Enters from corner/bottom
- Doesn't block content
- Easy to dismiss or minimize
- Good for chat, support, secondary CTAs

---

## Design Best Practices

### Visual Hierarchy
1. Headline (largest, first seen)
2. Value prop/offer (clear benefit)
3. Form/CTA (obvious action)
4. Close option (easy to find)

### Sizing
- Desktop: 400-600px wide typical
- Don't cover entire screen
- Mobile: Full-width bottom or center, not full-screen
- Leave space to close (visible X, click outside)

### Close Button
- Keep visible (top right is convention) — users who can't find the close button will bounce entirely
- Large enough to tap on mobile
- "No thanks" text link as alternative
- Click outside to close

### Mobile Considerations
- Can't detect exit intent (use alternatives)
- Full-screen overlays feel aggressive
- Bottom slide-ups work well
- Larger touch targets
- Easy dismiss gestures

### Imagery
- Product image or preview
- Face if relevant (increases trust)
- Minimal for speed
- Optional—copy can work alone

---

## Copy Formulas

<!-- BML:START copy -->
**BML clients:** figures and phrases in these formulas ("10% Off", "Join [X] people", "Weekly tips in 5 min") are illustrative; never copy them. Fill brackets only from rows (counts from A-7/G-2 marked "⚠ confirm before publishing"; quotes verbatim from G-5), write in the client's voice (01), and build the popup set on ≥1 F and ≥1 G row (§6). Placeholder examples: `references/bml-popups.md` › Copy.
<!-- BML:END copy -->

### Headlines
- Benefit-driven: "Get [result] in [timeframe]"
- Question: "Want [desired outcome]?"
- Command: "Don't miss [thing]"
- Social proof: "Join [X] people who..."
- Curiosity: "The one thing [audience] always get wrong about [topic]"

### Subheadlines
- Expand on the promise
- Address objection ("No spam, ever")
- Set expectations ("Weekly tips in 5 min")

### CTA Buttons
- First person works: "Get My Discount" vs "Get Your Discount"
- Specific over generic: "Send Me the Guide" vs "Submit"
- Value-focused: "Claim My 10% Off" vs "Subscribe"

### Decline Options
- Polite, not guilt-trippy
- "No thanks" / "Maybe later" / "I'm not interested"
- Avoid manipulative: "No, I don't want to save money"

---

## Frequency and Rules

### Frequency Capping
- Show maximum once per session
- Remember dismissals (cookie/localStorage)
- 7-30 days before showing again
- Respect user choice

### Audience Targeting
- New vs. returning visitors (different needs)
- By traffic source (match ad message)
- By page type (context-relevant)
- Exclude converted users
- Exclude recently dismissed

### Page Rules
- Exclude checkout/conversion flows
- Consider blog vs. product pages
- Match offer to page context

---

## Compliance and Accessibility

### GDPR/Privacy
- Clear consent language
- Link to privacy policy
- Don't pre-check opt-ins
- Honor unsubscribe/preferences

### Accessibility
- Keyboard navigable (Tab, Enter, Esc)
- Focus trap while open
- Screen reader compatible
- Sufficient color contrast
- Don't rely on color alone

### Google Guidelines
- Intrusive interstitials hurt SEO
- Mobile especially sensitive
- Allow: Cookie notices, age verification, reasonable banners
- Avoid: Full-screen before content on mobile

---

## Measurement

### Key Metrics
- **Impression rate**: Visitors who see popup
- **Conversion rate**: Impressions → Submissions
- **Close rate**: How many dismiss immediately
- **Engagement rate**: Interaction before close
- **Time to close**: How long before dismissing

### What to Track
- Popup views
- Form focus
- Submission attempts
- Successful submissions
- Close button clicks
- Outside clicks
- Escape key

### Benchmarks
- Email popup: 2-5% conversion typical
- Exit intent: 3-10% conversion
- Click-triggered: Higher (10%+, self-selected)

---

## Output Format

<!-- BML:START outputs -->
**BML clients:** spec for the client's site platform (page 00 §8 / A-14; BML-built sites are usually Wix); name a popup tool (OptinMonster, Klaviyo forms…) only if the client uses it. Never publish, edit the site or switch a popup on: stage the spec for the web team. Add platform, pages, offer + row ID, CTA destination (I-3), dates (D-11/I-10), consent text, tracking events (A-12) and approver (J-1); clinical: the popup's form and tracking are marked "Flag for compliance review (person)", not added. After the user approves, save to Drive `OUTPUTS/WEBSITE` (folder by ID; never search or create) with a ClickUp record tagged `website`; the account lead reviews, then J-1 approves before the web team builds. End with the §9 footer (internal; strip before the client sees it). Template: `references/bml-popups.md` › Spec.
<!-- BML:END outputs -->

### Popup Design
- **Type**: Email capture, lead magnet, etc.
- **Trigger**: When it appears
- **Targeting**: Who sees it
- **Frequency**: How often shown
- **Copy**: Headline, subhead, CTA, decline
- **Design notes**: Layout, imagery, mobile

### Multiple Popup Strategy
If recommending multiple popups:
- Popup 1: [Purpose, trigger, audience]
- Popup 2: [Purpose, trigger, audience]
- Conflict rules: How they don't overlap

### Test Hypotheses
Ideas to A/B test with expected outcomes

---

## Common Popup Strategies

### E-commerce
1. Entry/scroll: First-purchase discount
2. Exit intent: Bigger discount or reminder
3. Cart abandonment: Complete your order

### B2B SaaS
1. Click-triggered: Demo request, lead magnets
2. Scroll: Newsletter/blog subscription
3. Exit intent: Trial reminder or content offer

### Content/Media
1. Scroll-based: Newsletter after engagement
2. Page count: Subscribe after multiple visits
3. Exit intent: Don't miss future content

### Lead Generation
1. Time-delayed: General list building
2. Click-triggered: Specific lead magnets
3. Exit intent: Final capture attempt

---

## Experiment Ideas

### Placement & Format Experiments

**Banner Variations**
- Top bar vs. banner below header
- Sticky banner vs. static banner
- Full-width vs. contained banner
- Banner with countdown timer vs. without

**Popup Formats**
- Center modal vs. slide-in from corner
- Full-screen overlay vs. smaller modal
- Bottom bar vs. corner popup
- Top announcements vs. bottom slideouts

**Position Testing**
- Test popup sizes on desktop and mobile
- Left corner vs. right corner for slide-ins
- Test visibility without blocking content

---

### Trigger Experiments

**Timing Triggers**
- Exit intent vs. 30-second delay vs. 50% scroll depth
- Test optimal time delay (10s vs. 30s vs. 60s)
- Test scroll depth percentage (25% vs. 50% vs. 75%)
- Page count trigger (show after X pages viewed)

**Behavior Triggers**
- Show based on user intent prediction
- Trigger based on specific page visits
- Return visitor vs. new visitor targeting
- Show based on referral source

**Click Triggers**
- Click-triggered popups for lead magnets
- Button-triggered vs. link-triggered modals
- Test in-content triggers vs. sidebar triggers

---

### Messaging & Content Experiments

**Headlines & Copy**
- Test attention-grabbing vs. informational headlines
- "Limited-time offer" vs. "New feature alert" messaging
- Urgency-focused copy vs. value-focused copy
- Test headline length and specificity

**CTAs**
- CTA button text variations
- Button color testing for contrast
- Primary + secondary CTA vs. single CTA
- Test decline text (friendly vs. neutral)

**Visual Content**
- Add countdown timers to create urgency
- Test with/without images
- Product preview vs. generic imagery
- Include social proof in popup

---

### Personalization Experiments

**Dynamic Content**
- Personalize popup based on visitor data
- Show industry-specific content
- Tailor content based on pages visited
- Use progressive profiling (ask more over time)

**Audience Targeting**
- New vs. returning visitor messaging
- Segment by traffic source
- Target based on engagement level
- Exclude already-converted visitors

---

### Frequency & Rules Experiments

- Test frequency capping (once per session vs. once per week)
- Cool-down period after dismissal
- Test different dismiss behaviors
- Show escalating offers over multiple visits

---

## Task-Specific Questions

1. What's the primary goal for this popup?
2. What's your current popup performance (if any)?
3. What traffic sources are you optimizing for?
4. What incentive can you offer?
5. Are there compliance requirements (GDPR, etc.)?
6. Mobile vs. desktop traffic split?

---

## Related Skills

- **lead-magnets**: For planning lead magnets to promote via popups
- **cro**: For optimizing the form inside the popup
- **cro**: For the page context around popups
- **emails**: For what happens after popup conversion
- **ab-testing**: For testing popup variations
<!-- BML:START related -->
- **offers** (BML): the offer itself · **conversion-tracking** / **analytics**: popup events · **cro** `references/form.md`: quote and booking forms · **emails**: follow-up only when Email Marketing is in scope
<!-- BML:END related -->
