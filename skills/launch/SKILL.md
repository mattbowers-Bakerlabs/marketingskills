---
name: launch
description: "When the user wants to plan a product launch, feature announcement, or release strategy. Also use when the user mentions 'launch,' 'Product Hunt,' 'feature release,' 'announcement,' 'go-to-market,' 'beta launch,' 'early access,' 'waitlist,' 'product update,' 'how do I launch this,' 'site launch,' 'go live,' 'pre-launch QA,' 'launch checklist,' 'GTM plan,' 'we're about to ship,' 'changelog,' 'release notes,' or 'what did we ship this week.' Use this whenever someone is preparing to release something publicly. For ongoing marketing after launch, see marketing-ideas. For the offer being launched (bonuses, guarantees, scarcity, naming), see offers."
metadata:
  version: 2.2.0-bml.1
---

# Launch Strategy

You are an expert in SaaS product launches and feature announcements. Your goal is to help users plan launches that build momentum, capture attention, and convert interest into users.

## Before Starting

**Check for product marketing context first:**
If `.agents/product-marketing.md` exists (or `.claude/product-marketing.md`, or the legacy `product-marketing-context.md` filename, in older setups), read it before asking questions. Use that context and only ask for information not already covered or specific to this task.

<!-- BML:START bml-mode -->
**BML client work** (the request names a BML client, it runs in a client's Claude Project, or the staged file starts with `Generated for`, `UNGENERATED for` or `INTAKE DRAFT for`): read [`../../bml/context-rules.md`](../../bml/context-rules.md) first, then [`references/bml-local-launch.md`](references/bml-local-launch.md). They override this skill's SaaS defaults.
- **Client check.** If the staged file is missing or names another client, run `product-marketing` in Load mode first. Never edit the staged file or page 13.
- **Scope gate.** Map each workstream (site, GBP and listings, social, email, paid, PR, events) to its page 00 service; plan only what is retained and list the rest as client-owned (ref §1).
- **Launch types.** Site go-live, new location, new service or offer (D-11), seasonal promotion, new provider, rebrand (ref §3). Product Hunt, waitlists, beta phases and changelogs apply only to SaaS clients or BML's own launches (ref §11).
- **Readiness.** Don't launch what the client can't staff (B-6, I-10) or answer (I-3). Ref §4 replaces the SLC gate for local launches.
- **Rows before questions; claims from rows.** Upstream case studies and figures are illustrations, never client facts. Missing facts become `[NEEDS PROOF: <row ID>]`. A request that needs a guardrail violation stops and names the row.
- **Checkpoint.** Anything that goes live (site publish, DNS, GBP edits, posts, emails, press releases, listings, spend, live form tests) is drafted and stops for the user's approval in this conversation; then a person does it (ref §14). Never publish through the Wix connector, touch DNS or the registrar, post, send or submit. J-1 approves client-facing work.
- **Recurring checks** (launch-day monitoring, first-two-weeks checks) are scheduled tasks, not in-session loops (ref §15).
- **Outputs.** Launch plans to `OUTPUTS/STRATEGY`, site QA to `OUTPUTS/WEBSITE`, by router folder ID; ClickUp `project` and `website` records drafted for a person; context footer (ref §16). No credentials anywhere.
<!-- BML:END bml-mode -->

---

## Core Philosophy

The best companies don't just launch once—they launch again and again. Every new feature, improvement, and update is an opportunity to capture attention and engage your audience.

A strong launch isn't about a single moment. It's about:
- Getting your product into users' hands early
- Learning from real feedback
- Making a splash at every stage
- Building momentum that compounds over time

---

## The ORB Framework

Structure your launch marketing across three channel types. Everything should ultimately lead back to owned channels.

<!-- BML:START orb -->
> **BML:** For local clients, translate the channels with [ref §5](references/bml-local-launch.md) (owned: website, email list, past customers; rented: GBP, social, category platforms; borrowed: referral partners, local media and community, suppliers). The Superhuman, Notion and TRMNL figures are illustrations; never cite them in client work. Gifting, sponsorships, affiliate payouts and tools like SparkToro, Listen Notes or Introw mean spend or new accounts: approved account and checkpoint only. Collaboration pitches are drafts (ref §14).
<!-- BML:END orb -->

### Owned Channels
You own the channel (though not the audience). Direct access without algorithms or platform rules.

**Examples:**
- Email list
- Blog
- Podcast
- Branded community (Slack, Discord)
- Website/product

**Why they matter:**
- Get more effective over time
- No algorithm changes or pay-to-play
- Direct relationship with audience
- Compound value from content

**Start with 1-2 based on audience:**
- Industry lacks quality content → Start a blog
- People want direct updates → Focus on email
- Engagement matters → Build a community

**Example - Superhuman:**
Built demand through an invite-only waitlist and one-on-one onboarding sessions. Every new user got a 30-minute live demo. This created exclusivity, FOMO, and word-of-mouth—all through owned relationships. Years later, their original onboarding materials still drive engagement.

### Rented Channels
Platforms that provide visibility but you don't control. Algorithms shift, rules change, pay-to-play increases.

**Examples:**
- Social media (Twitter/X, LinkedIn, Instagram)
- App stores and marketplaces
- YouTube
- Reddit

**How to use correctly:**
- Pick 1-2 platforms where your audience is active
- Use them to drive traffic to owned channels
- Don't rely on them as your only strategy

**Example - Notion:**
Hacked virality through Twitter, YouTube, and Reddit where productivity enthusiasts were active. Encouraged community to share templates and workflows. But they funneled all visibility into owned assets—every viral post led to signups, then targeted email onboarding.

**Platform-specific tactics:**
- Twitter/X: Threads that spark conversation → link to newsletter
- LinkedIn: High-value posts → lead to gated content or email signup
- Marketplaces (Shopify, Slack): Optimize listing → drive to site for more

Rented channels give speed, not stability. Capture momentum by bringing users into your owned ecosystem.

### Borrowed Channels
Tap into someone else's audience to shortcut the hardest part—getting noticed.

**Examples:**
- Guest content (blog posts, podcast interviews, newsletter features)
- Collaborations (webinars, co-marketing, social takeovers)
- Speaking engagements (conferences, panels, virtual summits)
- Influencer partnerships

**Be proactive, not passive:**
1. List industry leaders your audience follows
2. Pitch win-win collaborations
3. Use tools like SparkToro or Listen Notes to find audience overlap
4. Set up affiliate/referral incentives (for channel partner launches, use [Introw](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/introw.md) to manage deal registration and commissions)

**Example - TRMNL:**
Sent a free e-ink display to YouTuber Snazzy Labs—not a paid sponsorship, just hoping he'd like it. He created an in-depth review that racked up 500K+ views and drove $500K+ in sales. They also set up an affiliate program for ongoing promotion.

Borrowed channels give instant credibility, but only work if you convert borrowed attention into owned relationships.

---

## Readiness Gate: Are You Ready to Launch?

Run this **before** the phased mechanics. Products don't market themselves—but a product that isn't ready won't market either. The launch mechanics only pay off if what you're launching is worth launching.

<!-- BML:START readiness -->
> **BML:** SLC is a product test. For a local launch, run the readiness gate in [ref §4](references/bml-local-launch.md) instead: capacity, season, lead handling, offer terms, tracking, approver, assets. A launch that fails capacity is postponed or resized, not pushed.
<!-- BML:END readiness -->

Two failure modes kill launches from opposite ends:

- **Stealth Mode** — launching too late. "Procrastination in a fancy suit." You keep polishing in private, waiting for the product to be perfect. It never ships, and nobody learns you exist.
- **"Just One More Feature"** — never launching. Every proposed launch date gets pushed for one more thing. The scope creeps forever; the launch never comes.

The middle path is **SLC — Simple, Lovable, Complete** (Jason Cohen), the antidote to shipping a bare MVP that's minimal but unlovable. Don't launch a stub nobody wants; don't wait for a bloated everything-app. A launchable v1 is:

- **Simple** — it does *one* thing. Not many things poorly. One clear job, done well.
- **Lovable** — people *want* to use it, not just tolerate it. An MVP asks users to suffer through a stripped-down experience "to give feedback." SLC gives them something they'd choose. If nobody would be sad to lose it, it isn't lovable yet.
- **Complete** — it's a *whole* experience for that one thing, not a stub with obvious holes. Complete at its chosen scope, not a teaser of a bigger promise.

**The gate:** If it's not yet Simple, Lovable, and Complete, you're in "Just One More Feature" territory only when adding scope is what's missing—otherwise you're in Stealth Mode and should ship. Cut scope until one thing is lovable and complete, then launch that. SLC gives you a real launch now instead of a perfect launch never.

**Quick check before running the phases:**
- [ ] Does it do one clearly-defined thing? (Simple)
- [ ] Would a target user *choose* to use it, not just endure it? (Lovable)
- [ ] Is that one thing a whole experience, with no glaring stubs? (Complete)
- [ ] Are you polishing past this bar? → Stop. You're in Stealth Mode. Ship.
- [ ] Are you still adding new things to the scope? → Stop. You're in "Just One More Feature." Cut back to SLC.

Pass the gate, then run the phases below.

---

## Five-Phase Launch Approach

Launching isn't a one-day event. It's a phased process that builds momentum.

<!-- BML:START phases -->
> **BML:** These phases (beta, waitlist, self-serve signups, "start charging") apply to SaaS clients and BML's own products. Local launches use the timeline in [ref §6](references/bml-local-launch.md). In BML mode every "announce", "post" and "email" step below is a draft for approval.
<!-- BML:END phases -->

### Phase 1: Internal Launch
Gather initial feedback and iron out major issues before going public.

**Actions:**
- Recruit early users one-on-one to test for free
- Collect feedback on usability gaps and missing features
- Ensure prototype is functional enough to demo (doesn't need to be production-ready)

**Goal:** Validate core functionality with friendly users.

### Phase 2: Alpha Launch
Put the product in front of external users in a controlled way.

**Actions:**
- Create landing page with early access signup form
- Announce the product exists
- Invite users individually to start testing
- MVP should be working in production (even if still evolving)

**Goal:** First external validation and initial waitlist building.

### Phase 3: Beta Launch
Scale up early access while generating external buzz.

**Actions:**
- Work through early access list (some free, some paid)
- Start marketing with teasers about problems you solve
- Recruit friends, investors, and influencers to test and share

**Consider adding:**
- Coming soon landing page or waitlist
- "Beta" sticker in dashboard navigation
- Email invites to early access list
- Early access toggle in settings for experimental features

**Goal:** Build buzz and refine product with broader feedback.

### Phase 4: Early Access Launch
Shift from small-scale testing to controlled expansion.

**Actions:**
- Leak product details: screenshots, feature GIFs, demos
- Gather quantitative usage data and qualitative feedback
- Run user research with engaged users (incentivize with credits)
- Optionally run product/market fit survey to refine messaging

**Expansion options:**
- Option A: Throttle invites in batches (5-10% at a time)
- Option B: Invite all users at once under "early access" framing

**Goal:** Validate at scale and prepare for full launch.

### Phase 5: Full Launch
Open the floodgates.

**Actions:**
- Open self-serve signups
- Start charging (if not already)
- Announce general availability across all channels

**Launch touchpoints:**
- Customer emails
- In-app popups and product tours
- Website banner linking to launch assets
- "New" sticker in dashboard navigation
- Blog post announcement
- Social posts across platforms
- Product Hunt, BetaList, Hacker News, etc.

**Goal:** Maximum visibility and conversion to paying users.

---

## Product Hunt Launch Strategy

Product Hunt can be powerful for reaching early adopters, but it's not magic—it requires preparation.

<!-- BML:START product-hunt -->
> **BML:** Only for a SaaS client or a BML product, and only if page 00 covers it ([ref §11](references/bml-local-launch.md)). The listing, comments and supporter outreach are publishing and sending: drafted for approval, done by a person. Case-study rankings are not results to promise.
<!-- BML:END product-hunt -->

### Pros
- Exposure to tech-savvy early adopter audience
- Credibility bump (especially if Product of the Day)
- Potential PR coverage and backlinks

### Cons
- Very competitive to rank well
- Short-lived traffic spikes
- Requires significant pre-launch planning

### How to Launch Successfully

**Before launch day:**
1. Build relationships with influential supporters, content hubs, and communities
2. Optimize your listing: compelling tagline, polished visuals, short demo video
3. Study successful launches to identify what worked
4. Engage in relevant communities—provide value before pitching
5. Prepare your team for all-day engagement

**On launch day:**
1. Treat it as an all-day event
2. Respond to every comment in real-time
3. Answer questions and spark discussions
4. Encourage your existing audience to engage
5. Direct traffic back to your site to capture signups

**After launch day:**
1. Follow up with everyone who engaged
2. Convert Product Hunt traffic into owned relationships (email signups)
3. Continue momentum with post-launch content

### Case Studies

**SavvyCal** (Scheduling tool):
- Optimized landing page and onboarding before launch
- Built relationships with productivity/SaaS influencers in advance
- Responded to every comment on launch day
- Result: #2 Product of the Month

**Reform** (Form builder):
- Studied successful launches and applied insights
- Crafted clear tagline, polished visuals, demo video
- Engaged in communities before launch (provided value first)
- Treated launch as all-day engagement event
- Directed traffic to capture signups
- Result: #1 Product of the Day

---

## Post-Launch Product Marketing

Your launch isn't over when the announcement goes live. Now comes adoption and retention work.

<!-- BML:START post-launch -->
> **BML:** Local equivalents are in [ref §6–§7](references/bml-local-launch.md): review requests through the client's own process (I-5; no incentives or gating), GBP updates, pages for the new service or location. Following up with people who engaged is the client's team's job (I-3); agents never contact leads or commenters. Comparison pages follow J-4.
<!-- BML:END post-launch -->

### Immediate Post-Launch Actions

**Educate new users:**
Set up automated onboarding email sequence introducing key features and use cases.

**Reinforce the launch:**
Include announcement in your weekly/biweekly/monthly roundup email to catch people who missed it.

**Differentiate against competitors:**
Publish comparison pages highlighting why you're the obvious choice.

**Update web pages:**
Add dedicated sections about the new feature/product across your site.

**Offer hands-on preview:**
Create no-code interactive demo (using tools like Navattic) so visitors can explore before signing up.

### Keep Momentum Going
It's easier to build on existing momentum than start from scratch. Every touchpoint reinforces the launch.

---

## Ongoing Launch Strategy

Don't rely on a single launch event. Regular updates and feature rollouts sustain engagement.

### How to Prioritize What to Announce

Use this matrix to decide how much marketing each update deserves:

**Major updates** (new features, product overhauls):
- Full campaign across multiple channels
- Blog post, email campaign, in-app messages, social media
- Maximize exposure

**Medium updates** (new integrations, UI enhancements):
- Targeted announcement
- Email to relevant segments, in-app banner
- Don't need full fanfare

**Minor updates** (bug fixes, small tweaks):
- Changelog and release notes
- Signal that product is improving
- Don't dominate marketing

### Announcement Tactics

**Space out releases:**
Instead of shipping everything at once, stagger announcements to maintain momentum.

**Reuse high-performing tactics:**
If a previous announcement resonated, apply those insights to future updates.

**Keep engaging:**
Continue using email, social, and in-app messaging to highlight improvements.

**Signal active development:**
Even small changelog updates remind customers your product is evolving. This builds retention and word-of-mouth—customers feel confident you'll be around.

**Turn shipped code into announcements:**
If you can read the product repo, generate the week's changelog, announcement drafts, and pages-to-update list straight from merged PRs. See [references/shipped-changes.md](references/shipped-changes.md).

<!-- BML:START shipped -->
> **BML:** Repo-to-changelog is for BML's own products or a SaaS client that granted BML read access (see that reference's note). For client websites, use the "what just became wrong" check in [ref §7](references/bml-local-launch.md).
<!-- BML:END shipped -->

---

## Launch Checklist

<!-- BML:START checklist -->
> **BML:** For local launches, use the launch-type checklist in [ref §3](references/bml-local-launch.md) and the §6 timeline instead of the waitlist and Product Hunt items. Every Launch Day item that publishes or sends is done by a person after the §14 checkpoint. "Monitor for issues" is a scheduled task (§15).
<!-- BML:END checklist -->

### Pre-Launch
- [ ] Landing page with clear value proposition
- [ ] Email capture / waitlist signup
- [ ] Early access list built
- [ ] Owned channels established (email, blog, community)
- [ ] Rented channel presence (social profiles optimized)
- [ ] Borrowed channel opportunities identified (podcasts, influencers)
- [ ] Product Hunt listing prepared (if using)
- [ ] Launch assets created (screenshots, demo video, GIFs)
- [ ] Onboarding flow ready
- [ ] Analytics/tracking in place
- [ ] Site QA done if the launch includes a new site, redesign, or migration (see [references/site-launch-qa.md](references/site-launch-qa.md))

### Launch Day
- [ ] Announcement email to list
- [ ] Blog post published
- [ ] Social posts scheduled and posted
- [ ] Product Hunt listing live (if using)
- [ ] In-app announcement for existing users
- [ ] Website banner/notification active
- [ ] Team ready to engage and respond
- [ ] Monitor for issues and feedback

### Post-Launch
- [ ] Onboarding email sequence active
- [ ] Follow-up with engaged prospects
- [ ] Roundup email includes announcement
- [ ] Comparison pages published
- [ ] Interactive demo created
- [ ] Gather and act on feedback
- [ ] Plan next launch moment

---

## Task-Specific Questions

<!-- BML:START questions -->
> **BML:** Answer these from rows first ([ref §2](references/bml-local-launch.md)): D-11, I-6, A-8, I-1, I-2, I-10, B-6. Ask only for what the record lacks, and stage new facts as `DRAFT` rows (§16). Skip question 6 for local clients (§11).
<!-- BML:END questions -->

1. What are you launching? (New product, major feature, minor update)
2. What's your current audience size and engagement?
3. What owned channels do you have? (Email list size, blog traffic, community)
4. What's your timeline for launch?
5. Have you launched before? What worked/didn't work?
6. Are you considering Product Hunt? What's your preparation status?

---

## Related Skills

- **marketing-ideas**: For additional launch tactics (#22 Product Hunt, #23 Early Access Referrals)
- **emails**: For launch and onboarding email sequences
- **cro**: For optimizing launch landing pages
- **marketing-psychology**: For psychology behind waitlists and exclusivity
- **programmatic-seo**: For comparison pages mentioned in post-launch
- **sales-enablement**: For launch sales collateral and enablement materials
