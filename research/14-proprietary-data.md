# Lane 14: Data that is not on the open web but can be obtained

*Round 2 research lane. Date: 2026-10-01. About 95 web searches and fetches. Every material claim has a link.*

## 1. Lane overview

**Brief.** Round 1 failed because "public data" was equally available to every competitor. This lane looks for datasets that (i) are **not** downloadable and not already aggregated by a funded vendor, (ii) can be built cheaply by agents, and (iii) feed the brothers' real edge, which is a **done-for-you outbound and reply machine**. I examined five source families:

| Family | Verdict in one line |
|---|---|
| (a) FOIA and records requests at scale | **Generic SLED contract data is taken.** GovSpend claims 2B+ POs, 96M contracts and 2.3M meeting transcripts, and every subscription includes custom data requests ([GovSpend FAQ](https://govspend.com/faq/), [fed-spend](https://fed-spend.com/blog/how-does-govspend-work-comparison)). Starbridge ($52M raised; "FOIA automation returns full competitor contracts with pricing, opt-out clauses, and expiration dates") ([Starbridge blog](https://starbridge.ai/blog/civiciq-alternatives), [pulse2](https://pulse2.com/starbridge-42-million-series-a-closed-to-transform-how-businesses-sell-to-government-and-education/)). HigherGov files FOIAs for $50 each ([HigherGov docs](https://docs.highergov.com/more/foia-service)). Civic IQ sells "Pipeline-as-a-Service" from $2,000/mo ([Civic IQ](https://civiciq.com/pursuit-alternatives)). **The surviving gap is non-procurement regulatory records**: who is overdue on a code-mandated inspection, held by ~2,000+ fire departments in vendor systems. |
| (b) Data co-ops and give-to-get | Vendr, Tropic (SaaS), CompStak (CRE leases, 40k members), ZenOne ($49/mo) and Alara (free) for dental already exist. Restaurants have GPOs and invoice tools. **The one co-op with real money moving is contingency audit of SMB recurring-service contracts (uniform/linen, waste)**, but it is already a consulting category. |
| (c) The brothers' own exhaust | **Dead.** Middesk already sells a `web_presence_quality` rating to lenders ([Middesk docs](https://docs.middesk.com/online-presence/web-presence)). Carpe Data sells 45M SMB online-presence profiles to The Hartford and Auto-Owners ([Carpe](https://carpe.io/the-hartford-taps-carpe-data-for-small-business-data/), [IIR](https://iireporter.com/carpe-data-launches-commercial-data-as-a-service-platform/)). PredictLeads sells "website evolution" signals from $40/mo ([coldiq](https://coldiq.com/tools/predictleads)). |
| (d) Agent-collected primary data (AI calls, mystery shops) | Real money moves: multifamily phone shops cost $40+ and programs run $800–2,400 per community per year ([Grace Hill](https://gracehill.com/pricing/mystery-shopping/), [Siro](https://www.siro.ai/insights/mystery-shopping-leasing-performance)). But AI-native shops already exist (Rev Leasing, EliseAI, Funnel) ([Funnel](https://funnelleasing.com/apartment-secret-shop-for-multifamily-leasing/)). Home-services firms score 100% of their own calls with Invoca, CallRail or ServiceTitan ([Invoca](https://www.invoca.com/reports/the-invoca-home-services-lead-conversion-benchmarks-report-2026)). TCPA (AI voice = "artificial voice", [FCC](https://docs.fcc.gov/public/attachments/DOC-400393A1.pdf)) and CIPA ($5,000 per violation, [Shouse](https://www.shouselaw.com/ca/defense/laws/california-invasion-of-privacy-act/)) add risk. |
| (e) Transcribing meetings and hearings | **Dead.** GovSpend has 2.3M transcripts. Hamlet covers 3,000+ governments with a free tier ([PublicCEO](https://www.publicceo.com/2026/02/hamlet-launches-nationwide-public-meeting-coverage-over-3000-local-governments-videos-now-discoverable/)). CitizenPortal.ai is $0–15/mo ([aichief](https://aichief.com/ai-productivity-tools/citizen-portal/)). Starbridge, Curate and Pursuit also play here. |

**Main finding.** One records family looks genuinely proprietary and early: **third-party fire and life-safety inspection compliance data (ITM: inspection, testing and maintenance)**. Fire codes (NFPA 25 and 72) require annual inspections. More than 2,000 jurisdictions make contractors upload every report to The Compliance Engine (Brycer) ([TCE news](https://www.thecomplianceengine.com/post/brycer-continues-to-expand-the-compliance-engine-with-new-2026-services), [San Diego](https://www.sandiego.gov/fire/community-risk-reduction/fire-protection-systems/compliance-engine)). Others use LIV or BuildingReports. That system knows (1) **which properties are overdue or carry unresolved deficiencies** and (2) **which contractor inspects which building**, which measures each contractor's recurring inspection book. Neither is on the web (San Francisco's open "Fire Inspections" set covers city inspections only, not contractor ITM: [data.sf.gov](https://data.sf.gov/Housing-and-Buildings/Fire-Inspections/wb4c-6hwj/data)). Brycer does not sell a list product. **However, the verifier found that in May 2026 Brycer began marketing TCE as "a consistent, trackable source of inbound demand for service providers".** It also launched satellite "Virtual Walkthroughs" to find unreported systems ([Digital Journal PR](https://www.digitaljournal.com/pr/news/prodigy-press-wire/compliance-engine-expands-access-compliance-driven-1675648375.html)). Every TCE notice to an owner prints the **contractor of record** with phone and email ([Sedalia plan](https://www.sedalia.com/wp-content/uploads/compliance-implementation-plan.pdf)). So the platform owner holds the data first-hand and is moving into this gap. Ideas 1 and 2 are built on this data. **After self-verification no idea in this lane scores above 4/10** (see sections 4–5).

**Honest caveat up front.** I could not find a single public example of an AHJ releasing a TCE overdue or contractor list in response to a records request. **Obtainability is the #1 unknown, and the cheapest test (section 2, idea 1) is built around it.** Florida's statute explicitly makes information "revealing security or firesafety systems" of privately owned property held by an agency confidential ([Fla. Stat. 119.071(3)(a)](https://www.flsenate.gov/Laws/statutes/2025/119.071)). Other states may take the same view.

---

## 2. Candidate ideas

### Idea 1: "Overdue Feed": fire/life-safety ITM overdue-and-deficiency lists via records requests, plus done-for-you owner outreach for fire protection contractors

**Pitch.** Agents file and chase public-records requests with hundreds of fire departments (AHJs) for one table: *property address, system type (sprinkler, alarm, kitchen hood, standpipe, fire pump), last report date, status (current, overdue, open deficiency), contractor of record*. Refresh quarterly. Overdue and stale-deficiency properties are owners who are **out of compliance today and being chased by the fire marshal**: TCE sends notice, then a 30-day second deficiency notice, then escalation ([Chino Valley FAQ](https://www.chinovalleyfire.org/m/faq?cat=16), [TCE](https://www.thecomplianceengine.com/)). We sell a territory-exclusive service to a fire protection contractor (or a PE roll-up branch). We run personalized outbound in the contractor's name to owners and property managers of those buildings, handle replies and book site visits.

**Data and access.**
- Source: AHJ records held in TCE, LIV, BuildingReports or in-house systems. Records held by a vendor for an agency are generally still agency records, but this varies by state.
- Access: state public-records acts. Seven states limit requests to residents (AL, AR, DE, NJ, KY, TN, VA), so filing needs an in-state requester or partner ([Ballotpedia](https://ballotpedia.org/List_of_who_can_make_public_record_requests_by_state), [McBurney v. Young](https://en.wikipedia.org/wiki/McBurney_v._Young)). Some states allow commercial-purpose fees, e.g. AZ and MA ([AZ DIFI](https://difi.az.gov/prr-commercial-purpose), [MA guide](https://www.sec.state.ma.us/divisions/public-records/download/guide.pdf)).
- **Florida is out** (firesafety exemption above). Texas Gov't Code 418.18x security exemptions must be tested.
- Response time: MuckRock's data shows ~59 days average, and well under half of local requests are completed, e.g. MA 32% and WA 50% success ([MuckRock](https://www.muckrock.com/news/archives/2019/mar/21/feature-state-data/), [MuckRock II](https://www.muckrock.com/news/archives/2019/mar/27/feature-state-data-ii/)). Plan on a **30–50% usable-yield rate per AHJ.**
- Enrichment: owner from county assessor (public). Property manager and email from standard enrichment.

**Buyer.** Commercial fire and life-safety service contractors: independents and branches of PE platforms. 1,300+ inspection companies use BuildingReports alone ([BuildingReports](https://www.buildingreports.com/m/feed/)). Consolidators include Pye-Barker (57 acquisitions in 2025, 22 in H1 2026; [IFSJ](https://internationalfireandsafetyjournal.com/pye-barker-acquisitions-2026/)), Summit, AI Fire (Blackstone), Marmic (KKR) and Sciens (Carlyle) ([CT Acquisitions](https://ctacquisitions.com/guides/private-equity-fire-life-safety-2026/)). These platforms push branch organic growth because "recurring inspection-contract density" drives exit multiples ([CT Acquisitions](https://ctacquisitions.com/guides/private-equity-fire-life-safety-2026/)).

**Evidence money moves today.**
- Fire protection paid leads cost **$60–250 per lead** ([Abstrakt review](https://www.abstraktmg.com/best-fire-protection-lead-generation-firms/), [cufinder](https://cufinder.io/blog/benchmarks/fire-protection/)). Agencies charge **$1,199–19,999/mo** ([Built Right Digital](https://builtrightdigital.com/fire-safety-lead-generation/)). Outbound appointment setters (Abstrakt, Calling Agency) sell this exact motion.
- Contractors already pay Brycer **$17–30 per report** filed ([Forney TX agenda packet](https://www.forneytx.gov/AgendaCenter/ViewFile/Item/8466?fileID=11907), [AP Fire](https://www.apfireprotection.com/why-does-my-bid-have-a-compliance-engine-fee/)). Brycer itself pitches contractors that TCE notices bring "a 10.8x difference in the cost of upload to the cost of increased work/revenue" (Forney packet). That shows overdue notices create contractor revenue.
- Claimed LTV of a commercial inspection contract is over $12k (vendor marketing, [Abstrakt](https://www.abstraktmg.com/best-fire-protection-lead-generation-firms/); treat as soft).

**Why the buyer can't do it themselves or buy it for $50/mo.** Contractors see only their own customers in TCE. The AHJ list of overdue properties is not exposed to contractors (Brycer's 2026 products add none). A contractor *could* file records requests itself. In practice that means hundreds of AHJs, follow-ups, format wrangling and enrichment, then running outbound at all. It is the same "why don't they build their own website" argument the brothers already win. No $50/mo product sells this list (8+ searches below).

**Is the trigger early enough?** Mostly yes, and better than in round 1. Overdue status *persists* until someone inspects, and the escalation cycle runs 30 + 30 days and beyond. Our snapshot is 1–3 months old on delivery. Some owners will already have called their old vendor, but chronically overdue properties (>90 days) are, by definition, not being served. **Risk:** the AHJ's own notices push owners to their *previous* contractor, so we win mostly where the previous contractor has gone out of business or been fired, or where no contractor is on record.

**Market size (bottom-up).** Assume 400 usable AHJs out of 2,000+ on TCE alone, an average of ~1,500 ITM properties each and 10–15% overdue at any time. That gives roughly 60–90k actionable properties per year. Buyers: ~250 sellable territories × $1,000/mo ≈ **$3M ARR ceiling for a done-for-you service**. Per-booked-visit pricing has a higher ceiling if conversion is good. This is a niche business, not a venture.

**Deliverable and pricing (recurring).** Territory-exclusive (AHJ cluster) *Overdue Outbound*: we refresh data quarterly, send monthly owner and property-manager sequences in the contractor's name, handle replies and book visits. **$750–1,500/mo per territory, or $150–250 per booked site visit.** The per-visit price sits within the $60–250 per-lead band, but for a qualified appointment.

**Automation pipeline.**
1. *Find (90% automated).* An agent builds the AHJ list from TCE/LIV/BuildingReports adoption pages, generates state-specific request letters and files them through portals or email.
2. *Follow-up (80%).* An agent tracks statutory deadlines, sends follow-ups, pays fees under a cap and parses PDFs and spreadsheets.
3. *Build (85%).* Normalize, geocode, join to assessor owner, enrich property manager and score (system type, months overdue, building size).
4. *Personalized outreach (90%).* Email and letter in the contractor's name: "Our records review shows the annual sprinkler ITM report for 123 Main St hasn't been filed with [City] since 03/2026. We can inspect this month." **Must not imitate an official notice** (FTC Act §5 deception).
5. *Replies (70%).* An agent qualifies and books into the contractor's calendar.
6. *Deliver and renew (80%).* Monthly report, quarterly data refresh.

Overall about **80% automatable**. **Human touchpoints:** the records-officer phone calls that unstick requests, denial appeals, contractor onboarding calls and the occasional angry owner.

**90-day GTM.**
- Days 0–30: file in 60 AHJs across 4 states with strong records laws and no firesafety exemption (e.g. WA, AZ, IL, CO; check each statute).
- Days 30–60: with the first 10 lists in hand, cold-email the 20–40 contractors registered in those AHJs (contractor registration lists are often public on AHJ pages) with a free sample of 25 overdue properties in their territory.
- Days 60–90: run 3 paid pilots at $500 for the first month.

**Unit economics (per territory).**
- Data: records fees about $0–150 per AHJ per refresh, plus about 2 human hours per AHJ per year.
- Enrichment: about $0.10–0.30 per property.
- Sending infrastructure: about $100/mo.
- Gross margin: **about 70–80% at $1,000/mo.** CAC is low because the buyer list is small and visible (AHJ contractor registries).

**Competitors (8+ searches, with prices).**

| Competitor | What it sells | Price | Overlap |
|---|---|---|---|
| The Compliance Engine (Brycer) | AHJ reporting. Sends notices to owners and the contractor of record. | Free to AHJ; $17–30/report to contractors | Holds the data; **could** launch a lead product (biggest strategic risk). No lead or data product today. |
| BuildingReports | Inspection documentation, 13M+ inspections, AHJ portal | Quote | Holds contractor-side data; "Facility Members own the data" ([BR](https://www.buildingreports.com/m/feed/)) |
| ServiceTrade "Trade Intelligence" | 48M assets and 17M deficiency events, used for upsell inside the contractor's own book | SaaS quote | Own-customer upsell, not prospecting ([ServiceTrade](https://servicetrade.com/solutions/trade-intelligence/)) |
| Inspect Point, Uptick, ZenFire, Ember, FireNspec | Contractor FSM software | ~$100s/mo | None on prospecting ([ServiceTrade list](https://servicetrade.com/resources/blog/best-fire-life-safety-software-2026/)) |
| Abstrakt, Calling Agency, Built Right Digital, Service Direct | Outbound appointment setting, SEO and PPC, pay-per-lead | $1,199–19,999/mo; PPL $60–250 | **Same buyer, same budget.** They prospect from generic building lists, not overdue status. |
| Shovels.ai, Gryd/BuildZoom | Permit data (new sprinkler and alarm permits) | API and seats | New installs, not ITM-overdue |
| FireProtectNearMe, FireCompliance Hub | Owner-side directories | Free | Inbound-only |

I found **no seller of AHJ overdue or deficiency lists** after searching for "overdue fire inspection leads", "fire protection leads data vendor", "compliance engine public records", startups and YC, G2 and Capterra lists, agency sites, and Shovels/BuildZoom.

**Legal and licensing.**
- (1) Records law. Florida exempts this data. Other states may invoke security exemptions. Request only minimal fields (no schematics, panel codes or device details).
- (2) No fire-protection license is needed to *market*. The contractor performs the work under its own license.
- (3) Pay-per-appointment is not fee-splitting in this trade (no licensing regime prohibits it, unlike insurance or law).
- (4) CAN-SPAM for email. Do not mimic government notices (FTC §5 and state UDAP).
- (5) Some AHJs may treat commercial reuse as hostile and refuse or slow-walk. A few states allow higher fees for commercial purpose (AZ, MA).

**Cold-email reply rate.**
- *Contractors (our buyers)*: construction-adjacent trades get a 0.6–5% generic reply rate, and trigger-based personalization roughly triples it ([Gangly](https://getgangly.com/blog/cold-email-reply-rate-benchmarks-by-industry), [Instantly](https://instantly.ai/cold-email-benchmark-report-2026)). Offering a free territory sample of named overdue buildings should be at the high end: **assume 5–10% reply and 1–3% pilot.**
- *Owners and property managers (their prospects)*: assume 2–5% reply on a precise compliance-status email.

**Kill risks.**
- (1) AHJs refuse, or release only after 3–6 months. Yield is under 25%.
- (2) Brycer launches its own contractor-lead feature or contractually limits AHJ disclosure.
- (3) Overdue properties are mostly tiny or vacant buildings, or the incumbent re-captures them through the AHJ notice.
- (4) Owners perceive the outreach as creepy or scammy, and AHJs complain.
- (5) Contractors are capacity-constrained (technician shortage) and don't want more leads ([ServiceTrade tech-retention survey](https://servicetrade.com/company-news/fire-protection-technicians-are-committed-to-the-work-but-operational-barriers-are-putting-retention-at-risk/)).

**Verifier-added problems (see section 4).**
- TCE notices already route owners to the incumbent.
- After TCE adoption the overdue pool is about 2–11%, not 10–15% (Buncombe County went from 12–15% to "2% or less").
- Texas AHJs will likely invoke Gov't Code 418.181, as Fort Worth did for hydrant inspection data ([Fort Worth Report](https://fortworthreport.org/2025/02/09/fort-worth-withholds-fire-hydrant-inspection-records-citing-texas-homeland-security-act/)).
- AZ (ARS 39-121.03), KY (KRS 61.874) and WA (RCW 42.56.070(8)) restrict commercial use or solicitation, or charge for it.
- AHJs earn a revenue share on report fees (IROL pays the AHJ $5–10 per report: [Greater Naples](https://greaternaplesfire.org/wp-content/uploads/2024/06/Third-Party-ITM-Reporting.pdf)), so they are the vendor's partners.
- Fire departments routinely warn businesses about fake inspection notices ([NV AG](https://ag.nv.gov/News/PR/2015/Nevada_Attorney_General_Warns_Consumers_of_Fire_Safety_Inspection_Scams)).

**Cheapest validation test ($500, 6 weeks).** File identical minimal-field requests with 40 TCE AHJs in 4 non-Florida states. **Kill if any of these hold:**
- fewer than 12 (30%) return a usable property-level list with status within 45 days;
- the median list has fewer than 50 overdue commercial properties;
- more than 30% of responses cite a security exemption or "no duty to create a record". In parallel, email 30 contractors in AHJs with returned data a free 25-property sample. **Kill if fewer than 3 agree to a paid pilot at $500.**

---

### Idea 2: "ITM Book Index": contractor-level recurring-inspection density as buy-side origination for fire/life-safety roll-ups

**Pitch.** The same records requests, aggregated by contractor of record, show how many annual ITM reports each private contractor files in each jurisdiction. That is a direct proxy for its **recurring inspection book**, the single biggest driver of its valuation. Annual inspection contracts trade at 2.0–3.5× annual recurring revenue and monitoring at 35–45× monthly RMR ([CT Acquisitions](https://ctacquisitions.com/fire-sprinkler-business-valuation-and-buyer-demand/), [CT guide](https://ctacquisitions.com/guides/private-equity-fire-life-safety-2026/)). We sell regional "add-on maps" (ranked private contractors by ITM report count, growth and system mix) to the ~13 PE consolidators and the strategic acquirers. Then we run done-for-you, owner-personalized outreach on the acquirer's behalf ("you file ~1,100 inspection reports a year in Maricopa County") and hand over warm owner conversations.

**Data and access.** Same as idea 1, but **it needs the contractor-of-record field**, which is the more sensitive field and the more likely to be withheld. Contractor registration lists (often public on AHJ pages) give the universe; report counts need the request.

**Buyer.** Corp-dev and M&A teams at Pye-Barker, Summit, AI Fire, Marmic, Sciens, APi Group and Fire & Life Safety America, plus 5–10 smaller PE platforms. DealSeam counts **13 PE-backed consolidators** ([DealSeam](https://dealseam.com/fire-life-safety-pe-rollup-tracker-2026)). More than 125 fire-protection deals closed in 2023 alone ([Fire & Safety Journal Americas](https://fireandsafetyjournalamericas.com/ma-quadruples-fare-safety)).

**Evidence money moves today.**
- DealSeam's model is "free for owners — we're paid by buyers" in exactly this niche ([DealSeam](https://dealseam.com/fire-life-safety-pe-rollup-tracker-2026)).
- Grata publishes a fire-safety PE playbook to sell its seats ([Grata](https://grata.com/resources)).
- Sell-side brokers (CT Acquisitions, Morgan Business Sales) are active.
- Pye-Barker closes 40–60 deals a year, so the add-on budget is real.

**Why they can't do it themselves or buy it for $50/mo.** Grata, Inven and SourceScrub estimate revenue from headcount and web signals. None, as far as I found, has *per-jurisdiction inspection report counts*. Consolidators could file records requests themselves, but their M&A teams are deal teams, not records-request factories. The real risk is that big platforms already know every target in their footprint (verify-1 found the same for HVAC).

**Timing.** Not event-driven. The value is ranking and sizing, which is evergreen. Outreach is timed when a contractor's report count *declines* (owner fatigue) or when its owner is older. Owner age is not in our data and would need other signals.

**Market size.** About 20–40 buyers × $3–8k/mo ≈ **$1–3M ARR ceiling.** Small and concentrated.

**Deliverable and pricing.** $15–25k one-off state or metro "add-on map", then a $3–6k/mo retainer for quarterly refresh plus done-for-you owner outreach (**flat fee, no success fee**).

**Automation.** Data pipeline 85% (shared with idea 1). Owner outreach 85%. **Humans:** buyer relationship calls, explaining the methodology, and the intro calls with owners (buyers want these themselves). Overall ~70%.

**90-day GTM.** Build a free sample for one metro using idea-1 data and send it to 15 corp-dev leads. Target 2 paid maps.

**Unit economics.** The marginal data cost is near zero once idea 1 exists. A map takes about 10–20 hours of human QA. Gross margin about 80%.

**Competitors (8+ searches).**

| Competitor | Price | Overlap |
|---|---|---|
| DealSeam | Buyer-paid (undisclosed) | **Direct**: buy-side fire-and-life-safety origination |
| CT Acquisitions, Morgan Business Sales, Security ProAdvisors | Sell-side success fees | Supply the same targets |
| Grata, Inven, SourceScrub | ~$10–50k/yr seats | Horizontal target lists; no ITM counts |
| In-house M&A teams (Pye-Barker 57 deals/yr) | — | May already map their regions |
| Valuation Research Corp. reports | Free | Market context only ([VRC](https://www.valuationresearch.com/wp-content/uploads/2025/03/Fire-Prevention.pdf)) |

**Legal.** The federal M&A broker exemption (15 U.S.C. 78o(b)(13)) covers private-company control deals, but **avoid transaction-based pay entirely** and charge flat fees for data and outreach. Contractor names and report counts are business information. If an AHJ provides the data, the obligations are the same as in idea 1.

**Cold-email reply rate.** PE and corp-dev buyers reply at 2–4% generically ([revenueflow](https://www.revenueflow.com/blog/investment-cold-email-benchmarks), [moderninbound](https://moderninbound.com/blog/cold-email-for-private-equity)). A free proprietary map of their own region should do better on a list of only 20–40 people, but the denominator is tiny. Owner outreach to fire-contractor owners: PE-fatigued trade owners (verify-1 noted hostility in HVAC), so assume 2–4%.

**Kill risks.**
- (1) The contractor field is withheld.
- (2) Buyers say "we already know them all".
- (3) Only 13–40 buyers, so two "no"s end it.
- (4) Report count correlates poorly with revenue (big-ticket installs, monitoring RMR not captured).

**Cheapest validation test.** Reuse idea 1's 40 requests and include the contractor field. Build one metro map. Show it to 10 corp-dev contacts. **Kill if fewer than 3 take a call, or if 0 pay ≥$5k within 60 days, or if a buyer shows they already have equivalent data.**

---

### Idea 3: "Collections-contract map": FOIA'd expiration and rate data for contingency-fee municipal contracts (EMS billing, delinquent-tax and utility collections, parking citation processing)

**Pitch.** Many municipal services are paid as a *percentage of collections*: EMS billing at ~4.5–6.75% of net collections ([CitizenPortal Laramie](https://citizenportal.ai/articles/6212908/Wyoming/Albany-County/Laramie-City/Laramie-City-Council/Council-approves-three-year-EMS-billing-contract-at-45-of-net-collections)) and Texas delinquent-tax at up to 15–20% ([Dallas County](https://dallascounty.civicweb.net/document/549136/Delinquent%20Tax%20Collection%20Contract%20with%20Linebar.pdf?handle=CAC7229FCDE042A7A2921D7BBF1A5B95), [Marlin](https://citizenportal.ai/articles/9132574/texas/falls-county/marlin/marlin-approves-15-contingent-fee-contract-with-perdue-for-delinquent-tax-collection)). My hypothesis was that these contracts are *under-represented in PO-based spend datasets* because there may be no PO. Agents would FOIA every EMS agency's billing contract (term, rate, renewal options, collection performance) and sell an expiration calendar plus done-for-you pre-RFP outreach to the ~100–300 EMS billing vendors.

**Evidence money moves.** The US EMS billing services market is about $2.1B ([Grand View](https://www.grandviewresearch.com/industry-analysis/us-ems-billing-services-market)). RFPs run constantly (Manheim Twp, Compton, Dougherty Co., Bedford, Nash Co. in 2026: [Manheim](https://www.manheimtownship.org/DocumentCenter/View/10321/MTFR-RFP-for-Billing-2026), [Compton](https://www.comptoncity.org/Home/Components/RFP/RFP/315/)). Terms are 3–5 years ([San Antonio PSA](https://webapp1.sanantonio.gov/RFPFiles/RFP_3645_201808310305550.pdf)).

**Why it's weak.**
- The "no PO" hypothesis is **unverified**. GovSpend has 96M contracts and does custom pulls.
- CitizenPortal.ai already surfaces council approvals of these contracts free (3 of my first 10 results were CitizenPortal articles).
- Civic IQ's done-for-you **Pipeline-as-a-Service at $2,000/mo** is the brothers' model in this exact market ([Civic IQ](https://civiciq.com/pursuit-alternatives)).
- RFP alerts are commoditized (InstantMarkets, RFPMart, BidNet).
- Delinquent-tax collection is a law-firm market, where solicitation and UPL questions arise.

**Trigger timing.** Good: contract expiry is known 6–18 months ahead. That is the one strength.

**Pricing.** $300–800/mo per vendor, or $2–5k per niche annual map.

**Market.** ~200 vendors × $500/mo ≈ $1.2M ARR ceiling, minus competition.

**Automation.** 85% (records requests plus extraction). **Human:** vendor sales calls.

**Competitors (8+ searches).** GovSpend ($8.5–24.75k/yr, median $11.6k: [Vendr](https://www.vendr.com/marketplace/gov-spend)), Starbridge (enterprise, demo-only), Civic IQ (from $2k/mo PaaS), Pursuit ($22M raised), HigherGov FOIA ($50/request), CitizenPortal (free–$15/mo), InstantMarkets, RFPMart, Pintel, GovTribe.

**Legal.** Records law only. Avoid the delinquent-tax (law firm) sub-niche.

**Reply rate.** Vendor sales leaders: 3–5%.

**Kill risks.** GovSpend or Starbridge already holds the contracts. Vendors already track their niche manually (it is small).

**Cheapest test.** Pull 30 EMS billing contracts from GovSpend's free trial or demo *and* from CitizenPortal. **Kill if ≥70% are already findable there with term dates.**

---

### Idea 4: "Linen and waste co-op": invoice give-to-get benchmark plus AI contingency renegotiation for SMB recurring-service contracts

**Pitch.** SMBs upload their Cintas, UniFirst or Vestis (uniform/linen) or waste-hauler invoices and contract (photos are fine). Agents extract line items, compare them to a growing benchmark of what similar businesses pay per garment, mat, towel or pickup, flag contract breaches (minimum charges, unexplained fee lines, price increases beyond contract terms) and draft and send the renegotiation or cancellation correspondence. We are paid **a share of savings**. The benchmark is give-to-get and becomes proprietary as invoices accumulate. The brothers' existing SMB website customers are the seed supply, so this is an **upsell to existing customers**, the pattern verifiers said survives.

**Evidence money moves.**
- Uniform-audit consultancies charge **25–50% of savings** on contingency ([invoicedataextraction](https://invoicedataextraction.com/blog/audit-cintas-invoice-overcharges-price-increases)).
- Cost Analysts/P3 and UniformBright advertise "proprietary vendor pricing databases" ([Cost Analysts](https://www.costanalysts.com/services/uniform-linen-services-auditing/), [UniformBright](https://uniformbright.com/)).
- Waste-bill audits are also contingency ([National Utilities Refund](https://nationalutilitiesrefund.com/audits/waste-trash-bill-audits/)), claiming 10–25% overpayment ([wastebillaudit](https://www.wastebillaudit.com/)).
- Cintas paid **$45M** to settle a contract-breach class action by public agencies ([Cintas 10-K](https://www.sec.gov/Archives/edgar/data/723254/000072325425000017/ctas-20250531.htm)). The US uniform rental market is about $9.5B, and 78% of customers have fewer than 50 employees ([uniformmarket](https://www.uniformmarket.com/statistics/uniform-rental-services-market-statistics)).

**Why not DIY or $50/mo?** SMB owners don't know benchmark prices or how to invoke contract clauses. Consultants ignore small accounts because a $4k/yr account yields only a ~$300–600 fee. AI collapses that cost, so the small-account tail is the gap.

**Timing.** Not trigger-based. The pain is chronic, and an auto-renewal anniversary is the trigger, found in the contract itself.

**Market.** About 780k SMB uniform customers. If the brothers' base is ~2–5k SMBs and ~25% rent uniforms, mats or towels, that is 500–1,250 accounts. At a ~$400 average fee and 30% conversion that is **~$60–150k one-off**. Selling beyond the base needs cold outreach (SMB reply 1–3%).

**Pricing.** 35% of first-year savings. An optional $29/mo "watch" plan for ongoing invoice monitoring (recurring).

**Automation.** Invoice OCR and benchmarking 90%. Drafting letters 80%. **Humans:** vendor phone negotiations (rental reps push back), dispute escalation. Overall ~65%.

**90-day GTM.** Offer a free invoice check to the existing customer base. Target 50 uploads.

**Unit economics.** About $400 per win at roughly 2 hours of human negotiation, so about $150/hr. Fine as an upsell, not a company.

**Competitors.** UniformBright (consulting, contingency or flat), Cost Analysts/P3 (contingency 25–50%), The Laundry Guy, Fine Tune (contingency procurement, [Fine Tune](https://www.finetuneus.com/spend-categories/uniform-rental/)), Expense Reduction Analysts (franchise, 50/50 split model), AuditMyWaste (free audit), WasteBillAudit, Copia Resources, generic AI invoice auditors (AuditGuard, Serina).

**Legal.**
- No licence is needed to negotiate on a client's behalf.
- **Do not give legal advice or threaten litigation**. Drafting "your contract is void" letters edges toward UPL. Use "requesting a review under section X".
- Virginia's amended auto-renewal statute now lets small businesses recover as consumers ([Benesch](https://www.beneschlaw.com/insight/the-coming-state-law-litigation-wave-of-2026-27-subscription-trap-class-actions/)). That is useful leverage, but refer clients to counsel.

**Reply rate.** For existing customers, a free audit offer should draw 5–15% engagement. Cold SMB outreach gets 1–3%.

**Kill risks.** Low upload rates (friction). Rental companies refuse renegotiation of small accounts. Savings too small.

**Cheapest test.** Email 300 existing customers. **Kill if fewer than 15 upload invoices or fewer than 5 have ≥$500 in identifiable annual savings.**

---

### Idea 5: "Shop Panel": AI-agent competitive mystery-shop panels for PE platform diligence and franchisor benchmarking

**Pitch.** For a PE platform evaluating a metro or an add-on target, an AI agent places web-form and SMS inquiries (no voice, to sidestep TCPA and CIPA) with the target and 20 local competitors. It measures response time, follow-up cadence, quoted diagnostic or service-call fees and booking friction, and delivers a "commercial diligence shop pack". The same approach serves franchisors benchmarking franchisees against local independents.

**Evidence money moves.** Phone and web shops sell for $40+ each ([Grace Hill](https://gracehill.com/pricing/mystery-shopping/), [Marketstat](https://marketstat.com/pricing.html)). Ellis shops 8,000 apartment communities a month ([Siro](https://www.siro.ai/insights/mystery-shopping-leasing-performance)). PE commercial diligence uses "secret shopper calls to competitors" ([Alexander Group](https://www.alexandergroup.com/insights/commercial-diligence-5-tips-to-assess-market-performance/)). Speed-to-lead studies show 40–44% of firms never reply ([FranFunnel](https://www.franfunnel.com/speed-to-lead), [ConXPros](https://conxpros.com/wp-content/uploads/2019/12/Speed2Lead-case-study.pdf)).

**Why weak.**
- Speed-to-lead audits are given away free as marketing by response-tool vendors (FranFunnel, Blazeo).
- Firms already measure 100% of their *own* calls (Invoca, CallRail, ServiceTitan).
- AI-native shopping already exists in the biggest vertical (Rev Leasing, EliseAI, Funnel).
- The diligence niche is episodic (not recurring), and the CDD firms that would buy it are few.
- Fake inquiries waste small businesses' time. That is ethically grey at scale and invites "spam lead" blowback.

**Legal.**
- TCPA: an AI voice is an "artificial voice", and calls to wireless numbers need consent ([FCC](https://docs.fcc.gov/public/attachments/DOC-400393A1.pdf), [WSGR](https://www.wsgr.com/en/insights/fcc-rules-ai-generated-voices-are-artificial-under-the-tcpa.html)).
- CIPA: two-party consent recording carries $5,000 per violation ([Shouse](https://www.shouselaw.com/ca/defense/laws/california-invasion-of-privacy-act/)).
- Hence web-form and SMS only. Inbound SMS replies from the business are fine; avoid outbound marketing texts.

**Market.** Small: maybe 50–150 diligence packs a year at $2–5k. Recurring only with franchisors.

**Automation.** 90%.

**Competitors.** Grace Hill ($40+), Marketstat ($23+ base), Ellis, Market Force, Intouch, BARE, Rev Leasing (AI), EliseAI, FireCoach (free AI sales-call shopper), FranFunnel (free audits).

**Reply rate.** PE operating partners and CDD firms: 2–4%.

**Kill risk.** Nobody pays separately for this. It gets bundled into CDD at a few hundred dollars.

**Cheapest test.** Run one free pack (HVAC in one metro) and pitch 20 CDD firms and PE operating partners. **Kill if 0 of 20 pay ≥$2k within 45 days.**

---

### Idea 6: "Due-list feeds" for other mandated recurring trades: backflow testing, FOG/grease-trap pumping, kitchen hood suppression

**Pitch.** Same records-request engine as idea 1, pointed at water utilities (backflow devices due or overdue, held in SwiftComply, BSI Online, Tokay or TCE) and sewer FOG programs (restaurants overdue on pumping). Done-for-you outreach for backflow testers, grease haulers and hood companies.

**Evidence.** These are mandatory annual or monthly-to-quarterly services ([WaterOne](https://www.waterone.org/183/Commercial-Backflow-Requirements-Cross-C), [Stuart FL FOG](https://www.stuartfl.gov/304/Grease-Management-Program-FOG)).

**Why weaker than idea 1.**
- Tickets are small (a backflow test costs about $75–200).
- Incumbency is strong: the tester of record is the default ([FireSprinklerMarketing](https://firesprinklermarketing.com/how-to-grow-a-backflow-testing-business/)).
- Utilities already send due notices *with approved-tester lists* (same source).
- Directories (FindBackflowTesters, BackflowPath) already capture owner demand ([BackflowPath](https://backflowpath.com/backflow-reporting-portals/tokay)).

**Market.** Thousands of small testers with low WTP: maybe $99–299/mo.

**Automation.** 85%.

**Legal.** Records law. Some utilities may treat customer account data as confidential.

**Reply rate.** Owner-operator trades: 1–3%.

**Use.** As a cheap **extension** of idea 1's pipeline (TCE also holds backflow), not as a standalone business.

**Cheapest test.** Add a backflow-overdue field to 20 of idea 1's requests. **Kill as a standalone if fewer than 5 testers out of 50 contacted pay $99.**

---

## 3. Rejected ideas

| Idea | Family | Why rejected (with evidence) |
|---|---|---|
| General SLED contract-expiration FOIA database for niche vendors (uniforms, waste hauling, IT, police software) | a | GovSpend (96M contracts, custom pulls included), Starbridge (FOIA automation, $52M raised), Civic IQ ($2k/mo done-for-you), Pursuit, HigherGov ($50 per FOIA) and Pintel. An open-source "Contract Expiration Finder" exists for police software. Commoditized. |
| School-district vendor contracts | a | Starbridge, DistrictIQ and Burbio cover K-12 ([Starbridge](https://starbridge.ai/blog/districtiq-alternatives)) |
| Police and fire equipment inventories (turnout gear, SCBA replacement cycles) | a | Sold through territory-exclusive dealers who already know their departments. AFG grant data is public. |
| Alarm-permit and false-alarm lists for alarm dealers | a | Alarm registration data is statutorily confidential in many states, e.g. NC, FL and Providence RI ([UNC SOG](https://canons.sog.unc.edu/2015/10/two-new-exceptions-to-the-public-records-law-protect-citizen-information/), [FL AG](https://www.myfloridalegal.com/ag-opinions/disclosure-of-name-address-of-security-system-owner), [Providence](https://ppd.providenceri.gov/alarm-system-registration/)) |
| Utility account data | a | Customer-confidential, not obtainable |
| Pre-opening restaurant leads from plan reviews | a | RestaurantData.com, Restaurant Activity Report (Starfleet), RestaurantPOSLeads and Restaurant Pipeline already sell pre-opening leads from DBAs, liquor and construction filings ([RestaurantData](https://restaurantdata.com/new-and-pre-opening-restaurant-leads/)) |
| Dental supply price co-op | b | ZenOne $49/mo, Alara free, Method ([Arini](https://www.arini.ai/blog/dental-supply-procurement-software-comparison)) |
| Small-space commercial lease comps | b | CompStak's give-to-get exchange, 40k+ members ([CompStak](https://compstak.com/exchange)) |
| HVAC equipment price benchmark | b | Distributor pricing is account-specific, and contractors won't share invoices with a stranger. HARDI and RSMeans publish benchmarks. Contractors mark up by 20–50% regardless ([ACDirect](https://www.acdirect.com/blog/why-hvac-contractors-double-equipment-price/)). Cold-start with no seed supply. |
| Restaurant food-cost price co-op | b | GPOs, MarginEdge, xtraCHEF and many invoice tools; price gaps are well publicized ([Genius Food Purchasing](https://geniusfoodpurchasing.com/restaurant-supplier-comparison/)) |
| Merchant-processing statement benchmark | b | Swipesum, Rombis, PayBlox and others give it away free ([Swipesum](https://www.swipesum.com/merchant-statement-audit)) |
| SMB insurance-premium benchmark co-op | b | Monetization runs through producer licensing and referral-fee limits (round-1 pattern 4). Cold-start. |
| Website-quality and "actively investing" index for lenders and insurers | c | Middesk `web_presence_quality`, Carpe Data (45M profiles, Hartford), Enigma (card-transaction revenue), PredictLeads ($40/mo+) |
| Selling reply-derived owner intent (retiring, selling) | c | Destroys trust with the brothers' own prospects, raises privacy issues, and verify-1 found M&A origination crowded |
| Multifamily AI mystery shopping | d | Rev Leasing and EliseAI already sell AI shops. Funnel replaces shops with 100% call scoring ([Funnel](https://funnelleasing.com/apartment-secret-shop-for-multifamily-leasing/)). |
| Insurance quote-shopping by AI | d | Requires misrepresenting risk details to carriers, and producer licensing applies |
| Funeral price panel by phone (FTC Funeral Rule requires phone price disclosure) | d | Weak WTP. Parting.com and Funeralocity exist. AI-voice and CIPA risk. |
| Child-care market-rate surveys for states | d | Surveys already reach 70%+ response, e.g. WI 71% and SD 73% ([SD report](https://dss.sd.gov/docs/childcare/state_plan/2025-2027/Market_Rate_Full_Report.pdf)). Only 56 buyers, on slow RFP cycles. |
| Public-meeting and hearing transcription | e | GovSpend 2.3M transcripts, Hamlet, CitizenPortal ($15/mo), Starbridge, Curate, Pursuit; verify-3 killed agenda-to-pipeline |
| Court hearing audio and earnings or industry webinars | e | Court audio is rarely public, and Trellis and UniCourt cover dockets. AlphaSense, Tegus and Quartr cover earnings. Low WTP for webinars. |

---

## 4. Self-verification results

Two general-purpose subagents attacked the draft in parallel, with about 30–35 searches each. One took ideas 1 and 6; the other took ideas 2–5. Where they were right, I accepted their findings and lowered the scores.

### Verifier A: ideas 1 and 6

| Draft claim | Finding | Verdict |
|---|---|---|
| TCE is used by 2,000+ jurisdictions | Confirmed: "trusted by over 2,000 AHJs" ([TCE](https://www.thecomplianceengine.com/)). Also LIV covers 350+ AHJs and 4,000+ contractors ([LIV](https://livsafe.com/who-we-serve/authorities-having-jurisdiction)), and IROL is a third vendor. | True; more vendors to request from |
| Contractor fee is $17–30 per report | The range is about $10–37: Redmond $37, Charleston $15→30, Raleigh $10–12 ([Redmond](https://www.redmond.gov/FAQ.aspx?QID=598), [Charleston](https://www.charleston-sc.gov/2586/Compliance-Reporting)). IROL charges $19.99 and pays the AHJ a **$5–10 per report revenue share** ([Greater Naples](https://greaternaplesfire.org/wp-content/uploads/2024/06/Third-Party-ITM-Reporting.pdf)). | Partly true. AHJs are the vendor's paid partners, which makes them less likely to help a third party. |
| Brycer has no lead product | **False in spirit.** In May 2026 Brycer started marketing TCE as "a consistent, trackable source of inbound demand for service providers", with satellite "Virtual Walkthroughs" ([PR](https://www.digitaljournal.com/pr/news/prodigy-press-wire/compliance-engine-expands-access-compliance-driven-1675648375.html)). | **Corrected in the text.** This is the biggest strategic risk, and it is already happening. |
| Owners being chased by the AHJ are open to a new vendor | Every TCE renewal, overdue and deficiency notice prints the **contractor of record** with phone and email. Brycer staff also make follow-up calls ([Sedalia plan](https://www.sedalia.com/wp-content/uploads/compliance-implementation-plan.pdf)). | Weakens the idea. The system is designed so the incumbent gets the work back. |
| 10–15% of properties are overdue | After TCE adoption it falls to about 2–11%; Buncombe County went from 12–15% to "2% or less" ([TCE](https://www.thecomplianceengine.com/fire)) | **Overstated 2–5×.** What remains is the chronic non-payer tail. |
| Obtainability is unknown | Still no public release example. **Texas precedent against us:** Fort Worth, a TCE city, withheld its hydrant inspection history under Gov't Code 418.181 ([Fort Worth Report](https://fortworthreport.org/2025/02/09/fort-worth-withholds-fire-hydrant-inspection-records-citing-texas-homeland-security-act/)). Agencies have no duty to create an "overdue" query, so many will offer PDFs instead. | Risk is higher than the draft assumed |
| Legal | AZ ARS 39-121.03 requires a commercial-purpose statement and names "solicitation". KY KRS 61.874 charges commercial fees. WA RCW 42.56.070(8) bars releasing lists of individuals (sole-proprietor owners) for commercial use. Fire departments and the NV AG warn about fake inspection notices ([NV AG](https://ag.nv.gov/News/PR/2015/Nevada_Attorney_General_Warns_Consumers_of_Fire_Safety_Inspection_Scams)). | New friction, added to the text |
| Lead price $60–250 and Built Right $1,199–19,999 | These come only from vendor marketing. Built Right's prices were not visible on the fetched page. | Weak evidence of willingness to pay |
| New competitors | FireProtectNearMe (3,100 companies) and FireInspectionDirectory (3,300) target overdue owners. DOBGuard monitors FDNY violations. For backflow: BackflowRates **$39.99/mo**, FindBackflowTesters and BackflowPath. Utility notices list the last tester and attach certified-tester lists ([Sugar Land](https://www.sugarlandtx.gov/627/Backflow-Testing-Program), [Tampa](https://www.tampa.gov/water/water-quality/backflow-testing)). | No direct seller of AHJ overdue lists exists, but Brycer is moving into that gap |

**Verifier A's scores:** idea 1 **4/10**, idea 6 **2/10**. I accept both.

### Verifier B: ideas 2–5

| Draft claim | Finding | Verdict |
|---|---|---|
| DealSeam is paid by buyers; there are 13 consolidators | True. DealSeam tracks 18 consolidators: 13 PE-backed and 5 strategic or family-owned ([DealSeam](https://dealseam.com/fire-life-safety-pe-rollup-tracker-2026)) | Partly true |
| Buyers lack the data | Pye-Barker has a Chief BD Officer for M&A plus 2 EVPs and an SVP for BD/M&A ([Equilar](https://people.equilar.com/bio/org/pye-barker-fire/6025157)). **Grata published a Fire Safety PE Playbook on 2026-08-27 covering 118,000 private targets**, segmented by inspection and testing ([GlobeNewswire](https://www.globenewswire.com/news-release/2026/08/27/3352141/0/en/fire-safety-sector-draws-investor-interest-as-m-a-activity-nearly-quadruples-since-2017-grata-finds.html)). **Shovels** sells contractor market share by trade, including FIRE_SPRINKLER permits, for deal sourcing at $599–999/mo ([Shovels](https://www.shovels.ai/data/contractors), [pricing](https://www.shovels.ai/pricing)). | False; idea 2 is crowded |
| A report count approximates the recurring book | An inspection costs $150–750 for a small building and $4–10k+ for a large one, a 20–50× spread. Quarterly and semi-annual filings inflate the counts ([TFP](https://www.tfp1.com/blog/fire-sprinkler-inspection-cost/)). | Weak proxy without weighting by square footage |
| Idea 3 has a "no PO" gap | **Starbridge Public Spend Intelligence already returns "full, unredacted competitor contracts, including pricing, opt-out clauses, and expiration dates, sourced through automated public records requests at national scale"** ([Starbridge](https://starbridge.ai/features/public-spend-intelligence)) | **Idea 3 killed** |
| Civic IQ $2k/mo PaaS | True. It uses human SDRs, and annual plans run $12–48k ([Civic IQ](https://civiciq.com/blog/starbridge-vs-civic-iq)). | True |
| Idea 4 competition and leverage | New competitors: SaveOnServices ($27 DIY guide, $247 audit), AuditMyWaste (free to the client, paid by the vendor, $13.7k average recovery), ConsultingAce, ProfitLine and Waste Consultants Inc. Cintas's standard agreement is a **60-month auto-renewal; early termination costs 50% of the average weekly invoice × the remaining weeks** ([ECWA copy](https://www.ecwa.org/files/pdf/item_4_standard_rental_agreement_with_cintas_corp_.pdf)). | Crowded, and small accounts have little leverage |
| $45M Cintas settlement; VA auto-renewal law | True. Virginia HB1022 took effect 2026-07-01 and covers firms with fewer than 250 employees or under $10M revenue. | True |
| Idea 5 buyers | CDD firms (Woozle, Baker Tilly, SATOV) run secret shops themselves, so they are competitors rather than buyers ([Woozle](https://insights.woozleresearch.com/blog/commercial-due-diligence-primary-research-for-private-equity-a-2026-practitioners-guide/)). Nevada requires a PI licence for mystery shoppers ([legalmatter](https://legalmatterblog.com/2013/06/26/demystifying-the-mystery-shopper/)). Maine's chatbot disclosure law adds optics risk. | Weakened further |

**Verifier B's scores:** idea 2 **3/10**, idea 3 **1/10**, idea 4 **3/10** as an upsell (2/10 standalone), idea 5 **2/10**. I accept all of them.

### What I got wrong

1. **I said Brycer does not sell leads.** That was true only of its product list. Its 2026 marketing explicitly targets contractor "inbound demand". This is round-1 failure pattern 1 again: the data holder is the competitor.
2. **I assumed an overdue pool that is 2–5× too large.** TCE itself shrinks it.
3. **I missed that TCE notices name the incumbent.** That undercuts the "these owners have no vendor" premise.
4. **For idea 2, I missed Grata's August 2026 fire-safety coverage and Shovels' contractor market-share product.**
5. **For idea 3, I treated "no PO" as a gap.** Starbridge FOIAs the contracts directly.

---

## 5. Ranked shortlist (post-verification)

Scores are 1–10; competition 10 = blue ocean.

| Rank | Idea | Market | WTP | Data access | Automation | Competition | Recurring | Time to $ | **Overall** | Confidence |
|---|---|---|---|---|---|---|---|---|---|---|
| 1 | **Overdue Feed** (fire ITM overdue lists via records requests + done-for-you outreach) | 4 | 5 | 3 | 7 | 4 | 7 | 3 | **4.0** | Low–medium |
| 2 | **ITM Book Index** (contractor inspection density → roll-up origination) | 3 | 5 | 3 | 6 | 3 | 5 | 3 | **3.0** | Medium |
| 3 | **Linen and waste co-op** (upsell to existing SMB customers only) | 4 | 4 | 6 | 6 | 2 | 3 | 5 | **3.0** | Medium |
| 4 | **Due-list feeds** for backflow, FOG and hood (as a field added to idea 1's requests) | 3 | 2 | 3 | 8 | 3 | 5 | 3 | **2.0** | Medium |
| 5 | **Shop Panel** (AI web-form mystery shops for diligence) | 2 | 3 | 8 | 9 | 2 | 2 | 4 | **2.0** | Medium-high |
| 6 | **Collections-contract map** (EMS billing and similar) | 2 | 3 | 5 | 8 | 1 | 5 | 4 | **1.0** | High |

**No idea reaches 7, or even 5.** Every one fails on either willingness-to-pay evidence or competition, which a 7+ requires.

**Bottom line for the brothers.**
- **"Proprietary data" is mostly an illusion when a vendor already holds the records first-hand.** Brycer holds the fire ITM data; GovSpend and Starbridge hold contracts; Carpe and Middesk hold SMB web signals. Each is already turning it into a product.
- **Agents filing FOIAs at scale is no longer a moat either:** Starbridge, GovSpend and HigherGov already do it.
- **The only thing worth spending money on is idea 1's $500, 40-request records test.** Run it with idea 2's contractor field and idea 6's backflow field bundled in, because one cheap experiment answers three questions. Apply the kill rules in section 2. If yields come back above 30% with no security-exemption pushback, revisit ideas 1 and 2 at about 5/10. Otherwise close this lane.
- **Idea 4 is a reasonable no-cost upsell email to the existing website customer base**, but it is not a business.
