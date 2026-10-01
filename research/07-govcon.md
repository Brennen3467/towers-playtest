# Lane 07: Government Contracting, Procurement and Grants

*Research date: 2026-10-01. Research only: no outreach, signups or purchases were made.*
*Convention: **[E]** marks my own estimate or arithmetic. Every other material claim has a source URL. Several pricing figures come from competitor blogs or aggregators such as Vendr and Capterra, and I say so where it matters.*

---

## TL;DR

- **The "find bids + AI proposal" layer is a red ocean, not a blue one.** In the last 24 months it filled with funded AI entrants: Starbridge ($10M seed plus a $42M Series A), GovDash ($30M Series B), CLEATUS ($4M seed, $1M first-year revenue). Price floors also collapsed: HigherGov is $500/yr, CLEATUS $39/mo, Bidscope $45/mo. A two-person team should not build another bid aggregator.
- **Several obvious tax-credit and grant plays are dead or closing.** ERC is barred and penalized. WOTC lapsed on 2025-12-31. The 174A retroactive window closed on 2026-07-06. 179D ends for construction begun after 2026-06-30. USDA REAP grants were rescinded in April 2026. FEMA BRIC is frozen in litigation. Grant-writing contingency fees are an ethics violation.
- **The blue water is in obscure compliance datasets that trigger a purchase.** Three were strongest:
  1. **Federal Audit Clearinghouse (FAC) single-audit findings.** About 46.6k audits a year; the data is public, has an API and includes auditee emails. The play is to sell done-for-you remediation of Uniform Guidance findings.
  2. **State Revolving Fund (SRF) Intended Use Plans plus EPA drinking-water data.** The play is a pre-RFP water and wastewater project pipeline sold to engineering firms and manufacturer reps.
  3. **Small-municipality grant desk.** Towns demonstrably approve retainers of $2.1k–$5.5k a month in public council minutes.
- None of the ideas scores above 7/10, and my overall confidence in this lane is **medium-low**. Federal policy volatility (grant cancellations, small-business set-aside erosion, DBE overhaul) is a cross-cutting kill risk.

---

## 1. Lane overview

### 1.1 Landscape and money flows

| Segment | Size | Source |
|---|---|---|
| Federal contract obligations FY2025 | ~$793B (up from $755B in FY2024) | https://federalnewsnetwork.com/contractsawards/2026/06/agencies-award-179b-to-small-firms-in-2025-down-from-2024/ |
| Federal dollars to small businesses FY2025 | $179B, down from $183.5B. Unique small-business primes fell ~7% in FY2025 and ~40% over a decade | same, and https://fedlift.substack.com/p/small-business-government-contracting |
| SLED procurement | $1.5T+ across 90,000+ entities (vendor claim); Starbridge/Craft say ~$2T | https://www.sledai.com/blog/sled-contracting-statistics-2026/ , https://www.govtech.com/biz/sled-procurement-firm-starbridge-raises-10m-in-seed-funding |
| Local governments | 90,837 (3,031 counties, 35,705 municipalities and townships, 12,546 school districts, 39,555 special districts) | https://www.census.gov/library/publications/2026/econ/govtorg2225.html , https://www.stlouisfed.org/publications/regional-economist/2024/march/local-governments-us-number-type |
| Active SAM.gov registrations | ~350,000 (secondary source) | https://en.wikipedia.org/wiki/System_for_Award_Management |
| Single audits filed per year | ~40,000 (GAO, FY2023); 46,650 for audit year 2024 (my FAC API count) | https://www.gao.gov/products/gao-24-106173 , https://api.fac.gov/general |
| Transferable clean-energy tax credits | $42B in 2025, up 48% | https://www.cruxclimate.com/insights/transferable-tax-credit-market-report |
| EPA State Revolving Funds FY2026 | $7.2B (final year of BIL supplemental money) | https://www.congress.gov/crs-product/IF13177 , https://www.epa.gov/dwsrf |

### 1.2 Incumbents and pricing (verified where possible)

| Vendor | Focus | Price | Source |
|---|---|---|---|
| Deltek GovWin IQ | Fed and SLED intelligence | Avg ~$29k/yr, range $13k–$119k (third-party estimate) | https://civiciq.com/blog/govwin-iq-pricing-2026 |
| GovSpend | SLED POs and bids; builds its data from public-records requests | Median $11,576/yr, range $7.9k–$49.5k (37 Vendr deals) | https://www.vendr.com/marketplace/gov-spend |
| HigherGov | Fed + SLED + grants, API | **$500/yr Starter**, $2,500/yr for 10 users | https://www.highergov.com/pricing/ |
| GovTribe | Fed + SLED | $1,350–$5,500/yr | https://www.rfprecon.com/intel/tool-comparisons/govtribe-pricing |
| BidNet Direct | SLED bids | $599/yr for 1 state, $1,999 national | https://civiciq.com/blog/civic-iq-bidnet-direct-review |
| Periscope S2G (BidSync) | SLED bids | State plan $779/mo billed annually (vendor page) | https://www.periscopeholdings.com/s2g/pricing |
| Starbridge | SLED signals (board minutes, expirations) + AI writer | Not public; raised $52M | https://pulse2.com/starbridge-42-million-series-a-closed-to-transform-how-businesses-sell-to-government-and-education/ |
| GovDash | AI capture and proposals | Custom; $30M Series B | https://www.govdash.com/blog/govdash-raises-30m-in-new-funding |
| CLEATUS | AI discovery + proposals | $39–$250/user/mo; $1M first-year revenue | https://technical.ly/entrepreneurship/cleatus-aims-to-be-the-ai-operating-system-for-govcon/ , https://www.cleat.ai/pricing |
| Bidscope | SLED, claims 50k sites | $45/seat/mo | https://bidscopeai.com/ |
| Instrumentl | Nonprofit grant discovery | $299–$999/mo | https://grantsights.com/blog/instrumentl-pricing |
| Grantable / Granted AI | AI grant writing | $50–$150/mo / $19.99/mo | https://grantable.co/for/government , https://grantedai.com/ |
| Euna (Bonfire, DemandStar, IonWave) | Agency-side e-procurement, free for bidders | Agency pays (~$26.5k+/yr) | https://blogs.civiciq.com/2026/04/06/best-government-procurement-software-for-municipalities-in-2026-opengov-vs-tyler-technologies-vs-euna-solutions-vs-planetbids/ |
| Grants Office LLC; Lexipol GrantFinder / PoliceGrantsHelp | Vendor-sponsored grant help for public-sector buyers | Undisclosed sponsorships (Motorola, VirTra and others) | https://www.grantsoffice.com/Work-with-Us/For-Industry-Partners , https://www.police1.com/police-grant-center/grantfinder-2-0-launches-a-new-era-for-grant-funding-and-technology |

Revenue context (aggregator estimates, low reliability): Deltek ~$340M; GovSpend ~$29–36M; Euna ~$122–126M. See https://www.zippia.com/deltek-careers-21240/revenue/ and https://growjo.com/company/GovSpend.

Commoditized data products already on Apify: SAM expiring-registration monitor (2 users), USAspending recompete finder, FAC single-audit lead scraper, E-Rate Form 470 radar, and an SBA DSBS crawler. See https://apify.com/lead.gen.labs/sam-gov-expiring-registration-monitor , https://apify.com/groundtruth/usaspending-government-contracts , https://apify.com/scrapesage/single-audit-leads-scraper , https://apify.com/yungstentech/erate-470-bid-radar and https://apify.com/jungle_synthesizer/sba-crawler. **Implication: raw public-data lead lists are worth roughly $0. The value has to come from interpretation plus a done-for-you deliverable.**

### 1.3 Data access reality

- **SAM.gov Entity API.** Public fields are name, UEI, addresses, NAICS and the expiration date. **POC emails and phones are FOUO**, so they are not public. Non-federal users with no role get **10 requests/day**; users with a role get 1,000. Monthly public extracts are free. Sources: https://open.gsa.gov/api/entity-api/ and https://open.gsa.gov/api/sam-entity-extracts-api/
- **SAM.gov terms of use** prohibit scraping and bots, and prohibit using D&B data for "commercial, resale or marketing purposes (e.g., identifying… prospective customers)". Source: https://sam.gov/about/terms-of-use
- **USAspending.** Free API, no key. It has no native period-of-performance filter, so expirations must be computed yourself. Source: https://dev.to/ka_shah/how-to-find-expiring-us-federal-contracts-before-the-rfp-drops-free-api-11kb
- **Grants.gov.** The `search2` endpoint needs no auth. Simpler.Grants.gov needs a free key. Sources: https://www.grants.gov/api/api-guide and https://wiki.simpler.grants.gov/product/api
- **FAC API** (api.fac.gov). Free api.data.gov key. Tables: general, federal_awards, findings, findings_text, corrective_action_plans and others. **Includes `auditee_email`, `auditee_phone`, contact title, auditor firm and auditor email.** Source: https://www.fac.gov/api/dictionary/
- **USAC E-Rate open data.** Socrata, public domain. Source: https://opendata.usac.org/E-Rate/E-Rate-Open-Competitive-Bidding-Basic-Information-/jp7a-89nd/data
- **State and local portals.** Fragmented across 90k entities. GovSpend files "tens of thousands of public records requests monthly" plus automated requests. Source: https://govspend.com/blog/unlocking-public-records-how-govspend-turns-prrs-into-your-competitive-edge/
- **Commercial-purpose rules on public-records requests vary by state.** Kentucky requires certifying commercial purpose; Arizona and Connecticut allow higher commercial fees. Source: https://www.rcfp.org/open-government-sections/3-use-of-records/

### 1.4 Program status check (what is alive in October 2026)

| Program | Status | Implication | Source |
|---|---|---|---|
| ERC | OBBBA bars Q3/Q4 2021 claims filed after 2024-01-31; 20% erroneous-claim penalty; $1,000 per due-diligence failure for promoters; 6-year statute of limitations | **Dead.** A promoter-liability magnet | https://www.irs.gov/newsroom/irs-frequently-asked-questions-faqs-address-employee-retention-credits-under-erc-compliance-provisions-of-the-one-big-beautiful-bill , https://www.jw.com/news/insights-erc-one-big-beautiful-bill-changes/ |
| WOTC | Lapsed for wages after 2025-12-31; extension bills pending, not passed | **Dormant.** Retroactive revival is possible but unbankable | https://www.congress.gov/crs_external_products/R/PDF/R43729/R43729.9.pdf , https://www.shrm.org/topics-tools/news/employers-advised-stay-the-course-wotc-expires |
| R&D credit / §174A | Immediate expensing restored; small-business retroactive amendment window **closed 2026-07-06**; contingency firms such as Strike (20%) dominate | The gold-rush window is over | https://www.pbmares.com/small-businesses-face-july-6-deadline-for-rd-tax-amendments/ , https://www.striketax.com/ |
| IRA credits / §6418 transferability | Transferability kept; wind and solar must begin construction by 2026-07-04 or be placed in service by end-2027; FEOC limits added; market $42B (2025) | Big but institutional (Crux and banks) | https://www.thomsonreuters.com/en/institute/articles/green-energy-tax-credits-survived , https://www.cruxclimate.com/insights/transferable-tax-credit-market-report |
| 179D | Ends for construction begun after 2026-06-30; tail runs through about 2028 for projects placed in service later | Shrinking tail, specialist incumbents | https://www.kbkg.com/feature/179d-after-the-sunset-why-designers-can-continue-claiming-the-deduction-for-years |
| SBIR/STTR | Lapsed 2025-10-01 to 2026-04-13; reauthorized through FY2031 | Alive, but the consultant market is crowded | https://fundinglandscape.com/answers/sbir-sttr-reauthorization-2026 |
| USDA REAP grants | Funding notice rescinded 2026-04-15; only loans remain | **Farm-grant play is dead for now** | https://opengrants.io/reap-grant-grants-stopped-loans-still-open/ |
| FEMA BRIC | Terminated in April 2025; court-ordered restoration; no notice of funding as of February 2026 | Federal municipal grants are volatile | https://fundinglandscape.com/answers/fema-grants-emergency-preparedness-2026 |
| DOT DBE | Interim final rule of 2025-10-03 removed presumptions; all DBEs re-evaluated. Pennsylvania: 1,408 firms led to 431 recertified, 155 withdrawn, 50 denied (status of the rest not given) | Disruption, but AI narrative tools already sell for $79 | https://www.pa.gov/content/dam/copapwp-pagov/en/penndot/documents/about-us/equalemployment/disadvantaged-business-enterprise/penndot%20dbe%20update%20august%2026%202026.pdf , https://dbenarrativepro.com/ |

### 1.5 Where the gaps are

1. **Long-tail buyers who will never buy software.** Small towns, $1–20M nonprofits and 5–50 person trade contractors want an outcome: a submitted grant, a fixed audit finding, a bid package. AI tools at $20–$150/mo are cheap but leave the work to the user. A done-for-you, AI-leveraged service priced against a human retainer of $2k–$5k/mo is the arbitrage, and it mirrors the brothers' website model.
2. **Compliance-triggered needs in obscure federal datasets.** Examples: FAC findings, SDWIS violations, UCMR5 PFAS exceedances, and Lead and Copper Rule Improvements (LCRI) deadlines. These datasets name the entity, the problem and a contact, which is exactly the "broken website" equivalent.
3. **Pre-RFP signals from funding documents.** SRF IUP priority lists name a community, a project and dollar amounts one to three years before a bid. That is earlier than Dodge or ConstructConnect bid-stage feeds.

---

## 2. Candidate ideas

### Idea A: "Finding Fixer", done-for-you remediation of single-audit findings

**One-line pitch:** Every nonprofit, tribe or town whose single audit just cited it for procurement, subrecipient-monitoring or allowable-cost failures gets a ready-to-adopt Uniform Guidance policy pack and corrective-action plan, then a monthly compliance-monitoring subscription so the finding doesn't repeat.

**Data sources**
- FAC API (api.fac.gov). Free key, PostgREST, public. Tables: `general` (auditee name, entity type, `auditee_email`, phone, contact title, auditor firm, total federal expenditure), `findings` (type of compliance requirement, material weakness, `is_repeat_finding`), `findings_text`, `corrective_action_plans`. DEMO_KEY is limited to about 10 requests/hour, so get a real key. Terms: https://www.fac.gov/api/ ; fields: https://www.fac.gov/api/dictionary/
- My counts from audit year 2024: **46,650 audits; 77,653 finding rows; 26,728 repeat-finding rows (~34%)**; ~11.5k rows whose requirement code contains "I", which is a rough proxy for procurement/suspension-and-debarment findings **[E: code-match is approximate]**. Source: https://api.fac.gov (queried 2026-10-01).
- 2 CFR 200 Subpart D procurement standards text (eCFR, public domain): https://www.ecfr.gov/current/title-2/subtitle-A/chapter-II/part-200/subpart-D/subject-group-ECFR45ddd4419ad436d
- USAspending assistance awards, to enrich which programs and agencies fund the auditee: https://www.usaspending.gov/

**Data combination that creates new value:** Finding text + corrective-action-plan text + the auditee's federal programs (Assistance Listing numbers) + whether the finding repeats + who audited them. Claude classifies each finding into a remediation template, such as "no written procurement procedures per 200.318" or "no SAM exclusion check before award". It then drafts the specific policy or procedure the auditee's own corrective-action plan promised to adopt. Nobody turns FAC findings into a pre-built fix today; the existing uses are lead lists for software vendors. Sources: https://apify.com/scrapesage/single-audit-leads-scraper and https://apify.com/pink_comic/federal-audit-clearinghouse-single-audit-data

**Buyer persona:** Finance director or CFO, sometimes the executive director, at a nonprofit (health center, Head Start, housing authority, community action agency), tribe or small local government that spends $1M–$20M a year in federal funds. These organizations have no dedicated grants-compliance staff and just received a finding, often a repeat one. Sample records from the API include "City of Nassau Bay, TX, Finance Director, $764k expended" and a Hawaii community health nonprofit whose contact is its CFO.

**Evidence of willingness to pay**
- Single audits already cost $22k–$26k for a $10M nonprofit, and a single audit adds $5k–$20k on top of a normal audit. These buyers already pay for compliance. Source: https://www.growthforce.com/blog/how-much-does-a-nonprofit-audit-cost
- A grants coordinator costs $67.5k/yr on average (Glassdoor), with an IQR of $54.8k–$83.7k. Source: https://www.glassdoor.com/Salaries/grants-coordinator-salary-SRCH_KO0,18.htm
- CPA firms (Aprio, EisnerAmper, BPM) sell outsourced grant compliance and audit-readiness. Sources: https://www.eisneramper.com/services/outsourcing/industry-operations/not-for-profit/ and https://www.grfcpa.com/resource/how-nonprofits-can-strengthen-compliance/
- Repeat findings carry consequences: federal agencies can impose specific award conditions. The 2024 Financial Management Risk Reduction Act adds OMB quality reviews. Source: https://www.gao.gov/products/gao-24-106173
- **Gap:** I found no published price list for third-party "finding remediation". Willingness to pay for this specific deliverable is **inferred, not proven**.

**Market size (bottom-up)**
- 46,650 audits a year. Assume 25–35% have at least one finding, giving ~12k–16k entities **[E]**.
- Of those, assume 50–60% sit in the $1–20M band and are not large universities or states, giving ~6k–9k targetable entities a year **[E]**.
- At $4k setup plus $300/mo, ACV is about $7.6k. A 3–5% capture gives ~200–450 clients, or **$1.5M–$3.4M ARR [E]**.
- There is a secondary, larger TAM in selling the same "compliance calendar" to all ~46k filers.

**Deliverable and pricing**
- (1) "Finding Fix Pack": entity-specific procurement, conflict-of-interest, subrecipient-monitoring, time-and-effort or cost-allowability policies, a board-resolution template, and a corrective-action-plan narrative. One-time **$2,500–$6,000**.
- (2) "Compliance Desk" subscription at **$250–$600/mo**:
  - monthly SAM exclusion checks on their vendors and subrecipients via the public SAM API (exclusions are public);
  - a procurement-threshold checklist per purchase;
  - grant-deadline calendar;
  - pre-audit readiness binder.
- The recurring part is plausible because a repeat finding is the pain.

**Automation pipeline**
1. **Find prospects:** a nightly FAC pull of new submissions; filter on finding codes, repeat flag, expenditure band and entity type. Fully automated.
2. **Build deliverable:** Claude reads `findings_text` and `corrective_action_plans` plus the program list, then generates a draft policy pack and a one-page "your finding, what the auditor will test next year, what to adopt" memo. This is the free sample, the analogue of the free website build. ~90% automated; a human reviews templates once per finding type.
3. **Personalized outreach:** email to `auditee_email` quoting their own finding reference number and the CAP language they committed to. B2B, CAN-SPAM compliant.
4. **Handle replies:** Claude agent answers scope and price questions, books a call when needed, and sends the order form.
5. **Deliver and renew:** policies customized via an intake form; the subscription runs automated monthly exclusion screening and reminders. A renewal trigger fires the next year when the FAC record shows the finding resolved or repeated.

**Percent automatable: ~75% [E].** Human touchpoints:
- quality review of the first ~20 templates and anything novel, such as a tribal or Davis-Bacon nuance;
- occasional calls with finance directors;
- liability posture (no attest work).

**GTM, first 90 days**
- Days 1–15: pull AY2023–2025 findings; cluster the top 10 finding archetypes; build 10 policy templates checked against 2 CFR 200 with a freelance CPA reviewer (~$3k [E]).
- Days 15–45: email 1,500 entities with fresh findings, in batches of 100/day per warmed domain, with a free personalized memo. Target 2% reply and 0.5% purchase, giving ~7 packs **[E]**.
- Days 45–90: add a partnership channel with small CPA firms. Auditors cannot remediate for their own attest clients, for independence reasons, so they need someone to refer to. Test the subscription upsell.

**Unit economics [E]**
- CAC ~$300–$600 (data free, email infrastructure ~$500/mo, Claude ~$0.20–$1 per prospect memo).
- First-year revenue per client ~$7.6k; gross margin ~80% after human review time; data cost ~$0.

**Competitors and crowding:** CPA and outsourced-accounting firms, plus grant-management software such as Euna Grants and AmpliFund, which sell systems rather than fixes. Raw lead scrapers exist on Apify. I found no direct "findings to fix" productized service. **Moderately blue.**

**Legal and regulatory**
- Not attest work. Avoid the words "audit" or "CPA" unless a licensed CPA partner is involved (state accountancy acts).
- CAN-SPAM: physical address, opt-out, truthful subject lines.
- Public-records emails are fine for B2B.
- Do not imply a federal affiliation, given the SAM-style scam stigma.
- FAC data is public; follow the api.data.gov terms.

**Kill risks**
1. Finance directors may simply ask their auditor or a known CPA rather than buy from a stranger. Trust barrier.
2. Policy templates are cheap and widely available (state associations, OMB resources), so willingness to pay could be well under $1k.
3. Uniform Guidance changes, such as the 2024 threshold rise to $1M, shrink the universe by ~15%, and FAC data quality has known gaps. Sources: https://www.cbiz.com/insights/article/2024-uniform-guidance-changes-requirements-for-single-audits and the GAO report above.

---

### Idea B: "Water Pipeline Radar", pre-RFP water and wastewater project intelligence

**One-line pitch:** A weekly, state-by-state feed of every water and wastewater project on SRF Intended Use Plans and priority lists, joined with each system's compliance pressure (violations, PFAS, lead lines). Sold to engineering firms, manufacturer reps and utility contractors 6–30 months before the RFQ or bid.

**Data sources**
- **State SRF IUPs and priority lists:** ~50 states × CWSRF + DWSRF, so ~100+ PDF or Excel documents a year plus amendments. Public, published by state environmental agencies on a draft (spring), comment and final cycle. Examples: https://www.mass.gov/info-details/srf-intended-use-plans , https://deq.mt.gov/files/Water/TFAB/DWSRF/IUP-PPL/2026%20DWSRF%20IUP_FINAL_AMENDED.pdf and https://www.michigan.gov/egle/-/media/Project/Websites/egle/Documents/Funding/State-Revolving-Fund/CWSRF/Program-Documents/2026/CWSRF-IUP-FY26.pdf. Cost: free; Claude does the extraction.
- **EPA SDWIS / ECHO:** violations by system, free. **UCMR5:** ~8% of systems above the PFOA 4 ppt MCL and 8.9% above PFOS. Source: https://www.pacelabs.com/analytical-environmental/making-sense-of-ucmr-5-results-key-pfas-findings-lithium-concerns-and-ucmr-6-signals/
- **Regulatory clocks:**
  - PFOA/PFOS compliance moved to 2031: https://www.epa.gov/newsreleases/epa-announces-it-will-keep-maximum-contaminant-levels-pfoa-pfos
  - LCRI compliance date 2027-11-01, with all lead lines replaced by 2037: https://www.ldh.la.gov/assets/oph/Center-EH/engineering/LCRI/LCRI-FAQs_05.21.2026.pdf
- **Funding:** $7.2B for SRFs in FY2026: https://www.congress.gov/crs-product/IF13177
- **System universe:** ~50,000 community water systems, more than 91% serving ≤10,000 people: https://www.congress.gov/crs-product/R47315

**Data combination that creates new value:** IUP rank and dollars (money is coming) + compliance violations or PFAS exceedance (the need is legally forced) + LCRI deadline (timing) + local procurement stage, found by watching council agendas and the portal for engineer RFQs. The result is a "who will buy what, when" score per project. The IUP cycle is a recognized lead source ("review draft and final IUPs… early heads-up to begin marketing… forming teams"; https://www.nlc.org/article/2023/11/14/municipal-water-projects-advance-with-state-revolving-fund-financing-and-funding/), but I found no product that normalizes all states' lists.

**Buyer persona:**
- Business-development or marketing lead at a regional civil engineering firm with 10–300 staff and a water/wastewater practice.
- Owner of a manufacturer's rep agency selling pumps, membranes, meters, PFAS treatment or valves to consulting engineers and utilities.
- Estimator or BD at a utility pipeline contractor.

**Evidence of willingness to pay**
- Construction-lead data already sells: ConstructConnect Project Intelligence $129–$199/mo, bid management $3.6k–$4.5k/yr; GovSpend median $11.6k/yr. Sources: https://bidfinds.com/blog/constructconnect-pricing-guide-2025 and https://www.vendr.com/marketplace/gov-spend
- DOTestimate sells DOT bid-history data to highway estimators, so a vertical public-data niche can sustain a business. Source: https://www.dotestimate.com/
- Engineering firms win this work through qualifications-based selection, so early relationships are the whole game. This is an inference; no direct pricing evidence exists for an IUP feed.

**Market size (bottom-up) [E]**
- ~2,000–3,000 US engineering firms with municipal water practices, plus ~1,000–2,000 water-focused rep agencies, plus ~3,000+ utility contractors, gives ~6k–8k potential accounts.
- At $3,600–$9,600/yr (1–3 states vs. national), 5% penetration is ~350 accounts × ~$5k = **~$1.75M ARR**. A ceiling of 15% is ~$5M.
- These counts are estimates; no clean public count of "water engineering firms" exists.

**Deliverable and pricing**
- Web dashboard plus a weekly email digest per state and service line; CSV export; a "new on draft IUP" alert; plus an engineer-RFQ watch on the named communities.
- **$300/mo per state, $800/mo for a region, $2k/mo national.** Annual contracts, so recurring.

**Automation pipeline**
1. **Find prospects:** firm lists from state engineering-board licensee lists, ACEC member directories (public pages) and named engineers inside IUP documents. Many IUPs list the consulting engineer of record, so prospects come from the data itself.
2. **Build deliverable:** a scheduled crawler of ~100 state SRF pages; Claude extracts table rows (community, PWSID or NPDES ID, project description, cost, rank, principal forgiveness) into a schema; joins with SDWIS/ECHO/UCMR5 by PWSID; scores readiness.
3. **Personalized outreach:** "Here are the 23 projects in your 2 states that are on the FY27 draft IUP and have no engineer of record named." Attach a free sample.
4. **Handle replies:** Claude handles questions and trial setup.
5. **Deliver and renew:** automated weekly delivery; usage-based renewal nudges.

**Percent automatable: ~85% [E].** Human touchpoints:
- PDF-extraction QA (scanned tables vary by state);
- state-specific rule nuances;
- occasional sales calls with larger firms.

**GTM, first 90 days**
- Days 1–30: build 5 high-volume states (for example CA, TX, NY, PA, OH; my pick) with the FY2026/27 lists.
- Days 30–60: 25 free pilot accounts drawn from engineers named in IUPs; track whether they act on the leads.
- Days 60–90: convert pilots at $300/mo; add 10 more states; post on water-industry LinkedIn and in AWWA/WEF section newsletters.

**Unit economics [E]:** CAC ~$500–$1,500 (more consultative); ARPA ~$400/mo; gross margin ~85–90%; data cost ~$0 plus Claude extraction of ~$50–$200/month total.

**Competitors and crowding:**
- Dodge and ConstructConnect cover planning-stage projects but are not water-specialized or SRF-normalized.
- Starbridge mines board minutes generally.
- State associations and EFCs publish guidance, not feeds.
- **Fairly blue in this niche.** Risk that Dodge or Starbridge adds it.

**Legal and regulatory:**
- IUPs and EPA data are public domain.
- B2B email under CAN-SPAM.
- No licensing.
- Do not give engineering advice.

**Kill risks**
1. Federal funding cliff after FY2026, the last BIL year, plus proposed SRF cuts (https://www.waterworld.com/drinking-water-treatment/infrastructure-funding/news/55287774/white-house-proposes-24b-reduction-for-2026-state-revolving-fund-programs). Fewer projects means a thinner product.
2. Engineers already know their regional utilities personally. The marginal lead value may be low for incumbents and high only for firms entering new territories.
3. Messy state PDFs mean extraction errors. One bad dataset kills trust.

---

### Idea C: "Town Grant Desk", AI-leveraged, done-for-you grant retainer for small municipalities and special districts

**One-line pitch:** For a flat $1,500–$3,000 a month, a town of 2,500–25,000 gets a monthly funding-match report, two drafted state or federal grant applications per quarter, and post-award reporting reminders. It replaces a $3.8k–$5.5k/mo consultant or a $67k grants coordinator.

**Data sources**
- Grants.gov `search2` (no auth) and Simpler.Grants.gov (free key): https://www.grants.gov/api/api-guide
- State grant portals: fragmented, scraped or manual (CA Grants Portal and others).
- Census of Governments (entity universe): https://www.census.gov/library/publications/2026/econ/govtorg2225.html
- FAC `general` + `federal_awards`, to see which towns already receive federal money and who their finance contact is.
- Headwaters Economics Rural Capacity Index (low-capacity targeting): https://headwaterseconomics.org/economic-development/equity/rural-capacity-map/
- Council agendas and minutes (public) that mention "grant writer", plus capital improvement plans.

**Data combination that creates new value:** Capital improvement plan line items (needs) + capacity index (can't do it themselves) + open programs with eligibility rules (Claude reads NOFOs) + past awards to peer towns (USAspending/FAC). The result is a "you are eligible for these 6 programs worth ~$X; here is a draft for the first" packet. This is the exact analogue of the pre-built website.

**Buyer persona:** City or town manager, clerk-treasurer or mayor of a small municipality, or the general manager of a water or fire district. Decision is by council vote, so the contract shows up in public minutes.

**Evidence of willingness to pay (strong, public)**
- **Grass Valley, CA: $3,800/mo** fixed retainer (California Consulting): https://mccmeetingspublic.blob.core.usgovcloudapi.net/grassvalca-meet-0374476e648e4a8abb905c2df2cb2612/ITEM-Attachment-001-9fa92cf88d1e49419babdd3b574d9763.pdf
- **Selma, CA: $5,500/mo** on-call retainer (Townsend Public Affairs): https://citizenportal.ai/articles/9778890/California/Fresno-County/Selma-City/Selma-council-awards-primary-on-call-grant-writing-contract-to-Townsend-Public-Affairs
- **Ozawkie, KS: $2,100/mo** retainer: https://citizenportal.ai/articles/8635049/kansas/jefferson-county/ozawkie/council-approves-2100-monthly-retainer-to-keep-grant-writer-on-contract
- **Needles, CA:** $125/hr: https://mccmeetingspublic.blob.core.usgovcloudapi.net/needlesca-meet-3184a9dce7be4d81a75b0ab7ff4d27e6/ITEM-Attachment-001-0ff94f5fe2a944009f0e28dc6972dc20.pdf
- Towns issue RFPs for grant writing (Elma WA, Scotts Valley CA): https://www.cityofelma.com/media/3446 and https://scottsvalley.gov/DocumentCenter/View/4045/Grant-Writing-Services-RFP
- Capacity gap is documented: "high-capacity counties… were chosen 83% of the time." Source: https://headwaterseconomics.org/economic-development/federal-climate-vulnerability-maps-overlook-low-capacity-communities/

**Market size (bottom-up)**
- 35,705 municipalities and townships, 3,031 counties, 39,555 special districts (Census).
- Assume ~8k–12k are small but active enough, with population 2.5k–25k or budget over $2M, to buy **[E]**.
- At a $24k/yr average, 1% penetration is ~100 clients = **$2.4M ARR**; 3% is ~$7M **[E]**.
- Proof that the category exists: California Consulting and Townsend serve many CA cities.

**Deliverable and pricing:** Monthly retainer at **$1,500 (Starter: 1 application a quarter), $3,000 (Pro: 2 a quarter plus reporting)**. Flat fee only. **No contingency or percentage pricing:** the GPA Code of Ethics item 19 bans it, and many funders bar paying writers from the grant. Source: https://www.nonprofitmarketingguide.com/avoiding-unethical-pay-structures-a-guide-for-grant-writers-nonprofit-professionals/

**Automation pipeline**
1. **Find prospects:** Census entity list, FAC contacts, municipal websites (staff directories), council agendas where "grant writer" appears or a retainer just expired.
2. **Build deliverable:** Claude matches the town's capital plan and needs (scraped from budget PDFs) to open federal and state programs; produces a "Funding Map" PDF with deadlines and eligibility notes plus a one-page draft project narrative.
3. **Personalized outreach:** email to the manager or clerk with their Funding Map ("3 programs close before Jan 31 that fit your Main St. sidewalk project in your FY26 CIP").
4. **Handle replies:** Claude answers questions; drafts the council staff report and agenda memo for the town (a huge friction-reducer); handles procurement paperwork (sole-source or small-purchase justification under the state threshold).
5. **Deliver and renew:** Claude drafts applications from intake plus the document library; a human grant professional edits and submits; Claude manages post-award reporting calendars. Renewal is monthly.

**Percent automatable: ~55–65% [E].** Human touchpoints:
- a senior grant writer edits every application (quality and ethics);
- a kickoff call per client;
- presentations to council for larger contracts;
- portal submissions requiring the town's own login (SAM, Grants.gov and state portals need the applicant to be the registrant).

**GTM, first 90 days**
- Pick one state with a big state-grant ecosystem and a low small-purchase threshold, such as CA, TX or PA (my pick).
- Weeks 1–4: build Funding Maps for 500 towns.
- Weeks 4–8: email 500 towns; target 10 discovery calls and 3 signed retainers.
- Weeks 8–13: deliver first applications; collect council minutes as public case studies.

**Unit economics [E]:** CAC ~$1,500–$3,000 (long council cycle); ARPA ~$2,000/mo; contractor grant-writer cost ~$600–$900/mo per client at AI-leveraged throughput; gross margin ~55–65%; data cost ~$0.

**Competitors and crowding:** Many regional consultancies (California Consulting, Townsend), regional planning commissions and councils of governments (often free or subsidized), AI tools (Grantable $50–$150/mo, Granted $19.99/mo), Euna Grants. **Crowded with humans, but fragmented and local.** AI cost advantage is the edge.

**Legal and regulatory**
- GPA ethics (no contingency).
- Some funders prohibit paying writers from grant proceeds.
- State procurement rules for professional services.
- Lobbying registration may apply in some states if contacting state legislators or agencies to influence awards **[E: verify per state]**.
- CAN-SPAM. Public officials' emails are public records.

**Kill risks**
1. Federal discretionary grant volatility (BRIC terminated, REAP rescinded) shrinks wins. Towns cancel after 2–3 losses.
2. Sales cycles run through council votes, so time to first dollar is 60–120 days and churn spikes at budget season.
3. Free regional councils of governments, plus the state's own technical-assistance programs, undercut on price.

---

### Idea D: "Grant-Funded Pipeline", vendor-paid grant enablement for public-sector sellers

**One-line pitch:** Vendors selling to police, fire, schools and water utilities (cameras, radios, training simulators, school-safety tech, meters) pay a subscription for a monthly list of their prospects matched to open grants that fund their product. Each list comes with prospect-specific Funding Maps that sales reps hand to the customer, and optional application help from an independent writer.

**Data sources:** Grants.gov and state programs (as above); USAspending assistance awards (who won DOJ BWC, COPS, AFG, SVPP in prior years); the vendor's CRM or territory; FAC federal-award lists; E-Rate open data for schools.

**Data combination:** "Agency X won AFG in 2023, so it is grant-capable; it is eligible for program Y closing on date Z; your product is an allowable cost under Y's NOFO section 4.2." Claude reads each NOFO's allowable-cost section and maps it to the vendor's SKU list.

**Buyer persona:** VP Sales or public-sector marketing director at a $5M–$500M company selling to SLED. The program already exists at Motorola, VirTra and Avigilon. Sources: https://www.police1.com/police-grant-center/grantfinder-2-0-launches-a-new-era-for-grant-funding-and-technology , https://www.avigilon.com/blog/school-security-grants and https://www.motorolasolutions.com/en_us/solutions/government-grants/education.html

**Evidence of willingness to pay:** Lexipol runs sponsor programs with manufacturers. Grants Office LLC sells "industry partner" programs and claims it facilitated $3B+ in awards over three years (https://www.grantsoffice.com/Services/Industry-Services). GovSpend's median of $11.6k/yr shows the SLED sales-intelligence budget exists. Sponsorship prices are not public, so this is a gap.

**Market size [E]:** ~1,000–3,000 vendors with grant-fundable public-sector products. At $1k–$3k/mo, 3% penetration is ~60 accounts × $24k = **~$1.4M ARR**.

**Deliverable and pricing:** $1,000–$3,000/mo per vertical and territory; optional $1.5k–$4k per application for writing paid by the vendor, using a separate independent writer.

**Automation pipeline**
1. Find vendors via conference exhibitor lists and cooperative-contract award lists.
2. Build a sample "Grant-ready accounts in your territory" report automatically.
3. Personalized email to the VP Sales.
4. Claude handles replies.
5. Monthly automated refresh; renewal on pipeline influence.

**Percent automatable: ~70% [E].**

**GTM, first 90 days:** One vertical, public safety, where federal grant programs (COPS, BJA, AFG, SHSP) are the most stable. Build 20 sample reports for mid-size vendors and convert 3.

**Unit economics [E]:** CAC ~$2k–$4k; ARPA ~$1.5k/mo; gross margin ~80%.

**Competitors:** Lexipol GrantFinder (media-backed, strong), Grants Office, vendors' in-house grant teams, Starbridge and GovSpend signals. **Moderately crowded.**

**Legal and regulatory**
- **2 CFR 200.319(b):** contractors who "develop or draft grant applications" or specifications should be excluded from competing for the resulting procurement. If the vendor's writer drafts the application, the vendor may be disqualified, so the writer must be truly independent and the vendor must not shape the specifications. Source: https://www.ecfr.gov/current/title-2/subtitle-A/chapter-II/part-200/subpart-D/subject-group-ECFR45ddd4419ad436d
- Anti-kickback and gift rules at the agency level.
- CAN-SPAM.

**Kill risks**
1. Federal public-safety and school grant programs get cut or re-scoped (FY2026–27 politics).
2. The conflict-of-interest rule above means the vendor gets less control than it wants.
3. Lexipol's media reach (Police1, FireRescue1) dominates attention.

---

### Idea E: Trade-specific SLED bid concierge plus price-to-win (janitorial and landscaping)

**One-line pitch:** For a 10–100 person janitorial or landscaping company, a done-for-you service that finds every relevant city, school and county bid in its metro area, shows what incumbents bid last time (from bid tabulations), and assembles the bid package for the owner to sign.

**Data sources:** HigherGov API (included even in the $500/yr plan; https://www.highergov.com/pricing/) or BidNet ($599/yr per state) as the bid feed, instead of building 90k scrapers. Bid tabulations come from portals (often posted) and **automated public-records requests** for tabs and awarded contracts, the method GovSpend uses at scale. SAM and USAspending cover federal set-asides in NAICS 561720 and 561730.

**Data combination:** Bid feed + historical unit prices from bid tabs (cost per square foot, cost per acre) + contract expiration from awarded contracts. The output is "this school district's custodial contract expires in June; last award was $X/sq ft to Y; here is a price-to-win band." DOTestimate proves this model works in highway construction, but I found no equivalent for local service contracts (https://www.dotestimate.com/).

**Buyer persona:** Owner-operator of a commercial cleaning or landscaping firm with $1M–$10M revenue. No BD staff; bids sporadically.

**Evidence of willingness to pay**
- Freelance proposal writers: $2.5k–$6k per simple state or local RFP; $75–$200/hr. Source: https://wonit.ai/questions/cost-freelance-proposal-writer-government-rfps
- Bid feeds sell at $599–$1,999/yr (BidNet).
- 67,799 janitorial employer establishments (Census CBP 2023, secondary): https://startbusinessbystate.com/cleaning-industry-statistics/

**Market size [E]:** Assume ~10% of 67.8k janitorial employers plus a similar landscaping pool pursue public work, giving ~10k–15k firms. At $300–$600/mo, 1% is ~120 × $5.4k = **~$650k ARR**. Small unless it expands to more trades.

**Deliverable and pricing:** $299/mo for alerts plus price bands; $499/mo including 1 assembled bid package a month; $750 per extra package.

**Automation pipeline:**
1. Find prospects via state contractor and business licenses, Google Maps and trade-association lists.
2. Build a "12 open bids near you + what incumbents charged" sample report.
3. Email.
4. Claude agent handles replies.
5. Monthly report plus package assembly. The owner still prices and signs; bonds and insurance stay human.

**Percent automatable: ~60% [E].**

**GTM, first 90 days:** One metro, one trade. File 200 records requests for custodial bid tabs and contracts in month 1, publish a price index, and use it as the hook.

**Unit economics [E]:** CAC ~$300–$800; ARPA ~$400/mo; gross margin ~70%; data ~$500–$2k/yr (HigherGov) plus records-request fees.

**Competitors:** Very crowded in discovery: Bidscope $45/mo, CLEATUS $39/mo, HigherGov, BidNet, GovSpend, Starbridge, JaniJobs. The price-to-win angle is the only differentiation.

**Legal and regulatory:**
- Public-records commercial-purpose rules vary (KY certification, AZ/CT fees).
- No ToS issue with the HigherGov API on a paid plan, but check redistribution limits **[E: verify]**.
- CAN-SPAM. TCPA if texting owners: avoid.

**Kill risks**
1. Discovery is commoditized; owners already get free alerts from Euna/Bonfire, which is free for bidders (https://www.ocoee.org/958/crc32).
2. Local janitorial bids are lowest-price, so concierge value is capped by thin margins.
3. Bid tabs are inconsistent across agencies, making price-to-win hard to normalize.

---

### Idea F: SAM registration renewal and compliance desk (examined at the brief's request)

**One-line pitch:** A legitimate, transparent annual "registration and compliance desk" for small federal contractors covering SAM renewal, Reps and Certs, SBA profile, CAGE and NAICS hygiene, and size re-certification.

**Data:** SAM monthly public extract with `REGISTRATION EXPIRATION DATE` (https://open.gsa.gov/api/sam-entity-extracts-api/). **Emails and phones are FOUO, not public** (https://open.gsa.gov/api/entity-api/). Contact data would have to come from SBA SBS/DSBS profiles (public, crawled on Apify) or websites.

**Data combination:** Expiration date + award history (USAspending), to target only *active awardees* for whom lapse means lost payments. That is a more defensible message than the mass spam.

**Buyer:** Owner of a micro or small federal contractor with 1–20 staff.

**Evidence of willingness to pay:** Third-party firms charge **$300–$3,000** (https://lobbyit.com/sam-gov-registration/). That is precisely the market GSA and the BBB warn about. "The most prevalent SAM.gov scam is a fake renewal notice… includes the business name and registration expiration date pulled from public SAM.gov data" (https://www.bbb.org/article/scams/31197-bbb-scam-alert-watch-out-for-third-parties-claiming-to-help-with-your-government-grant-registration , https://msac.org/media/1086/download?inline=).

**Market size [E]:** ~350k registrations, so ~29k expire per month. Maybe 5–10% would pay ~$500 a year, giving a $8M–$17M theoretical market. Realistically small for an honest entrant.

**Automation:** ~90%, since the pipeline is trivial. That ease is exactly why scammers dominate.

**Competitors:** Federal Processing Registry, US Federal Contractor Registration, many others. **Red ocean with a toxic reputation.**

**Legal:**
- SAM terms ban scraping and bars on "marketing purposes" use of D&B data (https://sam.gov/about/terms-of-use).
- Any expiration-triggered cold email reads like the GSA-warned scam pattern, inviting FTC Section 5 risk if anything implies a government affiliation or urgency.
- API limit is 10 requests/day without a role (public extract files avoid this).

**Kill risks**
1. The outreach pattern is indistinguishable from the scam in buyers' eyes, so reply rates and domain reputation are poor.
2. Registration is free and takes an afternoon. Value is tiny.
3. Shrinking small-business base: -7% unique small primes in FY2025.

**Verdict:** Only viable as a free lead magnet inside a broader govcon offer. **Do not build as a standalone.**

---

### Idea G: Subcontracting-plan partner matcher for mid-tier primes

**One-line pitch:** Large primes with FAR 19.7 subcontracting plans get a quarterly, AI-vetted short list of small-business subs (by NAICS, set-aside status, past performance and location) for each contract, plus good-faith-effort documentation.

**Data:** SAM extract (business types, NAICS); USAspending/FPDS (past performance); SBA SBS (capability narratives and emails); SubNet postings (free); eSRS (reports exist but are not openly downloadable per prime **[E: limited public access]**). Sources: https://www.congress.gov/crs-product/R47585 and https://www.sba.gov/federal-contracting/contracting-guide/prime-subcontracting

**Buyer:** Small-business liaison officer or supplier-diversity manager at a large or mid-tier prime holding plans above $900k ($2M for construction).

**Willingness to pay:** Indirect. Primes must document good-faith efforts and report in eSRS. Teaming features are bundled in GovWin, HigherGov and GovTribe, so stand-alone willingness to pay is weak.

**Market size [E]:** A few thousand prime business units. At $1k–$2k/mo, a 50-account ceiling is ~$1M ARR.

**Automation:** ~70%.

**Competitors:** Bundled in every intelligence platform; primes run their own supplier portals; free SBA SubNet.

**Legal:** None notable beyond CAN-SPAM and SAM terms.

**Kill risks**
1. Policy direction is against it. The SDB goal was cut and goals were missed in five of ten categories in FY2025 (https://www.inc.com/melissa-angell/small-businesses-snagged-273-billion-in-federal-contracts-even-as-thousands-continue-to-leave-contracting-base/91364996).
2. The function is bundled free in tools primes already own.
3. Primes pick subs by relationship, not lists.

---

### Idea H: Statutory incentive and credit recovery on contingency (referral model)

**One-line pitch:** Identify small and mid-size manufacturers and govcon firms that qualify for *statutory* (non-negotiated) state job, investment or R&D credits and federal R&D credits, then refer them to a licensed partner on contingency.

**Data:**
- State incentive statutes and program pages;
- Good Jobs First Subsidy Tracker, to find who has *already* claimed (free search; downloads $450–$1,500/yr; commercial license unclear): https://subsidytracker.goodjobsfirst.org/plans
- Expansion signals: job postings, permits, OSHA establishment data.

**Data combination:** Expanding-company signals + statutory eligibility rules − existing claims (Subsidy Tracker) = likely unclaimed credits.

**Buyer:** CFO or controller at a $10M–$200M manufacturer.

**Willingness to pay:** Strong for the category. Contingency R&D firms charge ~20% (https://www.striketax.com/); Ryan claims "more than 50% of credits and incentives go unclaimed" (https://ryan.com/practice-areas/credits--incentives/). Statutory credits can often be claimed retroactively; discretionary ones must be negotiated before the investment decision (https://info.siteselectiongroup.com/blog/valuing-different-economic-incentive-types-in-the-site-selection-process).

**Automation:** ~40%. The technical credit study and representation remain expert human work.

**Competitors:** Ryan, Big 4, regional CPAs, R&D boutiques (Strike, Swanson Reed, and others). **Crowded.**

**Legal**
- Circular 230 §10.27 restricts contingent fees for refund claims except in narrow cases. Contingent fees on *original* returns and ordinary refund claims were limited by *Ridgely v. Lew* (D.D.C. 2014), but the IRS proposed new rules in December 2024. Sources: https://www.currentfederaltaxdevelopments.com/blog/2024/12/22/irs-proposes-changes-to-circular-230 and https://www.hullandknarr.com/do-contingency-fees-leave-your-rd-credits-at-risk/
- Referral fees to non-CPAs are restricted by some state accountancy rules **[E: verify per state]**.
- The ERC promoter penalties are the cautionary tale.

**Kill risks**
1. The 174A retroactive gold rush ended on 2026-07-06.
2. Expertise and liability cannot be automated.
3. Incumbents own CFO relationships.

---

## 3. Ideas considered and rejected

| Idea | Why rejected | Evidence |
|---|---|---|
| Generic SLED bid aggregator for a niche vertical | 90k portals is a moat already crossed by funded players (Starbridge $52M; Bidscope claims 50k sites) and sold at $39–$45/mo floors; Euna/Bonfire is free for bidders | https://bidscopeai.com/ , https://www.cleat.ai/pricing , https://pulse2.com/starbridge-42-million-series-a-closed-to-transform-how-businesses-sell-to-government-and-education/ |
| Bid matching + AI proposal subscription (horizontal) | Same as above; plus GovDash ($30M), CLEATUS, Sweetspot, HigherGov AI tools. Survives only as Idea E with a price-to-win angle | https://www.govdash.com/pricing |
| Federal recompete / expiring-contract finder | Commoditized: free API, Apify actors, BidSparq index | https://apify.com/groundtruth/usaspending-government-contracts , https://bidsparq.com/research/federal-recompete-index |
| ERC recovery | Statutorily barred for late claims; promoter penalties; 6-year statute of limitations | https://www.irs.gov/newsroom/irs-frequently-asked-questions-faqs-address-employee-retention-credits-under-erc-compliance-provisions-of-the-one-big-beautiful-bill |
| WOTC screening service | Lapsed 2025-12-31 and not reauthorized as of the CRS update of 2026-05-13; also dominated by payroll providers (ADP and others) | https://www.congress.gov/crs_external_products/R/PDF/R43729/R43729.9.pdf , https://www.cpapracticeadvisor.com/2026/01/13/adp-pushes-lawmakers-to-extend-work-opportunity-tax-credit/176253/ |
| IRA credit-transfer marketplace for small sellers | $42B market run by Crux, banks and brokers; FEOC diligence; wind/solar construction cutoff 2026-07-04 shrinks the small-seller pipeline | https://www.cruxclimate.com/insights/transferable-tax-credit-market-report , https://www.thomsonreuters.com/en/institute/articles/green-energy-tax-credits-survived |
| 179D designer-allocation hunting (SLED building awards matched to architects) | Clever combination, but the deduction ended for construction begun after 2026-06-30; a shrinking tail through ~2028; specialist incumbents (KBKG, ETS) | https://www.kbkg.com/feature/179d-after-the-sunset-why-designers-can-continue-claiming-the-deduction-for-years , https://engineeredtaxservices.com/179d-energy-tax-deduction/179d-tax-credit-update-the-deadline-has-passed/ |
| Farm grant writing (USDA REAP) on success fee | REAP grant funding notice rescinded 2026-04-15; success fees violate GPA ethics | https://opengrants.io/reap-grant-grants-stopped-loans-still-open/ |
| Grant writing on contingency for nonprofits | GPA Code item 19 bans percentage compensation; many funders forbid it | https://www.nonprofitmarketingguide.com/avoiding-unethical-pay-structures-a-guide-for-grant-writers-nonprofit-professionals/ |
| SBIR proposal writing on success fee | Crowded consultants ($4k–$17k plus a 3–5% success fee); AI quality concerns; recent 5.5-month lapse shows policy risk | https://sbirgrantwriters.com/sbir-blog-grant-writing-services-compared-2026 , https://fundinglandscape.com/answers/sbir-sttr-reauthorization-2026 |
| DBE re-certification narrative writing | One-time window already mid-flight; $79 AI tools exist; narrative must be the owner's own account (ethics); final rule published 2026-09-25 | https://dbenarrativepro.com/ , https://www.federalregister.gov/documents/2026/09/25/2026-19688/disadvantaged-business-enterprise-and-airport-concession-disadvantaged-business-enterprise-program |
| E-Rate Form 470 vendor alerts | Commoditized (FRNHQ, ERateSignal, Apify); the FCC is building a bidding portal (FY2028) that could commoditize it further | https://www.frnhq.com/form-470-alerts , https://www.federalregister.gov/documents/2026/05/19/2026-10011/promoting-fair-and-open-competitive-bidding-in-the-e-rate-program-schools-and-libraries-universal |
| CA DIR public-works registration renewal (state-level SAM analogue) | Same scam-adjacent dynamics as SAM; DIR search is manual export only; low value per firm | https://www.dir.ca.gov/dlse/dlse-databases.htm |
| Certified payroll for prevailing-wage subcontractors | Real need, but software is cheap (LCPcertified from $145/mo; QuickBooks add-ons $50–$200/mo) and it is payroll-processing work, not data interpretation | https://lcptracker.com/solutions/lcpcertified/ |

---

## 4. Ranked shortlist

Scores run 1–10; 10 is best. For competition, 10 means blue ocean. The overall score is the unweighted mean; time to first dollar of 10 means fastest.

| Rank | Idea | Market size | WTP | Data access | Automation | Competition | Recurring | Time to $1 | **Overall** | Confidence |
|---|---|---|---|---|---|---|---|---|---|---|
| 1 | **A. Single-audit Finding Fixer** | 6 | 6 | 9 | 8 | 8 | 6 | 7 | **7.1** | Medium-low (WTP for this exact deliverable unproven) |
| 2 | **B. Water Pipeline Radar (SRF IUPs + SDWIS/PFAS/LCRI)** | 6 | 7 | 6 | 8 | 7 | 9 | 5 | **6.9** | Medium (post-BIL funding risk) |
| 3 | **C. Town Grant Desk (flat retainer)** | 7 | 8 | 8 | 5 | 5 | 8 | 5 | **6.6** | Medium (WTP proven by council minutes; volatile federal grants) |
| 4 | D. Grant-Funded Pipeline for vendors | 6 | 7 | 7 | 7 | 5 | 8 | 4 | **6.3** | Low-medium |
| 5 | E. Trade bid concierge + price-to-win | 6 | 5 | 5 | 6 | 3 | 7 | 7 | **5.6** | Medium (crowded) |
| 6 | G. Subcontracting-plan partner matcher | 4 | 4 | 6 | 7 | 4 | 6 | 4 | **5.0** | Low |
| 7 | H. Statutory incentive recovery (referral) | 6 | 7 | 5 | 3 | 3 | 2 | 4 | **4.3** | Medium |
| 8 | F. SAM renewal desk | 4 | 3 | 6 | 9 | 1 | 5 | 6 | **4.9 → effectively reject** (reputation/legal override) | High that it's a bad idea |

### Honest read

- **Best fit with the brothers' playbook:** **A** and **C**. Both have public data that names the entity and the specific problem, a free personalized "pre-built" deliverable (finding memo or Funding Map), email-first outreach to a public contact, and a done-for-you service with recurring pricing.
  - **A** has the cleanest data: an API with emails and the finding text.
  - **C** has the cleanest willingness-to-pay evidence: public council-approved retainers of $2.1k–$5.5k/mo.
- **Best pure-software business:** **B**. It is a recurring data subscription with ~85% automation, but needs consultative selling and faces a post-2026 funding cliff.
- **Suggested sequencing:**
  1. Run A as a two-week test: 500 emails with free finding memos. Kill if fewer than 3 paid packs.
  2. In parallel, build B's extraction for 5 states, since it is cheap given Claude PDF extraction, and test with 25 engineers.
  3. Hold C until a human grant writer partner is lined up, because quality failures on government applications are reputational.
- **What would change my mind**
  - On A: if a test shows finance directors pay under $1k, or only through their auditor, A collapses into a lead-gen product for CPA firms.
  - On B: if Dodge or ConstructConnect already parse SRF priority lists with PWSID joins (I could not confirm either way), B's moat shrinks.

---

### Research notes and limits

- Third-party pricing for GovWin, GovSpend and GovTribe comes from Vendr and competitor blogs (fed-spend, Civic IQ, RFP Recon), which have an incentive to inflate incumbent prices. HigherGov's price was verified on its own pricing page.
- FAC counts came from live API queries on 2026-10-01 using DEMO_KEY. The "procurement" proxy count (`type_requirement like *I*`) is approximate.
- Not verified:
  - the share of single audits with any finding;
  - the national count of water/wastewater engineering firms;
  - sponsorship prices for Lexipol and Grants Office programs;
  - HigherGov API redistribution terms.
