# Lane 05 — Real Estate, Construction & Property Data

*Research date: 2026-10-01. Research only: no outreach, signups or purchases were made. Every material claim has a URL. Anything marked **(est.)** is my own estimate, not a sourced figure.*

---

## TL;DR

- **Raw permit, planning, deed and foreclosure data is already a commodity.** Shovels sells nationwide permit data from $599/mo, and at least four AI-native startups now resell permits for $39/mo or less. An Apify actor that sells NYC elevator-compliance "leads" for $2.50 per 1,000 records has **2 total users**. Reselling a cleaner copy of the same public records is a losing business.
- **The value left is in *combinations* that point to a capital event**: a legal deadline, plus who owns the building, plus who currently services it, plus evidence that they haven't complied yet. The richest under-used example in this lane is **Florida's post-Surfside condo regime**. The state gives away CSV files of every condo association, a public database of who has filed their structural reserve study (SIRS), a public elevator registry that **names each elevator's current maintenance contractor**, and free bulk corporate records (Sunbiz) listing board officers and registered agents. Nobody I found joins these into a B2B feed.
- **Top recommendation:** build one **Florida association data spine** and sell it to three buyer groups: engineering and restoration firms, management (CAM) firms, and independent elevator contractors. NJ (reserve studies every 5 years) and other states come later.
- **Killed or deprioritized:** lender/insurer risk feeds (Verisk/BuildFax, Moody's/CAPE, ZestyAI), pre-foreclosure lists (PropStream $99/mo), interconnection queues (Enverus/Pearl Street, Paces, GridTracker), STR enforcement (Granicus, Deckard), planning-agenda feeds (cityminutes.ai, GatherGov), tax-sale surplus recovery, Texas BPP renditions (killed by HB 9's $125k exemption), and NYC violation monitoring ($9/building/mo).

---

## 1. Lane overview: landscape, incumbents, gaps

### 1.1 Incumbents and what they charge

| Segment | Incumbents | Pricing evidence |
|---|---|---|
| Permit data / API | Shovels | Free tier; Basic $599/mo; Pro $999/mo; Enterprise data license ([shovels.ai/pricing](https://www.shovels.ai/pricing), [coldiq](https://coldiq.com/tools/shovels)). Raised about $5M seed in June 2025 ([Commercial Observer](https://commercialobserver.com/2025/06/shovels-proptech-permits/)) |
| Permit leads (legacy) | Construction Monitor (since 1989) | Priced per market and category, about $31–$1,281/mo; LA is $960/yr ([Shovels comparison](https://www.shovels.ai/compare/construction-monitor), [JLC](https://www.jlconline.com/business/sales-marketing/pulled-permits-as-a-source-of-leads)) |
| Permit data (contractor history) | BuildZoom | Roughly $500–$2,000+/mo on annual contracts ([PermitLedger comparison](https://permitledger.com/blog/building-permit-database-comparison)) |
| Permit data, AI-native low end | PermitLedger, PermitStack, TradeBridge, Apify actors | PermitLedger $39/mo for 326 cities ([PermitLedger](https://permitledger.com/blog/building-permit-database-comparison)); [PermitStack pricing comparison](https://permit-stack.com/blog/building-permit-data-api-pricing-compared.html) |
| Pre-construction project leads | Dodge, ConstructConnect, PlanHub, BuildingConnected | Dodge: contractor reports put it around $5k–$15k+/yr ([constructionbids.ai](https://constructionbids.ai/blog/dodge-construction-network-alternative)). ConstructConnect: $129–$199/mo per market ([constructionbids.ai](https://constructionbids.ai/blog/dodge-vs-constructconnect-comparison)). PlanHub subs: $1,999–$3,299/yr ([PlanHub](https://planhub.com/pricing-subcontractors/)). BuildingConnected is free for subs ([constructionbids.ai](https://constructionbids.ai/blog/buildingconnected-pricing-2026)) |
| Planning / zoning agendas | cityminutes.ai, GatherGov, Apify scrapers | cityminutes claims 3,142 counties with a weekly feed ([cityminutes.ai](https://cityminutes.ai)); GatherGov claims 6,000+ jurisdictions ([GatherGov](https://gathergov.com/articles/land-entitlement-guide)) |
| Investor lists (deeds, liens, pre-foreclosure) | PropStream, BatchLeads, ATTOM | PropStream $99–$699/mo; BatchLeads from $119/mo; ATTOM API from about $95/mo ([search summary sources: offermarket](https://www.offermarket.us/blog/propstream-pricing), [resimpli](https://resimpli.com/blog/batchleads-review/), [trustradius](https://www.trustradius.com/products/attom-data-solutions/pricing)) |
| Residential tax appeal | Ownwell plus many clones | 25–35% contingency; more than 1M appeals; $74M raised; in 9 states ([Inman](https://www.inman.com/2026/02/25/ownwell-raises-50m-to-grow-its-property-tax-appeal-fintech/), [HousingWire](https://www.housingwire.com/articles/ownwell-property-tax-appeal-funding/), [appealdesk](https://www.appealdesk.com/blog/ownwell-pricing-review)) |
| Commercial tax appeal | Ryan, O'Connor, KSN, Marvin Poer, local attorneys | Typically 25–35% of first-year savings on standard commercial ([Paramount](https://www.paramountpropertytaxappeal.com/blog/contingency-fee-property-tax-appeal)) |
| Insurer / lender property risk | Verisk (BuildFax), Moody's (CAPE), ZestyAI | BuildFax roof-permit database covers 10M+ homes ([Verisk](https://www.verisk.com/blog/how-old-is-that-roof/)). Moody's closed its CAPE acquisition in January 2025 ([MarketScreener](https://www.marketscreener.com/quote/stock/MOODY-S-CORPORATION-16724/news/Moody-s-Corporation-completed-the-acquisition-of-Cape-Analytics-LLC-48746276/)) |
| Interconnection queues | Enverus (acquired Pearl Street in 2025), Paces, GridTracker / Interconnection.fyi, LBNL (free) | [Enverus](https://www.enverus.com/newsroom/undo-the-queue-enverus-acquires-pearl-street-technologies-to-solve-for-a-more-reliable-resilient-grid/), [Paces $11M Series A](https://www.esgdive.com/news/data-platform-paces-nabs-11m-to-scale-clean-energy-development/722671/), [Interconnection.fyi data](https://www.interconnection.fyi/data-subscription) |
| STR enforcement (sold to cities) | Granicus Host Compliance, Deckard | City contracts run about $3k–$46k/yr, low six figures in Nashville ([CBS Texas](https://www.cbsnews.com/texas/news/how-are-cities-monitoring-short-term-rentals-many-are-turning-to-tech/), [TrustRadius](https://www.trustradius.com/products/granicus-host-compliance/pricing)) |
| Energy benchmarking / BPS compliance | Envigilance, Insparisk, Vert, Touchstone IQ, Beacon, Elevate, local engineers | Elevate charges $800/building for Chicago benchmarking ([Elevate](https://www.elevatenp.org/energy-efficiency/chicago-benchmarking-compliance-services/)); Beacon $95/mo ([Beacon](https://www.beaconalerts.com/benchmarking)); Envigilance from $750/mo ([Envigilance](https://envigilance.com/energy-monitoring/energize-denver/)) |
| NYC violation / compliance monitoring | ViolationWatch, DOBGuard, SiteCompli | ViolationWatch $9/building/mo; DOBGuard about $50/mo ([ViolationWatch](https://violationwatch.nyc/resources/best-nyc-violation-monitoring-tools-2026)) |
| Fire-system inspection reporting | Brycer's The Compliance Engine | Free to the city; contractors pay $10–$75 per report ([Charleston](https://www.charleston-sc.gov/2586/Compliance-Reporting), [Gaithersburg](https://www.gaithersburgmd.gov/services/fire-marshal/fire-systems-license), [Raleigh FAQ](https://cityofraleigh0drupal.blob.core.usgovcloudapi.net/drupal-prod/COR18/TCEFaq.pdf)) |
| Municipal lien / open-permit search (FL) | PropLogix plus dozens of small firms | $100 basic, $125 with permits, plus municipal fees ([FL Municipal Lien Search](https://floridamunicipalliensearch.com/pricing/)). PropLogix has about 150–250 staff (estimates vary: [growjo](https://growjo.com/company/PropLogix), [craft](https://craft.co/proplogix)) |

### 1.2 What the evidence says about where value sits

1. **Raw records sell for almost nothing.** An Apify actor selling NYC elevator compliance flags at $2.50 per 1,000 records shows "2 total users, 1 monthly users" ([Apify](https://apify.com/kempdata/nyc-elevator-compliance)). PermitLedger sells 326 cities of permits for $39/mo ([PermitLedger](https://permitledger.com/blog/building-permit-database-comparison)). The brothers' advantage (agents that do the *work*: build the deliverable, write the outreach, handle replies) is wasted on reselling data.
2. **Compliance fines are often weaker than marketers claim.** In LL97's first year, about 28,000 buildings were required to report, 93% filed, and only about 470 BBLs exceeded their limits. Penalties for Article 320 buildings totalled about **$270,150** ([nyc.gov HPD](https://www.nyc.gov/site/hpd/news/023-26/new-compliance-data-shows-impact-local-law-97-improve-sustainability-new-york-city); [Yahoo/Habitat](https://www.yahoo.com/news/us/articles/strong-compliance-first-nyc-local-153439810.html)). "Fine avoidance" pitches for NYC are mostly fear marketing until 2030, when REBNY projects fines above $900M/yr ([REBNY](https://www.rebny.com/press-release/report-local-law-97-fines/)). The real near-term pain is **failure to file**: about 1,400 NYC properties didn't file ([nyc.gov](https://www.nyc.gov/site/hpd/news/023-26/new-compliance-data-shows-impact-local-law-97-improve-sustainability-new-york-city)).
3. **Mandates that force big capital spending are worth more than mandates that only require reporting.** Florida condos are the clearest case. Buildings three stories and up need a milestone inspection at 30 years and every 10 years after ([Fla. Stat. 553.899](https://www.leg.state.fl.us/Statutes/index.cfm?App_mode=Display_Statute&URL=0500-0599%2F0553%2FSections%2F0553.899.html)). They also need a SIRS (structural integrity reserve study), and reserves must be funded. Special assessments of $10k–$50k+ per unit are common ([Saving Advice](https://www.savingadvice.com/articles/2026/01/06/10712998_many-florida-condo-owners-are-facing-surprise-special-assessments.html)). Association loans of $5M–$30M+ for structural restoration are routine ([Mosaic](https://mosaichoa.com/blog/how-to-get-hoa-loan-florida/)). Each signal there points to five- to eight-figure spending.
4. **Gap: state-regulated association data.** Florida publishes:
   - **condo associations by county** (name, address, units, managing entity) as free CSVs ([DBPR public records](https://www2.myfloridalicense.com/condos-timeshares-mobile-homes/public-records/))
   - a **public SIRS reporting database** ([DBPR SIRS](https://www2.myfloridalicense.com/condos-timeshares-mobile-homes/condominiums-and-cooperatives-sirs-reporting/))
   - an **elevator registry** with install year, last passed inspection, and **maintenance-contract company** ([DBPR Elevator public records](https://www2.myfloridalicense.com/elevator-safety/public-records/))
   - **free bulk Sunbiz corporate files** with officers and registered agents ([FL DOS data downloads](https://dos.fl.gov/sunbiz/other-services/data-downloads/quarterly-data/))
   - the list of **2,001 licensed CAM (management) firms** ([Dwellory](https://dwellory.org/fl/cam-firms/), from DBPR's weekly extract).

   Consumer-facing condo "health scores" exist (Domexa Labs ([Grit Daily](https://gritdaily.com/domexa-labs-creates-condo-health-score/)), governingdocs.dev, probayway's deadline checker ([probayway](https://probayway.com/building-deadline-checker/))). I found **no B2B feed** that joins these sources for the vendors who sell into associations.

---

## 2. Candidate ideas

Ideas 1, 2 and 4 share one data spine. Building them together is the main recommendation.

---

### Idea 1 — Florida Condo Capital-Event Feed (SIRS, milestone inspection, special-assessment signals)

**Pitch:** A weekly, per-county feed of Florida condo associations that are about to spend money. Each record shows who manages the building, its age, height and unit count, its SIRS and milestone status, and its elevator age. Each comes with an agent-written outreach draft. It is sold to engineering firms, concrete-restoration contractors, association lenders and insurance brokers.

**Data sources (access / cost / terms):**
- **DBPR condominium files by county (CSV):** project, units, address, recorded date, managing entity. Free download ([DBPR](https://www2.myfloridalicense.com/condos-timeshares-mobile-homes/public-records/)). These are Florida public records under Ch. 119; commercial reuse is allowed.
- **DBPR SIRS reporting database:** which associations have certified completion, with optional cost and professional fields. Public web view, updated within one business day ([DBPR SIRS](https://www2.myfloridalicense.com/condos-timeshares-mobile-homes/condominiums-and-cooperatives-sirs-reporting/)). It holds no study documents, and its data quality is uneven (one submission reported $480M, another 6¢) ([Citizen Portal](https://citizenportal.ai/articles/6325346/Florida/2025-Legislature-FL/DBPR-says-SIRS-database-is-live-but-incomplete-agency-lacks-strong-enforcement-power)). Bulk export: **unverified**. Plan on scraping the public view or a Ch. 119 request.
- **DBPR online-portal reporting (since July 1, 2025):** building data, assessments and alternative funding, SIRS status, board members ([Eisinger Law](https://www.eisingerlaw.com/2025/08/important-update-for-florida-condominium-associations-new-dbpr-online-reporting-requirements-effective-july-1-2025/)). Whether this is public is **unverified**. Request it under Ch. 119; this is the highest-value semi-private dataset in the lane.
- **County property appraiser parcels:** year built, stories, sales. Free or cheap in most FL counties (est.).
- **Local building departments, milestone status:** Pinellas and Tampa run programs but don't publish lists ([Pinellas](https://pinellas.gov/condo-milestone-inspections/), [Tampa](https://www.tampa.gov/construction-services/condo-recert)). Local agencies report counts to the state each year ([553.899](https://www.leg.state.fl.us/Statutes/index.cfm?App_mode=Display_Statute&URL=0500-0599%2F0553%2FSections%2F0553.899.html)). Building-level status needs Ch. 119 requests or permit-portal scraping (milestone and repair permits). Expect a human to send public-records requests.
- **DBPR elevator registry:** install year, last passed inspection, maintenance company ([DBPR elevator](https://www2.myfloridalicense.com/elevator-safety/public-records/)).
- **Sunbiz bulk files:** association officers and registered agent. Free SFTP ([FL DOS](https://dos.fl.gov/sunbiz/other-services/data-downloads/)).

**The combination that creates new value:** compliance status (SIRS filed or not; milestone due by CO date plus 30 years) × building physicals (age, stories, coastal location, elevator age) × decision-maker (managing CAM firm or self-managed board) × money signals (reported assessments, SIRS cost, repair permits). Each source alone is free and nearly useless. Joined, they produce a ranked list of "who will issue an RFP for restoration or engineering work, or need a loan, in the next 6–18 months."

**Scale of the signal:**
- About 27,750 condo associations; 11,270 self-report buildings of 3+ stories ([Citizen Portal](https://citizenportal.ai/articles/6325346/Florida/2025-Legislature-FL/DBPR-says-SIRS-database-is-live-but-incomplete-agency-lacks-strong-enforcement-power), [search summary of HB 913 analysis](https://www.flsenate.gov/Session/Bill/2025/913/Analyses/h0913c.COM.PDF)).
- 4,096 SIRS submissions by February 2025 ([Citizen Portal](https://citizenportal.ai/articles/6325346/Florida/2025-Legislature-FL/DBPR-says-SIRS-database-is-live-but-incomplete-agency-lacks-strong-enforcement-power)); about 7,836 by November 30, 2025 ([Saving Advice](https://www.savingadvice.com/articles/2026/01/06/10712998_many-florida-condo-owners-are-facing-surprise-special-assessments.html)). That leaves roughly 3,400 3+ story associations unreported at the deadline (est.).
- South Florida: 62% had not completed a SIRS by the original deadline ([Zalewski / Miami Realtors data](https://peterzalewski.substack.com/p/warning-62-of-south-florida-condos)).
- Fannie Mae's "unavailable" list included 1,438 Florida buildings, most for critical repairs ([MPA](https://www.mpamag.com/us/news/general/fannie-maes-secret-blacklist-prevents-florida-condo-sales-mortgages/531270)).
- DBPR says it **lacks authority to penalize** SIRS non-reporting ([Citizen Portal](https://citizenportal.ai/articles/6325346/Florida/2025-Legislature-FL/DBPR-says-SIRS-database-is-live-but-incomplete-agency-lacks-strong-enforcement-power)). That cuts both ways: weak state enforcement, but lenders (Fannie) and buyers enforce it instead.

**Buyer personas (exact):**
1. Business-development lead or principal at a Florida structural/forensic engineering firm doing milestone inspections and SIRS (e.g., firms like UES, M2E ([UES](https://www.teamues.com/your-florida-milestone-inspection-experts/), [M2E](https://www.m2e.com/services/milestone-inspections/))).
2. Estimator or BD manager at a concrete-restoration or waterproofing contractor (balconies, garages).
3. Relationship manager at a community-association banking desk (assessment-backed loans of $100k–$30M+ ([Mosaic](https://mosaichoa.com/blog/how-to-get-hoa-loan-florida/))).
4. Commercial lines producer at an insurance agency writing condo master policies.
5. Sales rep at an elevator modernization company (see Idea 4).

**Evidence of willingness to pay:**
- Ticket sizes are large. A SIRS costs $3.3k–$22k+ depending on size; full reserve studies run $1.65k–$16.5k+ ([FPAT](https://fpat.com/reserve-study-cost-florida/)). A restoration job behind a $25k-per-unit assessment on a 100-unit building is about $2.5M (est., from [Saving Advice](https://www.savingadvice.com/articles/2026/01/06/10712998_many-florida-condo-owners-are-facing-surprise-special-assessments.html)).
- Comparable B2B construction-lead subscriptions sell for $1.2k–$15k+/yr (Dodge, ConstructConnect, PlanHub; see table).
- Modernization territory reps are paid up to about $150k base ([ZipRecruiter](https://www.ziprecruiter.com/Jobs/Elevator-Salesman)). One closed lead is worth far more than a year's subscription.
- **No direct evidence yet** that FL engineering firms buy lead feeds; they rely on CAM relationships. This is the main thing to validate.

**Market size (bottom-up, est.):**
- Buyers in FL (est.): 150–300 engineering/architecture firms doing condo work; 200–400 restoration and waterproofing contractors; 20–40 association-lending banks and desks; 300+ condo insurance agencies; about 100–200 elevator companies.
- Realistic paid base (est.): 60–150 subscribers × $500–$1,500/mo = **$0.4M–$2.7M ARR in Florida**.
- Expansion: NJ requires capital reserve studies within 2 years of January 2024 and every 5 years after, plus structural inspections ([MG McLaren](https://www.mgmclaren.com/blog/understanding-nj-condominium-inspections-law/), [Ansell](https://ansell.law/new-jersey-enacts-stringent-new-inspection-evaluation-and-maintenance-requirements-for-condominium-and-co-op-buildings/)). California has SB 326/721 balcony inspections, but no public registry ([Burlingame](https://www.burlingame.org/1298/SB-721-and-SB-326---Balcony-Laws)).
- Ceiling as a pure lead feed: probably **under $10M ARR** (est.). That is a good small business, not a venture-scale one.

**Deliverable and pricing:** a per-county subscription by vertical (e.g., "Broward + Palm Beach, restoration"). It includes a weekly ranked list, a one-page building dossier per lead, and an agent-drafted email to the CAM or board president. Proposed tiers: **$600/mo for one county, $1,500/mo for a region, $4k/mo statewide** (est.). Optional pay-per-meeting add-on of about $300 per booked meeting (est.). Recurring.

**Automation pipeline:**
1. *Find prospects:* scrape lists of engineering firms (Florida PE board licensee files), restoration contractors (DBPR CILB licensees), and the 2,001 CAM firms. Rank by size from websites and permit history.
2. *Build the deliverable:* a nightly ETL joins the DBPR condo CSV, SIRS database, appraiser parcels, elevator registry and Sunbiz officers on address and name, with fuzzy matching and Claude resolving ambiguous matches. Claude writes each building dossier and a "why now" line.
3. *Personalized outreach:* send each prospect a free sample of the 10 best leads in their own county, built specifically for them. This is the website-model playbook: show the finished product first.
4. *Handle replies:* Claude agent answers questions, sends extra samples, and books calls.
5. *Deliver and renew:* weekly delivery by email or CSV; a monthly "wins" report. Self-serve Stripe billing.

**Percent automatable:** about 80%. Remaining human touchpoints: sending and following up Ch. 119 requests (some counties want phone or mail), QA on entity matching, closing calls for regional and statewide tiers, and handling data-dispute emails from associations.

**GTM, first 90 days:**
- Days 1–30: build the spine for 3 counties (Miami-Dade, Broward, Palm Beach). Send 10 Ch. 119 requests (DBPR portal assessments, county milestone lists).
- Days 31–60: send free samples to 300 restoration contractors and engineers; target 15 calls and 5 paid pilots at $300/mo.
- Days 61–90: add Pinellas, Sarasota and Lee (Gulf coast; older buildings); launch the elevator-vendor product (Idea 4) on the same spine.

**Unit economics (est.):** ARPA about $800/mo. Outbound CAC about $400–$900 (email infrastructure, enrichment at about $0.05/contact, founder time on calls). Gross margin about 85–90%. Data cost is close to $0 (public records, plus about $50–$500 per county in records-request fees). LLM cost is under $100/mo per county. Payback is about 1 month if churn stays under 5% monthly.

**Competitors and crowding:**
- Consumer side: Domexa (free score), governingdocs.dev, probayway checker, Realtor education pages ([Miami Realtors](https://www.miamirealtors.com/condos/sirs/)).
- B2B side: generic construction-lead services (Dodge, ConstructConnect) catch the bid only *after* a project is designed. **No direct B2B competitor found. Moderately blue ocean.**

**Legal / regulatory:**
- CAN-SPAM applies to B2B email; no opt-in is needed, but you must honor opt-outs and use accurate headers ([FTC summary via Mailtrap](https://mailtrap.io/blog/can-spam-cold-emails/)). Florida's email law (§668.606) allows private suits over deceptive email ([FL AG](https://www.myfloridalegal.com/spam/floridas-law-what-spam-is-prohibited)).
- **Don't text or autodial.** The Florida Telephone Solicitation Act was narrowed in 2023 but is still litigated ([Gunster](https://www.gunster.com/newsroom/publications/governor-desantis-signs-amendment-to-the-ftsa)).
- Florida public records may be reused commercially. Avoid publishing individual owners' personal data.
- Defamation risk if a building is mislabeled "non-compliant" because of a database lag. Phrase it as "no SIRS on file with DBPR as of DATE".

**Kill risks:**
1. Engineering firms and contractors get enough work through CAM relationships and won't pay for leads. This is the core WTP risk; validate with 5 paid pilots before scaling.
2. The urgency is a one-time spike: SIRS was due 12/31/2025, milestone inspections hit their 2026 wave, and then demand settles into a 10-year cycle. Mitigation: shift to money signals (assessments, loans, repair permits) and new 30-year buildings each year.
3. The legislature changes the rules again (HB 913 already extended deadlines and loosened reserves ([Building Mavens](https://buildingmavens.com/blog/florida-2025-sirs-law-changes-hb913/))), or DBPR stops publishing the SIRS view.

---

### Idea 2 — Association "Switch-Signal" Engine for Management Companies (FL first)

**Pitch:** Tell Florida CAM firms which associations are **self-managed** or **likely to fire their manager** this quarter. Signals: board turnover, missing SIRS, DBPR complaints, a coming special assessment. Each lead comes with a ready-made proposal.

**Data sources:**
- Sunbiz quarterly and daily corporate files with officers and registered agent. Free SFTP ([FL DOS](https://dos.fl.gov/sunbiz/other-services/data-downloads/)). A registered agent who is an individual or a board member, rather than a CAM firm or law firm, suggests self-management.
- DBPR condo CSV "managing entity" field ([DBPR](https://www2.myfloridalicense.com/condos-timeshares-mobile-homes/public-records/)).
- DBPR CAM firm licensee list, 2,001 firms ([Dwellory](https://dwellory.org/fl/cam-firms/)).
- DBPR complaint status, publicly searchable via license verification ([DBPR FAQ](https://condos.myfloridalicense.com/faqs/)).
- SIRS database (above). HOAs (Ch. 720) aren't in DBPR's condo files, so Sunbiz plus appraiser parcels are needed to count homes.

**The combination:** Sunbiz officer changes (a new board often re-bids management) × self-management detection (registered agent type, blank managing entity) × size in doors (units/parcels) × compliance stress (SIRS missing, complaints). Management firms currently find this by hand through referrals.

**Buyer persona:** owner or VP of business development at a Florida CAM firm with 10–500 associations under management. PE-backed roll-ups (Associa, FirstService) are aggressive buyers of growth ([L.E.K.](https://www.lek.com/insights/ind/us/ei/hoa-management-services-gateway-residential-and-commercial-services)).

**Evidence of WTP:**
- Florida management fees are $10–$30 per unit per month, often with $1.5k–$3k/mo minimums ([search summary: Mosaic](https://mosaichoa.com/blog/hoa-management-company-cost/), [Edison](https://edisonassociationmanagement.com/blog/hoa-management-fees)). One 150-unit win is worth about $27k–$54k/yr (est.).
- HOAManagement.com sells flat annual directory listings to management companies ([HOAM](https://www.hoamanagement.com/advertiseonhoam/)), which shows they pay for lead flow.
- Nationally, 30–40% of about 373k associations are self-managed, and there are 9,000–10,000 management companies ([CAI Foundation](https://foundation.caionline.org/research/industry-data/)).

**Market size (est.):** Florida has 2,001 CAM firms. If 5% subscribe at $500/mo, that's about $600k ARR. Nationally, 9–10k management companies × 3% × $500/mo is about $1.7M ARR. Only about 7–8 states license CAMs ([Dwellory](https://dwellory.org/fl/cam-firms/)), so data quality drops outside FL; Colorado, Nevada and Virginia have HOA registries (unverified for bulk access).

**Deliverable and pricing:** a monthly "switch-ready" list per county with a dossier and a draft proposal letter. $400–$800/mo, or $500 per signed management contract as a success fee (est.). Recurring.

**Pipeline:**
1. *Find:* the CAM firm list (DBPR).
2. *Build:* diff Sunbiz daily filings for officer changes on association entities; score each association.
3. *Outreach:* email each CAM firm 5 real switch-signals in its own territory.
4. *Replies:* Claude agent.
5. *Deliver and renew:* monthly. About 80% automatable. Humans handle the sales call and QA on self-managed classification.

**GTM, 90 days:** same spine as Idea 1. Launch to the 2,001 FL CAM firms with free samples. Target 10 paying firms.

**Unit economics (est.):** price $500/mo; CAC $300–$600; gross margin about 90%; data cost about $0.

**Competitors:** HOAManagement.com (inbound directory), SEO agencies, and referral networks. **No signal-based product found.**

**Legal:** CAN-SPAM. Board members are private individuals acting in an official role; email them only at association addresses and avoid personal-data enrichment. Florida email statute as above.

**Kill risks:**
1. Management contracts change hands through relationships and RFPs; a lead doesn't move them.
2. The self-managed classifier from registered-agent heuristics is noisy.
3. A small buyer pool caps the market; it works mainly as an add-on to Idea 1.

---

### Idea 3 — Agent-Run Benchmarking Filing for Newly Covered Mid-Size Buildings

**Pitch:** A fixed-fee, nearly fully automated annual service for 10k–50k sq ft buildings newly caught by benchmarking and BPS laws. It requests utility data, builds the Portfolio Manager account, files, and handles deficiency notices. The first customers come from lists of *non-filers*.

**Data sources:**
- Covered-building lists, mostly open data. Chicago has 3,693 covered buildings on Socrata ([Chicago](https://data.cityofchicago.org/api/views/g5i5-yz37.json)); NYC's covered list is via DOF ([nyc.gov LL84](https://www.nyc.gov/site/buildings/codes/ll84-benchmarking-violations.page)); DC open data ([DC](https://opendata.dc.gov/content/dde606b4546341cd9c0e3087a8b476e6)).
- Disclosure datasets of who *did* file. **Covered list minus disclosed list = non-filers.**
- Utility data: 70+ utilities provide whole-building data, about 60 through Portfolio Manager web services ([ENERGY STAR](https://www.energystar.gov/sites/default/files/2025-01/Utility%20Data%20Access%20Fact%20Sheet%20-%20December%202024_508.pdf)). Portfolio Manager is free.
- Assessor owner records for building owners.

**The combination:** covered-building list × disclosure list (non-filers) × assessor owner/LLC × utility (does it offer automatic upload?) tells you who is out of compliance and how cheaply you can serve them.

**Where the new demand is:**
- **DC:** all private buildings over 10,000 sq ft must benchmark from CY2025 data, due May 1, 2026 ([DCSEU](https://www.dcseu.com/resource-library/beps), [Honeydew](https://honeydewadvisors.com/washington-dc-lowers-its-benchmarking-threshold-to-10000-square-feet/)).
- **Washington State Tier 2:** 20k–50k sq ft buildings must benchmark and also submit an energy management plan and O&M program by **July 1, 2027**, with penalties up to $0.30/sq ft ([WA Commerce](https://www.commerce.wa.gov/cbps/tier-2-compliance/)).
- **Maryland BEPS:** about 9,000 buildings of 35k+ sq ft, reporting annually from 2025, fines up to $500/day ([search summary: SMECO](https://www.smeco.coop/energy-efficiency/commercial-programs/maryland-building-energy-performance-standards-beps/), [swinter](https://www.swinter.com/maryland-beps-recommendations-for-building-owners/)).
- **Denver:** $2,000 for unapproved benchmarking; $10/sq ft for buildings that never submitted ([search summary: Envigilance](https://envigilance.com/blog/energize-denver-penalties/)).
- **NYC LL84:** $500 per quarter, up to $2,000/yr ([nyc.gov](https://www.nyc.gov/site/buildings/codes/ll84-benchmarking-violations.page)).
- **Boston BERDO:** $150–$300/day for non-reporting ([Facilities Dive](https://www.facilitiesdive.com/news/what-to-know-about-berdo-bostons-building-performance-standards-law/725082/)).
- Chicago reporting compliance has fallen to 82% ([search summary: Chicago 2023 report](https://www.chicago.gov/content/dam/city/depts/doe/Reports/43360-20250404-DOE-Sustainability%20Report_C%20-%202023%20infographic.pdf)).
- About 60 jurisdictions require benchmarking and 16 have active BPS laws ([IMT](https://imt.org/news/2026-building-policies-outlook-local-state-leadership-in-a-federal-vacuum/)).

**Buyer persona:** an owner or small property manager of a 10k–50k sq ft office, retail, church, school or multifamily building, with no energy staff. Usually an LLC owner who manages 1–10 buildings.

**Evidence of WTP:**
- Elevate charges $800/building ([Elevate](https://www.elevatenp.org/energy-efficiency/chicago-benchmarking-compliance-services/)); Beacon $95/mo ([Beacon](https://www.beaconalerts.com/benchmarking)).
- Manual benchmarking for 20 buildings across 5 jurisdictions can cost over $40k/yr in labor ([IFMA](https://jobboard.ifma.org/career-resources/on-the-job-3/energy-benchmarking-with-energy-star-portfolio-manager-for-facility-manager-2026-126)).
- Fines of $2k–$10/sq ft give a clear ROI.

**Market size (bottom-up, est.):** across NYC, DC, Chicago, Boston, Denver, Seattle, WA Tier 2 and MD, there are probably 60k–100k covered buildings (est.; NYC LL97 alone is about 28k). Assume 30% use paid help and 5–15% fail to file. A 3% capture at $500/yr is about $1M–$1.5M ARR. The ceiling is higher if you add WA Tier 2 energy-management-plan templates ($1.5k–$3k one-time, est.).

**Deliverable and pricing:** $450–$900 per building per year, with a filing guarantee: "we pay the late fine if we miss." Recurring annually. Upsell: WA Tier 2 plan pack, and BPS gap analysis delivered through partner engineers.

**Pipeline:**
1. *Find:* non-filer list plus assessor owner, with LLC piercing through Secretary of State data.
2. *Build:* a pre-filled "your compliance status and fine exposure" one-pager per building.
3. *Outreach:* email (and direct mail where no email exists) the owner or property manager with their building's fine exposure.
4. *Replies:* agent collects the utility authorization (e-sign) and account numbers.
5. *Deliver:* create the Portfolio Manager property, connect the utility web service, run data-quality checks, and submit to the city; renew annually.

**Percent automatable:** about 70%. Human touchpoints:
- utility authorization forms, which some utilities still handle on paper
- tenant meter data in cities without whole-building aggregation
- NYC LL97 and other BPS filings, which need a **registered design professional's attestation** ([NYC DOB](https://www.nyc.gov/assets/buildings/pdf/ll97-compliance-report-process.pdf)); partner with a PE for those
- WA Tier 2 plans, which need light review.

**GTM, 90 days:** pick **DC** (new 10k–25k cohort; first disclosure year is CY2026 data, due May 2027 ([search summary](https://www.dcseu.com/resource-library/beps))) and **WA Tier 2** (July 2027 deadline). Build non-filer and covered lists, then mail and email 2,000 owners. Target 50 buildings at $600.

**Unit economics (est.):** ARPU $600/yr; CAC $150–$300 (some direct mail at about $1 per piece); gross margin about 75% (agent plus about 30 min of human QA per building); data cost about $0.

**Competitors:** crowded and fragmented: Envigilance, Insparisk, Vert, Touchstone IQ, Beacon, Elevate, FirstService Energy, Honeydew, The Cotocon Group, and hundreds of local engineers. **Red-ocean product; the edge is price and automation.**

**Legal:** CAN-SPAM; direct mail has no consent rules. Don't misstate fines (state-law UDAP risk). Utility data authorizations must be properly executed.

**Kill risks:**
1. Low price combined with heavy human handling for edge cases (paper utility forms, tenant meters) squeezes margins.
2. Cities and utilities keep simplifying self-filing (free help desks, auto-upload), which erodes WTP. Denver and DC run free help desks.
3. Political rollback of BPS. The federal climate retreat is noted ([IMT](https://imt.org/news/2026-building-policies-outlook-local-state-leadership-in-a-federal-vacuum/)), and deadlines slip.

---

### Idea 4 — "Conveyance Intel" for Independent Elevator Contractors (FL, TX, NYC)

**Pitch:** For each territory, show independent elevator companies who services every elevator, how old it is, when it last passed inspection, and who owns it. Flag modernization candidates (older than about 25 years) and accounts serviced by a competitor where inspections are failing.

**Data sources:**
- **Florida DBPR elevator files (CSV):** install year, last passed inspection, landings, capacity, **maintenance company / contract status**, owner and address ([DBPR elevator](https://www2.myfloridalicense.com/elevator-safety/public-records/)).
- **Texas TDLR elevator data file** (about 8MB CSV): owner, contact, last and next inspection, 5-year test, year installed ([TDLR search help](https://www.tdlr.texas.gov/elevator_searchapp/home/searchhelp), [TDLR](https://www.tdlr.texas.gov/elevator_searchapp/elevator)).
- **NYC DOB NOW elevator compliance**, about 120k devices, open data ([NYC Open Data](https://data.cityofnewyork.us/Housing-Development/DOB-NOW-Elevator-Safety-Compliance/e5aq-a4j2)); DOB safety violations ([NYC](https://data.cityofnewyork.us/Housing-Development/DOB-Safety-Violations/855j-jady)).
- Permits for modernization history (Shovels or city portals); condo SIRS from Idea 1 (elevators are a common SIRS line item).
- All free; public records.

**The combination:** device age × current service provider × inspection lapses or violations × owner type (condo association in a SIRS cycle = funded capital plan) gives modernization and service-switch targets. Today a sales rep pieces this together from walk-ins and relationships.

**Buyer persona:** owner or sales manager at an independent elevator contractor (NAEC has 700+ members ([NAEC](https://www.naec.org/about))), and modernization sales reps at mid-size OEM dealers.

**Evidence of WTP:**
- The US elevator maintenance market is about $4.2B (2024). Independents reportedly hold about 55% of service ([MarketDataForecast](https://www.marketdataforecast.com/market-reports/us-elevator-market)); treat that figure cautiously.
- Modernization sales jobs pay up to $150k base ([ZipRecruiter](https://www.ziprecruiter.com/Jobs/Elevator-Salesman)).
- Counter-evidence: the NYC compliance-lead actor has almost no users ([Apify](https://apify.com/kempdata/nyc-elevator-compliance)), and elevatordatabase.com is still in beta with a waitlist ([Elevator Database](https://elevatordatabase.com/Texas)). *Raw* data doesn't sell; the dossier and outreach must be the product.

**Market size (est.):** about 1,000–1,500 independent elevator firms in the US (est.; NAEC has 700+ members). Coverage at launch is limited to 3 strong-data jurisdictions, so about 150–300 addressable firms (est.). 50 × $500/mo is about $300k ARR. **Small**, but nearly free to add on the Idea 1 spine.

**Deliverable and pricing:** a territory map and monthly target list, with a per-building modernization brief and email drafts to the property manager. $300–$900/mo per territory. Recurring.

**Pipeline:** find firms from the DBPR "registered elevator companies" file and the TDLR licensee list; build by joining device files, owners and violations; send each firm a sample showing *its competitors' aging accounts* in its own territory; agent handles replies; deliver monthly. About 85% automatable.

**GTM, 90 days:** Florida first (the maintenance-company field is unusually rich). Email all registered FL elevator companies with a territory sample. Target 8 paid.

**Unit economics (est.):** $500/mo; CAC $300–$700; gross margin about 90%; data cost about $0.

**Competitors:** no direct product found beyond raw-data tools. **Blue ocean, but a small pond.**

**Legal:** CAN-SPAM. Don't imply official status. Data is public.

**Kill risks:**
1. The market is too small to matter on its own.
2. Independents are craftsman-run and buy through relationships, not data.
3. Outside FL, TX and NYC, data access is spotty (many states don't publish).

---

### Idea 5 — Automated Municipal Lien and Open-Permit Search for Florida Title Agents

**Pitch:** Lien and open-permit search reports for Florida closings, delivered in about 48 hours at $85–$95. An agent fleet files the municipal requests, reads the replies and PDFs, and assembles the report. Today this is done by $19/hr processors.

**Data sources:** municipal lien-letter request portals and emails (each city differs; fees of $25–$100 are passed through); code-enforcement and permit portals (open, expired permits); county tax collector; utility billing departments. These are semi-private: you have to *ask* each municipality. Terms: none, but some municipalities restrict automated portal use (verify per city).

**The combination:** permits (open or expired) × code liens × utility liens × special assessments × tax status, assembled per parcel. Value comes from speed and coverage across 400+ Florida municipalities (est.).

**Buyer persona:** closing/escrow manager at a Florida title agency or real estate law firm.

**Evidence of WTP:**
- Published retail price $100 / $125 plus municipal fees ([FL Municipal Lien Search](https://floridamunicipalliensearch.com/pricing/)).
- PropLogix grew by acquisition (City Lien Search, ASAP Tax and Lien Search) ([ALTA](https://www.alta.org/news-and-publications/news/20220505-PropLogix-Acquires-City-Lien-Search)).
- Processor wages run $19/hr to $55k–$65k ([search summary: Tallo](https://tallo.com/talent/job/finance/insurance-claims-or-policy-clerk/fl/riviera-beach/municipal-lien-search-processo-0b16a28e), [ZipRecruiter](https://www.ziprecruiter.com/Jobs/Municipal-Lien-Search)).

**Market size (bottom-up, est.):** 343,805 existing-home sales in Florida in 2025 ([Florida Realtors](https://www.floridarealtors.org/news-media/news-articles/2026/01/flas-2025-housing-market-ends-positive-trends)), plus refinances, commercial and new construction: about 450k–550k searches/yr (est.). At about $110 each, that's **about $50M–$60M/yr** of service revenue (est.). A 2% share is about $1M/yr.

**Deliverable and pricing:** per-order PDF report through an API or email order desk; $85–$95 plus municipal fees. Recurring by volume, not by subscription.

**Pipeline:** find title agencies (FL DFS licensee lists, ALTA directories); build sample reports on their recent public closings; outreach offers 3 free searches; an agent handles intake; deliver via portal. About 50–60% automatable. Many municipalities need phone calls or mailed checks, and errors carry liability.

**GTM, 90 days:** cover 2 counties completely (municipal portal map); 10 title agencies on free trials; reach 300 orders/month.

**Unit economics (est.):** price $90; municipal pass-through excluded; cost per search about $15–$30 (human exception handling, LLM, payments); gross margin about 65–80%. CAC is low per order but relationships are sticky. Errors-and-omissions insurance is needed.

**Competitors:** PropLogix plus many small firms (Real Res, Skyline, Lien Searches Plus, and others; [search results](https://www.skylinetitlesupport.com/services/municipal-lien-searches)). **Crowded, but low-tech.**

**Legal:** liability for missed liens (E&O insurance); title-industry vendor management (ALTA Best Practices); municipal portal terms of use.

**Kill risks:**
1. Too much municipal-request work stays human, so it's an ops business, not an agent business.
2. Title agents won't switch from relationship vendors to save $15.
3. One missed lien means a claim and lost reputation.

---

### Idea 6 — Solar-Orphan Service Lead Feed

**Pitch:** Find homes whose solar installer went bankrupt or lost its license and whose inverters are nearing warranty end. Sell those addresses (with direct-mail creative) to local solar repair and O&M companies.

**Data sources:**
- Solar permits (Shovels API from $599/mo ([Shovels](https://www.shovels.ai/pricing)), or city portals).
- California DG Stats interconnection data (installer fields; check whether address-level data exists, since public files may be aggregated to zip) ([CA DG Stats](https://www.californiadgstats.ca.gov/get_file/interconnected_projects_readme/)).
- CSLB license master file, free ([CSLB data portal](https://www.cslb.ca.gov/onlineservices/dataportal/)).
- Bankruptcy lists ([solarpanelexit list](https://solarpanelexit.com/solar-company-bankruptcy-list/)).

**The combination:** permit contractor × license status / bankruptcy × system install date (inverter age) × ownership (cash/loan vs. lease) gives homeowners with no one to call.

**Scale:** SunPower had about 600k customers and filed for bankruptcy in August 2024; Sunnova had over 500k and filed in June 2025. More than 100 smaller CA installers have also failed ([search summary: CNBC](https://www.cnbc.com/2025/06/09/sunnova-files-for-bankruptcy.html), [California Solar Exit](https://www.californiasolarexit.com/blog/solar-company-bankrupt-california)). Caveat: many SunPower and Sunnova systems were installed by **dealers**, so the permit contractor isn't the bankrupt brand. Leases and PPAs moved to SunStrong ([solarpanelexit](https://solarpanelexit.com/sunnova-bankruptcy/)).

**Buyer persona:** owner of a 2–30-person solar service and repair company in CA, AZ, TX or FL.

**Evidence of WTP:** repair tickets of $400–$1,000 and maintenance of about $520/yr ([Angi](https://www.angi.com/articles/how-much-does-it-cost-repair-solar-panels.htm), [Angi maintenance](https://www.angi.com/articles/solar-panel-maintenance-cost.htm)). Ohm Analytics gives installers data for free in exchange for project data ([Ohm](https://www.ohmanalytics.com/solar-company-sign-up/)), which shows how cheap installer-facing data has become. No direct price evidence for orphan leads.

**Market size (est.):** perhaps 500–1,500 solar service companies in target states (est.). 100 × $300/mo is about $360k ARR. Small.

**Deliverable and pricing:** monthly address list plus postcard copy; $200–$500/mo per territory or $3–$8 per address (est.).

**Pipeline:** find service companies (Google Maps, CSLB C-10/C-46 licensees); build the join; send a sample of 50 local orphan homes; agent handles replies; deliver monthly. About 85% automatable. Outreach to homeowners is the buyer's job, by direct mail only.

**GTM, 90 days:** California only; 300 service firms emailed; 10 paid.

**Unit economics (est.):** $300/mo; CAC $300; gross margin about 70% (Shovels data cost dominates if used).

**Competitors:** Shovels and Ohm hold the data but not this specific product; consumer "solar exit" sites capture inbound. **Moderately open.**

**Legal:** buyers' calls and texts to homeowners trigger TCPA and state mini-TCPAs, so restrict use to direct mail in the license terms. Shovels' terms on resale need review.

**Kill risks:**
1. The dealer model breaks the "bankrupt installer on the permit" join.
2. Small buyers with low WTP churn fast.
3. The orphan wave fades as successor servicers (SunStrong) and warranty programs absorb customers.

---

### Idea 7 — Assessment-Anomaly Evidence Packets for Licensed Tax Consultants (Small Commercial)

**Pitch:** Don't file appeals yourself; licensing makes that hard. Each assessment season, sell licensed consultants and attorneys a ranked list of over-assessed small-commercial parcels ($1M–$10M), each with a ready-to-file evidence packet. Price per packet or as a revenue share.

**Data sources:**
- Assessor rolls and sales: free or via public-records request. TaxNetUSA resells Texas and Florida appraisal-district data ([TaxNetUSA FAQ](https://www.taxnetusa.com/faq/)).
- Recorded deeds (sale prices in disclosure states).
- Board-of-review outcome histories (e.g., Cook County BOR processed a record 290,533 appeals in tax year 2025 ([WTTW](https://news.wttw.com/2025/11/25/cook-county-board-review-reopen-2025-property-tax-appeals-window))).

**The combination:** assessment-to-sale ratios × equity comps × past appeal outcomes by parcel class × owner type identify "high-probability, uncontested" parcels.

**Buyer persona:** principal at a 2–20-person property tax consulting firm or tax-appeal law firm.

**Evidence of WTP:**
- Commercial contingency is 25–35% of first-year savings ([Paramount](https://www.paramountpropertytaxappeal.com/blog/contingency-fee-property-tax-appeal)).
- Property tax analysts earn about $68k at a Chicago appeal firm; property tax managers $106k–$139k ([search summary: Indeed/ZipRecruiter](https://www.ziprecruiter.com/Jobs/Property-Tax-Manager)).
- Texas has 2,216 registered consultants ([TDLR PTC at a Glance](https://www.tdlr.texas.gov/media/pdf/PTC%20at%20a%20Glance.pdf)).
- In Harris County, 81% of 516,654 protests were agent-filed ([texaspropertytaxappeal.com](https://texaspropertytaxappeal.com/blog/texas-property-tax-appeal-success-rates-by-county.html)). Agent penetration is very high.

**Market size (est.):** about 4,000–8,000 consultants and attorneys nationally (est.). The direct-to-owner market is huge, but this B2B slice is maybe $2M–$5M/yr.

**Deliverable and pricing:** $50–$150 per packet, or 5% of the consultant's fee (est.). Seasonal, so **weakly recurring**.

**Pipeline:** find consultants (TDLR licensee list, state bar sections); build models by county; email sample packets on their own region's parcels; agent handles replies; deliver at the start of the season. About 75% automatable.

**GTM, 90 days:** only works if timed to notice season (TX notices go out April–May). Building now for spring 2027 means 6+ months to first dollar.

**Unit economics (est.):** cheap data; gross margin about 85%; CAC $500+; concentrated in a few months.

**Competitors:** **saturated.** O'Connor, Ryan, Ownwell (commercial in 9 states ([Ownwell](https://www.ownwell.com/commercial))), TaxNetUSA QuickAppeal ([TaxNetUSA](https://www.taxnetusa.com/quickappeal/)), Property Data Cloud ([PDC](https://propertydatacloud.com/)), and V7-style AI agents ([V7](https://www.v7labs.com/agents/ai-agent-for-property-tax-consultants)).

**Legal:** filing directly has licensing barriers.
- Texas requires TDLR registration ([TDLR](https://www.tdlr.texas.gov/ptc/forms/PTC001%20Property%20Tax%20Consultant%20Registration%20Application.pdf)).
- In Pennsylvania, non-attorney appeal representation is unauthorized practice of law ([PA Bar](https://www.pabar.org/public/committees/UNA01/Opinions/uplm98-101.asp)).
- Cook County BOR requires attorneys for entity owners ([Cook BOR](https://www.cookcountyboardofreview.com/commercialindustrial-appeals)).
- The B2B packet model avoids this but caps upside.

**Kill risks:**
1. Saturated market with entrenched consultants.
2. Seasonal revenue and slow time to first dollar.
3. Consultants already have comp tools and don't value packets.

---

### Idea 8 — Pre-Bid Specialty-Subcontractor Lead Engine (Permits + Planning Agendas)

**Pitch:** Give specialty subs (glazing, roofing, fire protection, elevators) a weekly list of projects at the planning-approval stage, before GCs invite bids, with auto-drafted intro emails to the developer and architect.

**Data sources:** planning agendas and minutes (Legistar, Granicus, CivicPlus; scrapable); permits (Shovels or portals); architect licensee lists.

**The combination:** entitlement stage × project scope from the staff report × architect of record × trade fit.

**Buyer persona:** BD manager at a specialty subcontractor doing $5M–$50M/yr.

**Evidence of WTP:** Dodge $5k–$15k+/yr, ConstructConnect $1.2k–$2.2k/yr per seat, PlanHub $2k–$3.3k/yr (see table). Subs demonstrably pay.

**Market size:** large. There are hundreds of thousands of subcontractor firms in the US; Dodge and ConstructConnect are multi-hundred-million-dollar businesses (not verified here).

**Deliverable and pricing:** $150–$400/mo per trade per metro. Recurring.

**Pipeline:** highly automatable (about 90%).

**Competitors:** **saturated and getting worse.** cityminutes.ai explicitly targets "estimating managers at commercial GCs" and "architectural sales reps" with 8–24 months of lead time ([cityminutes.ai](https://cityminutes.ai)). Also GatherGov, Shovels, Dodge, ConstructConnect, PlanHub, BuildingConnected (free), constructionbids.ai, Apify agenda scrapers ([Apify](https://apify.com/jungle_synthesizer/municipal-council-minutes-agenda-scraper)).

**Legal:** low risk (CAN-SPAM, scraping terms).

**Kill risks:**
1. Competitors with funding and coverage already exist.
2. Planning-stage leads are early, and subs say most aren't actionable.
3. Price competition drives toward $39/mo.

---

## 3. Ideas considered and rejected

| Idea | Why rejected (evidence) |
|---|---|
| **Lender / insurer property-risk feed** (roof age, permits, violations) | Verisk/BuildFax (10M+ roofs), Moody's/CAPE, ZestyAI, Nearmap/Betterview already sell this to carriers, with regulatory model approvals as a moat ([Verisk](https://www.verisk.com/blog/how-old-is-that-roof/), [Moody's](https://www.moodys.com/web/en/us/insights/announcements/moodys-to-acquire-cape-analytics.html), [ZestyAI](https://zesty.ai/resource/roof-age-solution-for-property-risk-assessment)). Long enterprise sales cycles don't fit an agent-outreach model. |
| **LL97 / BPS fine-avoidance retrofit outreach** | First-year LL97 fines were about $270k across all of NYC; 93% filed ([nyc.gov](https://www.nyc.gov/site/hpd/news/023-26/new-compliance-data-shows-impact-local-law-97-improve-sustainability-new-york-city)). Performance compliance needs PE attestation ([NYC DOB](https://www.nyc.gov/assets/buildings/pdf/ll97-compliance-report-process.pdf)) and engineering. Revisit around 2029 when 2030 limits bite. The filing piece is folded into Idea 3. |
| **STR compliance service** (host-side or city-side) | City side is owned by Granicus and Deckard with procurement cycles ([GovTech](https://www.govtech.com/biz/Granicus-Buys-Short-Term-Rental-Compliance-Software-Company.html)). Host side: permit fees are only $64–$308 ([Minneapolis](https://www2.minneapolismn.gov/business-services/licenses-permits-inspections/rental-licenses/short-term-rentals/), [hoststarter](https://hoststarter.net/houston-texas-short-term-rental-license/)), so WTP is tiny, and platforms increasingly enforce registration themselves. |
| **Rental registry enforcement / landlord registration** | Low per-unit fees; government-side incumbents (Deckard already markets registry enforcement ([Deckard](https://deckard.com/resources/rental-registration-ordinance-best-practices))); landlords resist paying. |
| **Pre-foreclosure / deed / mortgage lists for investors** | Commodity: PropStream $99/mo with 120+ filters, BatchLeads $119/mo, ATTOM API from $95/mo (sources in §1.1). |
| **CRE maturity-wall refinance leads from mortgage records** | $875B maturing in 2026 ([MBA](https://www.mba.org/news-and-research/newsroom/blog-post/commercial-real-estate-loan-maturity-volumes)), but Trepp, CompStak, Reonomy and MSCI already map loan maturities; recorder data lacks maturity dates for most loans. |
| **Utility interconnection queue intelligence** | Enverus bought Pearl Street ([Enverus](https://www.enverus.com/newsroom/undo-the-queue-enverus-acquires-pearl-street-technologies-to-solve-for-a-more-reliable-resilient-grid/)); Paces raised $11M ([ESG Dive](https://www.esgdive.com/news/data-platform-paces-nabs-11m-to-scale-clean-energy-development/722671/)); Interconnection.fyi sells CSV and Snowflake feeds ([GridTracker](https://www.interconnection.fyi/data-subscription)); LBNL publishes free ([LBNL](https://emp.lbl.gov/publications/queued-2025-edition-characteristics)). Sophisticated buyers, crowded market. |
| **Tax-sale / foreclosure surplus-funds recovery** | Florida caps assignee compensation at 12% ([liensuite summary of §45.033](https://liensuite.com/tools/surplus-claim-deadline-lookup)). Consumer-facing with a predatory reputation and a flood of "course" competitors. Fails the "don't be hype-driven" test. |
| **Texas BPP rendition-as-a-service** | HB 9 raised the exemption to $125k from tax year 2026 ([NatLawReview](https://natlawreview.com/press-releases/texas-business-personal-property-renditions-due-april-15-2026), [expressbpp](https://www.expressbpp.com/states/texas/)), wiping out most small-business demand. |
| **NYC building violation / compliance monitoring** | ViolationWatch $9/building/mo, DOBGuard about $50, SiteCompli for enterprise ([ViolationWatch](https://violationwatch.nyc/resources/best-nyc-violation-monitoring-tools-2026)). The price floor has collapsed. |
| **Fire-inspection deficiency leads** | Brycer's Compliance Engine already sits between AHJs and contractors and charges contractors per report ([Charleston](https://www.charleston-sc.gov/2586/Compliance-Reporting)). The data isn't public in bulk. |
| **NYC elevator/boiler "lead lists" as raw data** | Already on Apify, $2.50 per 1k records, 2 users ([Apify](https://apify.com/kempdata/nyc-elevator-compliance)). Folded into Idea 4 with an actual deliverable. |
| **Residential tax appeal** | Ownwell ($74M raised, 1M+ appeals) plus dozens of AI clones (appealdesk, taxfightback, squaredeal, taxdrop) ([Inman](https://www.inman.com/2026/02/25/ownwell-raises-50m-to-grow-its-property-tax-appeal-fintech/)). Texas is 81% agent-filed already. |
| **Certificate-of-occupancy "new tenant" leads for B2B vendors** | Shovels and BuildZoom already expose COs and permits; low differentiation; vendors (cleaning, security) have low lead WTP. Not researched deeply. |

---

## 4. Ranked shortlist

Scores are 1–10 (for competition, 10 = blue ocean). "Mean" is the simple average of the seven criteria. "Overall" is my judgment after weighting WTP evidence and competition more heavily; the two differ where a high mean hides a fatal flaw.

| Rank | Idea | Market size | WTP | Data access | Automation | Competition | Recurring | Time to $1 | Mean | **Overall** | Confidence |
|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | **FL Condo Capital-Event Feed** (Idea 1) | 5 | 7 | 7 | 7 | 7 | 7 | 7 | 6.7 | **7.0** | Medium. Data path verified; buyer WTP for *leads* not yet proven |
| 2 | **Association Switch-Signal for CAM firms** (Idea 2) | 5 | 6 | 8 | 7 | 7 | 6 | 7 | 6.6 | **6.3** | Medium-low. Self-managed classifier untested |
| 3 | **Conveyance Intel for independent elevator cos.** (Idea 4) | 3 | 6 | 8 | 8 | 8 | 7 | 6 | 6.6 | **5.8** | Medium on data, low on demand; small market |
| 4 | **Benchmarking filing automation** (Idea 3) | 6 | 6 | 6 | 6 | 4 | 9 | 5 | 6.0 | **5.8** | Medium. Proven WTP ($800/bldg) but crowded and ops-heavy |
| 5 | **FL lien / open-permit search automation** (Idea 5) | 6 | 7 | 4 | 5 | 4 | 7 | 5 | 5.4 | **5.0** | Medium. Proven price, but much of the work is human |
| 6 | **Solar-orphan service leads** (Idea 6) | 4 | 5 | 5 | 7 | 7 | 5 | 6 | 5.6 | **4.8** | Low. Dealer-model join risk |
| 7 | **Tax-consultant evidence packets** (Idea 7) | 8 | 8 | 7 | 5 | 2 | 6 | 4 | 5.7 | **4.5** | Medium. Saturated |
| 8 | **Pre-bid sub lead engine** (Idea 8) | 7 | 5 | 7 | 8 | 2 | 8 | 6 | 6.1 | **4.0** | High that it's saturated |

### Recommendation

Build **Ideas 1, 2 and 4 as one "Florida Association Data Spine"**. The ETL is the same: DBPR condo CSVs + SIRS database + DBPR elevator registry + Sunbiz bulk + appraiser parcels + Ch. 119 requests. Sell three products to three buyer groups: engineers and restoration firms, CAM firms, elevator firms.

This matches the brothers' model well: it shows each prospect a finished, personalized sample in their own territory, and the data is free. The combination is new; no B2B competitor turned up in ~80 searches.

**Gate before scaling:** five paid pilots ($300+/mo) from engineering or restoration firms within 60 days. If restoration and engineering buyers won't pay for leads, the spine pivots to association lenders (fewer buyers, higher ACV) or is shelved.

### Honest caveats
- I could not verify that the DBPR SIRS database or the July 2025 portal data (assessments, building data) can be exported in bulk. The plan assumes scraping the public view plus Ch. 119 requests.
- Buyer counts in Florida (engineers, restoration contractors, elevator companies) are **estimates**. Count them from DBPR and FBPE licensee files in week 1.
- The 2025–2026 Florida deadline spike inflates short-term urgency. Steady-state demand depends on the 10-year cycles plus new 30-year buildings each year.
