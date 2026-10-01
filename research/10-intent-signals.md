# Lane 10: B2B intent and trigger-event signals for niche verticals

*Research date: 2026-10-01. Research only: no accounts, signups, outreach or purchases. Every material claim has a URL. Anything marked **[EST]** is our own estimate or arithmetic. Anything marked **[3P]** comes from a third-party aggregator or a competitor's blog rather than a primary source. Figures marked **[OWN ANALYSIS]** are counts we computed by downloading the primary dataset (DOL Form 5500 bulk files, CA/WA/OR breach lists, NPPES weekly file, ClinicalTrials.gov API).*

**Bottom line up front.** Raw public-record trigger data is already a commodity in nearly every vertical we checked:
- Apify actors sell it for $0.50–$20 per 1,000 records.
- Small SaaS tools sell it for $29–$300 a month.

The large incumbents (ZoomInfo, Clay, Apollo, Bombora, 6sense) cover the tech and white-collar web-intent world. Their weak flank is SMB, local and regulated businesses: ZoomInfo's own downmarket ACV fell 10% year over year.

The business, if there is one, is not selling signals. It is running the brothers' existing playbook (find prospect, build a personalized deliverable, send outreach, handle replies) on behalf of a high-ticket local seller. Public-record triggers decide who gets contacted and when. A Claude-built artifact decides why the prospect replies.

No idea below scores above 6.5/10, and our confidence is moderate at best.

---

## 1. Lane overview

### 1.1 The incumbents and what they cost

| Player | What it sells | Price | Notes / source |
|---|---|---|---|
| ZoomInfo (GTM) | Contacts plus intent and Copilot | Vendr median $33.5k/yr | FY2025 revenue $1,249.5M (+3%); NRR 90%; downmarket ACV −10% YoY; FY2026 guide ~+1%. CEO blames AI/SEO traffic loss. [Q4'25 call](https://www.fool.com/earnings/call-transcripts/2026/02/09/zoominfo-gtm-q4-2025-earnings-call-transcript/), [Vendr](https://www.vendr.com/marketplace/zoominfo). 10-K flags pay-as-you-go competitors as a risk in SMB and mid-market ([10-K](https://www.sec.gov/Archives/edgar/data/1794515/000179451526000012/zi-20251231.htm)) |
| Apollo.io | Contacts plus Bombora intent and job-change filter | $49–$119/user/mo | ARR ≈ $150M (May 2025) [3P] ([Sacra](https://sacra.com/c/apollo/)) |
| Clay | Enrichment orchestration; signals (job change, news, web intent) | $167–$446/mo and up | ARR ≈ $108M at end of 2025 and $150M in May 2026 [3P] ([Sacra](https://sacra.com/c/clay/)); $3.1B valuation in Aug 2025 ([Crunchbase News](https://news.crunchbase.com/venture/ai-powered-gtm-startup-clay-valuation-doubles-capitalg/)); [pricing](https://www.clay.com/pricing) |
| Bombora | Co-op web-content intent ("Company Surge") | Vendr median $25k/yr | Resold inside Apollo, Common Room and Warmly ([Vendr](https://www.vendr.com/marketplace/bombora)) |
| 6sense | Account intent | Vendr median $62k/yr | [Vendr](https://www.vendr.com/marketplace/6sense) |
| Common Room | Signals plus Bombora | $2,500/mo and up | [pricing](https://www.commonroom.io/pricing/) |
| UserGems | Job-change and champion tracking | $40k–$150k/yr | [pricing](https://www.usergems.com/pricing) |
| Sumble | Job-post-derived tech and project graph | Free; Pro $99/mo | $38.5M raised. Admits it is skewed to English-language, tech-forward companies; manufacturing, financial services and life sciences are listed as future work ([TechCrunch](https://techcrunch.com/2025/10/22/sumble-emerges-from-stealth-with-38-5m-to-bring-ai-powered-context-to-sales-intelligence/), [SiliconANGLE](https://siliconangle.com/2025/10/22/sumble-launches-38-5m-expand-ai-powered-go-market-intelligence-platform/), [pricing](https://sumble.com/pricing)) |
| PredictLeads / TheirStack / Coresignal | Job, news and tech data APIs | From $0.002–$0.04 per call; $49/mo and up | [PredictLeads](https://predictleads.com/pricing), [TheirStack](https://theirstack.com/en/pricing), [Coresignal](https://coresignal.com/pricing/) |
| Unify | Signals including "SMB & local business data" | $20–$60/seat/mo | [pricing](https://www.unifygtm.com/pricing) |

**Signals are commoditizing.** Job-change, hiring, funding, news and tech-stack signals now come bundled at $20/seat (Unify) and $167/mo (Clay Launch).

**AI SDRs show the risk of the "automate outbound" category.** 11x claimed customers it did not have, and former staff described 70–80% churn in early cohorts ([TechCrunch](https://techcrunch.com/2025/03/24/a16z-and-benchmark-backed-11x-has-been-claiming-customers-it-doesnt-have/)). This is a warning for any "we automate outbound" pitch.

### 1.2 The raw public-record layer is also commoditized

| Signal | Free primary source | Existing packagers and prices |
|---|---|---|
| Form D raises | EDGAR, 10 req/s, free ([SEC](https://www.sec.gov/os/accessing-edgar-data)) | Fundz $49–$299/mo ([pricing](https://www.fundz.net/pricing)); FilingFlow $84–$209/mo ([pricing](https://filingflow.app/pricing)); sec-api.io $49–$199/mo ([pricing](https://sec-api.io/pricing)); an Apify actor at $0.025/filing with **2 total users** ([Apify](https://apify.com/publicrecords-api/sec-form-d-api)) |
| WARN notices | ~43 state sites in PDF, Excel, HTML and Tableau ([warn-scraper](https://github.com/biglocalnews/warn-scraper)) | WARN Database API from $9/mo ([pricing](https://layoffdata.com/pricing/)); WARNTracker $250/mo ([pricing](https://www.warntracker.com/pricing)) |
| Form 5500 | DOL EFAST2 bulk CSV, monthly, free ([DOL](https://www.dol.gov/agencies/ebsa/about-ebsa/our-activities/public-disclosure/foia/form-5500-datasets)) | Judy Diamond from $75/mo ([order](https://www.judydiamond.com/order-now/)); FiduciarySignal $90/mo; 401kHunter $100/mo; Form5500Search $49/mo; Medistill $199/mo; BenefitFlow ≈ $14k/yr (see Idea 3) |
| FMCSA new authorities | Census and AuthHist files, free | TruckerDB $49/mo; Carrier Leads Direct $297/mo; Apify $20 per 1k (see Idea 6) |
| Building permits | Municipal | Shovels $599–$999/mo; Permit Ledger $39/mo; PermitStack $19–$49 ([Shovels](https://www.shovels.ai/pricing), [Permit Ledger](https://permitledger.com/blog/building-permit-database-comparison)) |
| New business filings | Secretary of State bulk data (FL free SFTP) | Apify $3–$4 per 1k; NewFilings $99/mo; Data Axle $0.065–$0.30/record ([Apify](https://apify.com/datadeltas/us-new-business-registrations), [NewFilings](https://newfilingalerts.com/)) |
| OSHA citations | DOL API, free | OSHAlert $49–$399/mo ([pricing](https://www.oshalert.com/pricing)) |
| Tech stack | — | BuiltWith $295–$995/mo, and its ToS bans redistribution ([plans](https://builtwith.com/plans), [terms](https://builtwith.com/terms)); Wappalyzer $250–$850/mo ([pricing](https://www.wappalyzer.com/pricing/)) |
| Exhibitor lists | Map Your Show pages | Apify $0.25–$4 per 1k; ExhibitorLens $199/mo ([Apify](https://apify.com/maximedupre/map-your-show-exhibitor-scraper), [ExhibitorLens](https://exhibitorlens.com/)) |

### 1.3 Where the gaps actually are

1. **Interpretation, not access.** Every packager sells rows. Almost none answers "is this record a real buyer, why now, and what do I say?" Some examples of what that would take:
   - Separating a new independent practice from an employed clinician in NPPES data.
   - Separating a liquor-license transfer from a new opening.
   - Separating a fund from an operating company in Form D filings (51% of Form Ds are funds; [SEC Reg D stats](https://www.sec.gov/data-research/statistics-data-visualizations/regulation-d-offerings)).
2. **Cross-source joins in SMB and local verticals.** For example:
   - NPPES with Secretary of State filings.
   - Liquor licenses with building permits.
   - Form 5500 with ATS hiring endpoints.
   - DoD awards with MX records.

   Incumbents stop at the edge of their own dataset.
3. **Fragmented, format-hostile sources.** 50 state alcohol-control agencies, state breach portals and state WARN sites. The moat is maintenance, and it is real but thin, because Apify actors keep appearing.
4. **Doing the outreach itself.** Buyers in these niches (401(k) advisors, MSPs, billing companies, POS reps) are not Clay power users. They pay $250–$800 per appointment to human appointment-setters:
   - MSP appointment setting at $400–$800 per BANT-qualified meeting ([DemandNexus](https://www.demandnexus.io/msp-appointment-setting/)).
   - Fractional CFO appointment setting at $5,250–$14,750/mo ([Alleyoop](https://alleyoop.io/appointment-setting/fractional-cfo-services/)).

   That spend is the wallet to capture, not the $49/mo data-tool wallet.

### 1.4 Data access and legal guardrails (applies to all ideas)

**Safe sources** are government bulk data (EDGAR, DOL EFAST2, NPPES, FMCSA, USAspending, state alcohol-control agencies, state AG breach lists) and official public ATS endpoints:
- Greenhouse and Lever expose unauthenticated GET endpoints ([Greenhouse](https://docs.greenhouse.io/job-board.html), [Lever](https://github.com/lever/postings-api)).
- Ashby's public API includes compensation ([Ashby](https://developers.ashbyhq.com/docs/public-job-posting-api)).

**Avoid:**
- **LinkedIn.** hiQ ended in a $500k consent judgment and a permanent injunction ([Proskauer](https://www.proskauer.com/blog/hiq-and-linkedin-reach-proposed-settlement-in-landmark-scraping-case)); the User Agreement §8.2 bans scraping ([LinkedIn](https://www.linkedin.com/legal/user-agreement)).
- **YouTube captions.** Download requires edit permission on the video, and the developer policies cap storage at 30 days ([captions API](https://developers.google.com/youtube/v3/docs/captions/download), [policies](https://developers.google.com/youtube/terms/developer-policies)).
- **Seeking Alpha transcripts.** The ToS bans scraping and redistribution ([terms](https://about.seekingalpha.com/terms)).
- **Listen Notes caching.** Free and Pro tiers may not store content ([pricing](https://www.listennotes.com/api/pricing/)).
- **BuiltWith resale** ([terms](https://builtwith.com/terms)).
- **NMLS Consumer Access.** The ToS bans using the data to solicit licensees ([NMLS ToU](https://www.nmlsconsumeraccess.org/Home.aspx/TermsOfUse)).
- **SAM.gov point-of-contact emails and phones.** These are FOUO and need a federal account ([GSA Entity API](https://open.gsa.gov/api/entity-api/)).

**Email:**
- CAN-SPAM has no B2B exemption. It requires accurate headers, a postal address and an opt-out honored within 10 business days; penalties run up to $53,088 per email ([FTC](https://www.ftc.gov/business-guidance/resources/can-spam-act-compliance-guide-business)).
- Cold email is legal in the US if you comply. CASL (Canada) and GDPR/PECR (EU and UK) are stricter, so keep every idea US-only.

**Phone:** TCPA applies to autodialed or prerecorded calls and texts to cell phones. Keep phone touches human-dialed.

**Security scanning:** passive DNS, MX, SPF/DMARC and certificate-transparency checks carry low CFAA risk. Active scanning of non-consenting prospects is risky, and a "we found your vulnerabilities" cold email reads as extortion-adjacent ([Van Buren](https://www.supremecourt.gov/opinions/20pdf/19-783_k53l.pdf), [DOJ policy coverage](https://techcrunch.com/2022/05/19/justice-department-good-faith-hackers-cfaa/amp)).

---

## 2. Candidate ideas

The common model for Ideas 1–5 is the "Agency-in-a-box" pattern. We sell a done-for-you, signal-triggered outbound program to a high-ticket local or regional seller:

1. Public records find the prospect.
2. Claude classifies the prospect and builds a one-page personalized artifact (benchmark, readiness brief, opening kit).
3. Outreach goes out under the client's name and domain.
4. Claude triages replies.
5. Booked meetings or warm replies are handed off.

Pricing is a monthly retainer plus an optional per-meeting fee. This mirrors the brothers' website model: the artifact replaces the website mockup.

### Idea 1: "New Practice Radar" for medical billing, credentialing and healthcare-IT firms

**Pitch.** Every week, detect newly formed independent medical, dental and behavioral practices from NPPES plus state business filings. Hand each to a billing or credentialing firm with a ready-to-send, practice-specific "first 90 days of revenue cycle" brief.

**Data sources**

| Source | Access | Cost | ToS / limits |
|---|---|---|---|
| NPPES weekly incremental and monthly full files ([CMS](https://download.cms.gov/nppes/NPI_Files.html)) | Bulk download | Free | Public; no email addresses |
| State Secretary of State new-entity filings (FL free SFTP; CA weekly unload free; IN $35/mo new-filings report) | Bulk ([FL](https://dos.fl.gov/sunbiz/other-services/data-downloads/), [IN fee schedule](https://www.in.gov/sos/business/files/Regulatory-Analysis-Business-Entity-Bulk-Data-Fees-LSA-25-155-OMB-2025-01R.pdf)) | $0–$1,350 per state | Public |
| CMS PECOS enrollment and Medicare opt-in (enrichment) | Bulk | Free | Public |
| Practice website and DNS (does a site exist, which EHR or patient portal) | Passive fetch | ≈ $0 | Low risk |

**Data combination that creates new value.** A new organization NPI is a weak signal on its own, because many are employed-group or hospital subsidiaries. The valuable records come from joining several sources:
- NPI taxonomy
- whether the address matches a known health system
- whether the authorized official is also a newly enumerated or newly relocated individual NPI
- a same-name LLC formed in the last 60 days
- no website or a placeholder site

Together these give a classifier for "an independent practice just opened and has not yet picked billing or IT vendors." Claude is good at this fuzzy entity resolution and taxonomy reasoning.

**Volume.**
- [OWN ANALYSIS] The Sep 21–27, 2026 weekly NPPES file had 11,038 new individual NPIs and 2,499 new organization NPIs, which is about 11k organization NPIs a month.
- [EST] Perhaps 10–25% of those are genuinely independent new practices, about 1–3k a month nationally.

**Buyer persona.** The owner or head of sales at a 5–50-person medical billing / RCM company, a credentialing service, or a healthcare-focused MSP. Secondary buyers are dental-specific billing firms and practice-management consultants.

**Willingness-to-pay evidence**
- Billing firms charge 4–9% of collections, about $1,500–$5,000/mo per small practice ([medicalbillersandcoders](https://www.medicalbillersandcoders.com/blog/how-much-does-medical-billing-cost/), [legitmedbilling](https://legitmedbilling.com/blog/how-much-does-medical-billing-cost)).
- [EST] One client is therefore worth roughly $18k–$60k a year.
- A niche feed already sells new behavioral-health organization NPIs to billing firms at $39/mo ([Actable](https://actablesite.com/npi-leads-for-medical-billing-companies)), which proves the persona buys. Its low price also shows the raw-list ceiling.
- The enterprise alternative is Definitive Healthcare at a median of about $50k/yr ([Vendr](https://www.vendr.com/marketplace/definitive-healthcare)). That is out of reach for a 10-person billing firm, which is the gap.

**Market size**
- IBISWorld counts 1,364 medical billing establishments in its NAICS cut, and that count is declining ([IBISWorld](https://www.ibisworld.com/united-states/industry/medical-billing-services/6341/)). This undercounts the market: many billing firms register under bookkeeping or consulting codes.
- [EST] Bottom-up: about 3–6k billing, RCM and credentialing firms plus about 2–4k healthcare-focused MSPs.
- At a 2% penetration of about 8k firms, that is 160 clients × $750/mo ≈ $1.4M ARR. The realistic ceiling is a $3–8M ARR niche business.

**Deliverable and pricing**
- Tier 1, a self-serve weekly territory feed with classification and "why new": $199–$399/mo per state.
- Tier 2, done-for-you outreach (practice-specific brief plus email sequence plus reply handling): $1,500–$3,000/mo, or $300–$500 per booked meeting.
- Both are recurring.

**Automation pipeline**
- *Find prospects (buyers):* billing firms are easy to list from Google Maps, AAPC/HBMA directories and their websites. Claude scores firms by specialty focus and state.
- *Build deliverable:*
  - Weekly ETL of NPPES and SOS data, then Claude classification and an entity-resolution confidence score.
  - Per-practice brief: specialty payer-mix notes, credentialing timeline, CMS enrollment status, and whether a site exists.
- *Personalized outreach:* first to the billing firm with three real new practices in its state ("here are 3 practices that opened near you this week"). For Tier 2, outreach then goes to the practices under the client's brand.
- *Handle replies:* Claude triages interested, not-now and unsubscribe replies and books onto the client's calendar.
- *Deliver and renew:* weekly digest plus a CRM push; renewal is justified by a monthly "meetings booked" report.

**Percent automatable.**
- [EST] About 85%.
- Human touchpoints remain at onboarding calls, QA of classifier edge cases in the first 4–6 weeks, and the occasional escalated reply.
- There is also a contact-data gap: NPPES has phones, not emails, so getting an email needs enrichment or a mailed letter.

**First 90 days of go-to-market**
- Weeks 1–3: build the classifier for 3 states (FL, TX, CA) and hand-check 200 records for precision.
- Weeks 3–6: send the free "3 new practices this week" sample to about 600 billing firms.
- Weeks 6–12: convert 10–15 firms to Tier 1 and sell Tier 2 to 2–3 firms.
- Target: $5–10k MRR by day 90 [EST].

**Unit economics [EST]**

| Item | Estimate |
|---|---|
| Data | Under $200/mo |
| Claude inference | About $0.01–$0.05 per record across ~10k organization NPIs a month, roughly $100–$500/mo |
| Email infrastructure | About $200/mo |
| CAC | About $300–$800 via cold email to the buyers |
| Gross margin | 85–90% (Tier 1); 70–80% (Tier 2) |

**Competitors and crowding**
- Raw NPI feeds are commoditized: Apify sells them at $0.50 per 1k ([Apify](https://apify.com/scrapesignal_labs/npi-healthcare-provider-leads)).
- Enterprise players (Definitive, IQVIA OneKey) price at $25k–$200k.
- [EST] The mid-market interpreted-feed niche looks open, at 6/10 blue ocean.

**Legal and regulatory**
- NPPES is public, so there is no HIPAA issue: it is provider data, not patient data.
- CAN-SPAM applies, and so do state telemarketing laws if calling. TCPA applies to cell-phone texting, so do not auto-text.
- No licensing requirement.

**Kill risks**
1. Classifier precision is below about 70%, and billing firms churn after receiving employed-physician noise.
2. Low reachability. NPPES has no email, and new practices have thin web presence, so the deliverable becomes physical mail.
3. Billing firms prove to be referral-driven and do not run outbound. Their actual buying behaviour is unverified, and the $39/mo competitor price hints at a low ceiling.

---

### Idea 2: Multi-state "Pre-Opening Radar" for restaurant and bar vendors

**Pitch.** Normalize liquor-license applications across states, plus building permits and new LLC filings, into a weekly "opening in 30–90 days" feed per metro. Each opening comes with a Claude-written opening kit for the vendor (POS, food distributor, linen, hood cleaning, insurance, payroll, beverage reps).

**Data sources**

| Source | Access | Cost | Limits |
|---|---|---|---|
| CA ABC daily New Applications, Issued and Status Change reports, plus daily raw CSV exports ([CA ABC](https://www.abc.ca.gov/licensing/licensing-reports/)) | Download | Free | Public |
| Other state and local alcohol-control agencies (TX TABC, FL DBPR, NY SLA, AZ, etc.) | Mixed: portals, PDFs, some scrape-only | Free, plus engineering time | Check each state's ToS; fragmentation is the moat |
| Building or tenant-improvement permits | Municipal portals, or Shovels | $0–$599/mo | Shovels is credit-metered ([pricing](https://www.shovels.ai/pricing)) |
| Secretary of State new LLCs (name match) | Bulk | $0–$100s per state | Public |

**Data combination.** A new alcohol-license application is early: per the Arizona vendor below, it appears 30–90 days before opening ([Liquor License Leads](https://liquorlicenseleads.com)). Two additions turn it into a better prospect:
- Separating new premises from transfers and ownership changes. Claude reads license type, prior licensee at the address and status codes.
- Adding the tenant-improvement permit and the LLC officer, which gives concept, size and owner name.

**Volume.**
- [OWN ANALYSIS] CA ABC's Sep 30, 2026 new-applications report had 38 entries, 19 of them restaurant license types 41/47.
- [EST] That is about 800 applications a month in CA, about half restaurants.
- Nationally, about 27,600–50,000 restaurant openings a year ([RestaurantData](https://restaurantdata.com/new-restaurant-openings-trends-for-4-5-years-since-the-pandemic/), [OysterLink](https://oysterlink.com/spotlight/us-restaurant-industry-statistics-2025/)).

**Buyer persona.**
- Territory sales reps and managers at POS resellers (Toast, Square and Clover independent resellers).
- Broadline and specialty food distributors.
- Linen and uniform companies.
- Hood and grease-trap cleaners.
- Restaurant insurance agents.
- Beer and wine distributor reps.

**Willingness-to-pay evidence**
- Restaurant Activity Report sells from $99/mo per trade area across 83 areas ([FAQ](https://restaurantactivityreport.com/faq/)).
- Liquor License Leads (Arizona only) charges $29/mo for Phoenix and $79/mo statewide ([site](https://liquorlicenseleads.com)).
- RecordPipe offers custom liquor feeds from $5,000 ([RecordPipe](https://recordpipe.com/leads/liquor-license-leads.html)).
- [EST] Per-buyer willingness to pay is real but low ($29–$199/mo). The model only works if one record is sold to many vendor categories.

**Market size [EST, bottom-up].**
- Assume roughly 20k POS, distributor, linen, hood and insurance reps or owners in the top 50 metros, with 2% at $149/mo.
- That gives 400 × $149 ≈ $0.7M ARR. Done-for-you tiers for distributors would add to it.
- This is small, a lifestyle-scale business unless it expands to adjacent triggers (new medical and dental offices, new gyms).

**Deliverable and pricing**
- $79–$199/mo per metro per vendor category, self-serve.
- $1,000+/mo for done-for-you outreach to openings, where Claude drafts a concept-specific pitch, e.g. "your 40-seat taqueria opening on Elm St: here's a hood-cleaning schedule required by fire code."
- Recurring.

**Automation pipeline**
- *Find prospects (buyers):* scrape vendor directories, Toast and Square partner lists, and distributor branch locators.
- *Build:* per-state parsers (Claude-assisted parser maintenance when formats change), dedupe, transfer-versus-new classification and owner lookup.
- *Outreach:* "5 restaurants opening in your territory next month, free sample."
- *Replies:* triaged by Claude.
- *Deliver and renew:* weekly email digest and CSV; renewal is self-serve via Stripe.

**Percent automatable.**
- [EST] About 90%.
- Humans handle new-state parser setup, the occasional legal review of a state's terms, and support.

**First 90 days of go-to-market.**
- Launch CA, TX and FL in the first 45 days.
- Cold-email about 3,000 vendor reps in those states with a free 2-week sample.
- Target 60 subscribers, about $6–9k MRR, by day 90 [EST].

**Unit economics [EST].**
- Data cost is close to $0 (engineering only).
- CAC about $150–$300.
- Price about $129/mo, gross margin about 90%.
- Churn risk is high: individual reps change jobs.

**Competitors.**
- Restaurant Activity Report and RestaurantData ([RestaurantData](https://restaurantdata.com/)).
- Single-state liquor-lead sites.
- Apify liquor actors at $3–$5 per 1k ([Apify](https://apify.com/registryfeeds/liquor-license-monitor)).
- **Moderately crowded on raw data. Classification across many states plus the per-vendor-category kit is the differentiation.** About 6/10 blue ocean.

**Legal.**
- Public data. CAN-SPAM applies.
- Some state alcohol-control portals may restrict bulk automated access, so verify each one.
- Owners' personal mailing addresses in alcohol-license data are personal data under CCPA, so B2B use requires CCPA notices for California residents [EST].

**Kill risks**
1. Low average price and high churn among individual sales reps, so LTV:CAC is thin.
2. Maintaining parsers across states costs more than the revenue per state.
3. Toast and Square already have in-house prospecting teams buying the same data cheaply, so the biggest buyers do not need us.

---

### Idea 3: Event-layered 401(k) and benefits prospecting with a personalized plan benchmark, done for the advisor

**Pitch.** For a retirement-plan advisor or benefits broker, monitor target plan sponsors for fresh non-5500 events: hiring surges via ATS endpoints, Form D raises, 8-K M&A, HR leadership changes, and nearing the audit threshold. When an event fires, Claude produces a one-page fiduciary benchmark from the sponsor's own 5500 and sends it in the advisor's name.

**Data sources**

| Source | Access | Cost | Limits |
|---|---|---|---|
| DOL EFAST2 Form 5500, 5500-SF and Schedules A, C, H, I | Monthly bulk CSV, anonymous ([DOL](https://www.dol.gov/agencies/ebsa/about-ebsa/our-activities/public-disclosure/foia/form-5500-datasets)) | Free | Public information ([Schedule C instructions](https://www.dol.gov/sites/dolgov/files/ebsa/employers-and-advisers/plan-administration-and-compliance/reporting-and-filing/form-5500/2025-instructions.pdf)) |
| Greenhouse, Lever and Ashby job boards | Public JSON | Free | Official endpoints |
| EDGAR Form D and 8-K | API | Free | 10 req/s with a User-Agent header |
| PredictLeads job and news events (optional) | API | From $40/mo ([pricing](https://predictleads.com/pricing)) | Commercial license |

**Data combination.** The 5500 alone is old. Combined with a fresh trigger, it becomes timely: "you raised a Series B and posted 22 jobs, your plan is at 0.9% all-in versus a peer median of 0.5%, and your plan will cross the audit threshold next year."

**Why 5500 alone fails**
- [OWN ANALYSIS] 2024 filings arrived mostly from August to October 2025, with about 19% trickling in until September 2026. The effective signal age is about 8–21 months.
- [OWN ANALYSIS] 62.1% of Schedule A health contracts renew in January.
- Fewer than 5% of plans changed recordkeeper in 2025 ([401k Specialist / Cerulli](https://401kspecialistmag.com/client-satisfaction-key-for-growth-among-recordkeepers/)).
- [OWN ANALYSIS] Year over year, only 2.6–4.7% of welfare plans fully replaced their broker.

**Buyer persona.**
- Plan-focused advisors at RIAs and broker-dealers.
- Benefits producers at independent agencies with 5–100 producers.
- [OWN ANALYSIS] 7,480 distinct advisory-firm EINs appear on 2024 Schedule C, and about 1,000 of them appear on 5 or more plans.

**Willingness-to-pay evidence**
- ERISApedia Plan Data Intelligence costs $2,087 per user per year ([pricing](https://www.erisapedia.com/pricing/)).
- BenefitFlow averages about $14.4k/yr across 5 Vendr deals ([Vendr](https://www.vendr.com/buyer-guides/benefitflow)).
- AdvizorPro PlanPro is about $5k–$15k/yr [3P] ([Tomba](https://tomba.io/blog/advizorpro-pricing-reviews-pros-and-cons)).
- Retirement Plan Sales Associates average about $100k ([Glassdoor](https://www.glassdoor.com/Salaries/retirement-plan-sales-associate-salary-SRCH_KO0,31.htm)).
- Internal wholesalers average about $151k ([Glassdoor](https://www.glassdoor.com/Salaries/internal-wholesaler-salary-SRCH_KO0,19_IP2.htm)).
- One plan win is worth a lot: a $5M plan at 0.37% is about $18.5k/yr ([401k Averages Book via 401k Specialist](https://401kspecialistmag.com/new-401k-averages-book-finds-plan-fees-still-falling-cost-disparities-persist/)).
- Group health commissions run about $12–$18 PEPM for 100–499 lives ([Upcision](https://upcision.com/group-health-insurance/group-health-broker-commissions-by-group-size-2026-benchmark/)).

**Market size.**
- Supply side: 724,720 401(k)-type plans and 83,031 large 401(k) plans in 2023 ([DOL bulletin](https://www.dol.gov/sites/dolgov/files/ebsa/researchers/statistics/retirement-bulletins/private-pension-plan-bulletins-abstract-2023.pdf)).
- Cerulli expects micro plans to exceed 1M by 2029 and more non-specialist advisors to sell plans ([PlanAdviser](https://www.planadviser.com/micro-401k-plan-market-ripe-non-specialist-adviser-growth/)).
- [EST] Buyers: about 3–8k plan-focused advisor teams plus about 9k active benefits agencies. At 1% of about 15k, that is 150 × $1,000/mo ≈ $1.8M ARR.

**Deliverable and pricing.**
- $750–$2,000/mo per advisor team for done-for-you: monitoring 500–2,000 territory sponsors, auto-built benchmark PDFs, sequences and reply triage.
- Optional $250 per booked meeting with a qualified sponsor (CFO or HR head).
- Recurring.

**Automation pipeline**
- *Find buyers:* Schedule C EINs to advisor firms; FINRA BrokerCheck; NAPA Top DC Advisor lists.
- *Build:* monthly 5500 ETL; daily ATS and EDGAR polling; Claude writes the benchmark ("your fees, peers, red flags") and the "why now" hook.
- *Outreach:* email to the sponsor CFO or HR lead, sent from the advisor's domain.
- *Replies:* Claude classifies replies and drafts a response with the advisor's compliance-approved language.
- *Deliver and renew:* a monthly pipeline report.

**Percent automatable.**
- [EST] About 75%.
- The main human touchpoint is **broker-dealer and RIA compliance pre-approval of templates**. FINRA Rule 2210 governs communications with the public by registered reps; RIAs are under the SEC Marketing Rule. Plus advisor onboarding.

**First 90 days of go-to-market.**
- Pilot with 5 benefits agencies first, because insurance producers face lighter content-approval burdens than securities reps [EST].
- Offer free 50-plan territory benchmarks to about 400 agencies from Schedule A broker names. Use office-level contacts, since Schedule A shows hub entities ([Benefeature](https://benefeature.com/benefeature-vs-benefitflow/)).
- Target 5–8 clients, about $6–12k MRR [EST].

**Unit economics [EST].**
- Data cost about $0–$100/mo.
- Claude cost about $0.05–$0.20 per benchmark.
- CAC about $1,000–$2,500 because of the compliance-heavy sales cycle.
- Gross margin about 80%.

**Competitors.**
- **Crowded and pricing-compressed on data:**
  - FiduciarySignal $90/mo, with switch prediction.
  - 401kHunter $100/mo, with fee grades.
  - Form5500Search $49/mo, with lists of recordkeeper changers.
  - Medistill $199/mo, with commission benchmarking.
  - RiXtrema 401kAI already drafts emails ([401k Specialist](https://401kspecialistmag.com/rixtrema-unveils-pair-of-ai-tools-for-401k-plan-advisors/)).
  - Sources: [FiduciarySignal](https://www.fiduciarysignal.com/tools/best-401k-prospecting-tools), [401kHunter](https://www.401khunter.com/), [Form5500Search](https://form5500search.com/), [Medistill](https://medistill.ai/industries/benefits-brokers).
- The open slot is "fresh trigger + done-for-you execution," at about 4/10 blue ocean.

**Legal.**
- Form 5500 data is public.
- FINRA 2210 / SEC Marketing Rule if we send on behalf of registered reps: we are a vendor, not a broker-dealer, but **content must be approved by the client's compliance team** [EST].
- CAN-SPAM. Sponsors are businesses.

**Kill risks**
1. Plan sponsors are already over-solicited: Fidelity found competitor solicitation doubled ([401k Specialist](https://401kspecialistmag.com/nearly-half-of-plan-sponsors-considering-changing-advisors-recordkeepers/)). Benchmark emails become noise.
2. Compliance approval friction kills the speed and automation advantage with broker-dealer-affiliated advisors.
3. Incumbents (RiXtrema, AdvizorPro) add ATS and Form D triggers within a year, collapsing the differentiation.

---

### Idea 4: FTC Safeguards Rule "gap brief" outbound engine for MSPs serving tax preparers, auto dealers and small financial firms

**Pitch.** Build MSPs a vertical-targeted pipeline. Claude assembles a passive, public-only posture brief per covered firm (email authentication, M365 vs. consumer mail, site TLS and CMS age) and maps it against the FTC Safeguards Rule checklist. The MSP sends it as a compliance conversation-starter, not a "we hacked you" note.

**Data sources**

| Source | Access | Cost | Limits |
|---|---|---|---|
| IRS PTIN holder FOIA file (CSV, semiannual) ([IRS](https://www.irs.gov/tax-professionals/ptin-information-and-the-freedom-of-information-act)) | Download | Free | FOIA release; fields not verified [EST: name and business address] |
| IRS preparer directory with credentials ([RPO](https://irs.treasury.gov/rpo/rpo.jsf)) | Web search | Free | No bulk export |
| Auto dealers (state DMV dealer license lists, OEM dealer locators) | Mixed | $0 to modest | Verify each source's ToS |
| DNS, MX, SPF/DMARC, CT logs (crt.sh) | Passive | Free | Low CFAA risk if passive |
| *Not* NMLS (ToS bans solicitation) | — | — | [NMLS ToU](https://www.nmlsconsumeraccess.org/Home.aspx/TermsOfUse) |

**Data combination.** Three inputs combine:
- A regulatory status (covered "financial institution" under the Safeguards Rule; [FTC](https://www.ftc.gov/business-guidance/resources/ftc-safeguards-rule-what-your-business-needs-know)).
- A passive technical posture (no DMARC, consumer Gmail, an outdated site).
- Peer-pressure context (local breach notices from WA's structured API, which includes cause, industry and ransomware fields: [data.wa.gov](https://data.wa.gov/resource/sb4j-ca4h.json)).

Generic MSP outreach lacks the regulatory hook. Generic scanners (EasyDMARC, Guardz) lack the vertical targeting.

**Buyer persona.** MSP owners with 3–50 staff who want a financial or compliance vertical. Secondary buyers are vCISO/WISP consultants.

**Willingness-to-pay evidence**
- MSPs pay $400–$800 per qualified meeting ([DemandNexus](https://www.demandnexus.io/msp-appointment-setting/)) and under $350 per lead ([TopLead](https://www.toplead.io/feeds/blog/results-appointment-setting-managed-services)).
- A Safeguards client is worth $1,200–$4,000/mo in retainer plus $4k–$18k in program build [3P] ([getcybr](https://getcybr.com/insights/msp-ftc-safeguards-rule-service-line/)).
- WISP-only products sell at $749–$999/yr ([Bellator](https://bellatorcyber.com/blog/ftc-safeguards-rule-for-tax-preparers), [Verito](https://verito.com/blog/how-to-comply-with-ftc-safeguards-rule/)).
- MSP MRR per client: the median band is about $1,000–$2,500/mo ([Kaseya 2024 benchmark](https://www.kaseya.com/wp-content/uploads/dlm_uploads/2024/03/Whitepaper-2024-MSP-Benchmark-Survey_Kaseya.pdf)).

**Market size.**
- Buyers: about 10.4k managed-IT firms headquartered in the US ([RevenueBase](https://revenuebase.ai/companies/managed-it-service-providers/united-states)). CompTIA's "100k+" includes resellers ([CompTIA](https://www.comptia.org/en-eu/blog/your-next-move-msp-personnel/)).
- [EST] 1.5% of about 10k MSPs gives 150 × $1,500/mo ≈ $2.7M ARR.

**Deliverable and pricing.**
- $1,000–$2,500/mo done-for-you campaign per MSP per territory and vertical, or $300–$450 per booked meeting.
- Recurring. Territory exclusivity adds urgency.

**Automation pipeline**
- *Find MSPs:* Google Maps, CompTIA and Channel Futures lists, and MSP websites. Claude checks vertical fit.
- *Build:* ingest the PTIN file and dealer lists, resolve domains, run passive checks, and have Claude write a one-page "Safeguards readiness snapshot" with plain-language FTC citations.
- *Outreach:* from the MSP's domain, to the firm owner.
- *Replies:* Claude triages; it books meetings or sends the full snapshot.
- *Deliver and renew:* monthly meetings report.

**Percent automatable.** About 80% [EST]. The humans are the MSP doing the meeting, and our QA of snapshots for tone and accuracy.

**First 90 days of go-to-market.**
- Pick one vertical (tax preparers) and time it with tax season: IRS PTIN renewal in the fall and the pre-season security push [EST].
- Pitch 300 MSPs with a free sample of 10 snapshots for their ZIP codes.
- Target 8–10 MSPs, about $10–15k MRR.

**Unit economics [EST].** Data $0. Claude about $0.02 per snapshot. CAC about $800. Gross margin about 80%.

**Competitors.**
- Outside-in "risk report as door-opener" is crowded:
  - ThreatMate Growth Engine ([pricing](https://threatmate.com/pricing/)).
  - Guardz free prospecting reports ([pricing](https://guardz.com/pricing/)).
  - EasyDMARC MSP reports ([EasyDMARC](https://easydmarc.com/blog/improvements-to-domain-scanner-streamline-your-dmarc-journey/)).
  - Coalition Control, free ([CISA](https://www.cisa.gov/resources-tools/services/coalition-control-scanning)).
- Vertical regulatory targeting plus done-for-you outreach is less crowded, about 5/10.

**Legal.**
- Keep scanning passive.
- Do not claim a firm is "non-compliant." Frame findings as observations, to avoid defamation and unfair-practice risk [EST].
- CAN-SPAM applies.
- Verify that the PTIN FOIA file contents allow solicitation use. IRS releases it publicly, but fields and terms are unverified.

**Kill risks**
1. Tax preparers and small dealers are price-sensitive and buy a $999 WISP template instead of a $1,500/mo MSP, so MSPs see poor close rates.
2. Free insurer and vendor scanners make the snapshot feel generic.
3. Thin contact data: many preparers are solo with only a phone number.

---

### Idea 5: Defense industrial base "CUI readiness" radar for CMMC consultants, MSPs and DCAA accountants (downgraded)

**Pitch.** Find small DoD prime and sub awardees, especially first-time ones, from USAspending. Join them with passive email-tenant detection: commercial M365 vs. GCC High, where GCC High MX records end in `mail.protection.office365.us` ([Microsoft](https://learn.microsoft.com/en-us/microsoft-365/enterprise/dns-records-for-office-365-gcc-high?view=o365-worldwide)). Add job posts mentioning CUI or NIST 800-171. Rank who is likely handling CUI on non-compliant infrastructure.

**Data.**
- USAspending API: free, no key, with NAICS and PSC on contracts ([guide](https://www.usaspending.gov/federal-spending-guide)).
- SAM entity API: public fields only; POC contact details are FOUO ([GSA](https://open.gsa.gov/api/entity-api/)).
- DNS (free) and ATS endpoints (free).
- Caveat: DFARS 252.204-7012 clause presence is **not** in USAspending, so CUI handling has to be inferred [EST].

**Combination value.** "Has DoD contracts" plus "is on commercial M365 / Google Workspace" plus "hiring for a cleared or ITAR role" is a sharp, novel readiness gap. Nobody sells this cut. [EST; no vendor found in our search.]

**Buyer.**
- Cyber-AB RPOs: 387 RPOs and 103 C3PAOs as of March 2026 ([Secureframe](https://secureframe.com/blog/cmmc-ecosystem)).
- About 3,607 unique entities in the Cyber AB marketplace ([Defense Compliance Report](https://thedefensecompliancereport.com/cmmc-provider-directory/)).
- Plus DIB-focused MSPs and GovCon accountants.

**Willingness to pay.**
- DoD models a small firm's Level 2 C3PAO path at $104,670 over 3 years, excluding remediation ([Federal Register 32 CFR 170](https://www.govinfo.gov/content/pkg/FR-2024-10-15/html/2024-22905.htm)).
- Consulting is reported at $75k–$150k in year one [3P] ([cispoint](https://cispoint.com/2026/01/26/cmmc-compliance-costs-what-defense-contractors-actually-pay-in-2026/)).

**Market size.** DoD awards 7012 contracts to 31,338 unique awardees a year, of which 23,475 are small (same Federal Register source). New small-business federal entrants number about 7.5k–8.3k a year ([Third Way](https://www.thirdway.org/report/12-solutions-for-small-business-success-in-federal-contracting)).

**Pricing.** $500–$1,500/mo per consultant per region feed. Done-for-you outreach at $2–4k/mo.

**Pipeline and automation.** Same structure as Idea 4; about 80% automatable. Contacts need enrichment because SAM POCs are gated.

**Unit economics [EST].** Data $0. CAC about $1,000. Gross margin about 85%.

**Competitors.** HigherGov $500/yr and GovWin about $29k/yr are opportunity tools, not readiness-gap tools ([HigherGov](https://www.highergov.com/pricing/), [civiciq](https://civiciq.com/blog/govwin-iq-pricing-2026)). About 7/10 blue ocean on the specific cut.

**Legal.** Passive DNS only. Avoid any implication of knowing someone handles CUI. CAN-SPAM. Export-control-sensitive language should be avoided.

**Why it is downgraded: the decisive fact.**
- **DoD suspended CMMC Phase 2** (mandatory C3PAO certification, planned for Nov 10, 2026) on **July 13, 2026**, and opened a 60-day Reform Task Force review.
- The SBA praised the pause, citing costs "approaching as much as $600,000."
- Sources: [Federal News Network](https://federalnewsnetwork.com/cybersecurity/2026/07/pentagon-suspends-cmmc-phase-two-requirements-launches-review-of-program/), [Wiley](https://www.wiley.law/alert-DOD-Pauses-CMMC-2-0-Implementation-A-Big-Deal-with-Little-Immediate-Impact), [Inside Government Contracts Sept 2026](https://www.insidegovernmentcontracts.com/2026/09/cmmc-reform-task-force-updates-september-2026/).
- The deadline that created urgency is gone until the task force reports, expected late September or early October 2026.

**Kill risks**
1. Reform permanently softens requirements, so demand evaporates.
2. GCC High detection is a weak proxy; many CUI handlers use enclaves rather than tenant-wide GCC High [EST].
3. The RPO market is small (387) and saturated with marketing noise.

**Verdict.** Revisit when the task force report lands. Build only if Phase 2 gets a firm new date.

---

### Idea 6: Trucking insurance renewal and lapse radar (insurance-filing interpretation, not "new authority")

**Pitch.** Infer each carrier's renewal month and current insurer from FMCSA insurance filings (ActPendInsur and InsHist). Flag pending BMC-35 cancellations (30-day lapse risk) and carriers whose insurer just exited the market. Sell to commercial-auto agents as a ranked weekly call list.

**Data.**
- data.transportation.gov ActPendInsur / InsHist: free; fields include effective date, cancel-effective date, insurer and cancellation method ([ActPendInsur](https://data.transportation.gov/Trucking-and-Motorcoaches/ActPendInsur/chgs-tx6x), [InsHist](https://catalog.data.gov/dataset/inshist)).
- The legacy InsHist stopped updating on May 14, 2026, after the Motus migration ([data.gov](https://catalog.data.gov/dataset/motus-inshist-all-with-history), [DISA](https://disa.com/news/fmcsa-motus-registration-system-2026/)).
- BMC-35 requires 30 days' notice ([49 CFR 387.313](https://www.govinfo.gov/content/pkg/CFR-2008-title49-vol5/pdf/CFR-2008-title49-vol5-sec387-313.pdf)).

**Combination.** Insurer, effective-date anniversary, fleet size from the Census file, and inspection/OOS rates. Claude assigns a "shoppable now" score and writes the opener.

**Buyer.** Commercial trucking insurance agents. New-authority premiums run about $900–$2,500+ per truck per month ([American Truckers](https://www.americantruckersllc.com/blog/best-trucking-insurance-new-authority-2026.html)), so lead value is high.

**Willingness to pay.**
- Carrier Leads Direct $297/mo ([site](https://www.carrierleadsdirect.com/)).
- PollyAI $39 plus $40 per state per month, already advertising "insurance expiration date" targeting ([PollyAI](https://getpollyai.com/blog/best-trucking-insurance-leads)).
- Shared quote leads at $30–$75 each.

**Market size.** No reliable agent count was found. [EST] Low thousands of specialized agencies, giving a $1–2M ARR niche ceiling.

**Pricing.** $199–$499/mo per state.

**Automation.** About 90%.

**Competitors.** **Very crowded:**
- TruckerDB $49/mo ([TruckerDB](https://www.truckerdb.com/motor-carrier-leads)).
- TruckingSignal already runs automated outreach in the agent's name with state exclusivity ([TruckingSignal](https://www.truckingsignal.com/)).
- PollyAI sells expiration-date targeting.
- About 2/10 blue ocean.

**Legal.** Public data. TCPA risk is high because agents call mobile numbers, so no auto-dialing or texting. CAN-SPAM.

**Kill risks**
1. Crowded, with TruckingSignal and PollyAI already doing this.
2. Carriers get 6+ calls before lunch ([TruckingSignal](https://www.truckingsignal.com/)).
3. FMCSA data-platform churn (Motus) breaks pipelines.

---

### Idea 7: Operating-company Form D feed for fractional CFOs, fund administrators and D&O brokers

**Pitch.** A daily feed of genuinely operating companies (not funds or SPVs) that just raised. Claude classifies issuers, writes a "finance-stack needs at this stage" note, and drafts outreach for fractional CFO firms.

**Data.** EDGAR, free. 34,553 new Form Ds in 2025, of which 17,593 were pooled funds and 16,960 non-fund ([SEC Reg D stats](https://www.sec.gov/data-research/statistics-data-visualizations/regulation-d-offerings)). Filing is not a condition of the safe harbor, so coverage is incomplete ([DERA](https://www.sec.gov/files/dera-offering-reg-d-cf-2504.pdf)).

**Combination.** Form D, plus ATS hiring (no finance roles posted), plus website and LinkedIn-free enrichment. The output is "raised $3M, 12 people, no controller, no CFO posting."

**Buyer.** Fractional CFO and outsourced accounting firms. Weak stat: about 2,500 providers [3P] ([Gitnux](https://gitnux.org/fractional-cfo-industry-statistics/)). Pilot CFO services start at $1,750/mo ([Pilot](https://pilot.com/pricing)).

**Willingness to pay.**
- These firms pay $5,250–$14,750/mo for appointment setting, but it is sourced from ZoomInfo funding data, not Form D ([Alleyoop](https://alleyoop.io/appointment-setting/fractional-cfo-services/)).
- Our agent found **no** job postings or case studies of CFO firms using Form D.

**Pricing.** $1–3k/mo done-for-you.

**Automation.** About 85%.

**Competitors.**
- Fundz $49/mo and up; FilingFlow; Crunchbase $49–$199/mo; and a Form D Apify actor with only 2 users, a sign of weak demand for raw Form D.
- About 3/10 blue ocean.

**Legal.** Public data. CAN-SPAM.

**Kill risks**
1. After stripping funds, real estate and SPVs, the real lead pool is probably fewer than 10k a year [EST], and the same companies are hammered by every vendor.
2. Funding is the most-commoditized signal in the market.
3. Unproven willingness to pay for this specific source.

---

## 3. Ideas considered and rejected

| Idea | Why it was killed (evidence) |
|---|---|
| **WARN notices → outplacement / staffing** | Outplacement vendors are selected *before* the reduction event ([Careerminds](https://careerminds.com/blog/what-is-outplacement-anyway)). Only about 3–4.5k notices a year, about 12–18 per business day ([Cleveland Fed](https://www.clevelandfed.org/publications/economic-commentary/2019/ec-201921-advance-layoff-notices-as-labor-market-indicator), [layoffalert](https://layoffalert.org/layoffs-2025) [3P]). Data is already $9/mo via API ([layoffdata](https://layoffdata.com/pricing/)). State Rapid Response teams provide free outplacement ([Mass.gov](https://www.mass.gov/doc/rapid-response-services-factsheet/download)). No buyer job posts mention WARN monitoring. |
| **State AG breach notices → cyber MSPs** | Fewer than 2k notices a year across the structured states ([OWN ANALYSIS] CA 565, WA 209, OR 248 in 2025; [CA list](https://oag.ca.gov/privacy/databreach/list), [WA API](https://data.wa.gov/resource/sb4j-ca4h.json), [OR](https://justice.oregon.gov/consumer/DataBreach/)). Breached firms already have counsel and an incident-response firm when notices post. Maine's database is offline due to abuse ([Maine AG](https://www.maine.gov/agviewer/content/ag/985235c7-cb95-4be2-8792-a1252b4f8318/list.html)). Kept only as content and context in Idea 4. |
| **Generic outside-in cyber risk reports** | Free from Coalition, UpGuard, SecurityScorecard and EasyDMARC, and bundled in ThreatMate and Guardz (see Idea 4 sources). |
| **CRE tenant-rep / relocation from hiring growth** | Lease expiry, the decisive variable, is proprietary (CompStak, CoStar; [CompStak Prospect](https://compstak.com/prospect)). Hiring is a noisy space proxy in a hybrid world. Cheap entrants already exist: Scayled at $59–$119/mo and BrokerHQ ([BrokerHQ](https://www.brokerhq.ai/resources/tenant-rep-broker-software-gap-2026)). |
| **Building permits → contractors / solar** | The most crowded vertical; prices compressed to $19–$39/mo; a pulled permit usually means a contractor is already hired ([JLC](https://www.jlconline.com/business/sales-marketing/pulled-permits-as-a-source-of-leads)). |
| **New business formation lists** | Fractions of a cent per record ([Apify](https://apify.com/deadwood_data_solutions/texas-new-business-leads)). Most filings are holding LLCs with registered-agent addresses. Buyers are spam-saturated. |
| **OSHA citations → safety consultants / P&C agents** | OSHAlert at $49–$399/mo plus 6+ Apify actors; a 30–60 day lag; no evidence that P&C agents buy ([OSHAlert](https://www.oshalert.com/pricing)). Possible niche for OSHA defense lawyers, but too small. |
| **RIA / Form ADV triggers (new RIAs, breakaways)** | Data is free and daily ([SEC IAPD](https://adviserinfo.sec.gov/compilation)), but AdvizorPro ($5k–$15k/yr), FINTRX ($10k–$20k) and Discovery Data already sell advisor-move and new-RIA alerts ([Tomba](https://tomba.io/blog/advizorpro-pricing-reviews-pros-and-cons), [Dakota](https://www.dakota.com/resources/blog/the-top-financial-advisor-databases-for-2025)). About 1.3–1.5k new SEC RIAs a year ([InvestmentNews](https://www.investmentnews.com/goria/practice-management/ria-industry-hits-record-highs-across-the-board-in-2025-as-assets-surge-22/266865)). |
| **8-K exec changes / Form 4 liquidity** | sec-api.io extracts Item 5.02 at $49–$199/mo ([pricing](https://sec-api.io/pricing)). Wealth-event tools (Aidentified, FINTRX, Verity) cover the rest. Public companies only, so no SMB angle. |
| **Earnings-call transcript niche mentions** | Licensing blocks redistribution (Seeking Alpha ToS; FMP needs a display license; Quartr is contract-only). AlphaSense at about $18k/seat already does keyword alerts ([Vendr](https://www.vendr.com/marketplace/alphasense)). Covers only public companies. |
| **Podcast / YouTube transcript signals** | YouTube captions are not downloadable for third-party videos, and storage is capped at 30 days. Podscan already sells mention alerts at $100–$2,500/mo ([Podscan](https://podscan.fm/pricing)). Low buying-intent density. |
| **Conference exhibitor lists** | $0.25–$4 per 1k on Apify; list prices are collapsing. Exhibitors are a list, not a trigger. |
| **Job-posting tech-stack intelligence** | Sumble ($38.5M raised, free/$99), TheirStack, PredictLeads and Coresignal cover it cheaply. A head-on fight with funded players. |
| **ClinicalTrials.gov → CROs** | Registration is due up to 21 days *after* first enrollment ([42 CFR 11.24](https://www.law.cornell.edu/cfr/text/42/11.24)). CROs are chosen earlier. Citeline Trialtrove dominates. |
| **DNS / SSL / app-store changes as a standalone feed** | An MX move to M365 means a partner has already been chosen. Certificate-transparency data (crt.sh) is unreliable under load. App-store changes are relevant only to mobile-app vendors, a narrow and tech-native space where incumbents (Sensor Tower-type tools) operate. Used only as enrichment in Ideas 1, 4 and 5. |
| **"Signal-as-a-service" newsletter (generic)** | We found no revenue disclosures for lead-list newsletters. Every raw feed is replicable by an Apify actor in a weekend. Kept only as the Tier-1 self-serve layer within Ideas 1 and 2. |
| **Form 5500 data product (pure)** | Six or more vendors at $25–$199/mo with fee grades, switch prediction and broker-change lists (Idea 3 sources). Only survives as Idea 3's trigger + done-for-you variant. |

---

## 4. Ranked shortlist

Scores run 1–10, where 10 is best. For competition, 10 means blue ocean. Overall is our judgment-weighted score, not a simple mean: it weights willingness to pay, competition and time to first dollar more heavily.

| Rank | Idea | Mkt size | WTP | Data access | Automation | Competition | Recurring | Time to $1 | **Overall** | Confidence |
|---|---|---|---|---|---|---|---|---|---|---|
| 1 | **New Practice Radar** (NPPES + SOS → billing / credentialing / healthcare MSPs) | 5 | 7 | 8 | 8 | 6 | 8 | 7 | **6.5** | Medium-low (buyer outbound behaviour unverified) |
| 2 | **FTC Safeguards gap-brief engine for MSPs** | 6 | 6 | 7 | 8 | 5 | 8 | 7 | **6.0** | Medium-low |
| 3 | **Pre-Opening Radar** (multi-state alcohol licenses + permits) | 4 | 4 | 7 | 9 | 6 | 7 | 8 | **5.5** | Medium |
| 4 | **Event-layered 401(k)/benefits + benchmark, done-for-you** | 6 | 8 | 9 | 6 | 4 | 8 | 4 | **5.5** | Medium |
| 5 | **DIB CUI-readiness radar** | 4 | 8 | 6 | 8 | 7 | 7 | 3 | **4.5** | Low (policy paused) |
| 6 | **Trucking insurance renewal / lapse radar** | 4 | 6 | 6 | 9 | 2 | 8 | 7 | **4.0** | Medium |
| 7 | **Operating-company Form D feed for fractional CFOs** | 3 | 4 | 9 | 9 | 3 | 7 | 6 | **3.5** | Medium |

### Honest takeaways

1. **This lane is weaker than the brothers' core website business.** Signals are a crowded, deflating market. The trend is toward $0.002–$0.04 per call APIs and $20/seat bundles, and the AI-SDR category has documented churn and credibility problems.
2. **Price for the meeting, not the data.** What survives is the appointment-setting wallet ($250–$800 per meeting, $3k–$15k/mo retainers) in fragmented local B2B services, plus the interpretive layer that cheap scrapers lack: classification, joins and a personalized artifact.
3. **Cheapest test.** Run Idea 1 (New Practice Radar) in 3 states for 6 weeks. Measure classifier precision against 200 hand-checked records, and see whether 600 billing firms reply to a free "3 new practices near you" sample. If fewer than 2% reply positively, kill it.
4. **Run the same test on Idea 2 in parallel.** Same infrastructure: weekly public-record ETL, Claude classifier, sample-first cold email.
5. **Watch list.** Idea 5 becomes a 6.5–7 if DoD sets a firm Phase 2 date after the task force report.

### Method note

- About 174 web searches across this lane: five parallel research passes plus our own checks.
- Primary data was pulled directly for:
  - DOL 5500 (2023–2024 bulk files)
  - CA, WA and OR breach lists
  - NPPES weekly file
  - CA ABC new applications
  - ClinicalTrials.gov API v2
- Sources we could not access: Reddit (blocked), Glassdoor (snippets only), some vendor pricing pages (403s).
- Buyer-pain evidence from forums is therefore thin, and willingness to pay is inferred mostly from competitor pricing and appointment-setting rates.
