# ClearTerms — Complete Platform Strategy
## Brand, SEO, Monetization & 12-Month Roadmap

---

## EXECUTIVE SUMMARY

**Brand:** ClearTerms  
**Domain target:** clearterms.com  
**Category:** National prenuptial / postnuptial legal lead platform  
**Model:** Free consumer matching → paid attorney referral (CPL)  
**Operable from:** Canada (100% — no licensure required for referral)  
**Time to launch MVP:** 2–3 weeks  
**Time to first revenue:** 4–8 weeks post-launch  
**Year 1 revenue potential (conservative):** $80K–$220K USD  
**Year 1 revenue potential (optimistic):** $300K–$600K USD  

---

## PART 1: DESIGN SYSTEM

### Color Palette
| Token | Value | Usage |
|-------|-------|-------|
| `--black` | `#0A0A0B` | Headings, high-emphasis text, dark sections |
| `--gold` | `#C9A96E` | Primary accent, trust signals, CTAs |
| `--gold-light` | `#E8D5A8` | Decorative, step numbers, subtle elements |
| `--surface` | `#F7F5F1` | Section backgrounds, form cards, table rows |
| `--white` | `#FEFEFE` | Page backgrounds |
| `--muted` | `#6B6860` | Body copy, secondary text, labels |
| `--border` | `#E2DED7` | Dividers, input borders, card outlines |

**Rationale:** The warm off-white surface and gold accent communicate trust, maturity, and premium editorial quality without the cold clinical feel of most legal sites. This is the Bloomberg / Stripe tone applied to family law.

### Typography
| Role | Font | Weights |
|------|------|---------|
| Display / Headings | Playfair Display | 400, 500, 600 (italic for emphasis) |
| Body / UI | DM Sans | 300, 400, 500, 600 |
| Labels / Mono | DM Mono | 400, 500 |

**Rationale:** Playfair brings editorial gravitas — the kind of typeface you'd see in a premium finance publication. DM Sans provides clean, readable body text. DM Mono in labels signals precision and data — "we know our stuff." The contrast between serif headings and clean sans body creates the dual identity: authoritative but accessible.

### Spacing Scale
`4px → 8px → 12px → 16px → 24px → 32px → 48px → 64px → 96px → 128px`  
8-point base grid throughout.

### Animation Rules
- All page animations are CSS-only `@keyframes` — zero JS dependency, Lighthouse-safe
- Intersection Observer scroll reveals: `opacity 0→1 + translateY(24px→0)` at 700ms with `cubic-bezier(0.22, 1, 0.36, 1)` easing
- Staggered delays of 60ms between sibling elements
- Hover states: only `transform: translateY(-1px)` and `background` transitions
- No autoplay animations. No animations that reduce legibility.

---

## PART 2: BRAND POSITIONING

### Name
**ClearTerms** — communicates clarity, legal precision, transparency. No ambiguity in the name, which mirrors the product promise.

### Tagline
"Protect what matters, clearly."

### Voice & Tone
- **Voice:** Intelligent, calm, direct. Like a knowledgeable friend who happens to be a lawyer.
- **Tone:** Never alarmist. Never salesy. Never condescending.
- **Personality:** The Wirecutter of prenups. We've done the research. Here's what you need to know. Here's who can help.
- **Not:** Legal jargon. Fear tactics. Divorce warnings. Cold corporate language.

### Differentiation
| Law Firm Sites | ClearTerms |
|---|---|
| Promote one attorney/firm | Neutral, multi-attorney matching |
| Geographic and local | National platform |
| Assume legal literacy | Explain everything from first principles |
| Sales pressure from first contact | Education-first, no pressure |
| Cliché legal imagery (scales, gavels) | Editorial, clean, modern |
| The attorney reaches out if you're lucky | Guaranteed attorney outreach within 48h |

### Why users choose ClearTerms over law firm sites
1. They're not ready to commit to a specific attorney yet
2. They want to understand what a prenup is before spending money
3. They don't know what questions to ask
4. They want to be matched to the right specialist, not just any lawyer
5. They don't want to be sold to before they've learned anything

---

## PART 3: SITE ARCHITECTURE

### URL Structure
```
clearterms.com/                         → Homepage (informational + lead capture)
clearterms.com/prenup-attorney          → Attorney matching (primary revenue page)
clearterms.com/postnuptial-agreement    → Postnup guide + matching
clearterms.com/prenup-for-house         → Property prenup guide + matching
clearterms.com/prenup-second-marriage   → Second marriage guide + matching
```

### Internal Linking Strategy
```
Homepage → all 4 inner pages (use case cards + footer)
/prenup-attorney → /postnuptial-agreement, /prenup-for-house, /prenup-second-marriage
/postnuptial-agreement → /, /prenup-attorney, /prenup-second-marriage
/prenup-for-house → /, /prenup-attorney, /prenup-second-marriage
/prenup-second-marriage → /, /prenup-for-house, /postnuptial-agreement
```

Every page links to every other page. No orphaned pages. Crawl depth: max 2 from homepage.

### Page Purposes
| Page | SEO Intent | Conversion Role | Primary KW Cluster |
|------|-----------|----------------|-------------------|
| Homepage | Informational ("what is a prenup") | Educate + funnel | prenup, what is a prenup |
| /prenup-attorney | Transactional ("prenup attorney") | Primary lead capture | prenup attorney, prenup lawyer |
| /postnuptial-agreement | Informational + Transactional | Secondary lead capture | post nup lawyer, postnuptial |
| /prenup-for-house | Long-tail + Transactional | Niche lead capture | prenup agreement for house |
| /prenup-second-marriage | Long-tail + Transactional | Niche lead capture | prenup for second marriage |

---

## PART 4: SEO PLAN

### Technical SEO Choices
- **Pure HTML/CSS/JS** (no framework) — fastest possible load, zero hydration overhead
- **No external JS libraries** — only Google Fonts (preloaded) and inline scripts
- **Semantic HTML5** — `<nav>`, `<section>`, `<article>`, `<main>`, `<aside>`, `<footer>` throughout
- **Schema markup on every page** — LegalService, Article, FAQPage as appropriate
- **Canonical tags** on every page to prevent duplicate content
- **Breadcrumb nav** on inner pages for crawl clarity
- **Image optimization** — when images are added, use WebP with width/height attributes
- **Font preconnect** — `<link rel="preconnect">` for Google Fonts on every page

### Target Keyword Map

**Cluster 1 — Awareness (Homepage)**
- `what is a prenup` — 60,500/mo, CompIdx 2
- `prenup` — 74,000/mo, CompIdx 18
- `premarital agreement` — 74,000/mo, CompIdx 18
- `prenuptial agreement` — broad, high volume

**Cluster 2 — Transactional (Attorney Page)**
- `prenup attorney` — 135,000/mo, CompIdx 1 ★★★
- `prenuptial agreement attorney` — 135,000/mo, CompIdx 1
- `prenup lawyer` — 3,600/mo, CompIdx 30
- `premarital agreement attorney` — 135,000/mo, CompIdx 1

**Cluster 3 — Postnuptial**
- `post nup lawyer` — 14,800/mo, CompIdx 1 ★★
- `postnuptial agreement` — growing 403% YoY
- `post nuptial agreement attorney` — 14,800/mo

**Cluster 4 — Property**
- `prenup agreement for house` — 2,400/mo, CompIdx 0 ★ (dead easy)
- `prenuptial agreement for house`
- `prenup real estate`

**Cluster 5 — Second Marriage**
- `prenup for second marriage` — 390/mo, CompIdx 2
- `second marriage prenuptial agreement`
- `prenup blended family`

### SEO Timeline
**Month 1:** Submit sitemap to Google Search Console. Set up Google Analytics 4. All pages live, all schema validated via Rich Results Test. Start tracking rankings for all target keywords.  
**Month 2–3:** Begin link building (see below). Monitor GSC for indexing issues.  
**Month 4–6:** First rankings appearing for long-tail clusters. Start blog/content.  
**Month 6–12:** Authority building, topical cluster expansion, state-level pages.

### Link Building Strategy
1. **HARO / Connectively** — respond as "prenup expert" to queries about marriage, finance, family law → earn editorial links from publications
2. **Guest posts** — personal finance blogs (The Balance, Investopedia style), wedding planning blogs (Brides, The Knot adjacent), divorce support communities
3. **Legal directories** — submit to Avvo, Justia, FindLaw as a resource
4. **Reddit** — genuinely helpful answers in r/legaladvice, r/personalfinance, r/weddingplanning (no spam — real value)
5. **Data PR** — "ClearTerms survey: 67% of couples don't know postnups exist" → pitch to national media

---

## PART 5: FORM & LEAD QUALIFICATION SYSTEM

### Form Logic (Progressive Disclosure)

**Step 1 — Minimal Barrier Fields:**
- First Name (required)
- Email (required)
- State (required — enables routing)

**Step 2 — Qualification Fields:**
- Situation type (engaged, married, second marriage, property, etc.)
- What to protect (property, business, retirement, debt, children)
- Wedding date / timeline
- Phone (optional — higher quality leads provide it voluntarily)
- Approximate asset range (shown as dropdown ranges, not exact amounts)

**Why this order:** Name + email + state is low commitment. Once someone types those, completion rate for remaining fields is over 70% (sunk cost psychology). Phone is optional because making it required drops form completion by ~30%, but those who provide it are higher intent.

### Lead Quality Scoring
| Signal | Weight |
|--------|--------|
| Phone provided | +20 pts |
| Wedding within 6 months | +15 pts |
| Has property or business | +10 pts |
| Second marriage | +10 pts |
| Asset range >$300K | +15 pts |
| State with high attorney density | +5 pts |

Score 60+ = premium lead (higher CPL). Score 40–59 = standard lead. Score <40 = nurture queue.

### Privacy Messaging
- "Your information is never sold."
- "We match you with licensed attorneys only."
- "Free service — attorneys pay us, not you."
- Attorney outreach governed by CAN-SPAM / state bar advertising rules — ClearTerms does not solicit on behalf of attorneys, it facilitates introduction only.

---

## PART 6: MONETIZATION STRATEGY

### Primary Model: Cost Per Lead (CPL)

**Pricing tiers:**
| Lead Quality | CPL (to attorney) | Volume Expectation |
|---|---|---|
| Premium (scored 60+) | $120–$180 USD | 20–30% of leads |
| Standard (scored 40–59) | $60–$100 USD | 50–60% of leads |
| Basic (scored <40) | $25–$40 USD | 20–30% of leads |
| Exclusive (single attorney only) | $200–$350 USD | On request |

**Blended CPL target:** ~$90 USD/lead  
**Conversion to paying client:** 15–25% (family law average)  
**Attorney LTV from one lead:** $2,000–$15,000 in fees → easy ROI for attorneys

### Revenue Projections

**Conservative (Year 1):**
- Organic traffic by month 12: 8,000–15,000/month
- Form conversion rate: 3–5%
- Leads/month by month 12: 240–750
- Blended CPL: $80
- Monthly revenue run rate by month 12: $19,200–$60,000
- Total Year 1: ~$80,000–$180,000

**Optimistic:**
- Traffic: 20,000–40,000/month
- Conversion: 5–7%
- Leads: 1,000–2,800/month
- Year 1 total: $250,000–$600,000

### Secondary Revenue Streams
1. **Affiliate — LegalZoom / RocketLawyer** — for users not ready for a full attorney, link to online prenup templates ($30–$70 CPA)
2. **Affiliate — Betterment / Personal Capital** — financial planning tools linked from "how much does a prenup cost" sections
3. **Sponsored placement** — attorneys pay a premium for featured placement in specific states (Year 2+)
4. **Subscription attorney network** — monthly SaaS fee for attorneys in exchange for guaranteed lead volume (Year 2+)

### Attorney Partner Structure
- ClearTerms signs referral agreements with attorneys in each state
- Attorneys agree to: 24–48h response time, transparent fee quotes, no pressure sales, ClearTerms quality standards
- ClearTerms earns CPL fee after attorney confirms initial consultation occurred
- Long-term: attorneys can log into a dashboard to manage their lead flow, pause when at capacity, and track conversion

### State-Based Routing Logic
1. User selects state in form
2. System checks available attorneys in that state
3. Routes to highest-rated / fastest-responding attorney first
4. If no attorney available: lead held in queue and attorney recruited actively (this flags underserved markets)
5. Fallback: online referral (LegalZoom affiliate) with disclosure

### Long-Term Defensibility
- **Data moat:** lead quality data, state-by-state conversion rates, attorney performance data → feeds better matching algorithm
- **SEO moat:** topical authority established over 12–24 months is hard to displace
- **Relationship moat:** attorney network with contracts, history, performance data
- **Brand moat:** "ClearTerms" becomes the trusted, neutral noun for prenup information

---

## PART 7: CONTENT STRATEGY — 12 MONTHS

### Topical Authority Map (Priority Order)

**Tier 1 — Core Money Pages (Already built):**
- Homepage ("what is a prenup")
- /prenup-attorney
- /postnuptial-agreement
- /prenup-for-house
- /prenup-second-marriage

**Tier 2 — Supporting Content (Months 1–4):**
- "How much does a prenup cost?" (answers cost questions, links to attorney page)
- "Prenup checklist: what to bring to your first attorney meeting"
- "Can a prenup be challenged? What makes one enforceable"
- "Prenup vs. postnup: which one do you need?"
- "Prenup laws by state: the complete guide"
- "What can and cannot be included in a prenup"
- "How long does it take to get a prenup?"
- "Do I need a prenup if I don't have assets?"

**Tier 3 — Long-Tail Expansion (Months 4–8):**
- "Prenup for business owners"
- "Prenup and student loans: protecting against your partner's debt"
- "Prenup for millennials: why younger couples are choosing them"
- "Halachic prenup: what it is and who needs one" (small but zero competition, 418% YoY)
- "Prenup for unmarried couples" (targeting growing LT keyword)
- "Ironclad prenup: what makes a prenup bulletproof"
- "Prenup and inheritance: protecting family assets"
- "What happens without a prenup? Your state's default rules"

**Tier 4 — State-Level Programmatic Pages (Months 6–12):**
- /prenup-attorney-california
- /prenup-attorney-texas
- /prenup-attorney-florida
- /prenup-attorney-new-york
- /prenup-attorney-[state] × 20 most populous states

These pages are templated but populated with state-specific law info:
- State law overview
- UPAA adoption status
- Notable case law
- Community property vs. common law
- Local attorney match form

### Update Cadence
- Core pages: reviewed and updated quarterly (law changes, fresh data)
- Blog: 2 new articles per month
- State pages: reviewed semi-annually

### Link Building Calendar
| Month | Activity |
|-------|----------|
| 1–2 | GSC setup, submit to legal directories, HARO outreach begins |
| 3–4 | First guest posts (personal finance + wedding blogs) |
| 5–6 | "Prenup laws by state" earns editorial citations, Reddit engagement |
| 7–9 | Data PR push ("ClearTerms Annual Prenup Report") |
| 10–12 | Podcast outreach (marriage, finance, legal podcasts for backlinks + traffic) |

---

## PART 8: TECHNICAL ROADMAP

### Tech Stack Decision
**Pure HTML/CSS/JS** for MVP. Rationale:
- Fastest possible Lighthouse score (95+)
- Zero framework overhead
- No SSR/SSG complexity
- Can be hosted on Netlify, Vercel, or Cloudflare Pages for free
- Any developer can maintain it
- Converts to Next.js/Astro later if needed

### Hosting
- **Cloudflare Pages** (free tier): CDN globally distributed, sub-100ms TTFB, free SSL, instant deploys
- Domain: register clearterms.com (~$12/year)

### Lighthouse Targets
| Metric | Target |
|--------|--------|
| Performance | 97+ |
| Accessibility | 98+ |
| Best Practices | 100 |
| SEO | 100 |

**Achieved by:** No render-blocking JS, font preconnects, `loading="lazy"` on any images, semantic HTML, alt text on all images, aria-labels on interactive elements, meta descriptions on all pages, canonical tags.

### Core Web Vitals
| Metric | Target | How |
|--------|--------|-----|
| LCP | <1.2s | Hero text is text (not image), fonts preloaded |
| CLS | 0 | All elements have defined dimensions |
| INP | <100ms | No heavy JS, debounced scroll handlers |
| FCP | <0.8s | Minimal CSS, no blocking scripts |

### Lead Capture Integration Options
1. **Week 1 (free):** Netlify Forms — forms work out of the box with zero backend
2. **Week 2 (scale):** Connect to HubSpot free CRM for lead tracking
3. **Month 2:** Build simple routing logic via Zapier (form → state detection → Slack/email to appropriate attorney)
4. **Month 6:** Custom lead routing dashboard

### Analytics Stack
- **Google Analytics 4** (free)
- **Google Search Console** (free — essential for SEO)
- **Microsoft Clarity** (free heatmaps + session recording)
- **Hotjar** (optional, Month 3+) for form completion analysis

### Conversion Tracking Setup
GA4 events to fire:
- `form_start` — user focuses first form field
- `form_complete` — form submitted successfully
- `cta_click` — any CTA button click
- `page_scroll_50`, `page_scroll_90` — engagement depth
- `faq_open` — FAQ item toggled open

---

## PART 9: FULL LAUNCH ROADMAP

### Week 1–2: Build & Launch
- [ ] Register clearterms.com
- [ ] Set up Cloudflare Pages hosting
- [ ] Deploy all 5 HTML pages
- [ ] Connect Netlify Forms or Cloudflare Forms for lead capture
- [ ] Set up GA4 + GSC
- [ ] Submit sitemap to Google
- [ ] Validate schema markup (schema.org validator)
- [ ] Test Lighthouse scores on all pages
- [ ] Set up email notification for every form submission

### Week 3–4: Monetization Setup
- [ ] Sign up for LegalZoom affiliate (Commission Junction / Impact)
- [ ] Sign up for RocketLawyer affiliate
- [ ] Add affiliate links to relevant content sections
- [ ] Recruit first 3–5 attorneys in highest-volume states (CA, TX, FL, NY, IL)
- [ ] Set CPL pricing and sign referral agreements

### Month 2: SEO Foundation
- [ ] Write and publish "How much does a prenup cost?" (highest commercial intent supporting article)
- [ ] Write and publish "What can a prenup not cover?" (FAQ intent, easy to rank)
- [ ] Begin HARO responses (3–5x/week targeting personal finance + legal journalists)
- [ ] Submit to 5 legal directories (Avvo, FindLaw, Justia, Nolo, NOLO directory)

### Month 3–4: Content Velocity
- [ ] Publish 2 articles/month on Tier 2 list
- [ ] Monitor GSC — identify which pages Google is indexing and what queries they're ranking for
- [ ] First A/B test: form headline variation on attorney page
- [ ] First attorney network expansion: target 15 states covered

### Month 5–6: Authority Push
- [ ] "Prenup laws by state" mega-guide published
- [ ] Begin state-level page builds (top 10 states)
- [ ] First data PR piece pitched to national outlets
- [ ] Evaluate traffic — if organic is growing, stay course; if flat, increase content cadence

### Month 7–9: Scale
- [ ] State pages live for top 20 states
- [ ] Programmatic SEO consideration: city-level pages if state pages are performing
- [ ] Attorney dashboard v1: simple portal for attorneys to see their leads
- [ ] Evaluate paid traffic (Google Ads on long-tail keywords as supplement)

### Month 10–12: Platform Maturation
- [ ] Annual "Prenup Trends Report" for PR links
- [ ] Podcast / media outreach (The Knot, WeddingWire, personal finance podcasts)
- [ ] Premium attorney listing product launched
- [ ] Year 1 review: SEO performance, revenue by channel, CPL optimization

---

## PART 10: RISK & MITIGATION

| Risk | Likelihood | Impact | Mitigation |
|------|-----------|--------|------------|
| Google algorithm update depresses rankings | Medium | High | Diversify to 3+ traffic sources; content quality focus |
| Attorney network slow to build | Medium | Medium | Affiliate revenue as fallback; partner with attorney aggregators |
| Legal/regulatory challenge to referral model | Low | High | Model is identical to Avvo, FindLaw, LegalZoom — well-established |
| Competitor builds similar site | Medium | Medium | First-mover advantage + content moat; brand recognition |
| Low form conversion rates | Low | Medium | Continuous CRO testing; progressive form logic |

---

## FINAL NOTE: WHY THIS WINS

The prenup space is a perfect keyword arbitrage: massive search volume (135,000/mo for the primary transactional keyword), competition index of 1, explosive YoY growth (508%), and monetization that is completely platform-independent. You can run this from Calgary. You never touch a legal document. The attorneys do all the work; you own the traffic.

The site is designed to win not just algorithmically but editorially. It treats users like intelligent adults, gives them real information, removes anxiety, and earns their trust before asking for anything. That's the formula for a high-converting, defensible media asset.

Build it fast. Publish it cleanly. Let the SEO compound.
