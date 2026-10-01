# Lane 04: Regulatory and compliance monitoring, audits and remediation for SMBs and niche industries

*Research date: 2026-10-01. Research only: no outreach, signups or purchases were made. Every material claim has a URL. Anything labeled **(est.)** is my own estimate and is not sourced.*

---

## TL;DR

- **Most of the obvious plays in this lane are saturated or legally weakening:**
  - ADA/WCAG website scans: AudioEye alone has about 131k customers at roughly $305 ARPU, and the FTC fined accessiBe $1M.
  - Cookie/privacy consent: Termly charges $14/mo, CookieYes $8/mo, and most SMBs fall below state-law thresholds.
  - CIPA pixel-risk scans: SB 690 was signed 30 Sep 2026 and ends private pen-register suits from 1 Jan 2027.
  - FMCSA lead feeds for insurance agents: CarrierIQ, MyTruckingLeads and Apify scrapers already sell them.
  - Raw OSHA and EPA ECHO violator lists: Apify scrapers sell these for a few dollars.
- **The openings are in data combinations, not raw public data.** Every public enforcement dataset in this lane is already scraped and resold cheaply. Value comes from (a) predicting *who is next* and (b) doing the remediation.
- **Best idea: Prop 65 "Next Defendant" alerts plus a catalog exposure scan** for multi-brand e-commerce and specialty retailers. It joins CA AG 60-day notices (which name the product and brand) to retailer catalogs scraped from their storefronts. Notice volume hit about 5,400 in 2024 and climbed through 2025. 2025 out-of-court settlements reached $66.3M across 1,545 settlements. The Jan 2028 short-form warning deadline forces catalog-wide relabeling.
- **Other ideas worth testing:**
  - **#2 Restaurant health-inspection → pest/hood-cleaning done-for-you outbound.** Closest to the brothers' existing model, with the fastest first dollar.
  - **#3 OSHA SST target predictor.** Uses public ITA 300A injury data run through OSHA's own published selection logic. I found no product doing this.
  - **#4 California industrial stormwater citizen-suit risk monitor.** Draws on SMARTS data for 20,332 active permitted facilities.

---

## 1. Lane overview

### 1.1 The landscape

Compliance enforcement against SMBs in the US comes from two sources:

1. **Agency enforcement:** OSHA, EPA, FDA, FMCSA, state boards and state AGs. These records are almost all public, mostly free and often have APIs:
   - OSHA inspections and violations via the DOL API, updated daily, free key: https://developer.dol.gov/health-and-safety/dol-osha-enforcement/
   - EPA ECHO Exporter, covering more than 1.5M facilities: https://echo.epa.gov/tools/data-downloads
   - FDA Data Dashboard API (inspections, 483 citations, compliance actions, import refusals): https://datadashboard.fda.gov/oii/api/index.htm
   - FMCSA SMS and L&I insurance history on data.transportation.gov: https://data.transportation.gov/Trucking-and-Motorcoaches/ActPendInsur-All-With-History/y77m-3nfx
   - MSHA open data, updated weekly: https://www.msha.gov/data-and-reports/data-sources-and-calculators/data-resources/msha-data-set-resources-gateway
   - CFPB complaint API: https://cfpb.github.io/ccdb5-api/
   - CSLB contractor master, workers' comp and bond files: https://www.cslb.ca.gov/onlineservices/dataportal/ContractorList
2. **Private "bounty-hunter" enforcement:** this is where SMB pain is most acute and willingness to pay is highest.
   - **Prop 65:** about 5,398 notices in 2024 from about 40 private enforcers; $27.08M in 2024 out-of-court settlements, of which $23.55M was attorneys' fees. https://ceitoday.com/conference-materials/2025/05-Settlement%20Hot%20Topics/Prop.%2065%20Out-of-Court%20Settlements%20in%202024-%20Year%20in%20Review.pdf In 2025: 1,545 out-of-court settlements worth $66.3M, plus 293 in-court settlements worth $19.85M. https://oag.ca.gov/prop65/report/out-of-court-settlements
   - **ADA website suits:** 3,117 federal suits in 2025, up 27% (https://www.adatitleiii.com/2026/03/federal-court-website-accessibility-lawsuit-filings-bounce-back-in-2025/), and more than 5,000 including state courts (https://blog.usablenet.com/ada-web-lawsuit-trends-2026).
   - **CIPA wiretap and pen-register suits:** more than 4,000 claims against small businesses over 4 years, with $5,000 statutory damages per violation. https://calmatters.org/economy/technology/2026/09/california-privacy-act-reform-for-small-business-helped-big-tech/
   - **TCPA class actions:** about 2,400 projected for 2025, roughly double 2024. https://www.leadgen-economy.com/blog/tcpa-litigation-statistics/
   - **Clean Water Act stormwater citizen suits in California:** "a cottage industry", with settlements of $312k–$775k in examples. https://natlawreview.com/article/cottage-industry-economics-cwa-citizen-suit-enforcement

### 1.2 Incumbents by sub-segment

| Sub-segment | Incumbents | Crowding |
|---|---|---|
| ADA/WCAG web | AudioEye ($40.3M 2025 revenue, ~131k customers: https://www.prnewswire.com/news-releases/audioeye-reports-record-fourth-quarter-and-full-year-2025-results-302705842.html), accessiBe (FTC $1M order: https://www.ftc.gov/news-events/news/press-releases/2025/04/ftc-approves-final-order-requiring-accessibe-pay-1-million), UserWay/Level Access, Deque, Siteimprove, plus dozens of AI-scan startups (wcagsafe, abledly, sitecomply, testparty, adaquickscan) | **Saturated** |
| Cookie/consent/privacy | Termly ($14–15/mo), CookieYes ($8–46/mo), Osano ($199+/mo), Cookiebot, OneTrust (https://www.enzuzo.com/blog/osano-pricing, https://www.saasworthy.com/product/cookieyes/pricing) | **Saturated** and commoditized |
| FMCSA carrier monitoring for brokers | Carrier411 ($99/mo; 97 of the top 100 brokers: https://www.carrier411.com/faq.cfm), Highway, RMIS, CarrierOK, VerifyCarrier | **Saturated** |
| FMCSA data for insurance agents | CarrierIQ (renewals, mid-term cancellations, new ventures: https://carrieriq.io/blog/lead-generation-trucking-insurance), MyTruckingLeads, Polly, Apify scrapers at $4 per 1,000 leads (https://apify.com/foxlabs/fmcsa-carrier-leads) | **Crowded** |
| FMCSA new-authority compliance | Many "DOT compliance" firms, some impersonating FMCSA; FMCSA publishes fraud alerts (https://www.fmcsa.dot.gov/registration/fraud-alerts) | **Saturated and reputationally toxic** |
| FDA intelligence | Redica Systems/FDAzilla ($289 per 483: https://www.redica.com/document-store/store/483s), 483signal | Enterprise-focused; SMBs don't buy intelligence |
| FDA registration/agent | Registrar Corp ($100–500M revenue range, 20k+ clients: https://www.innovate757.org/hampton-roads-business-directory/business-listing/registrar-corp/) | **Dominated** |
| Prop 65 data | Prop 65 Clearinghouse ($1,150–$1,800/yr, aimed at lawyers: https://www.prop65clearinghouse.com/subscribe), lab bulletins (Intertek, BV), law firms | **Open for an SMB/retailer product** |
| PFAS / product chemicals | Assent, Certivo, Compliance & Risks, 3E, UL | Enterprise; SMB demand is episodic |
| OSHA lead data | Many Apify scrapers (https://apify.com/ayoub_highlighter/osha-enforcement-leads), safetyrecord.org | Raw data commoditized; **predictive layer open** |
| CA stormwater | QISP consulting firms (local, fragmented), californiastormwater.com (data viewer) | **Fragmented and open** |

### 1.3 Where the gaps are

1. **"Who is next" prediction.** Public enforcement data tells you who *was* hit. The bounty-hunter plaintiffs' workflow is predictable, though:
   - Prop 65 enforcers notice the same product at retailer after retailer.
   - Stormwater plaintiffs mine SMARTS for exceedances (https://natlawreview.com/article/environmental-plaintiffs-guide-organizations-filing-stormwater-citizen-suits).
   - OSHA publishes its SST selection logic, and the data it uses is public.

   Nobody sells this forward-looking view to SMBs.
2. **Remediation, not alerts.** Alert data is worth $4 per 1,000 rows. Remediation is where the money is:
   - Prop 65 lab tests cost $150–$2,000 per product (https://www.compliancegate.com/california-proposition-65-product-lab-testing/).
   - OSHA informal conferences reduce penalties by 20–50% (https://evolutionsafetyresources.com/osha-informal-conference-preparation-guide/).
   - SWPPP updates and ERA reports need a QISP.
3. **Done-for-you outbound for remediation vendors.** Pest control, safety consultants and QISPs are fragmented local firms that can't build data pipelines. This mirrors the brothers' website model: an agent finds a business with a detectable problem and pitches the fix.

---

## 2. Candidate ideas

### Idea 1: Prop 65 "Next Defendant" alerts plus catalog exposure scan

**Pitch:** "A product you sell was just named in a Prop 65 notice against another retailer. You're likely next. Here's the fix." The service runs on a continuous scan of a retailer's online catalog against every new 60-day notice and against current enforcement trends.

**Data sources**

| Source | Access | Cost | ToS/licensing |
|---|---|---|---|
| CA AG 60-Day Notice database (1988–present; noticing party, attorney, alleged violators, chemical, **Source/Product text naming the brand and product**, PDF, complaint, docket) | Web search UI and per-notice pages, e.g. https://oag.ca.gov/prop65/60-day-notice-2026-00064; no documented bulk export (https://oag.ca.gov/prop65/60-day-notice-search) | Free | Public government records; scrape politely. No explicit restriction found on the search page. |
| AG settlement reports (amounts, attorneys' fees) | https://oag.ca.gov/prop65/report/out-of-court-settlements | Free | Public |
| OEHHA chemical list and warning rules (short-form changes, BPS guidance) | p65warnings.ca.gov | Free | Public |
| Retailer/brand catalogs | Shopify stores expose `/products.json` publicly; other platforms via sitemap and product-page crawl. About 1.07–1.18M US Shopify stores (https://bootleads.com/stores/shopify/countries/us/); store-intel data via StoreLeads (https://storeleads.app/reports/shopify) | Free crawl; StoreLeads is a paid subscription (price not verified) | Crawling public pages is generally lawful in the US. **Do not scrape Amazon**: Amazon's Conditions of Use prohibit it. Use a licensed data API if Amazon coverage is needed. |

**The data combination that creates new value**

A notice names *Product X by Brand Y sold by Retailer A*. Our product works through three steps:

1. Find every other storefront selling Brand Y / Product X, or the same product type with the same supply chain (e.g. ceramic mugs from the same importer, spiced sardines, BPS receipt paper).
2. Check whether each storefront displays a compliant warning. Short-form warnings will need to name a chemical for products manufactured or labeled from 1 Jan 2028 (https://www.spencerfane.com/insight/changes-to-california-proposition-65-short-form-warnings/).
3. Score the storefront's risk against which enforcers are currently working which chemical/product combinations.

Enforcement clusters heavily. In Oct 2025, 453 notices were heavy metals and 209 were BPS in receipts and labels (https://jurislawgroup.com/prop-65-violations-newsletter-october-2025/), and over 900 BPS receipt notices went out in 2025 (https://www.lexology.com/library/detail.aspx?g=9d2825f0-72f7-4f94-894a-41df785286ac). The Clearinghouse sells lawyers a feed of notices. Nobody sells a retailer a match between notices and *its own catalog*.

**Buyer persona**

- **Primary:** owner or ops lead of a CA-shipping multi-brand online retailer or specialty store with 10–200 employees. Fewer than 10 employees is exempt (https://www.oag.ca.gov/prop65/faq). Typical categories: specialty food/grocery, kitchenware/ceramics, supplements, beauty, gifts, art supplies.
- **Secondary:** importers and DTC brands in noticed categories.
- **Tertiary (channel):** Prop 65 defense firms and labs, selling them the "likely next" list as a flat-fee data subscription.

**Willingness to pay**

- Small-manufacturer settlements usually run **$10k–$40k** (https://www.foodlawfirm.com/what-we-do/defending-prop-65-lawsuits/settling-prop-65-cases-for-smaller-manufacturers/).
- Amazon-product settlements typically run $10k–$20k (https://ecom.law/what-amazon-sellers-need-to-know-about-prop-65/).
- The 2024 average settlement was $24,600 (ceitoday PDF above).
- Lawyers already pay $1,150–$1,800/yr for raw notice data (Clearinghouse).
- Label reviews cost $350–$1,500 per label (https://naturproscientific.com/dietary-supplement-facts-and-label-review/).
- Labs charge $150–$2,000 per product (compliancegate).
- **A retailer has 5 business days after receiving a notice to cure** by warning or pulling the product (https://www.p65warnings.ca.gov/sites/default/files/2025-03/GuideSmallBusiness60day.pdf), so the urgency is concrete.

**Market size**

- **Bottom-up (est.):**
  - About 1.1M US Shopify stores (bootleads). Health category: about 145k; vitamins/supplements: about 55k (https://storeleads.app/reports/shopify/category/Health).
  - Assume about 15% of US Shopify stores sell in high-notice categories and are large enough to be in scope: **about 150k storefronts (est.)**. Add non-Shopify specialty retailers.
  - Realistic serviceable segment for 10+ employee businesses with CA sales: **15–30k (est.)**.
  - At $99–$299/mo, that is **$18–$100M ARR serviceable (est.)**.
- **Top-down anchor:** about $86M/yr in 2025 settlements alone (AG figures above), before defense fees, testing and relabeling.

**Deliverable and pricing**

- **Free:** one-time "Prop 65 exposure report" covering top at-risk SKUs, live notices on matching products, and missing or outdated warnings.
- **Monitoring:** subscription at $99/mo (≤500 SKUs) or $299/mo (≤5k SKUs). Includes real-time "next defendant" alerts, warning-text generation for the 2028 short form, and warning-placement checks on product pages.
- **One-off:** remediation ($500–$2,500): lab-test coordination at pass-through cost plus margin, and label/warning implementation.
- **Recurring:** yes. Notices and listings change monthly.

**Automation pipeline**

1. **Find prospects:** a daily scrape of new notices; an LLM extracts brand, product, chemical and defendant. The catalog index then finds other sellers of the same brand/product type, starting with StoreLeads plus our own crawl.
2. **Build deliverable:** an LLM matches catalog SKUs to notice product types and the chemical list, checks product pages for warning text, and renders a PDF/HTML report per prospect.
3. **Personalized outreach:** a B2B cold email citing the specific AG notice number and the specific SKU on their site.
4. **Handle replies:** a Claude agent answers FAQs (what Prop 65 is, the 10-employee exemption, testing options) and books a call or self-serve checkout. Legal questions are deflected to "consult counsel" with a directory.
5. **Deliver/renew:** continuous monitoring, monthly digest, alerts and renewal.

**Percent automatable:** about 85% (est.). Human touchpoints:
- reviewing borderline product matches before claiming "your product was noticed" (defamation and accuracy risk)
- choosing and contracting with lab partners
- QA on warning text
- escalation to attorneys

**GTM, first 90 days**

- **Days 1–30:** build the notice scraper and extractor; backfill 2024–2026 notices; build product-type taxonomy; build Shopify catalog matcher; hand-validate 200 matches.
- **Days 31–60:** send 2,000 emails in the 3 hottest clusters: heavy metals in food/ceramics, BPS receipts for multi-location retail/restaurants, phthalates in vinyl bags. Offer the free report. Sign 2 labs as fulfillment partners. Pitch 5 defense firms on the flat-fee data feed.
- **Days 61–90:** convert to the $99/$299 monitoring tiers. Goal: 30 paying customers, about $6k MRR (est.).

**Unit economics (est.)**

| Item | Estimate |
|---|---|
| CAC | $150–$400 (cold email + LLM costs; about 1–2% free-report → paid conversion) |
| ARPU | about $180/mo, plus about $800 per remediation project |
| Gross margin | 80–85% on monitoring; 30–40% on remediation pass-through |
| Data cost | about $0 for notices, crawl compute about $200–$500/mo, StoreLeads subscription (unverified price) |
| Payback | 1–3 months |

**Competitors and crowding:** Prop 65 Clearinghouse (lawyer-oriented), lab bulletins (free, marketing), law firms, and enterprise PLM/chemical tools (Sustalium, ComplyMarket: https://complymarket.com/en/blogs/prop-65). I found **no retailer-facing product that matches notices to catalogs.** Crowding: **low**.

**Legal/regulatory risks**

- **CAN-SPAM:** B2B cold email is allowed with an honest sender, a physical address and an opt-out.
- **Unauthorized practice of law:** risk if we tell a business it "must" warn. Frame output as data plus industry practice and offer attorney referral.
- **Fee-splitting:** no per-referral fees to lawyers (ABA Model Rule 7.2(b)). Defense firms may only pay flat-fee advertising or subscriptions.
- **Defamation:** state only facts from the AG record, e.g. "AG notice 2026-00064 alleges lead in Nuri sardines."
- **Fear-based marketing:** keep claims accurate (FTC Act §5).
- **Scraping ToS:** stay off Amazon.
- **No impersonation:** never mimic the CA AG or OEHHA. The FTC Impersonation Rule carries penalties up to $53,088 per violation (https://www.ftc.gov/business-guidance/blog/2024/02/new-impersonator-rule-gives-ftc-powerful-tool-protecting-consumers-businesses).

**Kill risks**

1. **Product-matching accuracy.** Notice product descriptions are free text. False positives destroy trust and create defamation exposure.
2. **Enforcer behavior shifts.** Courts or legislation curb Prop 65 bounty hunting (e.g. *CalChamber v. Bonta* acrylamide ruling on appeal), or the BPS wave ends.
3. **Buyers ignore it until noticed.** Prevention sells poorly to SMBs, which may make this a post-notice "defense kit" business with low recurrence.

---

### Idea 2: Restaurant health-inspection violations → done-for-you outbound for pest-control and hood-cleaning firms

**Pitch:** "We book commercial pest-control appointments with restaurants that were cited for vermin this week." A Claude-run outbound engine is sold to local pest control and hood-cleaning firms on retainer.

**Data sources:** city and county restaurant-inspection open data. NYC, Chicago, LA County, SF, King County, Austin and others publish open data, usually Socrata or ArcGIS (free, public). Many other counties publish only HTML or PDF, which can be scraped. Apify already offers a multi-city feed (https://apify.com/scrapemint/restaurant-inspection-leads). Restaurant contact data comes from Google Places API (paid per call, and Google's ToS restricts storage) or from website crawl.

**Data combination:**
1. Violation text: rodents, roaches, flies, and grease/hood/fire-suppression violations.
2. The restaurant's website and phone.
3. Whether the restaurant already shows a pest vendor sticker or vendor name in the inspection notes (some jurisdictions record "pest control service log present").
4. Re-inspection date.

The result is a *timed* pitch ahead of re-inspection. The vendor's service area and capacity then decide routing.

**Buyer persona:** owner or GM of a 3–50-tech independent pest control company (commercial division) or a hood/exhaust cleaning company in a metro with open inspection data.

**Willingness to pay:**
- Commercial pest leads cost **$40–$75 CPL**. A booked commercial lead costs about $340, and restaurant contracts run **$200–$800/mo** (https://cubecreative.design/blog/pest-control-marketing/pest-control-cost-per-lead-benchmarks, https://advancedexterminating.com/blog/nyc-commercial-pest-control-cost/).
- Pest-related violations make up about 20% of restaurant inspection scores (https://apify.com/scrapemint/restaurant-inspection-leads summary).

**Market size (est.):**
- About 20k US pest control companies (est.; not verified in this lane) and about 750k+ US restaurants (est.).
- Serviceable: firms with commercial divisions in about 50 metros with open data, roughly 3–5k firms (est.).
- At $1–3k/mo retainers, that is **$36–$180M (est.)**.

**Deliverable and pricing:**
- $1,000–$2,500/mo retainer per metro per vertical, with exclusivity per metro as the upsell, plus $100–$200 per booked appointment.
- Recurring: yes. Violations recur weekly.

**Automation pipeline:**
1. **Find prospects:** daily ingest of inspections, LLM classification of violation text, then entity resolution to the restaurant's website, email and phone.
2. **Build deliverable:** the vendor gets a weekly "cited restaurants" dashboard; each restaurant gets a short "re-inspection prep checklist" PDF co-branded with the vendor.
3. **Personalized outreach:** email to the restaurant citing the inspection date and violation category, sent on the vendor's behalf from a vendor-branded domain.
4. **Handle replies:** an agent qualifies and books a slot on the vendor's calendar.
5. **Deliver/renew:** monthly report of booked visits; renew the retainer.

**Percent automatable:** about 75%. Humans are needed for vendor onboarding, phone follow-up (many restaurants don't answer email), and quality control on appointment quality.

**GTM, first 90 days:** launch in 3 metros with clean APIs (NYC, Chicago, LA County). Cold-email 300 pest firms with a free sample list of "47 restaurants cited for vermin in your zip codes this week". Sign 5 pilot vendors at $1k/mo.

**Unit economics (est.):** CAC about $500 per vendor; ARPU about $1.5k/mo; gross margin about 70% (email infrastructure, data enrichment at about $0.05–$0.20 per contact, LLM costs); data cost low.

**Competitors:** Apify lead feeds (raw lists), generic pest-control marketing agencies (PPC/LSA), and Yelp/Angi. Done-for-you, violation-triggered outbound is **moderately open**, but the data side is commoditized.

**Legal/regulatory:**
- CAN-SPAM covers B2B emails to restaurants.
- **TCPA if calling or texting:** no autodialed or prerecorded calls or texts to restaurant owners' cell phones without consent. Keep phone calls manual.
- Inspection data is public, but **do not imply affiliation with the health department** (impersonation rule).
- Google Places data has storage limits under its ToS.

**Kill risks:**
1. Restaurants hate being "ambulance-chased", so reply rates may be low.
2. Many restaurants already have pest contracts (often required by landlords or chains). The real target is independents whose current vendor is failing.
3. Data coverage is uneven across counties, and per-metro scraping maintenance is heavy.

---

### Idea 3: OSHA SST target predictor ("you are probably on OSHA's inspection list")

**Pitch:** use OSHA's own public injury data and its published selection logic to tell 20+ employee establishments they are likely Site-Specific Targeting (SST) picks. Then sell a mock inspection or recordkeeping fix, or sell the list to safety consultants and workers' comp agents.

**Data sources:**
- **OSHA ITA establishment-level Form 300A data:** more than 390,000 establishments submitted 2024 data, with CSV downloads for summary and case detail (https://www.osha.gov/Establishment-Specific-Injury-and-Illness-Data, https://www.osha.gov/sites/default/files/OSHA_2024_Work-Related_Injury_and_Illness_Summary.pdf). Free, public.
- **SST directive CPL 02-01-067** (https://www.osha.gov/sites/default/files/enforcement/directives/CPL-02-01-067.pdf). It selects:
  1. high-DART establishments, with separate manufacturing and non-manufacturing cut-offs
  2. upward-trending establishments at or above 2× the national rate in 2022 and rising from 2021 to 2023
  3. a random sample of non-responders
  4. a random sample of low-rate establishments

  Scope is non-construction, 20+ employees.
- **OSHA enforcement history** via the DOL API (free key).
- **For non-responders:** business registries or Census County Business Patterns-type data showing establishments that *should* have filed. This is harder, and commercial firmographic data costs money.

**Data combination:** ITA DART rates by NAICS, 3-year trend computation and prior inspection history produce a ranked SST likelihood score. OSHA does not publish the exact DART cut-offs (I verified that the directive text describes the method, not the number), so the score is a *probability* calibrated against actual SST-coded inspections in the enforcement data. That calibration is the moat.

**Buyer persona:**
- EHS manager or plant manager at a 20–250 employee manufacturer, warehouse or nursing home (high-DART NAICS).
- **Channels:** independent safety consultants (about 1,500–2,000 firms: https://apify.com/belcaidsaad/safety-consultants-supply) and workers' comp agents and brokers (DART drives experience mods).

**Willingness to pay:**
- OSHA serious penalty maximum is $16,550 per violation in 2025, with up to 70% size reduction for ≤25 employees (https://www.worksafelysmb.com/blog/osha-penalties-2025-small-business).
- Initial 2024 penalties totaled $459.7M across 75,927 inspections (https://safetyrecord.org/analysis/osha-enforcement-2024).
- Occupational health and safety specialists earn a median $83,910 across 131,900 jobs (https://www.bls.gov/ooh/healthcare/occupational-health-and-safety-specialists-and-technicians.htm#tab-2). That salary is the human doing this analysis manually.

**Market size:**
- Bottom-up: 390k ITA filers. Assume the top-risk decile is about 39k establishments (est.); SST lists have historically run about 10–15k (https://www.horstinsurance.com/news-and-blog/osha-site-specific-targeting-sst-inspection-program-overview/).
- At $500–$2,000 per mock audit, or a $99/mo monitor: **$20–60M (est.)**.
- A consultant lead-feed SaaS at $200–$500/mo × 1,500 firms is roughly $4–9M ARR (est.).

**Deliverable and pricing:**
- Free "SST risk score" report.
- $1,500 virtual mock inspection and recordkeeping review, delivered with a partner consultant.
- $99/mo "OSHA radar" for annual re-scoring, new-inspection alerts for neighbors in the same NAICS, and ITA filing reminders. The 2 March filing deadline is itself a non-responder risk.
- Consultant edition: $300/mo per territory.

**Automation pipeline:**
1. **Find:** annual ITA ingest, then scoring.
2. **Build:** a per-establishment PDF showing their DART against the industry rate, trend, prior inspections and their likely SST category.
3. **Outreach:** email to the EHS or plant manager, found via website crawl and LinkedIn-free enrichment.
4. **Replies:** an agent explains the methodology and books the mock audit.
5. **Deliver/renew:** consultant partner performs the audit; annual re-score.

**Percent automatable:** about 70%. Mock audits and site walks are human, and calibration needs expert review.

**GTM, first 90 days:** build the score from 2021–2024 ITA data and back-test against 2025–2026 SST inspections in the DOL data (inspection type "programmed planned" plus SST emphasis codes). If precision is good, launch the consultant edition to 300 safety consulting firms first. It is easier to sell and lower legal risk than fear-marketing to employers.

**Unit economics (est.):** consultant edition CAC $300, ARPU $300/mo, gross margin about 90%, data cost $0.

**Competitors:** I found no SST-prediction product; searches surfaced only explainers. Raw OSHA data feeds are crowded. Crowding for the *predictive* layer: **low**.

**Legal/regulatory:**
- Public data.
- Don't claim "you ARE on OSHA's list"; say "your public data matches the criteria". Implying government affiliation is prohibited.
- ITA data has had litigation over publication. OSHA posts it publicly, but case-level 300/301 data is sensitive, so use summary data only.

**Kill risks:**
1. **Back-test precision may be poor.** OSHA randomizes within lists and Area Offices have limited capacity, so "likely" may mean a 5–15% chance (est.). That is a weak hook.
2. **The SST program could be cut.** Current OSHA leadership emphasizes compliance assistance (2025 penalty-reduction guidance), and fewer programmed inspections would kill the urgency.
3. **The buyer is a 20+ employee plant, not a micro-SMB.** These buyers have insurer loss-control reps who do this for free.

---

### Idea 4: California industrial stormwater citizen-suit risk monitor (SMARTS)

**Pitch:** "Your SMARTS filings show the patterns stormwater plaintiffs sue on. Here's your exposure and the fix." Monitoring is sold to permitted facilities and as a lead feed or white-label tool to QISP consultants.

**Data sources:**
- **SMARTS** public portal (NOIs, SWPPPs, sampling results, annual reports; text downloads by region: https://www.waterboards.ca.gov/water_issues/programs/stormwater/smarts/).
- **Water Boards ArcGIS layer** of active IGP facilities: I queried it directly and it returned **20,332 active facilities** as of 8 Dec 2025, with SIC code and location. Endpoint: `gispublic.waterboards.ca.gov/.../IGP_Active_Facilities_12_08_25/FeatureServer/0`.
- **EPA ECHO** NPDES/DMR violations for other states (https://echo.epa.gov/tools/web-services).
- **303(d) impaired waters and TMDLs.**

All free and public.

**Data combination:**
1. Facility sampling results against NAL thresholds and Level 1/Level 2 status.
2. Late or missing annual reports.
3. Whether the facility drains to impaired waters with a TMDL.
4. The plaintiff-geography model: LA Waterkeeper in LA County, EDEN in the Central Valley and Bay Area (https://natlawreview.com/article/environmental-plaintiffs-guide-organizations-filing-stormwater-citizen-suits).

Together these produce citizen-suit likelihood. Plaintiffs "identify potential targets through California's SMARTS database" (same source). We run their screen first.

**Buyer persona:**
- Owner or operations manager of auto dismantlers, scrap and metal recyclers, trucking yards, small manufacturers (SIC 4212, 5015, 5093, 3xxx).
- **Channel:** QISP consultants and environmental engineering firms.

**Willingness to pay:**
- Example settlements: auto dismantler $624k; scrap recycler $312k; molding company $325k+, of which $185.5k was attorneys' fees (https://natlawreview.com/article/cottage-industry-economics-cwa-citizen-suit-enforcement).
- The IGP annual fee is about $1,800 (https://www.anaheim.net/DocumentCenter/View/29422/Storm-Water-General-Permit-Fact-Sheet).
- QISP Level 1 ERA reports are mandatory (https://www.all4inc.com/4-the-record-articles/the-california-industrial-general-permit-understanding-your-level-status/).

**Market size:** about 20k CA facilities. If 30% are at elevated risk (est.), that is about 6k. At $150–$300/mo monitoring that is **$11–22M ARR**, plus remediation fees. Other states via ECHO DMR add more, but plaintiff activity is lower outside CA. Small but very high willingness to pay.

**Deliverable and pricing:** free "citizen-suit exposure report"; $199/mo monitoring with sampling-calendar reminders, NAL exceedance alerts, annual report pre-check and BMP recommendations; QISP partner remediation as referral or white label.

**Automation pipeline:** SMARTS ingest → per-facility risk score → LLM-written exposure report citing their own sample data → email and letter to facility owner → agent handles replies and books a QISP partner → monthly monitoring.

**Percent automatable:** about 65%. The QISP must sign ERA reports and SWPPP amendments, and site BMPs are physical.

**GTM, first 90 days:** partner with 2–3 QISP firms (revenue share). Target Level 1/2 facilities in LA County and the Central Valley first. Mail physical letters as well: these owners aren't email-first.

**Unit economics (est.):** CAC $400–$800 (letters plus calls); ARPU $199/mo plus a 15–20% referral share on QISP work averaging $5–15k; gross margin about 80% on software.

**Competitors:** local QISP firms (fragmented); californiastormwater.com (a data viewer: https://californiastormwater.com/). Crowding: **low**.

**Legal/regulatory:**
- CAN-SPAM; postal mail is fine.
- Do not give legal advice about pending 60-day notices.
- QISP certification is required for certain deliverables, so partner rather than self-perform.
- SMARTS terms: public portal, so scrape politely.

**Kill risks:**
1. The market is small and California-centric.
2. Owners of scrap yards are slow to buy software, so this may collapse into a consulting lead-gen business.
3. Plaintiffs could shift strategy, or the State Board could change the IGP and its reporting cadence.

---

### Idea 5: Small local-government digital accessibility remediation (ADA Title II), sold to special districts and small cities

**Pitch:** an AI-native crawl, remediation and monitoring service for the PDFs and web pages of water, fire, park and school districts and small towns. These entities must meet WCAG 2.1 AA by 26 April 2028, while large entities have until 26 April 2027 (https://www.adatitleiii.com/2026/04/doj-extends-ada-title-ii-website-accessibility-deadlines-for-governmental-entities-but-litigation-and-compliance-risks-remain/).

**Data sources:**
- Census of Governments list: 90,837 local governments, 39,555 special districts (https://www.census.gov/library/stories/2023/08/2022-census-of-governments.html). Free.
- Each entity's public website: crawl it to count PDFs and pages and score WCAG.

**Data combination:** the government roster, a site crawl (PDF count, automated WCAG errors) and the deadline tier (population) produce an exact scoped quote per entity before first contact. That is the website-business pattern applied to governments.

**Buyer persona:** general manager or board clerk of a special district; city clerk or IT generalist in a town under 50k.

**Willingness to pay:**
- PDF remediation costs $4–$30 per page from traditional vendors and $0.30–$12 per page from AI-native vendors (https://venngage.com/blog/pdf-accessibility-cost/, https://casocomply.com/pricing, https://accessibility.build/services/pdf-remediation).
- Public entities have a legal mandate.

**Market size:** about 60k small entities (est.). At a $1.5–5k first-year remediation plus a $50–$150/mo monitor, that is **$150–400M of first-year spend (est.)**, much of it under small-purchase thresholds that skip RFPs.

**Deliverable and pricing:** a fixed-price remediation of the existing PDF backlog, then a $99/mo monitor that auto-remediates new PDFs (board agendas and minutes recur monthly, so recurrence is genuine).

**Automation pipeline:** roster → crawl → quote report → email to clerk → agent replies and handles W-9 and procurement paperwork → LLM remediation pipeline with human QA sampling → monthly monitoring.

**Percent automatable:** about 70%. Humans are needed for QA of complex tables and forms (accuracy is the legal standard) and for procurement hand-holding.

**GTM, first 90 days:** pick 2 states with good district rosters (CA and TX have thousands of special districts). Offer a free crawl report. Get 3 references, then sell through state special-district associations (CSDA in California).

**Unit economics (est.):** CAC $300–$1,000 (slow procurement); first-year revenue $2–4k; gross margin 60–75% (QA labor); data cost $0.

**Competitors:** CivicPlus, Granicus, AudioEye, Allyant, Level Access, plus a wave of AI PDF startups (casocomply, Accessibility On Demand, accessibility.build). Crowding: **medium and rising.** The 2027 extension gives competitors time too.

**Legal/regulatory:**
- Overlays and "100% compliant" claims are the accessiBe FTC trap: never promise compliance.
- Public procurement rules.
- Liability if remediated documents still fail.

**Kill risks:**
1. Price collapse toward $0.30/page commoditizes remediation.
2. Procurement friction and slow sales cycles.
3. DOJ could extend or narrow the rule again: it already extended once, via an interim final rule open for comment (https://www.archerlaw.com/en/blogs/your-campus-counsel/doj-extends-ada-web-accessibility-deadline-to-april-2027).

---

### Idea 6: OSHA "just cited" informal-conference kit for cited SMBs, or a lead feed to safety consultants

**Pitch:** within days of a federal citation going public, send the employer a personalized analysis of their citations, comparable settlements and a 15-working-day action plan. Sell a $750–$2,500 informal conference package delivered with partner safety consultants.

**Data sources:** DOL OSHA enforcement API, updated daily with a free key (https://developer.dol.gov/health-and-safety/dol-osha-enforcement/). Federal citations appear about 5 days after the employer receives them, and state-plan citations about 30 days after (https://www.osha.gov/help/establishment-search). That leaves about 10 working days of the 15-working-day contest window for federal cases.

**Data combination:** each citation (standard, classification, penalty) joined with historical outcomes for the same standard, NAICS and Area Office (initial versus current penalty) gives an *expected reduction* number. In 2024, penalties fell 25.5% from $459.7M to $342.4M after settlements (https://safetyrecord.org/analysis/osha-enforcement-2024).

**Buyer:** owner of a cited 5–250 employee contractor or manufacturer; channel is safety consultants and OSHA defense attorneys.

**Willingness to pay:** consultants advertise 20–50% reductions (https://evolutionsafetyresources.com/osha-informal-conference-preparation-guide/); median safety specialist salary is $83,910 (BLS).

**Market size:** 42,267 inspections with violations in 2024 (safetyrecord.org). If 50% are SMBs with penalties above $5k (est.), that is about 20k per year. At $1,000 average and 5% capture, roughly $1M per year (est.). The **lead feed for consultants** is about 1,500–2,000 firms × $200/mo, roughly $4M ARR (est.).

**Deliverable and pricing:** a mostly one-off kit; recurring only via a "post-citation abatement tracker" at $49/mo or the consultant feed subscription.

**Automation:** about 80% (data → report → outreach → reply agent → consultant handoff). Informal conference representation is human.

**GTM:** consultant feed first, since there are already sellers of raw lists and the differentiator is expected-reduction analytics plus ready-to-send outreach.

**Unit economics (est.):** CAC $200; one-off revenue $1k; 40% margin after consultant split.

**Competitors:** Apify OSHA lead scrapers ([1](https://apify.com/ayoub_highlighter/osha-enforcement-leads), [2](https://apify.com/belcaidsaad/osha-citation-scraper)), safetyrecord.org, local consultants and OSHA defense firms. Crowding: **medium-high** on data.

**Legal:** don't give legal advice on whether to contest; no impersonation of OSHA; CAN-SPAM.

**Kill risks:**
1. The response window is short and contact data is weak.
2. It is one-off revenue.
3. Raw lists are already cheap, so differentiation is thin.

---

### Idea 7: DTC supplement and cosmetics claims scanner (FDA/FTC disease-claim risk)

**Pitch:** crawl a supplement or cosmetics brand's website and marketplace listings, flag disease claims, missing DSHEA disclaimers and drug-like cosmetic claims, and offer a fixed-fee rewrite plus monitoring.

**Data sources:**
- FDA warning letters (openFDA and FDA site) for the claim patterns FDA actually cites: e.g. 10 diabetes-claim letters in 2025 (https://ndnr.com/fda-diabetes-supplement-warning/) and 7 cardiovascular-claim letters (https://natlawreview.com/article/fda-issues-warning-letters-to-7-dietary-supplement-companies-drug-claims).
- FTC Health Products Compliance Guidance (https://www.ftc.gov/business-guidance/resources/health-products-compliance-guidance).
- Brand websites, via Shopify `/products.json` and crawl.

All free.

**Data combination:** a warning-letter claim corpus (a classifier trained on the exact phrases FDA cites), the brand's live copy and Prop 65 metals exposure (the supplement category overlaps Idea 1) produce a combined "regulatory copy risk" score.

**Buyer:** founder or marketing lead of a Shopify supplement or skincare brand. There are about 55k Shopify vitamins/supplements stores (https://storeleads.app/reports/shopify/category/Health/Nutrition/Vitamins%20&%20Supplements).

**Willingness to pay:** label and marketing review costs $800–$1,500 per label (https://naturproscientific.com/dietary-supplement-facts-and-label-review/); FoodLab charges $240–$480 (https://foodlab.com/services-pricing/).

**Market size (est.):** about 55k stores; 20% addressable gives 11k. At $99/mo that is about $13M ARR, plus one-off rewrites.

**Pricing:** $299 one-off copy audit and rewrite; $49–$99/mo monitoring of new pages and ads.

**Automation:** about 85% (LLM classification and rewrite); a human regulatory reviewer signs off for credibility.

**GTM:** crawl 10k supplement stores, send a free top-5 risky claims report, and partner with supplement contract manufacturers as a channel.

**Unit economics (est.):** CAC $100–$200; ARPU $70/mo; gross margin 85%.

**Competitors:** regulatory consultancies (Dicentra, Nutrasource, EAS), FDA law firms and general AI copy-compliance tools. Crowding: **medium**.

**Legal:** UPL-style risk (frame as a regulatory review, not legal advice); CAN-SPAM.

**Kill risks:**
1. FDA enforcement intensity on small brands is low (letters number in the dozens per year), so the fear is weak.
2. Amazon policy enforcement may be the bigger driver, and Amazon data is hard to get under its ToS.
3. Founders deliberately keep aggressive claims because they convert.

---

### Idea 8: SMS/10DLC compliance website fix for SMBs, sold through SMS platforms and agencies

**Pitch:** scan an SMB's website for the opt-in, privacy-policy and terms language carriers require for A2P 10DLC campaign approval. Auto-generate compliant pages and fix rejected campaigns.

**Data sources:**
- Prospect website crawl.
- Carrier and TCR rejection criteria. Twilio error 30908 requires a compliant privacy policy that says mobile data isn't shared (https://www.twilio.com/docs/api/errors/30908). Required SMS disclosures cover brand, frequency, "msg & data rates", privacy link and opt-out (https://www.textmymainnumber.com/blog/why-10dlc-campaigns-get-rejected).

**Combination:** website crawl plus the rejection rulebook give a pre-flight approval score. This could be combined with TCPA quiet-hours and consent-capture checks, a live litigation theme with 478 quiet-hour cases and demand letters (https://www.blacklistalliance.com/blog/beware-the-tcpa-quiet-hour-a-new-wave-of-litigation).

**Buyer:** home-services and clinic SMBs that text customers. The better buyer is CSPs and SMS platforms (Text Request, SalesMessage, etc.) and marketing agencies, who eat the support cost of rejections.

**Willingness to pay:** TCR fees are small ($4–$44 brand, $15 vetting: https://www.text-em-all.com/sms-compliance/10dlc-registration). Platforms already give away AI rejection fixers (https://www.txtimpact.com/blog/10dlc-campaign-rejection-and-solution). Consulting exists (https://www.missionmobile.net/10dlc-consulting/). Direct SMB willingness to pay is **low**.

**Market:** large in count (millions of texting SMBs), but value per SMB is about $50–$200 one-off.

**Automation:** about 90%.

**Competitors:** every SMS platform builds this in for free. Crowding: **high**.

**Kill risks:**
1. Platforms bundle it free.
2. It is a one-off fix.
3. It is cheap to copy.

*Kept as a candidate only as a possible add-on to the brothers' website-building product: every new site they build could ship with compliant SMS opt-in and privacy pages.*

---

### Idea 9: FMCSA insurance-lapse and CSA-trend feed for trucking insurance agents and safety consultants

**Pitch:** daily alerts on carriers with BMC-35 cancellations (30 days to replace insurance or face revocation), rising inspection out-of-service rates and upcoming renewals, plus auto-drafted outreach for agents.

**Data:**
- FMCSA L&I ActPendInsur/Insur history (insurer, effective and cancel dates) on data.transportation.gov (https://data.transportation.gov/Trucking-and-Motorcoaches/Insur-All-With-History/ypjt-5ydn/about_data).
- SMS monthly raw data. Property-carrier percentiles are **hidden from public display** under the FAST Act, but inspection and crash data remain public (https://ai.fmcsa.dot.gov/SMS/HelpCenter/Index.aspx).

Free.

**Buyer:** commercial trucking insurance agents; also safety consultants.

**Willingness to pay:** exclusive trucking insurance web leads cost $30–$65, live transfers $50–$120, exclusive fleet leads $110 (https://www.getinsureleads.com/commercial-truck-insurance-leads, https://getpollyai.com/blog/best-trucking-insurance-leads).

**Market:** about 91.5% of carriers run ≤10 trucks (https://maxdispatchservice.com/how-many-trucking-companies-in-the-us/). There are thousands of agents.

**Competitors:** CarrierIQ (renewal, mid-term cancellation and new-venture signals already productized), MyTruckingLeads, Polly, and Apify actors at $4 per 1,000. Crowding: **high**.

**Legal:** carriers are flooded with spam and impersonation scams (https://www.thetruckersreport.com/truckingindustryforum/threads/dot-compliance-group-scam-and-spam.2350203/), so trust is poisoned. TCPA applies to calls and texts to owner-operators' cell phones, which are effectively consumer numbers.

**Kill risks:**
1. Saturation.
2. Carrier-side trust is destroyed.
3. Thin differentiation.

**Verdict: do not pursue except as a white-label for an existing agency.**

---

## 3. Ideas considered and rejected

| Idea | Why rejected (evidence) |
|---|---|
| **ADA/WCAG lawsuit-risk scans and monitoring for SMB websites** | **Saturated.** AudioEye: about 131k customers on $40M ARR (~$305/yr ARPU) (https://www.prnewswire.com/news-releases/audioeye-reports-record-fourth-quarter-and-full-year-2025-results-302705842.html). Dozens of AI-scan startups appear on page 1 of search (wcagsafe, abledly, sitecomply, testparty, adaquickscan, ratedwithai). The FTC's $1M accessiBe order bars "makes you compliant" claims (https://www.ftc.gov/news-events/news/press-releases/2025/04/ftc-approves-final-order-requiring-accessibe-pay-1-million). 28% of 2025 suits hit sites *with* overlays (https://info.usablenet.com/ada-website-compliance-lawsuit-tracker), so scan-and-widget products don't protect buyers. Real remediation is human-heavy. The brothers could bundle accessibility into the sites they build, but it is not a standalone business. |
| **Cookie-consent / state-privacy scans for SMBs** | **Saturated and low ARPU:** Termly $14/mo, CookieYes $8–46/mo (https://www.saasworthy.com/product/cookieyes/pricing). **Most SMBs are legally exempt:** most of the 20 state laws trigger at 100k consumers (https://iapp.org/news/a/new-year-new-rules-us-state-privacy-requirements-coming-online-as-2026-begins); only TX and NE lack a numeric threshold (https://privacylawmap.com/compare). |
| **CIPA pixel/chat "wiretap risk" scans** | It was a hot SMB pain (1,500 suits in 18 months to Aug 2025: https://cookie-script.com/news/tracking-pixels-cipa-wiretap-lawsuits/amp). But **SB 690 was signed 30 Sep 2026.** It ends private pen-register/trap-and-trace website claims from 1 Jan 2027, and those were about two-thirds of the litigation (https://www.newsmediaalliance.org/newsom-signs-sb-690-into-law/, https://www.sidley.com/en/insights/newsupdates/2026/09/californias-sb-690-clears-the-legislature-what-it-means-for-cipa-website-tracking-claims). §631 wiretap claims for chat and session replay survive, but demand is about to shrink sharply. |
| **BIPA exposure scans** | The 2024 amendment caps damages per person, not per scan; filings fell, with about 107 new class actions in 2025 (https://www.lexology.com/pro/content/bipa-complaints-fall-after-2024-amendment-privacy-risks-remain). Illinois-only, with few SMB targets. |
| **TSCA 8(a)(7) PFAS reporting help** | The reporting window was pushed to **31 Jan 2027 or later**, pending a rule revision (https://greensofttech.com/blog-2026-current-status-of-the-tsca-8a7-pfas-reporting-rule/). EPA proposed exempting **article importers**, the SMB segment (https://regbase.com/pfas-reporting-rule). One-time reporting with a moving target suits consultants, not a recurring business. |
| **Minnesota PFAS-in-products reporting** | One-time report plus an $800 fee. The deadline (15 Sep 2026, extendable to 14 Dec 2026) has largely passed (https://www.bdlaw.com/publications/minnesota-extends-pfas-in-products-reporting-deadline-to-september-15-2026/). Enterprise tools (Certivo, Compliance & Risks) own it. *Exception:* state PFAS product **bans** could become a module of Idea 1's catalog scanner. |
| **FMCSA new-authority "DOT compliance" packages** | Scam-saturated; FMCSA issues fraud warnings about compliance-company impersonators (https://www.operatingauthority.com/avoiding-dot-and-mc-authority-scams/, https://www.fmcsa.dot.gov/registration/fraud-alerts). Reputational poison. |
| **FDA 483/warning-letter intelligence for SMBs** | SMBs don't buy intelligence. Redica owns the enterprise segment ($289 per 483: https://www.redica.com/document-store/store/483s). FDA Data Dashboard data is free (https://datadashboard.fda.gov/oii/api/index.htm). |
| **FDA import-refusal → registration/US-agent services for foreign exporters** | Registrar Corp dominates (20k+ companies, $100–500M revenue range: https://www.innovate757.org/hampton-roads-business-directory/business-listing/registrar-corp/). Buyers are overseas, where CAN-SPAM, GDPR and other foreign rules complicate outreach. |
| **CFPB complaint monitoring** | 13.8M complaints, dominated by credit bureaus and big banks. In June 2026 the CFPB itself said volume has "diminished the usefulness of complaint data" (https://www.consumerfinancemonitor.com/2026/06/25/cfpb-announces-major-overhaul-of-consumer-complaint-system-a-shift-toward-integrity-standardization-and-statutory-compliance/). Few SMB buyers. |
| **NHTSA recall outreach for dealers** | Recall Masters already sells a turnkey, OEM-reimbursed recall department with a guaranteed ROI (https://www.recallmasters.com/dealers/). Closed. |
| **MSHA violation feeds** | Data is free and weekly (https://www.msha.gov/data-and-reports/data-sources-and-calculators/data-resources/msha-data-set-resources-gateway), and MshaScan already exists (https://mshascan.com/). The universe is small (low tens of thousands of mines (est.)), with entrenched Part 46/48 trainers. |
| **State AG action monitoring** | Unstructured press releases mostly target large companies. No repeatable SMB trigger. |
| **Generic EPA ECHO violator lists** | Already resold by Apify actors (https://apify.com/nexgendata/epa-echo-enforcement-scraper). Value exists only in niche combinations like Idea 4. |
| **CSLB contractor license/bond/workers' comp lapse leads** | Free CSV files (https://www.cslb.ca.gov/onlineservices/dataportal/ContractorList) are already scraped (https://apify.com/scrapersdelight/cslb-contractor-scraper). Bond and insurance agents already mine them. Possibly viable as a micro-feed, but a weak moat. |
| **ADA lawsuit "just sued" alerts to defendants** | Ambulance-chasing at the worst moment. Defendants need lawyers, not scans. 46% of federal cases are repeat defendants (https://blog.usablenet.com/ada-web-lawsuit-trends-2026), which shows scans after the fact don't help. |

---

## 4. Ranked shortlist

Scores run 1–10; 10 is best. For competition, 10 = blue ocean. **Overall is a judgment-weighted score, not a simple average.** It weights willingness to pay, competition and data accessibility more heavily, because those are what killed most ideas in this lane.

| Rank | Idea | Market size | WTP | Data access | Automation | Competition | Recurring | Time to $1 | **Overall** | Confidence |
|---|---|---|---|---|---|---|---|---|---|---|
| 1 | Prop 65 "Next Defendant" alerts + catalog scan | 6 | 8 | 7 | 8 | 8 | 7 | 7 | **7.4** | Medium. Enforcement volume and settlement data are solid. Unproven: match accuracy and whether retailers pay *before* being noticed. |
| 2 | Restaurant inspection → pest/hood DFY outbound | 6 | 7 | 6 | 7 | 5 | 8 | 9 | **6.8** | Medium. Pest-lead economics are well documented; reply rates from restaurants are unknown. Closest fit to the brothers' existing skills. |
| 3 | OSHA SST target predictor | 6 | 6 | 8 | 8 | 8 | 5 | 5 | **6.5** | Low–medium. Depends entirely on back-test precision against SST inspections; program continuity is a political risk. |
| 4 | CA stormwater citizen-suit risk monitor | 4 | 9 | 7 | 6 | 8 | 7 | 5 | **6.4** | Medium. Huge per-incident pain; small, offline buyer base. |
| 5 | Small-gov Title II PDF/web remediation | 7 | 6 | 9 | 7 | 4 | 7 | 4 | **6.0** | Medium. Real mandate and real money, but crowding and price collapse are under way and procurement is slow. |
| 6 | Supplement/cosmetic claims scanner | 5 | 5 | 8 | 9 | 5 | 6 | 6 | **5.8** | Medium-low. Weak regulatory fear; cheap to build. Best as a module of #1. |
| 7 | OSHA "just cited" kit / consultant feed | 5 | 7 | 9 | 7 | 4 | 3 | 7 | **5.5** | Medium. Real need, but the data is commoditized and revenue is mostly one-off. |
| 8 | FMCSA insurance-lapse feed for agents | 6 | 7 | 9 | 8 | 2 | 8 | 7 | **5.3** | High confidence that it's crowded. |
| 9 | 10DLC website compliance fixer | 6 | 3 | 8 | 9 | 3 | 3 | 6 | **4.5** | High confidence that standalone WTP is weak; useful as a feature of the website product. |

### Recommendation

- **Build #1 (Prop 65) first** as the lane's flagship. A one-week validation test:
  1. Scrape 60 days of notices.
  2. Extract brands and products.
  3. Find other Shopify stores carrying them.
  4. Hand-check 100 matches.
  5. Send 300 free reports.

  **Kill criteria:** match precision below 80% after hand review, or reply-to-call conversion below 2%.
- **Run #2 in parallel as the cash-flow play.** It reuses the brothers' existing outbound and reply-handling stack almost unchanged.
- **Treat #3 as a data-science spike before it is a business.** Back-test the SST score first; abandon it if precision is not clearly above base rates.
- **Fold #6 and #8 into existing products** (#1, and the website business) rather than standing them up separately.
- **Don't enter ADA web scanning, cookie consent, CIPA scans or FMCSA lead data.** They are saturated, commoditized or being legislated away.
