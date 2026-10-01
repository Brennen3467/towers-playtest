# Lane 09: Adjacent plays that reuse the local-SMB website pipeline

*Research date: 2026-10-01. This is desk research only: no outreach, signups or purchases. Every material claim has a URL. Anything marked **(est.)** is our own arithmetic or judgement, not a sourced figure.*

**Limits of this research**

- reddit.com was blocked for both search and fetch in this environment. Evidence on buyer pain and churn therefore comes from surveys, vendor filings and industry press instead of forums. Read every willingness-to-pay call with that in mind.
- Several prices come from third-party aggregators, because Birdeye, Podium, Yext, BentoBox, Technomic and others don't publish prices. Those prices are labeled as such.
- About 125 web searches were used across this lane.

---

## TL;DR

1. **Most "adjacent" plays are already saturated, and the brothers' advantage is not the product.** About 60,000 GoHighLevel (GHL) agencies resell the same bundle: missed-call text-back, AI receptionist, reviews, calendar and Google Business Profile (GBP) management. They charge about $97–$297/mo ([ghlexperts](https://www.ghlexperts.com/what-is-gohighlevel), [GHL pricing](https://www.gohighlevel.com/pricing)). The brothers' only defensible edge is **proof-first outreach**: showing a specific, verifiable defect from public data before asking for anything. Ideas that can't produce that proof lose that edge.
2. **Problems that public data *can* prove:**
   - AI-search invisibility (sampled through LLM APIs)
   - review gaps against the top 3 competitors in the map pack
   - incomplete GBP fields
   - a restaurant "Order" button that routes to DoorDash at 15–30% commission
   - dead booking links, expired SSL, and hours that don't match between GBP and the website
   - trucking insurance filings (FMCSA, free daily data)
   - estimated business value
3. **Problems public data *cannot* prove:** merchant-fee, utility, telecom/SaaS, payroll and small-business health-benefit overspend all need the prospect to upload a document. These are a poor fit for proof-first outreach.
4. **Strategic warning.** Owner.com raised $240M at a $2.3B valuation in August 2026, has $100M+ ARR, uses an outbound-led go-to-market, and says it is expanding from restaurants to "every local business" ([PRNewswire](https://www.prnewswire.com/news-releases/owner-raises-240m-led-by-goldman-sachs-alternatives-to-build-the-ai-native-platform-for-every-local-business-302862420.html)). That is the brothers' core model, run by a well-funded company. Adjacent recurring products that lift revenue per customer are a defensive necessity, not optional.
5. **Recommendation.** Ship a single **"Local Visibility Plan"** at $99–$199/mo, made of AI-search monitoring, GBP management, a review engine and schema. Lead with a stacked defect audit. As a separate experiment, test **FMCSA-driven trucking insurance renewal outreach** through a licensed agency partner. Kill the rest or keep them as proof lines inside emails.

---

## 1. Lane overview

### 1.1 Buyer universe

| Count | Figure | Source |
|---|---|---|
| US small businesses | 36.2M | [SBA Advocacy 2025](https://advocacy.sba.gov/2025/06/30/new-advocacy-report-shows-the-number-of-small-businesses-in-the-u-s-exceeds-36-million/) |
| Employer firms (2022) | 6.4M, about 89% with fewer than 20 employees | [SBE Council summarizing Census SUSB](https://sbecouncil.org/about-us/facts-and-data/), [Census SUSB 2022](https://www.census.gov/data/tables/2022/econ/susb/2022-susb-annual.html) |

Employer establishments by local vertical, parsed directly from Census County Business Patterns 2023 ([cbp23us.zip](https://www2.census.gov/programs-surveys/cbp/datasets/2023/cbp23us.zip)):

| Vertical (NAICS) | Establishments |
|---|---|
| Restaurants and other eating places (7225) | 618,476 (full-service 258,626; limited-service 270,088) |
| Physicians' offices (621111) | 204,617 |
| Auto repair and maintenance (8111) | 169,572 |
| Law offices (541110) | 165,491 |
| Personal care (8121) | 160,726 (beauty salons 84,176; nail salons 34,417) |
| Dentists (621210) | 135,665 |
| Landscaping (561730) | 117,969 |
| Plumbing / HVAC (238220) | 111,207 |
| Electricians (238210) | 83,342 |
| PT / OT / speech therapy (621340) | 52,058 |
| Fitness centers (713940) | 41,556 |
| Bars (722410) | 40,835 |
| Veterinary (541940) | 34,296 |
| Self-storage lessors (531130) | 18,564 (undercounts facilities that have no employees) |
| Med spas (no NAICS code) | ~11.5K forecast for 2025, 81% single-location ([AmSpa via Aesthetic Hires](https://www.aesthetichires.com/med-spa-industry-statistics/)) |

These verticals sum to roughly **2.0M employer establishments**. That is the realistic prospect universe for the existing pipeline **(est.)**.

### 1.2 What the agency market pays

- **Number of agencies.** IBISWorld counts about 114K US advertising agencies in 2026, growing about 6.7% a year ([IBISWorld](https://www.ibisworld.com/united-states/number-of-businesses/advertising-agencies/1433/)).
- **SEO retainers.**
  - The most common SEO retainer is $501–$1,000/mo (20.4% of 439 providers), and 68.8% charge ≤ $2,000/mo ([Ahrefs survey](https://ahrefs.com/blog/seo-pricing)).
  - BrightLocal's 2019 agency survey found average revenue of $1,779/mo per client and a median minimum retainer of $500–699 ([BrightLocal](https://www.brightlocal.com/research/local-search-industry-survey-2019/)).
  - Micro-SMBs (plumbers, salons) in practice buy productized tools at $49–$500/mo **(est., consistent with the vendor prices below)**.
- **GoHighLevel.**
  - Plans are $97 / $297 / $497. SaaS-mode white-labeling comes with the $497 tier. The "AI Employee" add-on costs $50–$97 per sub-account ([GHL pricing](https://www.gohighlevel.com/pricing)).
  - Reach is about 60K agencies and about 1.4M SMB sub-accounts (third-party: [ghlexperts](https://www.ghlexperts.com/what-is-gohighlevel), [builts.ai](https://builts.ai/blog/gohighlevel-review-small-business/)).
  - In practice, any commodity SMB marketing product can be cloned and white-labeled within a week.

### 1.3 Incumbents by category

| Category | Incumbents and price anchors |
|---|---|
| GBP / listings | Merchynt/Paige $99/profile ([pricing](https://www.merchynt.com/pricing)); BrightLocal $39–59 ([checkthat](https://checkthat.ai/brands/brightlocal/pricing)); Synup from $49; Localo from $69; Yext (quote only) |
| Reviews | Podium $399–$599/mo on annual contracts, about $220–321M ARR (est. by [Latka](https://getlatka.com/companies/podium) / [Sacra](https://sacra.com/c/podium/); pricing via [socialpilot](https://www.socialpilot.co/reviews/blogs/podium-pricing)); Birdeye about $299–449/location ([costbench](https://costbench.com/software/review-management/birdeye/)); NiceJob $75/$125 ([NiceJob](https://get.nicejob.com/pricing)) |
| AI phone | Smith.ai AI tier from about $97.50; Rosie $49–$299; Goodcall about $59–79 ([aggregator](https://www.getaira.io/blog/ai-receptionist-pricing-guide), [workflowstackai](https://workflowstackai.com/blog/ai-receptionist-comparison-2026)); GHL Voice AI |
| AI-search visibility | Profound ($1B valuation, enterprise) ([Profound](https://www.tryprofound.com/blog/profound-raises-96m-series-c)); Otterly $29–$489 ([aeolabs](https://www.aeolabs.ai/blog/otterly-ai-review)); Peec about €85+; Semrush AI toolkit $99 ([eesel](https://www.eesel.ai/blog/semrush-seo-pricing)); BrightLocal Local AI Visibility ([PRNewswire](https://www.prnewswire.com/news-releases/brightlocal-launches-ai-insights-to-help-businesses-navigate-increasingly-complex-local-search-302736885.html)); Yext Scout |
| Restaurant ordering | Owner.com $249/mo + 5% or $499/mo flat ([pricing](https://www.owner.com/pricing)); Toast online ordering about $75 add-on across about 164K locations ([Toast FY25](https://www.businesswire.com/news/home/20260212058106/en/Toast-Announces-Fourth-Quarter-and-Full-Year-2025-Financial-Results)); ChowNow $249–$449; Popmenu $179–$499; free tiers (Square Online, Menufy, GloriaFood) ([getsauce](https://www.getsauce.com/post/chownow-pricing-and-fees)) |
| Accessibility | AudioEye FY25 revenue $40.3M ([SEC 8-K ex.99](https://www.sec.gov/Archives/edgar/data/1362190/000110465926024106/aeye-20260305xex99d1.htm)); accessiBe $490–$3,990/yr, fined $1M by the FTC in 2025 ([FTC](https://www.ftc.gov/news-events/news/press-releases/2025/01/ftc-order-requires-online-marketer-pay-1-million-deceptive-claims-its-ai-product-could-make-websites)) |
| Merchant statement analysis | NMI Fee Navigator ([NMI](https://www.nmi.com/products/merchant-central/fee-navigator/)); ISO Amp ([site](https://getisoamp.com/)); FeeQuery ([site](https://feequery.net/)); Merchant Statement Analysis $24.95/quote ([pricing](https://www.merchant-statement-analysis.com/pricing)) |

### 1.4 Where the gaps are

1. **Proof-first outreach at scale.** GHL clones send generic "never miss a call" funnels. A Google search for "AI receptionist / missed call text back" returns mostly cloned app.gohighlevel.com preview pages. An email that names the prospect's specific defect differentiates on credibility, not on product.
2. **AI-search visibility for the local long tail.** Funded vendors (Profound, Peec, Otterly) price per prompt for brands. BrightLocal and Yext are only now adding local AI tracking. The **window lasts 12–18 months before this becomes a checkbox feature (est.)**.
3. **Data combinations in licensed niches.** Examples are FMCSA insurance filings, and Form 5500 combined with website and contact data. The data is free, but licensing keeps the GHL crowd out. The cost is that the brothers would need a license or a licensed partner.
4. **Gaps that are *not* real.** Merchant fees, AI phone, direct ordering, booking software and ADA all have either a dominant funded player or a free floor.

---

## 2. Candidate ideas

### Idea 1: "AI + Maps Visibility Plan" (lead offer)

**Pitch.** A free personalized snapshot shows whether ChatGPT, Gemini and Google AI recommend you, compared with the competitors who do get recommended. That leads into a $99–$199/mo plan that fixes the underlying signals (GBP, reviews, schema, citations) and reports monthly.

**Data sources**

| Source | Access | Cost | Limits |
|---|---|---|---|
| Google Places API (New): rating, review count, categories, hours, website | API key | Place Details Pro $17/1K, Enterprise $20/1K, Text Search Pro $32/1K, with small free caps ([Google pricing](https://developers.google.com/maps/billing-and-pricing/pricing)) | Maps Platform terms §3.2.3: no scraping and limited caching ([terms](https://cloud.google.com/maps-platform/terms)). So the snapshot must be generated and sent, not used to build a permanent stored database. |
| LLM APIs with web search, used to sample prompts like "best emergency plumber in Dayton" N times | API | cents per query **(est., not verified)** | Must use the API. OpenAI's terms bar programmatic extraction from the consumer product outside the API ([summary](https://ospo.co/blog/be-careful-with-openais-terms-of-use/)). Do not scrape Google AI Overviews: Google sued SerpApi in December 2025 under the DMCA ([ppc.land](https://ppc.land/google-sues-serpapi-over-search-scraping-in-copyright-lawsuit/)). |
| Prospect website crawl (schema, NAP, FAQ) | Headless browser | ~$0 | Respect robots.txt |
| GBP API, after the client authorizes | OAuth | Free but quota-gated | **Lead generation via the API is explicitly prohibited.** Automated edits or replies need explicit consent, the client must be notified of changes within 48h, and caching is limited to 30 days ([GBP API policies](https://developers.google.com/my-business/content/policies), [prereqs](https://developers.google.com/my-business/content/prereqs)) |

**Data combination that creates value.** It joins three signals: LLM answer sampling (whether you are mentioned and who is), Places structured data (your review count and fields against the cited competitors), and a site schema check. The result is a causal story, "you're invisible because X, Y, Z," rather than a vanity screenshot. No single incumbent sells this to a $500K-revenue plumber with outbound proof.

**Buyer.** An owner-operator of a service business with 1–20 employees (HVAC, plumbing, dental, med spa, law, auto repair) that already spends something on marketing. The decision-maker is the owner or office manager.

**Willingness to pay**

- Adjacent prices are proven: Paige $99/profile, BrightLocal $39–59, Semrush AI toolkit $99, Otterly $29–$489 (sources above).
- Consumer demand is real. In BrightLocal's 2026 survey (n=1,002), 45% of US consumers had used AI tools for local recommendations, up from 6% the prior year. But 97% cross-check against reviews ([BrightLocal](https://www.brightlocal.com/research/lcrs-ai-trust/)).
- **SMB willingness to pay specifically for AI visibility is unproven.** Most claims ("ChatGPT recommends 1.2% of local businesses") are vendor marketing ([thestacc](https://thestacc.com/blog/local-business-chatgpt-recommendation/)).
- The manual labor this replaces is the local SEO account manager on a $500–$1,000/mo retainer ([Ahrefs](https://ahrefs.com/blog/seo-pricing)).

**Market size**

- Bottom-up: about 2.0M employer establishments in target verticals (CBP, above).
- Assume 25% already spend on marketing and are reachable by email **(est.)**, giving about 500K.
- At $149/mo that is about **$900M/yr serviceable (est.)**.
- A 2,000-client book equals about $3.6M ARR **(est.)**.

**Deliverable and pricing.**

- Free one-page snapshot that serves as the proof.
- Paid plan at $149/mo **(est. price point)**:
  - monthly AI and map-pack visibility report
  - GBP posts, Q&A, categories and photos
  - review engine (Idea 2)
  - LocalBusiness/FAQ schema on the site
  - quarterly citation cleanup
- Recurring, month-to-month.

**Automation pipeline**

1. *Find prospects.* Places Text Search by vertical and city, plus a site crawl, then filter for businesses absent from LLM answers while competitors are present.
2. *Build the deliverable.* Sample 5 prompts × 3 runs × 2 models. Render a PDF or landing page showing quoted LLM answers, the competitor review gap and missing schema.
3. *Personalized outreach.* Email with the screenshot and one specific fix.
4. *Handle replies.* Claude agent answers questions and books a call or sends a checkout link.
5. *Deliver and renew.* GBP OAuth onboarding, automated posting and schema injection, monthly re-sample and report, with churn-risk alerts when visibility drops.

**Automatable: about 80% (est.).** Human touchpoints that remain:

- GBP access and verification problems
- suspended profiles
- disputed categories
- occasional sales calls
- QA on LLM answers before sending, because a hallucinated "competitor" would be embarrassing

**GTM, first 90 days**

- **Weeks 1–3:** build the snapshot generator on 3 verticals (HVAC, dental, med spa) in 5 metros. Hand-QA 200 snapshots.
- **Weeks 4–8:** send 5K emails and measure reply and close rates. Also offer the plan to existing website customers, which is the fastest first dollar.
- **Weeks 9–13:** keep the best vertical, add a review engine to the plan, and price-test $99 against $199.
- Target: 50 paying clients by day 90 **(est.)**.

**Unit economics (est.)**

| Item | Value |
|---|---|
| Data per prospect | Places ~$0.05 + LLM sampling ~$0.20–$0.50 + crawl ~$0.01, so about $0.50 |
| Per 1,000 prospects | ~$500 data + ~$50 email infrastructure |
| Close rate | at 0.5–1%, 5–10 clients per 1,000 prospects |
| CAC | ~$60–$120 (excluding founder time) |
| Price | $149/mo |
| COGS | ~$15–$25/mo (LLM monitoring, review SMS, support), so gross margin ~85% |
| Churn | 5%/mo, giving LTV ≈ $2,500 and LTV:CAC > 20 on paper |

The main uncertainty is churn: the value is hard to see once the novelty wears off.

**Competitors and crowding.** Crowded and rising. BrightLocal, Semrush, Yext, Birdeye and a wave of "AI SEO for plumbers" shops (e.g. [LocalVitals](https://getlocalvitals.com/plumbers)) are all entering. **Not blue ocean.** The edge is proof-first outreach plus the existing site relationship.

**Legal**

- **CAN-SPAM:** truthful header and subject, physical address, opt-out.
- **FTC deception standard:** never promise "guaranteed ChatGPT ranking." The accessiBe order shows the FTC acts against unsubstantiated AI-outcome claims ([FTC](https://www.ftc.gov/news-events/news/press-releases/2025/01/ftc-order-requires-online-marketer-pay-1-million-deceptive-claims-its-ai-product-could-make-websites)).
- **GBP API rules:** obtain consent for automated edits.
- **Platform terms:** use LLM APIs, never consumer-UI scraping.
- **GDPR:** only relevant if expanding to the EU/UK.

**Kill risks**

1. AI visibility becomes a free feature inside GBP, BrightLocal or GHL within about 12 months.
2. LLM answers are non-deterministic. Prospects or clients see different answers on their own phone, which undermines both the proof and retention.
3. SMBs pay for leads, not visibility. Without attributable calls, churn stays above 6%/mo.

---

### Idea 2: Review engine (attach product, also sold standalone)

**Pitch.** "You have 38 reviews; the three businesses above you on Maps average 212. We'll close the gap compliantly." The product requests a review from every customer after each job and drafts owner replies with an LLM.

**Data sources**

- Places API for rating, review count and up to 5 reviews ([Google pricing](https://developers.google.com/maps/billing-and-pricing/pricing)).
- Computing reply rate and recency needs a full review history, which means scraping Google (ToS-grey). Avoid that. Use count, rating and the most-recent dates from the API.
- Client side: job or customer list via CSV, or integrations with Jobber, Housecall Pro or Square.

**Data combination.** Your review velocity compared with the top 3 in the map pack, combined with the percentage of reviews that have an owner reply. The ask is quantified: "you need about 14 reviews/mo for 12 months to reach parity."

**Buyer.** Service SMBs with repeat or high-volume customers: dental, auto repair, HVAC, med spa, salons.

**Willingness to pay**

- Podium sells at $399–$599/mo on annual contracts, with real cost often $500–$800 ([socialpilot](https://www.socialpilot.co/reviews/blogs/podium-pricing)), and has about $220–321M ARR (estimates: [Latka](https://getlatka.com/companies/podium), [Sacra](https://sacra.com/c/podium/)).
- Birdeye charges about $299–449 per location ([costbench](https://costbench.com/software/review-management/birdeye/)); NiceJob $75–$125 ([NiceJob](https://get.nicejob.com/pricing)).
- The fact that SMBs pay $400+/mo to Podium is the strongest willingness-to-pay evidence in this lane.

**Market size**

- Same ~2.0M establishments as Idea 1.
- Podium's ~$250M ARR alone implies at least 40K paying locations **(est. at ~$500/mo)**.
- Serviceable at $79–$149/mo: about **$500M–$900M (est.)**.

**Deliverable and pricing.** A $79/mo standalone review engine, or bundled into the $149 plan. It includes the request flow, an SMS/email sender, a reply drafter and a monthly report.

**Automation pipeline**

1. Find prospects: Places review-gap filter.
2. Build the deliverable: gap chart plus "reviews needed per month" math.
3. Outreach: email.
4. Replies: AI agent.
5. Deliver: CSV or integration import, automated requests after each job, LLM drafts replies for approval (auto-post only with explicit consent, per GBP policy), monthly report, renew.

**Automatable: about 75%.** Human work remains in onboarding the customer-data feed and in A2P 10DLC registration delays.

**GTM.** Attach to every website customer at launch, then cold outreach in two verticals with the highest review sensitivity (dental, auto repair).

**Unit economics (est.)**

- Price $79.
- COGS:
  - A2P 10DLC brand and campaign fees ($4 brand + $15 vetting + $2/mo for sole-prop on [Twilio](https://support.twilio.com/hc/en-us/articles/9550596959643-A2P-10DLC-Sole-Proprietor-Brands-FAQ))
  - SMS ~$0.01 each × ~200/mo
  - LLM ~$1
  - support
  - Total about $8–12/mo, so gross margin ~85%.
- CAC ~$80–150.

**Competitors.** Very crowded: Podium, Birdeye, NiceJob, Grade.us, and GHL's built-in reputation module. The edge is price under Podium plus proof-first outreach.

**Legal**

- **FTC fake-reviews rule** (effective October 2024): no fake or AI-written reviews, no buying reviews, no suppressing negatives. Up to $51,744 per violation ([FTC](https://www.ftc.gov/news-events/news/press-releases/2024/08/federal-trade-commission-announces-final-rule-banning-fake-reviews-testimonials)).
- **Google bans review gating**, i.e. routing only happy customers to Google ([Sterling Sky](https://www.sterlingsky.ca/review-gating-is-now-against-the-google-my-business-guidelines/)). The product must ask everyone.
- **TCPA:** review-request SMS to consumers needs consent obtained by the business and opt-out handling.
- **10DLC registration** required.

**Kill risks**

1. Commoditized: NiceJob at $75 and GHL bundles cap the price.
2. Onboarding the customer list is real friction. Many owners never upload, so no reviews get generated, and the client churns.
3. A compliance error (gating, incentivized reviews) by a client exposes the brothers' brand.

---

### Idea 3: Restaurant "commission-leak" site + direct ordering (vertical variant of the core pipeline)

**Pitch.** "Your Order button sends customers to DoorDash at 25–30%. Here's your new site with commission-free ordering." The offer is the existing free site plus an ordering layer, sold as a recurring plan.

**Data sources**

- Crawl the restaurant's own website and classify where its Order and Menu links go: doordash.com, ubereats.com, grubhub.com and slicelife.com, versus toasttab.com, chownow.com, owner.com, or no link at all. This is free and low-risk.
- Places API booleans for delivery, takeout and website (Enterprise + Atmosphere tier ~$25/1K) ([field docs](https://developers.google.com/maps/documentation/places/web-service/data-fields)). The API does **not** expose which provider sits behind GBP's Order button, and scraping Maps for it breaches Maps terms §3.2.3 ([terms](https://cloud.google.com/maps-platform/terms)).
- DoorDash menu price markups: check manually only. DoorDash terms prohibit scraping.

**Data combination.** Join the website link-target classification with DoorDash's published commission tiers (15/25/30%) ([DoorDash](https://merchants.doordash.com/en-us/pricing)) and a seat-count or review-volume proxy for order volume. That produces a dollar estimate of the commission leak in the outreach email.

**Buyer.** Independent full-service and limited-service restaurant owners with 1–3 locations that are not on Toast. Toast users can switch on online ordering for about $75.

**Willingness to pay**

- Owner.com:
  - pricing $249 + 5% or $499 flat ([pricing](https://www.owner.com/pricing))
  - ARR went from $16M (2023) to $100M+ (2026) ([Contrary](https://research.contrary.com/company/owner), [PRNewswire](https://www.prnewswire.com/news-releases/owner-raises-240m-led-by-goldman-sachs-alternatives-to-build-the-ai-native-platform-for-every-local-business-302862420.html))
  - about 79% of new ARR came from outbound at a $5.5K ACV ([outbound.kitchen](https://newsletter.outbound.kitchen/p/ownercom-founder-led-to-30m-outbound))
- ChowNow $249–$449; Popmenu $179–$499 ([getsauce](https://www.getsauce.com/post/chownow-pricing-and-fees), [orderitto](https://orderitto.com/compare/popmenu-pricing)).
- Willingness to pay is proven beyond doubt. The question is whether a newcomer can win share.

**Market size**

- 618,476 restaurant establishments (CBP 2023).
- Minus Toast's ~164K locations and chains: about 300K independents **(est.)**.
- At $149/mo, about **$540M serviceable (est.)**.

**Deliverable and pricing.**

- Free site that already embeds a commission-free ordering option. To avoid building payments, use Square Online ($0/mo, 3.3%+30¢ on the free plan) ([getsauce](https://www.getsauce.com/post/square-online-ordering-pricing-fees)) or Menufy.
- $99–$149/mo for hosting, menu updates, GBP "Order" link correction and monthly commission-savings reporting **(est. pricing)**.

**Automation pipeline**

1. Find prospects: CBP and Places restaurant lists, then crawl and classify link targets.
2. Build the deliverable: auto-build the menu site from the PDF or website menu (LLM extraction) with the ordering embed.
3. Outreach: email with the leak estimate.
4. Replies: AI agent.
5. Deliver and renew:
   - The client connects Square.
   - Ask the owner to remove the third-party Order link in GBP. Google's own help page documents this, and the provider has 5 business days to comply ([Google help](https://support.google.com/business/answer/10842217?hl=en)).
   - Monthly report.

**Automatable: about 65%.** Payments onboarding, menu-change requests and delivery dispatch questions need people.

**GTM.** A subset of the existing pipeline. Target independents in 3 metros whose site links only to marketplaces. Ninety-day goal: 30 paying clients **(est.)**.

**Unit economics (est.)**

- Price $129.
- COGS ~$15 (hosting, menu updates via LLM, support), so gross margin ~85%.
- CAC ~$150–300, because restaurants are heavily pitched.
- Churn is high, as restaurant closure rates are high: assume 4–6%/mo.

**Competitors.** **Extremely crowded**: Owner (outbound and well-funded), Toast, ChowNow, Popmenu, BentoBox/Fiserv, free tools, plus GHL restaurant snapshots ([ghlautomations](https://ghlautomations.com/restaurant-snapshot)).

**Legal**

- CAN-SPAM.
- Don't scrape Maps or DoorDash.
- The savings estimate must be labeled as an estimate (FTC deception standard).
- ADA exposure for restaurant sites is real: 21% of 2025 digital ADA suits hit food service ([UsableNet](https://info.usablenet.com/hubfs/Remediated%20-%202025_Year-End_Digital_Accessibility_Lawsuit_Report_FINAL.pdf)). Build WCAG-clean sites.

**Kill risks**

1. Owner.com outspends and out-executes on the identical pitch.
2. Restaurants on Toast or Clover don't need it, and the remaining pool is the most price-sensitive and highest-churn.
3. Without your own payments stack you capture no transaction revenue, which is a structural margin disadvantage compared with Owner's 5% fee.

---

### Idea 4: Trucking insurance renewal intelligence (FMCSA data combination; licensed-partner model)

**Pitch.** "Your BMC-91 liability filing with Insurer X became effective 14 Nov 2025, so your renewal is in about 45 days. Here's a benchmark and a quote." This is sold through, or as, a licensed P&C agency.

**Data sources**

- **FMCSA ActPendInsur**: a free daily-difference file plus "All With History." Fields include insurer name, effective, posted and cancel-effective dates, BI&PD limits, and DOT and docket numbers. It covers BMC-91 (liability), BMC-34 (cargo) and BMC-82 (bond) ([data.transportation.gov](https://data.transportation.gov/Trucking-and-Motorcoaches/ActPendInsur/chgs-tx6x), [All With History](https://data.transportation.gov/Trucking-and-Motorcoaches/ActPendInsur-All-With-History/y77m-3nfx)). It is US government open data with no licensing restriction found.
- Insurers must give FMCSA 30 days' notice of cancellation (49 CFR 387.313), so pending cancellations show up in near-real time ([XDate Alert](https://xdatealert.com/data/trucking-insurance-cancellation-trends)).
- Combine with the FMCSA census and SMS data (power units, drivers, inspections, out-of-service rates) and the carrier's website quality from the existing crawler.
- **Not usable for automation:** the California WCIRB coverage lookup. Its terms allow only "manually conducted, discrete, individual" searches ([WCIRB terms](https://www.caworkcompcoverage.com/Privacy)). The NY WCB lookup is limited to verification use ([NY WCB](https://www.wcb.ny.gov/icpocinq/)).

**Data combination.** Join the insurer and filing date (giving an inferred renewal window) with fleet size, safety scores (a risk proxy for underwriting appetite) and pending cancellations (urgent need). The result is a renewal-timed, risk-scored prospect with specific proof. Note that the renewal date is *inferred* from the anniversary of the effective date, because BMC-91 filings are continuous ([ActPendInsur docs](https://data.transportation.gov/Trucking-and-Motorcoaches/ActPendInsur/chgs-tx6x)).

**Buyer.** Owner-operators and small fleets with 1–20 power units. The money buyer is either (a) the carrier, through a licensed agency, or (b) independent P&C agencies specializing in trucking, which buy leads or tech.

**Willingness to pay**

- Commercial commissions are about 10–15% for general liability and about 5–12% for workers' comp, typically renewing ([InSifter](https://insifter.com/commission-benchmarks.html), [Sonant](https://www.sonant.ai/blog/insurance-agent-commission-structure)).
- Trucking premiums are large: often five figures per power unit **(est., unverified)**.
- Lead vendors already sell X-date feeds ([Nexpro](https://www.thenexpro.com/trucking-transportation-insurance-leads), [Apify FMCSA feed](https://apify.com/jobito/fmcsa-new-authority-feed)). Agencies demonstrably pay for this data.

**Market size**

- The count of active interstate carriers is several hundred thousand, the majority with fewer than 10 trucks **(est., needs verification against the FMCSA census file)**.
- At about $1,500/yr average commission per small carrier **(est.)**, a 1,000-carrier book is about $1.5M/yr in renewing commission.

**Deliverable and pricing.**

- *Option A (license):* get a P&C producer license, which takes weeks, and appoint with trucking markets or a wholesaler. Revenue is commission, renewing annually.
- *Option B (no license):* sell a "renewal radar" SaaS or lead feed to trucking agencies at $299–$999/mo **(est.)**. Unlicensed referral fees must be flat and not contingent on a sale, and some states cap them (NC $50) ([Insurance Journal](https://www.insurancejournal.com/magazines/mag-features/2024/02/19/761025.htm), [NCDOI](https://www.ncdoi.gov/documents/agent-services/referral-fees-faqs/open)). The SaaS model avoids that limit.

**Automation pipeline**

1. Find prospects: daily ActPendInsur diff, then compute renewal windows, then join census and SMS data.
2. Build the deliverable: a per-carrier "renewal brief" (current insurer, filing age, safety percentile, peers' typical insurers).
3. Outreach: email, from a licensed agency's domain for Option A, or to agencies for Option B.
4. Replies: AI triage that collects the quote application data (loss runs, VINs, drivers). **The human licensed producer quotes and binds.**
5. Renewal: the next year's window triggers automatically.

**Automatable: about 60% (Option A) or about 85% (Option B).** Quoting, underwriting submissions and binding need licensed humans.

**GTM, 90 days.** Build the data pipeline in weeks 1–2. Interview 10 trucking agencies (Option B validation) in weeks 3–6. Then sign one agency revenue-share or SaaS pilot. In parallel, one brother obtains a P&C license.

**Unit economics (est.)**

| Item | Option B (SaaS) | Option A (commission) |
|---|---|---|
| Data cost | ~$0 | ~$0 |
| Infrastructure | ~$100/mo | ~$100/mo |
| Price / revenue | $499/mo per agency | ~$1–3K first-year commission per bound small fleet (est.) |
| CAC | ~$500–$1,500 (agencies are few and reachable) | — |
| Gross margin | ~90% | — |
| Conversion | — | ~2–4% of renewal-window prospects quote; ~25% of quotes bind (est.) |

**Competitors.** Moderate. XDate Alert, Nexpro, multiple Apify actors, and large lead vendors already mine FMCSA data. New-authority carriers in particular are flooded with calls. Renewal-window plus risk-scored data combined with personalized proof is less common, but **not blue ocean**.

**Legal**

- State P&C producer licensing (Option A).
- Referral-fee rules (Option B must stay a non-contingent SaaS fee).
- TCPA: email only. No AI voice calls to carriers' cell phones, which the FCC's February 2024 ruling treats as artificial-voice calls ([FCC](https://docs.fcc.gov/public/attachments/DOC-400393A1.pdf)).
- CAN-SPAM.
- FMCSA data is public, but many carriers are sole proprietors, so treat it as personal data under state privacy laws such as CCPA. Offer opt-out.

**Kill risks**

1. The lead pool is over-solicited and carriers ignore yet another insurance email.
2. The inferred renewal date is wrong often enough to damage credibility.
3. The licensing and appointment path (markets often won't appoint new small agencies) delays the first dollar past 90 days.

---

### Idea 5: Merchant-processing bolt-on (agent residuals with a statement-upload hook)

**Pitch.** "Restaurants your size on flat-rate processing typically overpay $X/mo. Upload a statement for a 60-second exact analysis." Revenue comes from residuals under an ISO agent agreement.

**Data sources**

- Website and BuiltWith/Wappalyzer detection of processor or POS (Square, Stripe, Toast, Clover). Coverage is mostly e-commerce ([BuiltWith](https://trends.builtwith.com/payment/payments-processor)).
- Revenue proxies from reviews and seat counts **(est.)**.
- No public data reveals the effective rate. **Proof requires the statement.**
- White-label statement readers already exist: FeeQuery, ISO Amp, NMI Fee Navigator, and Merchant Statement Analysis at $24.95/quote.

**Data combination.** Join detected processor type with an estimated volume and the published flat rate. That produces a *modeled* overpayment, which is a teaser rather than proof. The effective rate of a typical small business is 2.5–3.5%, against 1.7–2.2% for a well-priced interchange-plus account ([FeeQuery](https://feequery.net/)).

**Buyer.** Owners of non-Toast restaurants, retail shops, salons and auto shops processing $20K–$150K/mo.

**Willingness to pay (the economics)**

| Item | Figure | Source |
|---|---|---|
| Average residual per merchant | ~$30/mo | [CCSalesPro](https://www.ccsalespro.com/blog/much-commission-can-make-selling-merchant-services) |
| Upfront per sale | $275–$325 | same |
| Agent residual split | 50–70% | [Unison](https://www.unisonpayment.com/blog/merchant-services-agent-program-residual-income) |
| Signature Card split | 80/20 | [Newswire](https://newswire.com/signature-card-services-celebrates/201150) |
| North/NAB terms | 50–65% plus $200 activation | [Shaw](https://www.shawmerchantgroup.com/north_american_bancard_agent_program) |
| SMB account attrition | 24.6%/yr | [TSG 2014](https://tsgpayments.com/wp-content/uploads/2017/09/MWAA-Presentation-on-Merchant-Retention-Kurt-Strawhecker-July2014.pdf) |
| SMB accounts lost YoY in 2020 | 28.2% | [TSG](https://webview.thestrawgroup.com/hubfs/TSG%20Big%20Data%20-%20Growth%20&%20Attrition%20of%20SMB%20Merchants%20in%20the%20US.pdf) |
| Portfolio buyout multiples | 2–3× for small books up to ~40× for large, low-attrition books | [CCSalesPro](https://www.ccsalespro.com/blog/understanding-the-value-of-your-merchant-residual-portfolio), [733 Park](https://www.733park.com/guides/merchant-portfolio-valuation/) (sell-side) |
| Manual human equivalent: merchant services sales rep pay | ~$83.7K | [Indeed](https://www.indeed.com/cmp/Merchant-Services-7/salaries/Sales-Representative) |

**Lifetime value per merchant ≈ $30 × 12 ÷ 0.25 + ~$250 upfront ≈ $1,700 (est.).**

**Market size.**

- Millions of card-accepting SMBs in principle.
- But software-bundled payments are taking share: Toast has about 164K locations ([10-K](https://www.sec.gov/Archives/edgar/data/1650164/000165016426000057/tost-20251231.htm)), and Clover holds about 20% of small-restaurant processing ([Payments Dive](https://www.paymentsdive.com/news/toast-clover-battle-for-small-eateries/809108/)).
- Only about 25% of merchants sign up through ISOs ([Clearly Payments](https://www.clearlypayments.com/blog/the-payments-ecosystem-in-2025-processors-acquirers-isos-fraud-solutions-merchant-services/)).
- The switchable pool is far smaller than the headline count.

**Deliverable and pricing.** Free statement analysis. Revenue is about $30/mo per merchant in residuals plus upfront bonuses. The SMB pays the processor, not the brothers.

**Automation pipeline**

1. Find prospects: processor detection.
2. Build the deliverable: modeled teaser.
3. Outreach: email.
4. Replies: AI asks for the statement; the white-label reader produces a proposal.
5. Deliver: e-sign merchant application, ISO underwriting, terminal shipping or reprogramming.
6. Renew: residuals accrue automatically.

**Automatable: about 60%.** Underwriting back-and-forth, equipment and installation, and PCI questions remain. Statement upload conversion is the bottleneck.

**GTM.** Sign an 80/20 agent agreement and a white-label upload widget. Add a "processing check" CTA to every website customer and every restaurant email (Idea 3). Do no dedicated cold campaign until the upload rate is measured.

**Unit economics (est.)**

- CAC: assume a 0.2% prospect→merchant rate at ~$0.10/prospect, about $50 in data per merchant plus labor.
- Lifetime value ~$1,700.
- Gross margin ~100% of residual, minus about $25/analysis.
- Time to first residual about 45–60 days.

**Competitors.** **Maximally saturated.** High-volume ISOs still cold-call 700–1,000 deals a month ([CCSalesPro](https://www.ccsalespro.com/blog/does-cold-calling-still-work-selling-merchant-services)), and every ISO already has an AI statement reader.

**Legal**

- As a sub-agent, no card-brand registration is needed. Becoming a registered ISO needs a sponsor bank, ~$5K/yr Visa registration and ~$100K liquidity ([Akurateco](https://akurateco.com/blog/how-to-become-a-registered-iso-msp)).
- Surcharging rules: Visa 3% cap, banned in CT, ME, MA and CA; dual-pricing pitches are risky ([Corepay](https://corepay.net/articles/credit-card-surcharge-laws-state-by-state/)).
- The pending Visa/Mastercard settlement (preliminary approval June 2026) would cap standard consumer credit interchange at about 1.25% ([America's Credit Unions](https://www.americascreditunions.org/news-media/news/court-grants-preliminary-approval-interchange-lawsuit-settlement)). That compresses the savings story.
- TCPA: no AI cold calls.

**Kill risks**

1. No public proof means it is just another "lower rates" email, and conversion stays tiny.
2. Software-bundled POS (Toast, Square, Clover) locks out switching.
3. About 25% annual attrition plus clawbacks keep the book small. At 25 merchants/mo the year-1 residual is only about $9K/mo **(est.)**.

---

### Idea 6: Free "What's your business worth?" valuation (lead-gen feed into the M&A lane)

**Pitch.** A personalized estimated value range for owners aged 55+ in valuation-friendly verticals. Owners who show interest are sold as qualified leads, or referred to brokers and search-fund buyers.

**Data sources**

- **Medians:** BizBuySell published medians: sale price $350K, SDE $158,950, revenue $703K, 170 days to close ([BizBuySell Q4 2025](https://www.bizbuysell.com/news/bizbuysell-2025-fourth-quarter-insight-report/)); about 2.65× SDE in 2026 ([Sundance](https://sundancefg.com/resources/bizbuysell-q2-2026-insight-report)).
- **Business facts:**
  - Secretary of State filings for business age
  - Places API for review volume, a revenue proxy
  - CBP payroll per establishment by county and NAICS (free)
  - website signals
- **Owner age:** proxies are weak. Business age plus LinkedIn tenure is ToS-grey; avoid scraping LinkedIn.

**Data combination.** Industry multiples combined with a revenue estimate (from reviews, payroll per establishment and business age) produce a personalized value range. This is a modeled figure, not proof.

**Buyer.**

- Owner (free deliverable): retirement-age owners of HVAC, plumbing, dental-lab, landscaping and auto-repair firms.
- Payers: business brokers, M&A advisors, search funders and PE roll-ups.

**Willingness to pay.**

- Brokers earn about 10% commission with a $10–15K minimum ([MidStreet](https://www.midstreet.com/blog/business-broker-fees-when-selling-a-business)), so a median deal grosses about $35K.
- ValuSource costs $135–$465/mo ([ValuSource](https://www.valusource.com/pricing/)).
- BizEquity sells valuation widgets to advisors as lead generation ([SourceForge](https://sourceforge.net/software/business-valuation/)).

**Market size.**

- About 2.9M employer businesses have owners over 55 (Project Equity citing Census ABS; [summary](https://ctacquisitions.com/guides/boomer-business-succession-wave-report-2024-2030/), [Census ABS](https://www.census.gov/newsroom/press-releases/2025/business-owner-characteristics.html)).
- Only about 10K deals a year close through BizBuySell's reporting brokers.

**Deliverable and pricing.**

- Free report.
- Monetization options:
  - Qualified seller leads sold to brokers at $250–$1,000 each **(est.)**
  - A referral share of commission, 10–25% **(est.)**
  - A $300–$1,000/mo exclusive-territory subscription per broker, which gives a recurring element **(est.)**

**Automation pipeline**

1. Find prospects: CBP and Places by vertical, then filter by business age.
2. Build the deliverable: valuation estimate PDF.
3. Outreach: email.
4. Replies: AI qualifies (revenue, timeline, motivation).
5. Deliver: route to a broker partner and track outcomes.

**Automatable: about 85%** up to the hand-off.

**GTM.** Sign 3 broker partners on exclusive metros, then send 5K valuation emails. Measure the percentage of owners who reply with real financials.

**Unit economics (est.).** Data cost about $0.10/prospect. If 0.3% become qualified leads at $500, revenue is about $1,500 per 1,000 prospects against about $150 cost. Revenue is lumpy and depends on broker follow-through.

**Competitors.** Moderate: BizEquity, broker-run "free valuation" funnels, and Exit Planning advisors. Few do outbound with personalized estimates.

**Legal.**

- Disclaim that it is "an estimate, not an appraisal."
- Business-broker licensing (some states require a real-estate license) bites only if the brothers broker deals themselves; not verified here.
- CAN-SPAM.

**Kill risks**

1. Wrong numbers insult owners, which hurts reply rates and the brand.
2. Timing: sale intent is triggered by life events, so most recipients aren't selling within 12 months.
3. Not recurring unless brokers pay subscriptions, and brokers are notoriously cheap.

---

### Idea 7: Self-storage vertical (site + online rental + rate visibility)

**Pitch.** "You don't list prices or allow online rental. The three facilities near you do. Here's your new site with online move-in."

**Data sources**

- Facility websites: detect storEDGE or SiteLink rental widgets and published unit prices with the existing crawler.
- Operators publish street rates publicly, so competitor-rate snapshots are low-risk.
- CBP shows 18,564 employer establishments (undercounting facilities with no employees).

**Data combination.** Your missing online rental and hidden pricing, set against nearby competitors' published street rates. The deliverable is a market-rate table plus a rebuilt site.

**Buyer.** Independent 1–3-facility owner-operators. That is a different buyer from REITs (Public Storage, Extra Space).

**Willingness to pay.** The vertical already buys software. StorTrack Optimize is listed at £45 per store per month for a single store in the UK ([StorTrack](https://optimize.stortrack.co.uk/)), and Yardi Matrix and Radius+ sell institutional rate data ([Yardi](https://www.yardimatrix.com/property-types/self-storage/)). US independent willingness to pay for websites is not directly evidenced.

**Market size.** Small: roughly 15–25K independent facilities **(est.)**. At $149/mo × 3K clients that is about $5M ARR, which caps the opportunity.

**Deliverable and pricing.** Free site, then $149–$249/mo for hosting, an online rental integration and a monthly competitor-rate report **(est.)**.

**Automation pipeline.** Same as the core pipeline. A rate scrape of competitor sites feeds the monthly report.

**Automatable: about 85%.** The rental-software integration is the human step.

**GTM.** Pilot 300 independents in Sun Belt metros.

**Unit economics (est.).** CAC about $150. Gross margin about 85%. Churn likely low (facilities are stable): about 2%/mo.

**Competitors.** Storage-specific web vendors (storEDGE, SiteLink and Storable bundles). Less GHL saturation.

**Legal.** Low. Scrape competitor sites politely.

**Kill risks**

1. Small total addressable market.
2. Storable (storEDGE and SiteLink) bundles websites with its management software.
3. Independents may be selling to REITs or consolidating.

---

### Idea 8: Small-401(k) fee benchmarking via Form 5500-SF (licensed-partner model)

**Pitch.** "Your 401(k) has $1.4M across 23 participants and reported $X in administrative expenses, which is high for your size. A fiduciary adviser can benchmark it free."

**Data sources**

- DOL EBSA Form 5500 and 5500-SF bulk datasets: free, about 800K plans, updated monthly, no stated license restriction ([DOL](https://www.dol.gov/agencies/ebsa/about-ebsa/our-activities/public-disclosure/foia/form-5500-datasets)).
- The 5500-SF carries plan assets, participants, contributions, and aggregate administrative expenses. **Schedule A and C detail is not on the SF**, so fee visibility is aggregate only. Verify against the instructions before building.
- **Small fully insured health plans are exempt from filing**, which kills the health-benefits angle for local SMBs ([DOL instructions](https://www.dol.gov/sites/dolgov/files/ebsa/employers-and-advisers/plan-administration-and-compliance/reporting-and-filing/form-5500/2025-instructions.pdf)).

**Data combination.** Join 5500-SF expense and asset ratios (benchmarked against peers by plan size) with sponsor website and contact data and plan-year timing. That yields a personalized fee benchmark.

**Buyer and payer.** Owners of companies with 5–100 employees who have a small 401(k). The payer is a registered investment adviser (RIA) or 401(k) adviser, who earns basis points on plan assets.

**Willingness to pay.** Advisers already buy this data: Judy Diamond $795–$3,900/yr ([401kHunter](https://www.401khunter.com/judy-diamond-review)), BenefitFlow about $14.5K/yr ([Vendr](https://www.vendr.com/buyer-guides/benefitflow)), and Apify actors ([example](https://apify.com/yungstentech/form-5500-prospect-radar)).

**Market size.** Hundreds of thousands of small plans file the SF **(est. from the DOL ~800K total)**. Adviser-side: sell to RIAs at $500–$1,500/mo **(est.)**.

**Deliverable and pricing.** A per-plan benchmark brief. Either sell briefs and outreach-as-a-service to RIAs (SaaS), or act as a paid promoter under the SEC Marketing Rule with disclosure. The latter needs compliance review.

**Automatable: about 85%** up to the adviser hand-off.

**GTM.** Interview 10 small-plan RIAs, then pilot one metro.

**Unit economics (est.).** Data free. Infrastructure trivial. RIA SaaS at $999/mo with a CAC of about $1K.

**Competitors.** The data layer is commoditized (Judy Diamond, BenefitFlow, Apify). Personalized proof-first outreach is less common.

**Legal.**

- SEC/state adviser rules.
- Marketing Rule promoter disclosures.
- ERISA fiduciary language: don't call it "advice."
- CAN-SPAM.

**Kill risks**

1. It is not a local-SMB pipeline. The buyer is the adviser, which needs a new go-to-market.
2. Aggregate SF data gives weak proof of fees.
3. Regulatory friction slows time to first dollar.

---

## 3. Ideas considered and rejected

| Idea | Why rejected |
|---|---|
| **AI phone receptionist / missed-call text-back** | The most saturated category in the lane. GHL clone funnels dominate search, turnkey reseller businesses are sold on BizQuest ([listing](https://images.bizquest.com/start-up-business/turnkey-ai-voice-receptionist-reseller-opportunity/BW2400009)), and prices are falling to $49 (Rosie). **Not detectable from public data** without test-calling, which raises TCPA and recording-consent issues. The FCC treats AI voices as "artificial" ([FCC](https://docs.fcc.gov/public/attachments/DOC-400393A1.pdf)). The "62% of calls unanswered" stat comes from an 85-business test ([411 Locals](https://411locals.us/small-business-owners-dont-answer-62-of-phone-calls/)). Offer it at most as a white-label add-on. |
| **Standalone GBP optimization** | Detectable and recurring, but Paige at $99 and every GHL agency already bundle it. The GBP API forbids lead generation. Folded into Idea 1. |
| **Standalone local SEO audits** | Free audits are the oldest agency lead magnet. Delivery (content, links) is labor-heavy. Used as proof lines inside Idea 1, not as a business. |
| **Google / Meta ads audits** | The US commercial ad data isn't available by API. The Meta Ad Library API returns US political ads only ([adlibrary](https://adlibrary.com/posts/meta-ad-library-api-limitations)). The Google Ads Transparency BigQuery data covers only the EEA and Turkey ([Google README](https://storage.googleapis.com/ads-transparency-center/api-data/README.txt)). Public data never shows spend or waste. The audit needs account access, and PPC management carries spend liability. |
| **Website ADA compliance (standalone)** | Detectable via axe-core, but a scan isn't proof of compliance. Fear-based selling mirrors the accessiBe FTC case ([FTC](https://www.ftc.gov/news-events/news/press-releases/2025/01/ftc-order-requires-online-marketer-pay-1-million-deceptive-claims-its-ai-product-could-make-websites)). Lawsuits concentrate in eCommerce (70%) and food service (21%) ([UsableNet](https://info.usablenet.com/hubfs/Remediated%20-%202025_Year-End_Digital_Accessibility_Lawsuit_Report_FINAL.pdf)). AudioEye has taken years to reach $40M revenue. **Make "WCAG 2.1 AA, axe-clean" a default feature of every site built.** |
| **Broken / missing booking flows (standalone)** | The best *detection* signal: dead booking links, reCAPTCHA errors, no booking embed. Monetization is weak. Jobber affiliate pays about $50–$300 one-off ([lasso](https://getlasso.co/affiliate/jobber/)). Housecall Pro pays up to $180–$320 per lead or enrollment ([HCP](https://www.housecallpro.com/partner/)). Vagaro pays only credits ([Vagaro](https://support.vagaro.com/hc/en-us/articles/204947034-Refer-a-Friend-in-the-United-States)). Square pays nothing without a separate agreement ([Square](https://squareup.com/us/en/legal/general/partnerships)). The booking calendar is the core GHL offer. Used as a proof line, with optional HCP and Jobber referrals. |
| **Restaurant price / menu monitoring** | Buyers are chains and consumer-packaged-goods brands (Datassential, Technomic, RMS). The data comes from DoorDash and Uber Eats under terms that prohibit scraping. hiQ ultimately lost on breach of contract ([ZwillGen](https://www.zwillgen.com/alternative-data/hiq-v-linkedin-wrapped-up-web-scraping-lessons-learned/)). SMB tools sit at about $25/mo. Not a "defect" you can prove. |
| **Utility bill audits / energy brokerage** | No public proof (needs a bill or UtilityAPI authorization at $15/meter, [UtilityAPI](https://utilityapi.com/pricing)). Contingency fees run 25–40% and are one-off ([UtiliSave](https://utilisave.com/about-us/utility-bill-audits-value/)). An average commercial customer uses about 6.2K kWh/mo ([EIA](https://www.eia.gov/electricity/sales_revenue_price/pdf/table_5B.pdf)), so brokerage pays only about $220–370/yr per account **(est.)**. Only about 18 states allow choice, broker licensing applies, and telemarketing has a poor reputation. |
| **Telecom & SaaS spend audits on contingency** | Telecom expense management makes sense at $25K+/mo of spend, while local SMBs spend about $300–1,500 **(est.)**. Franchises such as Expense Reduction Analysts average only about $165K in sales per license ([FranchiseChatter](https://www.franchisechatter.com/2024/02/10/fdd-talk-expense-reduction-analysts-franchise-costs-fees-average-revenues-and-or-profits-2024-review/)), which suggests a thin pool. No public proof. |
| **Payroll / PEO / health-benefit audits** | Small fully insured health plans don't file Form 5500 ([DOL](https://www.dol.gov/sites/dolgov/files/ebsa/employers-and-advisers/plan-administration-and-compliance/reporting-and-filing/form-5500/2025-instructions.pdf)), and payroll fees aren't public. It needs uploads plus a life-and-health license. The 401(k) slice survives as Idea 8. |
| **Insurance benchmarking for micro-SMB BOPs** | About $100–400/yr in commission per account **(est.)**, competition from Next, CoverWallet and Huckleberry, and a license required. The WC lookups in CA and NY block automation by their terms ([WCIRB](https://www.caworkcompcoverage.com/Privacy)). Only the trucking slice (Idea 4) has public proof. |
| **Health-inspection data + reviews** | Free data ([Yelp LIVES](https://www.yelp.com/healthscores)), but the fix isn't automatable and "you failed inspection" is an adversarial opener. At most, a lead feed for pest-control or food-safety partners. |
| **Expired SSL / domain, hours mismatch** | Trivial to detect ([open-source example](https://github.com/dreadmoreeee/website-health-audit)) and great *timing triggers* for the core site email. Not products in themselves. |

---

## 4. Ranked shortlist

Scores run 1–10. A competition score of 10 means blue ocean. Overall is a judgement-weighted average, not a simple mean. It weights detectability and proof, automation and competition most heavily, given the brothers' edge.

| Rank | Idea | Market size | WTP | Data access | Automation | Competition | Recurring | Time to $ | **Overall** | Confidence |
|---|---|---|---|---|---|---|---|---|---|---|
| 1 | **AI + Maps Visibility Plan** (Ideas 1+2 bundled) | 8 | 6 | 8 | 8 | 3 | 8 | 9 | **7.0** | Medium: GEO willingness to pay unproven; churn unknown |
| 2 | Review engine (attach / standalone) | 7 | 8 | 7 | 7 | 2 | 9 | 8 | **6.6** | Medium-high: Podium proves willingness to pay; crowded |
| 3 | Trucking insurance renewal intelligence (FMCSA) | 6 | 8 | 9 | 7 | 5 | 7 | 4 | **6.4** | Low-medium: need agency interviews; renewal inference unvalidated |
| 4 | Restaurant commission-leak site + ordering | 7 | 8 | 8 | 6 | 2 | 8 | 7 | **6.0** | Medium: willingness to pay proven; Owner.com threat severe |
| 5 | Self-storage vertical | 3 | 6 | 8 | 8 | 6 | 8 | 7 | **5.9** | Low: small market, independent buyer willingness to pay unverified |
| 6 | Valuation lead feed (into M&A lane) | 7 | 5 | 7 | 8 | 6 | 3 | 5 | **5.6** | Low-medium: depends on broker partners and accuracy |
| 7 | Small-401(k) 5500-SF benchmarking (RIA partner) | 6 | 7 | 9 | 7 | 5 | 7 | 3 | **5.5** | Low: new buyer type and regulatory friction |
| 8 | Merchant-processing bolt-on | 8 | 5 | 3 | 6 | 1 | 7 | 6 | **4.9** | Medium: economics well documented, and they're mediocre |

### Honest bottom line

- **Nothing in this lane is blue ocean.** It is the most picked-over corner of SMB services: 114K agencies, 60K GHL resellers, and a $2.3B Owner.com coming horizontally.
- **The right move is a single bundle sold to the existing pipeline**, and in particular to the brothers' own website customers. Those buyers already trust them, so CAC is close to $0. A $149/mo visibility-plus-reviews plan adds roughly $1.8K/yr per site customer **(est.)**. Lead with a **stacked defect audit**:
  - AI-search absence
  - review gap against the map pack
  - incomplete GBP
  - dead booking link or expired SSL
  - DoorDash-routed Order button
  - mismatched hours

  Stacking several defects makes the email more credible than a GHL clone, and it is all legally obtainable via APIs and the prospect's own website.
- **The only genuinely differentiated data play is FMCSA trucking insurance.** It is worth a two-week validation (10 agency interviews) because licensing keeps the GHL crowd out. It belongs as a hand-off to the regulated or licensed-niche lanes rather than here.
- **Use merchant processing, valuations and ADA as features or CTAs, never as core bets.**
