# Lane 03: Public-Records Signals and Combinations

*Research date: 2026-10-01. This is desk research only. No outreach, signups or purchases were made. Every material claim links to its source. Anything I estimated is marked **(est.)**. Scores and verdicts are my own judgement and say so.*

---

## TL;DR

1. **Extracting raw public records is no longer a moat.** On the Apify marketplace, anyone can buy scrapers for liquor licenses, UCC filings, code violations, health inspections, Secretary of State (SOS) entities, CSLB, BuildZoom and PACER data at **$2–$50 per 1,000 records** ([liquor licenses](https://apify.com/nexgendata/liquor-license-leads/api), [code violations](https://apify.com/permitdata/us-code-violations-scraper), [new business filings at $4/1k](https://apify.com/lergassy/us-business-filings), [BuildZoom at $4/1k](https://apify.com/parsebird/buildzoom-scraper/api)). SOS lookups cost as little as **$0.03 live or $0.003 cached** at OpenSOSData, versus $0.50–$2.00 at Cobalt ([OpenSOSData vs Cobalt](https://opensosdata.com/vs/cobalt/)). The premise that "LLMs make extraction cheap, so extraction is the moat" cuts both ways: it is cheap for everyone else too.
2. **What is still defensible:** (a) **joining several records into one buyer-specific trigger** that no single dataset shows ("this contractor's GL expires in 45 days, their current agency is X, and they just pulled $2M of permits"), and (b) **done-for-you conversion of that trigger into booked meetings or closed work.** (b) is exactly the machine the brothers already run. Buyers demonstrably pay **$300–$550 per booked meeting** in commercial insurance ([VA Horizon via its x-date guide](https://www.vahorizon.site/b2b/guides/what-x-dates-are-and-how-to-source-them/)), but only **$0.005–$0.30 per raw UCC record** ([uccdata.io](https://uccdata.io/), [MCA lead pricing](https://apify.com/deadwood_data_solutions/ucc-filing-leads)).
3. **Best candidates:** (1) a contractor insurance renewal-date (X-date) engine for commercial insurance agents, built from free state license and insurance files; (2) a restaurant inspection-violation-to-vendor router (pest, hood, refrigeration); (3) good-standing rescue for businesses dissolved on paper but still operating. The last carries meaningful legal and reputational risk. Restaurant pre-opening feeds are real but crowded at the data layer.
4. **Killed:** probate, divorce, tax-lien leads for tax-resolution firms, residential code-violation leads, judgment recovery, MCA UCC lead lists, raw new-business lists sold as data, generic lawsuit alerts for attorneys, and professional-license continuing-education (CE) leads. Reasons are in §3.

---

## 1. Lane overview

### 1.1 The landscape

| Record type | Where it lives | Access reality | Who already sells it |
|---|---|---|---|
| **UCC filings** | 50 SOS offices plus some county recorders | Mixed: free bulk in CO, VT, CT and WV; paid bulk elsewhere (MN $9,600 initial + $2,400/quarter; AZ $24k; KY $1,500/mo; TX $1,150/mo + daily fees). **NC prohibits scripted use and GA's bulk agreement forbids screen scraping** ([Quintel state guide](https://quintel.ai/blog/ucc-filing-search-by-state); [MN SOS price list](https://sos.mn.gov/business-liens/business-liens-data/ucc-data-available-for-purchase/)) | MCA lead sellers (~$0.10–$0.75/record) ([merchantfinancingleads](https://www.merchantfinancingleads.com/merchant-cash-advance-ucc-leads-lists), [uccdata.io $0.30](https://uccdata.io/)); EDA/Fusable for equipment ([EDA](https://edadata.com/industryinsight/construction/)); Middesk and Cobalt for KYB |
| **Business registrations / dissolutions** | SOS (plus TX Comptroller and CA FTB for tax status) | FL publishes **free daily and quarterly files via public SFTP** ([Sunbiz data downloads](https://dos.fl.gov/sunbiz/other-services/data-downloads/)); CT posts monthly administrative-dissolution PDFs ([CT SOTS](https://portal.ct.gov/sots/business-services/administrative-dissolution-notices/administrative-dissolution-notices)); TX posts **weekly new sales-tax permits with NAICS codes** ([TX Comptroller](http://comptroller.texas.gov/transparency/open-data/recent-sales-tax-permits/)) | OpenCorporates (£2,250–£12,000/yr API) ([pricing](https://opencorporates.com/pricing/)); Cobalt; OpenSOSData; Enigma (credits, $20–$200/mo self-serve) ([Enigma pricing](https://www.enigma.com/pricing/)); Middesk |
| **DBAs / fictitious business names** | Mostly **county clerks** (CA files at county level within 40 days of starting business) ([summary](https://riskmanagement.lexisnexis.com/bps/web20_help/RSKM/bsp_search_fictitious_business_names_dba_c.html)) | Highly fragmented; often PDFs or legal-notice newspapers | LexisNexis; local list brokers. (The brief's "Ficticious.com" did not resolve; DNS lookup failed on 2026-10-01, so I could not price it.) |
| **Tax liens** | County recorders (federal + state) | Fragmented, but already aggregated | Several vendors cover "3,000+ counties" daily at **$0.16–$0.40/record** ([Extrakt](https://www.extraktdata.com/tax-liens), [taxlienlists](https://www.taxlienlists.net/Products/tax_liens.html)) |
| **Mechanics liens** | County recorders | Fragmented; images; backlogs (NCS revises its index as recorders catch up) ([NCS Lien Index Q1-26](https://www.ncscredit.com/education-center/blog/lien-index-q1-2026)) | NCS LienFinder, NACM reports ($14.50–$25 each) ([NACM](https://nacmsouthatlantic.com/services/commercial-credit-reporting/nacm-national-trade-credit-report/)), BICA, Levelset/Procore |
| **Court dockets** | Federal: PACER, plus free RECAP via CourtListener ([API](https://courtlistener.com/help/api/)). State: thousands of portals, many on Tyler Odyssey | State access is fragmented. Portals and terms of service vary, and the judyrecords/Tyler incident shows the security and legal minefield ([judyrecords](https://www.judyrecords.com/what-happened-with-tyler-technologies)) | Trellis ($69.95–$199.95/mo) ([plans](https://trellis.law/plans)); UniCourt ($59–$399/mo; Enterprise API from $2,250/user/mo) ([pricing](https://unicourt.com/pricing), [GetApp](https://www.getapp.com/legal-law-software/a/unicourt/)) |
| **Code violations** | City code-enforcement systems (Socrata/Accela/PDF) | Partial open data | GetCodeViolations ($49/mo, 56+ cities) ([site](https://getcodeviolations.com/)); PropStream; ListCentral |
| **Contractor licenses + insurance/bond** | State boards | **Excellent in several states:** CSLB free files include **WC carrier, policy number and policy dates** ([CSLB portal](https://www.cslb.ca.gov/onlineservices/dataportal/ContractorList)); WA L&I publishes **insurance carrier, agency name and expiration/cancel dates, plus bond expiration/impairment, updated 3×/day** ([WA insurance dataset](https://data.wa.gov/Labor/L-I-Contractor-License-Data-Insurance/ciwg-agsx), [bond](https://data.wa.gov/Labor/L-I-Contractor-License-Data-Bond/bzff-4fmt)); OR CCB includes liability-insurance expiration, 56k active ([data.oregon.gov](https://data.oregon.gov/business/CCB-Active-Licenses/g77e-6bhs)); FL DBPR offers free weekly licensee files with expiration dates ([DBPR readme](https://www2.myfloridalicense.com/sto/documents/readme.pdf)) | Insurance Xdate, miEdge (Zywave), LeO, Neilson ([vendor list](https://www.vahorizon.site/b2b/guides/what-x-dates-are-and-how-to-source-them/)) |
| **Health inspections** | ~3,000 local health departments | Socrata in big cities, but schemas, **score polarity**, row granularity and lag all differ (NYC 2-day lag vs King County 237 days stale) ([dev.to analysis](https://dev.to/mayd-it/restaurant-health-inspection-data-by-city-apis-and-traps-2o9p)) | Hazel Analytics (Ecolab-owned; serves chains: "over half of the 100 largest food service and retail brands", 300k locations) ([Ecolab](https://en-uk.ecolab.com/pages/hazel-analytics-acquired), [Crunchbase](https://www.crunchbase.com/organization/hazel-analytics)) |
| **Liquor licenses** | State ABC boards (plus local) | CA ABC posts daily new-application reports ([CA ABC](https://www.abc.ca.gov/licensing/licensing-reports/new-applications/?RPTTYPE=2&DATEOFFSET=6)); TX publishes **monthly mixed-beverage gross receipts per establishment** ([data.texas.gov](https://data.texas.gov/dataset/Monthly-Revenue-by-Bar/vw6v-nwfk)) | CHD Expert ($59k–$119k/yr) ([price table](https://www.chd-expert.com/pricetable-us/)); RestaurantData.com (450+ openings/week) ([plans](https://restaurantdata.com/plans/)); PreopeningRestaurants; Recordpipe (from $5k) ([page](https://recordpipe.com/leads/liquor-license-leads.html)) |
| **Probate / divorce** | County courts | Fragmented | Saturated real-estate-investor market: probate costs $69–$1,200+/county/mo ([probatedata](https://www.probatedata.com/blog/best-probate-lead-services-for-multi-county-investors)); divorce is sold by PropStream and others ([PropStream](https://www.propstream.com/real-estate-agent-blog/divorce-real-estate-leads-5-reasons-theyre-beneficial-for-agents)) |

### 1.2 Incumbents by tier

- **Enterprise KYB and risk:** Middesk (usage-based, ~$2–$5/verification at mid volume; monitoring is a per-entity add-on) ([Vendr](https://www.vendr.com/marketplace/middesk)); Enigma; LexisNexis; D&B; Experian; DataMerch for MCA funders ($695–$945/mo, 300+ funders) ([DataMerch](https://www.datamerch.com/pricing/index.html)).
- **Vertical data platforms:** CHD Expert (foodservice), EDA/Fusable (equipment UCC), Shovels ($599–$999/mo for permits and contractors) ([Shovels](https://www.shovels.ai/pricing)), Trellis and UniCourt (courts), Insurance Xdate and miEdge (insurance).
- **Commodity list sellers and Apify scrapers:** they own the raw-record layer at near-zero prices.

### 1.3 Where the gaps actually are

1. **The SMB buyer who will not operate a data tool.** CHD Expert starts at $59k/yr, and Shovels and UniCourt are built for analysts. A local pest-control owner, a two-producer insurance agency or a hood-cleaning company will not buy a data subscription. They will pay for **meetings or jobs**. Commercial pest leads cost **$50–$200** ([Cube Creative](https://cubecreative.design/blog/pest-control-marketing/pest-control-cost-per-lead-benchmarks)); commercial insurance leads **$40–$200** ([insuranceleadsguide](https://insuranceleadsguide.com/commercial-insurance-leads/)). That is the brothers' model.
2. **Cross-source joins that require interpretation.** Examples: free-text violation narratives mapped to a vendor category; "dissolved on paper but alive on Google"; UCC collateral text mapped to an equipment class and lease maturity; insurance expiration combined with the current agency (WA publishes the agency name). This is where an LLM is worth paying for. Extraction cost itself is trivial: Claude Haiku 4.5 costs $1/$5 per million input/output tokens, or $0.50/$2.50 on the Batch API ([pricing summary](https://www.clawrouters.com/blog/claude-haiku-4-5-api-pricing-2026)). Parsing **100k PDF pages a month** (~1.5k tokens in, 300 out each) costs about **$150–$300/mo (est.)**.
3. **Buyer triggers built on dissatisfaction or deadlines** rather than "a new entity exists." The best signals mark the moment when switching is legal or forced: a policy expiration, a re-inspection deadline, a forfeiture date, a lien-filing deadline.

---

## 2. Candidate ideas

### Idea 1 — Contractor coverage X-date engine (insurance renewal windows → booked meetings for commercial agents)

**One-line pitch:** Use free state contractor-license files that show when each contractor's workers' comp, GL and bond coverage expires (and, in WA, which agency writes it), and turn the 30–90-day pre-renewal window into booked meetings for independent commercial insurance agents.

**Data sources**

| Source | Access | Cost | Terms / limits |
|---|---|---|---|
| CA CSLB License Master + Workers' Comp + Personnel files (~290k licensees) ([portal](https://www.cslb.ca.gov/onlineservices/dataportal/ContractorList), [count](https://en.wikipedia.org/wiki/California_Contractors_State_License_Board)) | CSV/XLS download | Free | No email addresses ("excluded per California law"), so contact data must be appended |
| WA L&I Contractor License: General, Insurance (carrier, **agency name**, expiration/cancel), Bond (expiration, impairment), Principals | Socrata SODA API, updated 3×/day ([insurance](https://data.wa.gov/Labor/L-I-Contractor-License-Data-Insurance/ciwg-agsx)) | Free | Open data; verify the portal licence |
| OR CCB Active Licenses (56k+, liability insurer + expiration) ([dataset](https://data.oregon.gov/business/CCB-Active-Licenses/g77e-6bhs)) | Socrata | Free | Same |
| FL DBPR licensee files (weekly, with expiration) ([readme](https://www2.myfloridalicense.com/sto/documents/readme.pdf)) | Download | Free | Same |
| Growth signals: permits via Shovels ($599+/mo) or city open data ([Shovels](https://www.shovels.ai/pricing)) | API | $0–$599/mo | Credit-based |
| Contact append (owner email/cell) | Vendor | ~$0.10/record (e.g., uccdata.io's append price as a proxy) ([uccdata.io](https://uccdata.io/)) | Vendor terms |

**The combination that creates new value:** expiration date + current carrier + **current agency (WA)** + license class (a proxy for trade risk) + bond impairment or cancellation (a distress signal) + recent permit volume (a growth/payroll proxy, which predicts audit surprises and a desire to re-shop). No single file says "this $3M-revenue roofing contractor's GL renews in 60 days and their agency is a captive that just lost the carrier." The join does. The LLM's role is entity resolution across license, permit and web data, plus writing a credible outreach note per prospect.

**Buyer persona:** Owner or commercial-lines producer at an independent P&C agency with a contractor or construction niche, 2–20 staff, in CA, WA, OR or FL. Producers are paid on new business: commercial producers typically earn **40–50% of new commission and 25–30% of renewal**, and are expected to write **$75k–$150k of new commission a year** ([Insurance Journal via search summary](https://www.insurancejournal.com/magazines/mag-features/2020/06/15/572064.htm)). The average commercial producer salary is **$86k–$123k** ([Salary.com](https://www.salary.com/research/salary/position/commercial-insurance-producer-salary), [Glassdoor](https://www.glassdoor.com/Salaries/commercial-lines-producer-salary-SRCH_KO0,25.htm)).

**Evidence of willingness to pay**
- An appointment-setting firm for commercial x-dates charges **$300–$550 per meeting plus a $300 setup fee** ([VA Horizon guide](https://www.vahorizon.site/b2b/guides/what-x-dates-are-and-how-to-source-them/)).
- Insurance Xdate, an incumbent x-date platform using WC rating-bureau, OSHA, DOT and 5500 filings ([site](https://www.insurancexdate.com/)); LeO from $59/mo ([guide](https://www.vahorizon.site/b2b/guides/what-x-dates-are-and-how-to-source-them/)).
- Agents on an Insurance Journal forum report raw x-dates at "$1 per record," appointments at "$50–100," and complain that data goes stale with "bad x-date information" ([IJ forum](https://www.insurancejournal.com/forums/viewtopic.php?t=2529)). Freshness is the wedge: WA updates 3×/day.
- Exclusive commercial leads cost **$40–$200** ([insuranceleadsguide](https://insuranceleadsguide.com/commercial-insurance-leads/)).

**Market size**
- Independent agencies: **39,000 (2024)** ([Big I Agency Universe](https://www.independentagent.com/news/big-i-and-future-one-release-2024-agency-universe-findings/)), reported as **~37,000 in 2026** ([agencychecklists](https://agencychecklists.com/2026/09/28/independent-agency-count-ai-adoption-2026-83509/)).
- Bottom-up for the launch states (est.): CA+WA+OR+FL hold roughly 25% of agencies, so ~9,000. If ~30% write meaningful contractor business, that is ~2,700 targetable agencies. Capturing 3% (80 agencies) at $1,200/mo gives **~$1.15M ARR**. A national ceiling with more states' data is perhaps 5–10× that, but most states do not publish GL/WC expirations freely.
- Prospect pool: ~290k CA licensees, 56k OR, plus WA and FL. Small contractor premiums: GL averages ~$990/yr (often $1k–$5k); WC averages $2.3k–$3.8k for GCs ([Insureon](https://www.insureon.com/contractor-business-insurance/cost), [MoneyGeek](https://www.moneygeek.com/insurance/business/contractor/general-contractors/cost/)). At ~10–15% commission (est.), a small-contractor account is worth only **~$300–$1,000/yr** to the agency. **That caps what agencies will pay per meeting for micro-contractors**, so the product must filter for mid-size contractors (permit volume, multiple classifications, employees).

**Deliverable and pricing:** Option A: pay-per-held-meeting at $150–$250. Option B: territory subscription at $800–$1,500/mo with a guaranteed 4–8 meetings, plus a monthly X-date intelligence report (who is renewing, with whom, and agency market share by ZIP, built from WA's agency field). Both are recurring.

**Automation pipeline**
1. **Find buyers:** agency lists from state DOI producer databases and agency websites. Rank agencies by contractor focus (site text) and by their share of WA contractor policies (WA agency field).
2. **Build the deliverable:** nightly ingest of state files → entity resolution → filter for expirations in 30–90 days → enrich (web presence, permits, employee estimate) → LLM writes the prospect brief.
3. **Personalized outreach:** (a) to the agency: "Here are 37 roofers in your county renewing GL in the next 60 days; 9 are with [competitor agency]." (b) On the agency's behalf, emails to contractors framed as a renewal review offer.
4. **Handle replies:** an LLM triages replies, books on the producer's calendar and collects dec pages/ACORD info **without discussing coverage terms** (see Legal).
5. **Deliver and renew:** meeting held → producer feedback → monthly report, auto-renewal, territory exclusivity.

**Percent automatable:** ~75% (est.). Human touchpoints: agency sales calls in the early months, compliance review of outreach templates per state, and handling contractors who ask coverage questions (must route to a licensed producer).

**GTM, first 90 days**
- Days 1–30: build the WA + OR pipeline (Socrata, easiest). Hand-check 200 records against the source. Compute agency market share by county.
- Days 31–60: offer 20 WA/OR agencies a free "renewal radar" report with 10 named prospects each. Convert 3–5 to a pay-per-meeting pilot.
- Days 61–90: add CA (CSLB WC dates). Measure show rate and bind rate. Kill if fewer than 2 of 5 pilots renew.

**Unit economics (est.):** Price $1,200/mo. Data is mostly free, plus ~$0.10/record for contact append (~$200/mo per territory). LLM cost under $50/mo per territory. Email infrastructure ~$100/mo. **Gross margin ~75–80%.** CAC by direct outreach plus a free report: ~$800–$1,500. Payback ~1–2 months if retention is 6+ months.

**Competition and crowding:** Moderate. Data-tier competitors exist (Insurance Xdate, miEdge, LeO, Neilson), and Apify sells CSLB and WA scrapers ([CSLB scraper](https://apify.com/scrapersdelight/cslb-contractor-scraper), [WA scraper](https://apify.com/haketa/washington-li-contractor-license-scraper)). At the done-for-you tier, few competitors use real-time state insurance data. VA Horizon sells meetings but is human-staffed.

**Legal and regulatory**
- **Insurance producer licensing:** generally only licensed producers may "solicit or negotiate" insurance, and the rules are state-specific ([Harbor Compliance](https://www.harborcompliance.com/insurance-producer-license); NAIC Producer Licensing Model Act exemptions are mostly for employees not paid commission ([NAIC model](https://content.naic.org/sites/default/files/model-law-218.pdf))). Keep outreach to appointment-setting with no quotes or coverage advice, and **avoid per-policy contingent pay**. Get a state-by-state legal check before launch.
- **CAN-SPAM** applies to B2B email (identify the sender, include a physical address, honor opt-outs) ([summary](https://mailtrap.io/blog/can-spam-cold-emails/)).
- **TCPA:** AI voice counts as "artificial" (FCC, Feb 2024), so no AI cold calls to mobiles without prior express written consent; $500–$1,500/call exposure ([WSGR](https://www.wsgr.com/en/insights/fcc-rules-ai-generated-voices-are-artificial-under-the-tcpa.html)). **Email only.**
- **CA Delete Act:** if you sell personal information (sole-proprietor names count) about CA consumers you have no direct relationship with, data-broker registration ($6,000 in 2026) and DROP deletion processing may apply. Publicly available information is partially exempt ([CA privacy agency](https://privacy.ca.gov/drop-for-data-brokers/), [DataGrail](https://www.datagrail.io/blog/regulations/the-delete-act-and-drop-what-you-need-to-know/)). Selling meetings rather than lists reduces this exposure.

**Kill risks**
1. Small-contractor accounts are too small to support $150+ per meeting. The target filter must work, or agencies churn.
2. Free GL/WC expiration data exists in only a handful of states. Expansion stalls, or requires rating-bureau data that Insurance Xdate already licenses.
3. Agents historically distrust x-date vendors ("sleazy," stale data per the [IJ forum](https://www.insurancejournal.com/forums/viewtopic.php?t=2529)). Reply rates on contractor outreach may be low because contractors are heavily solicited.

---

### Idea 2 — Restaurant violation-to-vendor router (health inspections → pest, hood, refrigeration and plumbing work)

**One-line pitch:** Read every restaurant inspection narrative in a metro, use an LLM to classify each violation by the vendor who can fix it (pest, hood/grease, refrigeration, plumbing, food-safety training), and deliver re-inspection-deadline leads with done-for-you outreach to local service firms on territory subscriptions.

**Data sources:** Socrata inspection datasets for NYC, Chicago, Austin, Cincinnati, King County, Boulder and Montgomery County (free API; differing schemas) ([dev.to](https://dev.to/mayd-it/restaurant-health-inspection-data-by-city-apis-and-traps-2o9p); [Chicago](https://data.cityofchicago.org/Health-Human-Services/Food-Inspections/4ijn-s7e5)). Beyond the big cities, county portals and PDF reports need LLM scraping; check robots and terms per county. Enrichment: Google/Yelp listings for size and review mentions ("roach," "mouse"); TX mixed-beverage receipts as a revenue proxy ([data.texas.gov](https://data.texas.gov/dataset/Monthly-Revenue-by-Bar/vw6v-nwfk)).

**The combination that creates new value:** violation text → vendor category (NYC codes 04L mice, 04K rats, 04M roaches, 08A harborage; "evidence of mice" is **6.8%** of NYC violations, and pest harborage 10.4%) ([NYC code summary](https://www.renthop.com/research/restaurant-health-code-violations-skyrocket-across-nyc/)). Add the **repeat-violation history**, which means the incumbent vendor is failing and the restaurant is a switch opportunity. Add re-inspection timing for urgency and a size proxy from liquor receipts. Hazel sells inspection intelligence **to chains about themselves**. Nobody I found sells it **to vendors as a switch signal** for SMB restaurants (moderate confidence; absence of evidence isn't proof).

**Buyer persona:** Owner or GM of a local commercial pest-control firm (3–30 techs), a kitchen-exhaust/hood-cleaning company, or a commercial refrigeration repair shop in a metro with open inspection data.

**Evidence of willingness to pay:** commercial pest leads run **$50–$200 each**; commercial accounts are worth **$2k–$10k+/yr** with multi-year contracts ([Cube Creative](https://cubecreative.design/blog/pest-control-marketing/pest-control-cost-per-lead-benchmarks)). Hood cleaning costs restaurants **$600–$2,500 per visit**, recurring quarterly or semi-annually ([Ziva](https://zivacleaning.com/blog/kitchen-hood-cleaning-service-cost-guide)). Commercial-cleaning outbound CPL runs **$200+** ([Abstrakt](https://www.abstraktmg.com/cost-of-commercial-cleaning-leads-appointments/)).

**Market size**
- **16,565 pest-control firms** (81.4% with one or two locations), **$13.4B in 2025 service revenue**, commercial up ~7% ([NPMA](https://www.npmapestworld.org/your-business/latest-news/us-pest-control-industry-sustains-steady-growth-with-6-increase-in-2025/)).
- Kitchen-exhaust cleaning is a **~$1.2–2.5B** global market, with the US ~40% ([WiseGuy](https://www.wiseguyreports.com/reports/kitchen-exhaust-cleaning-services-market), [DataInsights](https://www.datainsightsmarket.com/reports/kitchen-exhaust-cleaning-services-1979287)). These market reports are low quality; treat them as directional.
- Restaurants: **700k+ locations, 1M+ foodservice outlets** ([Toast](https://pos.toasttab.com/blog/on-the-line/how-many-restaurants-are-in-the-us)).
- Bottom-up (est.): the top 25 metros with usable inspection data cover ~40% of restaurants. Assume ~3 vendor categories × ~15 viable SMB vendors per metro × 25 metros ≈ 1,100 potential subscribers. At 10% penetration (110) and $600/mo, that is **~$0.8M ARR**. Larger only with national coverage, which is where the fragmentation, and therefore the moat, sits.

**Deliverable and pricing:** a weekly "violation radar" per territory, exclusive per category per ZIP cluster, at **$400–$800/mo**, plus an optional done-for-you outreach add-on (email plus a mailed one-pager to the restaurant) at **$300/mo or $75 per booked site visit**. Recurring.

**Automation pipeline**
1. **Find buyers:** Google Maps/LSA listings for pest, hood and refrigeration vendors per metro; score by commercial focus (site text).
2. **Build:** ingest inspections → normalize polarity and outcomes → LLM classifies violations by vendor category and severity → dedupe chains (exclude them, since Hazel and Ecolab own chains) → enrich.
3. **Outreach to vendors:** a sample radar showing their own ZIPs ("14 restaurants within 5 miles had mouse or roach violations in the last 30 days; 6 are repeat offenders").
4. **Replies:** LLM triage and onboarding forms.
5. **Deliver and renew:** weekly email/CSV/CRM push, monthly ROI check-in (ask which leads closed), auto-renewal.

**Percent automatable:** ~80% (est.). Humans handle new-jurisdiction QA, schema mapping for portals that break, and occasional vendor calls.

**GTM, first 90 days:** Start in NYC (2-day data lag; 04L/04M codes are directly actionable) and Chicago. Give 30 pest and hood firms a free 2-week trial and track self-reported closes. Add Austin and King County only if the King County lag (237 days) is fixed or excluded. Kill if fewer than 5 paying vendors by day 90.

**Unit economics (est.):** Price $600/mo. Data is free (Socrata) plus enrichment of ~$50/mo per metro. Scraping and LLM costs ~$100/mo per metro. **Gross margin ~85%.** CAC ~$300–$600 by outbound email to vendors. Churn is the main unknown.

**Competitors and crowding:** Hazel/Ecolab (enterprise, chain-side; Ecolab also sells pest services, so it is a channel conflict for them). Apify inspection scrapers ([example](https://apify.com/civicdataforge/restaurant-inspection-scores)). Local pest firms already **manually read the inspection pages**; several publish NYC-violation guides as content marketing ([Victory Pest](https://victorypestsolutions.com/nyc-restaurant-health-inspection-pest-failures/)), which suggests they see the trigger but have no feed. I'd call this **low-to-moderate crowding.**

**Legal and regulatory:** CAN-SPAM for vendor outreach. For the restaurants, use email or mail rather than calls. Do not imply government affiliation. Some counties' web terms forbid automated access, so check per county. Reputational: "We saw you failed" outreach can feel predatory, so frame it as "re-inspection prep."

**Kill risks**
1. Restaurants already have pest contracts, so switching is slower than the trigger suggests, and vendors may see low close rates and churn.
2. Inspection data is stale or absent in many jurisdictions (King County 237 days), which limits geography.
3. Low price tolerance among small vendors: GetCodeViolations sells an analogous contractor product at **$49/mo** ([site](https://getcodeviolations.com/)), which may anchor expectations low.

---

### Idea 3 — Pre-opening restaurant and bar signals for local vendors (done-for-you)

**One-line pitch:** Detect restaurants 2–6 months before opening (liquor applications + sales-tax permits + tenant-improvement permits + DBA/LLC) and deliver warm introductions to local vendors (POS resellers, linen, hood install, pest, insurance, payroll).

**Data sources:** CA ABC daily new-application reports (free) ([ABC](https://www.abc.ca.gov/licensing/licensing-reports/new-applications/?RPTTYPE=2&DATEOFFSET=6)); TX weekly new sales-tax permits with NAICS 722 (free) ([Comptroller](http://comptroller.texas.gov/transparency/open-data/recent-sales-tax-permits/)); city permit portals or Shovels ($599+/mo); SOS new-entity files (FL free daily) ([Sunbiz](https://dos.fl.gov/sunbiz/other-services/data-downloads/daily-data/)).

**The combination that creates new value:** liquor application (concept + owner names) + permit valuation (size/budget) + sales-tax "first sales date" (opening estimate) + owner's other entities (repeat operator vs first-timer) → an opening-date estimate and buyer-stage classification. 71% of operators reportedly finalize key vendor decisions before opening, per RestaurantData's own research ([RestaurantData](https://restaurantdata.com/restaurant-leads/); vendor-sourced, treat with caution).

**Buyer persona:** independent Toast/Clover/Square reseller or ISO agent; local commercial insurance agent with a restaurant program; regional linen or hood company.

**Evidence of willingness to pay:** CHD Expert sells at **$59k–$119k/yr** to distributors and manufacturers ([CHD](https://www.chd-expert.com/pricetable-us/)). RestaurantData sells team plans with weekly pre-opening leads, 450+ per week ([plans](https://restaurantdata.com/plans/)). Recordpipe sells custom liquor-license feeds from **$5,000** ([Recordpipe](https://recordpipe.com/leads/liquor-license-leads.html)). Commercial insurance leads cost $40–$200.

**Market size:** ~**2,400 new restaurant openings per month** in Datassential's recent data ([Datassential](https://datassential.com/resource/foodservice-industry-trends-2026/)), so ~29k/yr. Bottom-up (est.): if each opening supports 6 vendor categories × 2–3 local competitors, there are ~35–50k vendor-opening matches a year. At $50–$100 per qualified intro, that is a **$2–5M/yr serviceable pool** (est.), and the SMB tier is fragmented.

**Deliverable and pricing:** a territory subscription at $300–$600/mo per category, or $75–$150 per accepted intro.

**Automation:** ~75% (est.). The pipeline is the same shape as Ideas 1 and 2. Outreach to the new owner works best by **mail to the premises plus email**, because owners are hard to reach before opening.

**GTM, 90 days:** TX first (free NAICS-coded permits, plus mixed-beverage receipts to measure post-opening success), then CA (ABC daily). Pitch POS resellers first: they have the highest deal value and the fastest decisions.

**Unit economics (est.):** $450/mo; data ~free (TX, CA) unless Shovels is needed; **GM ~80%**; CAC ~$400.

**Competition:** **crowded at the data tier** (CHD, RestaurantData, PreopeningRestaurants, Recordpipe, multiple Apify actors at $3–$50/1k: [Apify liquor](https://apify.com/registryfeeds/liquor-license-monitor/api), [OpenSoon](https://apify.com/nobler_voyager/opensoon-usa/api)). Only the done-for-you local tier is open. Best treated as an **add-on bundle with Idea 2** (same buyers in hood and pest; same restaurant graph).

**Legal:** CAN-SPAM; no robocalls; liquor-application owner data is public, but don't republish home addresses.

**Kill risks**
1. National data vendors move down-market with cheap self-serve tiers.
2. Opening dates slip, so leads go cold.
3. Big POS vendors (Toast) prospect in-house and resellers are thin-margin ([retailsystems commentary](https://retailsystems.org/restaurant-pos-finding-it-difficult-to-grow-toast-pos/)).

---

### Idea 4 — Good-standing rescue: "dissolved on paper, alive in reality"

**One-line pitch:** Find businesses that the state has administratively dissolved, forfeited or suspended, but that are demonstrably still operating (live website, recent reviews, active sales-tax permit or contractor license). Offer done-for-you reinstatement plus an annual compliance subscription, sold directly or white-labelled through CPAs and bookkeepers.

**Data sources:** CT monthly administrative-dissolution PDFs ([CT](https://portal.ct.gov/sots/business-services/administrative-dissolution-notices/administrative-dissolution-notices)); FL free daily corporate files (status changes after the fourth-Friday-of-September dissolution) ([Sunbiz](https://dos.fl.gov/sunbiz/other-services/data-downloads/), [FL annual report rule](https://dos.fl.gov/sunbiz/manage-business/efile/annual-report/)); TX Comptroller forfeiture status via taxable-entity search ([scraper reference](https://apify.com/bovi/texas-taxable-entity)) **cross-checked against the active TX sales-tax permit file (888k rows)** ([data.texas.gov](https://data.texas.gov/Government-and-Taxes/Active-Sales-Tax-Permit-Holders/jrea-zgmq?defaultRender=table)); OpenSOSData at $0.03/lookup for other states ([OpenSOSData](https://opensosdata.com/vs/cobalt/)); Google/Yelp/website liveness checks.

**The combination that creates new value:** dissolution status × evidence of operation × exposure (contractor license, liquor license, active contracts, UCC debtor status). The "alive" filter is the LLM-plus-web join. In TX, a forfeited entity's officers can be **personally liable for debts incurred after forfeiture** (Tax Code §171.255), and the entity cannot sue or defend suits ([Freeman Law](https://freemanlaw.com/forfeiture-and-reinstatement-under-the-texas-franchise-tax/), [LegalClarity](https://legalclarity.org/right-to-transact-business-in-texas-forfeited-what-it-means/)). That is real, documentable urgency rather than manufactured fear.

**Buyer persona:** owner of a 1–20-employee LLC or corporation that missed an annual report or franchise-tax filing. Alternative channel: CPA and bookkeeping firms wanting a client-monitoring add-on.

**Evidence of willingness to pay:** Harbor Compliance reinstatement starts at **$399 + state fees** ([Harbor](https://www.harborcompliance.com/reinstate-llc-corporation)). ZenBusiness and Northwest charge **$100 + state fee** per annual report filing ([ZenBusiness comparison](https://www.zenbusiness.com/best-annual-report-filing-services/)). State reinstatement fees run ~$70 (TN) to $260 (GA) ([Harbor TN](https://www.harborcompliance.com/reinstate-revive-tennessee-corporation-llc-nonprofit), [GA guide](https://registeredagentguides.com/reinstatement/georgia/)).

**Market size:** national dissolution counts are **not published consistently** ([SC SOS: no reason-coded data](https://www.scstatehouse.gov/CommitteeInfo/HouseLegislativeOversightCommittee/AgencyWebpages/SecretaryofState/Business%20Corporation%20administrative%20dissolution%20-%20Reasons%20and%20Statistics.pdf)). South Carolina **business corporations alone** saw 2,014–6,293 administrative dissolutions a year in 2015–2019 (same source). Bottom-up (est., **low confidence**): ~5.6M business applications a year ([Census BFS](https://www.census.gov/econ/bfs/index.html)) and a 3–5% annual lapse rate on a ~30M registered-entity base suggest ~1M lapses a year nationally. If ~20% are still operating (200k), 2% convert (4,000) at ~$450 first-year revenue plus $150/yr renewal, the result is **~$1.8M year one + ~$0.6M recurring**. Verify by sampling FL daily files before committing.

**Deliverable and pricing:** a one-time reinstatement filing ($349–$449 + state fee) that converts to "Good Standing Guard" at $12–$19/mo (deadline tracking, annual report filing, registered-agent upsell). Recurring, but low ARPU.

**Automation pipeline:** find via state files → liveness and exposure scoring → personalized letter and email ("Your Texas LLC's right to transact business was forfeited on [date]; here is what that means; you can fix it yourself for $X at the state, or we'll do it for $Y") → an LLM handles replies and intake → filings prepared by agent with **human review and submission** → auto-renew compliance. **~80% automatable (est.)**; a human reviews each filing (tax clearance in TX, delinquent reports).

**GTM, 90 days:** pilot FL (free daily files; the September 2026 dissolution wave just happened, so timing is ideal) and TX (forfeiture + sales-tax join). Send 2,000 letters and emails, measure the reply rate, and kill below 1% paid conversion. In parallel, test a white-label offer to 30 CPA firms.

**Unit economics (est.):** first-year revenue ~$450. Fulfilment cost ~$40 (human review time + postage + LLM). Acquisition cost ~$1.50 per letter, or ~$150 per paid customer at 1% conversion. **GM ~85% after state fees pass through.**

**Competitors and crowding:** Harbor Compliance, LegalZoom, ZenBusiness, Northwest, plus local attorneys and CPAs, mostly **inbound/SEO.** The category is **polluted by deceptive "certificate of status" and annual-report mailers.** Multiple SOS offices warn about them (TN, GA, CO, MS, MT, CT) ([TN SOS](https://sos.tn.gov/press-releases/secretary-of-states-office-warns-of-new-scam-targeting-tennessee-businesses), [GA SOS](https://sos.ga.gov/news/new-business-owner-alert-misleading-certificate-existence-solicitations-sent-out-statewide), [MS SOS](https://www.sos.ms.gov/news/warning-misleading-annual-report-mailers-0)).

**Legal and regulatory:** **this is the highest-risk idea in the lane.** California B&P §17533.6 requires conspicuous "NOT A GOVERNMENT DOCUMENT" and "not approved by any government agency" disclaimers on such solicitations ([text](https://law.onecle.com/california/business/17533.6.html)), and AGs sue violators ([CA AG](https://oag.ca.gov/news/press-releases/brown-sues-8-individuals-and-6-businesses-operating-scams-targeting-california)). Montana issued a cease-and-desist to a mailer ([MT SOS](https://sosmt.gov/secretary-christi-jacobsen-warns-montana-businesses-of-new-deceptive-mailing-issues-cease-and-desist-letter/)). Requirements: show the state fee next to yours, use no seals and no "required by law" language, and avoid unauthorized practice of law (filing ministerial forms is generally fine; advising on liability is not).

**Kill risks**
1. Recipients bin the outreach as a scam because of the category's reputation, so conversion falls below 1%.
2. A single AG complaint or SOS warning naming the brand kills the business.
3. Low ARPU: the recurring piece ($150/yr) is small, and CAC per recurring customer may not pay back.

---

### Idea 5 — Construction payment-distress radar for supplier credit managers

**One-line pitch:** Monitor a building-materials supplier's contractor customers for mechanics liens filed against them, lawsuits, bond impairment or cancellation, license suspension, and fresh MCA UCC filings (a sign of cash stress). Send weekly interpreted alerts.

**Data sources:** county recorder indexes and images (fragmented; LLM extraction of lien PDFs); WA bond-impairment field ([WA bond](https://data.wa.gov/Labor/L-I-Contractor-License-Data-Bond/bzff-4fmt)); CSLB status; state court portals (UniCourt/Trellis as a backfill); UCC data (free in CO, VT, CT and WV; paid elsewhere) ([Quintel](https://quintel.ai/blog/ucc-filing-search-by-state)).

**The combination:** liens and suits **filed against** a customer + **MCA UCCs** (secured parties that are known MCA funders) + license/bond changes. Today a supplier sees these only in separate NACM or NCS products, if at all, and the MCA-stacking angle is generally absent from construction credit tools (my reading of [NCS](https://www.ncscredit.com/services/additional-tools/lien-finder) and [BICA](https://www.bicanet.com/products/construction-credit-report/) pages).

**Buyer:** credit manager at an LBM dealer or an electrical, plumbing or HVAC distributor. There are **34,448 LBM stores** ([IBISWorld](https://www.ibisworld.com/united-states/number-of-businesses/lumber-building-material-stores/1034/)). Credit manager pay is **$81k–$131k** ([search summary of ZipRecruiter/Salary.com](https://www.salary.com/research/company/us-lbm-holdings-llc/regional-credit-manager-salary?cjid=12752913)). Public-records researchers who do this manually earn **$22–$36/hr** ([ZipRecruiter](https://www.ziprecruiter.com/Salaries/Public-Records-Researcher-Salary)).

**Evidence of willingness to pay:** NACM reports at $14.50–$25 each ([NACM](https://nacmsouthatlantic.com/services/commercial-credit-reporting/nacm-national-trade-credit-report/)); NCS LienFinder and BICA exist as paid products; DataMerch's analogous MCA portfolio monitoring costs **$695–$945/mo** ([DataMerch](https://www.datamerch.com/pricing/index.html)).

**Market size (est.):** ~34k LBM stores, but they consolidate to perhaps ~6–8k credit-decision entities. Add ~10k electrical, plumbing and HVAC distributor branches, again consolidated. Say ~10k buyers at $400/mo × 5% = **$2.4M ARR**.

**Deliverable and pricing:** upload an AR customer list and get weekly alerts plus a monthly risk memo. $250–$1,000/mo by number of monitored customers. Highly recurring.

**Automation:** ~65% (est.). Recorder coverage needs ongoing human QA, and AR-list onboarding needs hand-holding.

**GTM, 90 days:** pick TX and FL (top lien states per [NCS](https://www.ncscredit.com/education-center/blog/lien-index-q1-2026)); cover 10 metro counties. Run free "backtest" reports on 5 suppliers' past write-offs to show what the radar would have caught.

**Unit economics (est.):** $500/mo; per-county data cost (images, court fees) ~$1–3k/mo amortized across customers; GM 60–70% at 30+ customers; CAC $1,500–$3,000 (longer B2B cycle).

**Competition:** moderate (NCS, NACM, BICA, Levelset/Procore, D&B/Experian). The blue-ocean element is the MCA-UCC and bond-impairment join.

**Legal:** if alerts are used for credit decisions about **businesses**, FCRA generally doesn't apply. For **sole proprietors** it may (consumer-report risk), so get counsel. Recorder image terms vary.

**Kill risks**
1. Coverage gaps across 3,000+ recorders make alerts unreliable, and credit managers stop trusting them.
2. Long sales cycles and incumbent bundling (NACM membership).
3. The data-cost floor (per-page image fees) erodes margin before scale.

---

### Idea 6 — ADA web-suit radar → accessible rebuilds (adjacent to the brothers' core)

**One-line pitch:** Track federal and key-state website-accessibility suits to learn which industries, platforms and geographies serial plaintiffs are targeting now. Scan look-alike SMB sites and offer an accessible rebuild plus monitoring, using the brothers' existing site-building engine.

**Data:** CourtListener RECAP API and webhooks (free or means-based) ([API](https://courtlistener.com/help/api/)); PACER fallback; NY, FL and IL state dockets.

**Combination:** fresh filings (plaintiff firm, defendant industry, venue) + an automated WCAG scan of similar businesses' sites + the brothers' rebuild pipeline. The court data picks *who is next*, not just who was sued.

**Evidence:** **3,117** federal website-accessibility suits in 2025 (+27%; NY 1,021, FL 961, IL 585) ([Seyfarth ADA Title III](https://www.adatitleiii.com/2026/03/federal-court-website-accessibility-lawsuit-filings-bounce-back-in-2025/)); **5,000+** including state courts, with **1,427** against prior defendants ([UsableNet via search summary](https://info.usablenet.com/hubfs/2025-MidYear-Report-FINAL.pdf?hsLang=en), [summary](https://wcagsafe.com/blog/ada-lawsuit-statistics)).

**Buyer:** SMB owner (e-commerce, restaurant, retail) in NY, FL or IL; defense attorneys as a referral channel.

**Pricing:** rebuild $1.5–5k + $99–$199/mo monitoring (est.).

**Market (est.):** ~5k defendants a year plus a much larger "look-alike" pool. Even 0.5% of 200k look-alikes is 1,000 deals a year.

**Automation:** ~80%. **Competition:** crowded (overlays such as accessiBe and UserWay, audit firms, UsableNet).

**Legal:** the FTC fined accessiBe **$1M** for claiming its tool made sites WCAG-compliant ([FTC case](https://www.ftc.gov/legal-library/browse/cases-proceedings/2223156-accessibe-inc)). Never claim "lawsuit-proof." Fear-based marketing to sued defendants is sensitive; CAN-SPAM applies.

**Kill risks**
1. The fear-marketing reputation of the category.
2. Plaintiffs' targeting shifts faster than the outreach cycle.
3. Overlays undercut on price.

**Verdict:** a **feature for the brothers' existing business, not a new lane.**

---

### Idea 7 — Equipment refresh-window signals from UCC collateral text

**One-line pitch:** Parse UCC-1 collateral descriptions (equipment class, make or model where stated) and the secured party (a captive finance arm or bank) to estimate lease or loan maturity. Sell "equipment likely coming off lease in 3–6 months" leads to independent equipment dealers and lessors.

**Data:** state UCC bulk files. Costs range from Ohio's one-time $83.75 to Arizona's $24k and Kentucky's $1,500/mo; NC prohibits scripts; GA prohibits scraping ([Quintel](https://quintel.ai/blog/ucc-filing-search-by-state)). EDA/Fusable already does this at scale ([EDA](https://edadata.com/industryinsight/construction/), [IronSolutions on EDA](https://ironsolutions.com/what-is-eda/)). NAEDA training material promotes UCC data for dealers ([NAEDA PDF](https://www.naeda.com/wp-content/uploads/2025/12/How-to-Use-UCC-Filing-Data-to-Sell-More-Equipment-Fusable.pdf)).

**Combination:** collateral text (LLM) + secured-party type + filing age + permit or contract activity for construction firms.

**WTP:** proven (EDA has existed for decades; uccdata.io charges $0.30/record). **Competition:** high. EDA is entrenched; Quintel positions itself on interpretation ("a filing is not a prospect by itself").

**Market (est.):** a few thousand dealers and lessors. **Data cost and access restrictions are high.**

**Kill risks**
1. EDA's incumbency and dealer-management-system integrations.
2. A many-state data bill before revenue.
3. Collateral descriptions are often generic ("all assets"), which caps signal quality.

**Verdict: low priority.**

---

### Idea 8 — Verified new-business feed ("real operating businesses only") for local vendors

**One-line pitch:** Take raw formation, DBA and permit filings, discard holding, real-estate and shell LLCs, keep entities with a physical outlet (TX sales-tax permits carry NAICS and first-sales date), and sell weekly verified new local businesses to CPAs, insurance agents, banks, payroll firms and web designers.

**Data:** FL daily SOS files (free), TX weekly sales-tax permits (free, with NAICS) ([Comptroller](http://comptroller.texas.gov/transparency/open-data/recent-sales-tax-permits/)), county DBAs (fragmented), Census BFS for sizing (**5.62M applications in 2025**) ([Census](https://www.census.gov/econ/bfs/index.html)).

**WTP:** weak for raw data. Apify sells new filings at **$4/1k** ([Apify](https://apify.com/lergassy/us-business-filings)); Data Axle charges $0.07–$0.30/record ([bookyourdata](https://www.bookyourdata.com/blog/data-axle-pricing)). Enrichment and verification may lift that to ~$0.50–$2 per verified record or $99–$299/mo per territory (est.).

**Competition:** saturated at the data layer. New-business mail is also the favoured channel of deceptive mailers (TN warned in **September 2026** of a scam targeting newly registered companies) ([WVLT](https://www.wvlt.tv/2026/09/16/tennessee-secretary-state-warns-bogus-mail-scam-targeting-newly-formed-businesses/)). New owners are flooded with offers.

**Best use:** as an **internal prospecting source for the brothers' own website business** (new businesses with no site), not as a product to sell.

**Kill risks**
1. Commoditized pricing.
2. Buyer fatigue and scam association.
3. Low differentiation, since verification is easily copied.

---

## 3. Ideas considered and rejected

| Idea | Why rejected (evidence) |
|---|---|
| **Probate leads → real-estate investors** | Saturated: dozens of vendors at $69–$1,200+/county/mo, with per-lead pricing down to **$0.10** ([probatedata](https://www.probatedata.com/blog/best-probate-lead-services-for-multi-county-investors), [Tracerfy](https://www.tracerfy.com/leads/probate/), [USLeadList](https://usleadlist.com/probate-leads)). The fragmentation moat has already been crossed. |
| **Divorce filings → realtors and lenders** | Sold by PropStream and specialist vendors ([PropStream](https://www.propstream.com/real-estate-agent-blog/divorce-real-estate-leads-5-reasons-theyre-beneficial-for-agents), [All The Leads](https://alltheleads.crisp.help/en/category/divorce-leads-faq-7is28t/)). Heavy TCPA/DNC exposure (consumers), high reputational risk, no B2B recurring angle. |
| **Federal/state tax liens → tax-resolution firms** | Commodity: **$0.16–$0.40/record**, "3,000+ counties" already aggregated daily ([Extrakt](https://www.extraktdata.com/tax-liens), [irsleads](https://irsleads.com/)). The buyer industry has ongoing FTC and AG enforcement ([FTC 2026](https://www.ftc.gov/news-events/news/press-releases/2026/06/ftc-nevada-will-require-tax-relief-scammers-pay-cash-turn-over-assets-worth-nearly-10-million-settle)). Consumer TCPA risk. |
| **Residential code violations → contractors** | Low WTP and crowded: GetCodeViolations at **$49/mo** across 56+ cities; PropStream; ListCentral; Apify from $2/1k ([GetCodeViolations](https://getcodeviolations.com/), [Apify](https://apify.com/permitdata/us-code-violations-scraper)). |
| **MCA UCC lead lists → brokers** | Commodity at **$0.005–$0.30/record** ([Apify UCC](https://apify.com/deadwood_data_solutions/ucc-filing-leads), [uccdata.io](https://uccdata.io/)). Regulatory churn (TX HB 700 registration and disclosure; non-first-position funders can't auto-debit) ([Mayer Brown](https://www.mayerbrown.com/en/insights/publications/2025/06/texas-commercial-financing-disclosure-and-registration-law-threatens-sales-based-financing-industry), [FunderIntel](https://www.funderintel.com/post/texas-tightens-sales-based-financing-rules-under-hb-700)). Broker TCPA risk. |
| **MCA funder stacking/default monitoring** | Real WTP but crowded: DataMerch ($695–$945/mo, 300+ funders), Middesk Monitor, Cobalt, MCA Track ([DataMerch](https://www.datamerch.com/pricing/index.html), [Middesk](https://www.middesk.com/blog/ucc-lien-monitoring), [MCA Track](https://mca-track.com/mca-stacking-detection/)). Small buyer base: Virginia lists only ~115 registered sales-based financing providers ([deBanked](https://debanked.com/2023/05/how-many-funders-and-brokers-are-there/)). |
| **Judgments → judgment recovery and collections** | Collection-agency licensing and bonds (e.g., FL $50k bond, NY $25k) and debt-buyer licensing in NY, MA, CA, WA, CT, IL, MN; unlicensed collection can void judgments ([startpermit](https://startpermit.com/blog/how-to-start-a-collection-agency/), [debtbuyerrights](https://debtbuyerrights.org/state-licensing.html)). Too regulated for an automated outreach model. |
| **New-lawsuit alerts → attorneys** | Trellis ($69.95–$199.95/mo), UniCourt ($59–$399/mo), Case Filings Alert ([Trellis](https://trellis.law/plans), [UniCourt](https://unicourt.com/pricing), [CFA](https://casefilingsalert.com/)). Attorney solicitation rules constrain the end use. State court access is legally and technically fraught ([judyrecords](https://www.judyrecords.com/what-happened-with-tyler-technologies)). |
| **Professional-license expirations → CE providers** | Boards publish expiration data free (e.g., FL DBPR weekly files) ([DBPR](https://www2.myfloridalicense.com/sto/documents/readme.pdf)), so CE providers can self-serve. Low value per lead. |
| **Elevator and boiler inspection deadlines → service firms** | Data exists (TX TDLR elevator file with next-inspection date ([TDLR](https://www.tdlr.texas.gov/elevator_searchapp/home/searchhelp)); MN boiler CSV ([MN DLI](https://www.dli.mn.gov/workers/boiler-engineer/certificate-registration-boilers-and-pressure-vessels))). But the buyer universe is small: independents hold ~55% of service and OEMs 45% ([search summary](https://elevatorworld.com/article/the-impact-of-consolidation-and-globalization-on-the-u-s-market/)), coverage is state-by-state, and a free TX aggregator already exists ([elevatordatabase.com](https://elevatordatabase.com/Texas)). A good niche **add-on** for a building-services product; too small alone. |
| **Raw new-business lists sold as data** | See Idea 8. Commoditized; use internally only. |

---

## 4. Ranked shortlist

Scores are 1–10; 10 is best. For **Competition**, 10 means blue ocean. Overall is the unweighted mean of the 7 dimensions. These are judgement calls, not measurements.

| Rank | Idea | Market size | WTP | Data access | Automation | Competition (10 = blue ocean) | Recurring | Time to first $ | **Overall** | Confidence |
|---|---|---|---|---|---|---|---|---|---|---|
| 1 | **Contractor coverage X-date engine** (CA/WA/OR/FL → booked meetings for commercial agents) | 6 | 8 | 8 | 7 | 5 | 8 | 7 | **7.0** | Medium. WTP for meetings is proven; contractor account size and licensing constraints are unverified |
| 2 | **Restaurant violation-to-vendor router** (pest/hood/refrigeration) | 6 | 6 | 6 | 7 | 8 | 7 | 7 | **6.7** | Medium-low. No direct proof vendors pay for *this* trigger; a cheap pilot can test it |
| 3 | **Good-standing rescue** (dissolved but operating → reinstatement + compliance) | 7 | 6 | 6 | 8 | 6 | 5 | 8 | **6.6** | Low-medium. Volume unverified; high legal and reputational risk |
| 4 | **ADA web-suit radar** (feature for the brothers' web business) | 6 | 6 | 7 | 7 | 4 | 6 | 7 | **6.1** | Medium |
| 5 | **Pre-opening restaurant signals, done-for-you** (bundle with #2) | 6 | 7 | 6 | 7 | 3 | 7 | 6 | **6.0** | Medium. Proven WTP, crowded data tier |
| 6 | **Verified new-business feed** (internal prospecting use) | 7 | 3 | 8 | 8 | 2 | 6 | 7 | **5.9** | High that it's weak as a product |
| 7 | **Construction payment-distress radar** | 5 | 7 | 4 | 6 | 5 | 9 | 4 | **5.7** | Medium |
| 8 | **Equipment refresh windows from UCC** | 5 | 7 | 4 | 6 | 3 | 8 | 4 | **5.3** | Medium |

### My recommendation

- **Run two cheap pilots in parallel (~90 days, under $5k in data and tools, est.):**
  - **Idea 1** in WA and OR first. Free Socrata data, an insurance-agency field, updated 3×/day; this is the cleanest data asset in the lane.
  - **Idea 2** with Idea 3 bundled, in NYC and Chicago (fresh data, actionable pest codes).
  - Both reuse the brothers' find → build → outreach → reply → renew machine almost unchanged. The "deliverable" is a prospect brief or booked meeting instead of a website.
- **Run Idea 4 only after a legal review** of mailer and disclaimer rules. Start with a CPA white-label channel, not direct-to-owner mail, to avoid the scam association.
- **Fold Ideas 6 and 8 into the existing website business** as prospecting signals rather than standalone companies.
- **Honest overall read:** this lane has **no 9/10 idea.** Public records are well mined at the data layer, and the AI-extraction edge is already priced into Apify-level commodity scrapers. The durable advantage is **conversion as a service on top of joined signals**, and that advantage is about the operator's execution, not data exclusivity. Expect modest, sub-$5M-ARR businesses per idea (est.), not venture-scale outcomes.

---

### Appendix A: Cross-cutting legal checklist

- **CAN-SPAM:** applies to B2B email: accurate headers, physical address, opt-out honored within 10 business days ([Mailtrap summary](https://mailtrap.io/blog/can-spam-cold-emails/)).
- **TCPA:** AI voices count as "artificial" (FCC, Feb 2024). Marketing calls to mobiles using them need prior express written consent; $500–$1,500 per call ([WSGR](https://www.wsgr.com/en/insights/fcc-rules-ai-generated-voices-are-artificial-under-the-tcpa.html), [FCC](https://docs.fcc.gov/public/attachments/DOC-400393A1.pdf)). **Default to email and mail; no AI dialing.**
- **Government-lookalike solicitation laws:** CA B&P §17533.6 plus active SOS warnings in many states (see Idea 4).
- **Data-broker laws:** CA Delete Act registration ($6,000 for 2026) and DROP deletion processing from Aug 1, 2026 if selling personal information about CA consumers ([CA privacy agency](https://privacy.ca.gov/drop-for-data-brokers/)). Similar registries exist in VT, TX and OR (verify). Selling outcomes (meetings) rather than records reduces exposure.
- **GDPR:** not material for US-only public records, unless EU data subjects appear (e.g., foreign owners listed on filings).
- **Source-specific terms:** NC UCC prohibits scripted access; GA bulk UCC prohibits scraping; WV requires a contract for commercial resale ([Quintel](https://quintel.ai/blog/ucc-filing-search-by-state)); CSLB excludes emails by law ([CSLB](https://www.cslb.ca.gov/onlineservices/dataportal/ContractorList)). Court portals: avoid anything resembling the Tyler/judyrecords access-control situation ([judyrecords](https://www.judyrecords.com/what-happened-with-tyler-technologies)).
- **Insurance producer licensing:** keep outreach to appointment-setting with no quotes or advice, and no contingent per-policy compensation, unless licensed ([NAIC model act](https://content.naic.org/sites/default/files/model-law-218.pdf)).

### Appendix B: The manual labour being replaced

- Public-records researchers: avg **$26.79/hr** (25th–75th percentile $22–$36) ([ZipRecruiter](https://www.ziprecruiter.com/Salaries/Public-Records-Researcher-Salary)); title/lien researchers $45–51k ([ZipRecruiter UCC research](https://www.ziprecruiter.com/Jobs/Ucc-Research)).
- Commercial insurance producers spend unpaid time sourcing x-dates. Outsourced appointment setting is billed at ~$5.25/hr (offshore) or $50–$100 per appointment ([IJ forum](https://www.insurancejournal.com/forums/viewtopic.php?t=2529)), and up to $300–$550 per meeting for commercial accounts ([VA Horizon](https://www.vahorizon.site/b2b/guides/what-x-dates-are-and-how-to-source-them/)).
- Construction credit managers ($81k–$131k) manually pull lien and credit reports per customer ([Salary.com](https://www.salary.com/research/company/us-lbm-holdings-llc/regional-credit-manager-salary?cjid=12752913)).

### Appendix C: Research gaps (verify before investing)

1. National administrative-dissolution volume. Sample the FL daily files for October 2026 to count the September 2026 dissolution wave.
2. Whether GL/WC expiration data is public in states beyond CA, WA, OR and FL (rating-bureau access terms in NCCI states).
3. RestaurantData.com and Insurance Xdate actual prices (not published).
4. Ficticious.com: the domain did not resolve on 2026-10-01; confirm the intended vendor name.
5. Close rates for pest and hood vendors on violation-triggered outreach. There is no public data; the pilot is the test.
