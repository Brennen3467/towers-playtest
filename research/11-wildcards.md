# Lane 11: Wildcards (obscure data sources, non-obvious buyers)

*Research date: 2026-10-01. This is research only: no accounts were created, nothing was sent or bought, and nobody was contacted.*
*Legend: **[EST]** = my estimate or inference. **(secondary)** = taken from a third-party comparison or SEO page rather than the vendor or the government source; treat as indicative.*
*Method: about 195 web searches plus about 40 fetches of primary pages, run across five parallel research threads. That is slightly over the ~180 search budget. Several primary sites blocked automated fetches: FAA registry, serff.com, LBNL emp, gridstatus pricing, BoardDocs, Reddit, the FedEx service guide. Where that happened I relied on search snippets or secondary pages and flag it.*

---

## TL;DR (read this first)

1. **"Public filing → lead list" is a red ocean almost everywhere in 2026.**
   - Solo developers sell Apify actors at roughly $1–$50 per 1,000 records for each of these feeds: Legistar agendas, liquor licenses, FMCSA new authorities, UCC filings, FAA aircraft owners, interconnection queues, and the WI/MN/CA franchise registries. Links are in each section.
   - One person has already used Claude agents to build a 142,579-operator franchisee database from FDD Item 20. It sells for **$50/mo** ([Blueprint GTM](https://edge.blueprintgtm.com/p/142579-franchise-operators-built)).
   - **Raw public data can no longer be the product.**
2. **What is left is service work, sold to small buyers that enterprise tools ignore.** The pattern is: an agent interprets *unstructured* public documents (agendas, packets, assessor records), works out what a specific small buyer would gain, then does the outreach and the work. That is the same shape as the brothers' website business, so their real moat is the outreach and fulfilment machine, not the data.
3. **None of my ideas is truly blue-ocean *and* backed by proven willingness to pay.** I ranked everything below honestly. The top three:
   - **(A) Trade-specific "agenda-to-pipeline" feeds** for small public-sector vendors.
   - **(B) Property-tax appeal evidence packets** for small commercial owners, delivered through licensed partners.
   - **(C) Done-for-you aircraft-owner outreach** for avionics and maintenance shops.
   - All three are purple-ocean at best, and my confidence in all three is medium-low.
4. **Lowest-risk adjacent move:** use the free datasets researched here (990s, vet boards, church data, new franchisor registrations) as *vertical lead sources for the existing website business*. That needs no new product and no new legal exposure. See §3, "Adjacent quick wins".

---

## 1. Lane overview: landscape, incumbents, gaps

### 1.1 Where the data is, and who already monetizes it

| Data family | Access | Who already monetizes it | Crowding |
|---|---|---|---|
| Local-government agendas and minutes (90,837 governments in the [2022 Census of Governments](https://www.census.gov/library/publications/2026/econ/govtorg2225.html); 91,438 in the 2025 update) | Legistar has a public OData API ([docs](https://webapi.legistar.com/Home/Examples); an unauthenticated call to `webapi.legistar.com/v1/seattle/events` returned JSON on 2026-10-01). CivicPlus AgendaCenter uses predictable URLs plus RSS. BoardDocs sits behind CloudFront bot protection. | Starbridge ($52M raised, [blog](https://starbridge.ai/blog/starbridge-raises-42m-series-a-to-make-it-easy-for-any-business-to-sell-to-government-education)); Pursuit ($22M Series A, [TAMradar](https://www.tamradar.com/funding-rounds/pursuit-series-a-22m)); Curate/FiscalNote (12k+ municipalities, ~400k docs/week, [FiscalNote](https://fiscalnote.com/newsroom/curate-announces-expansion-of-state-local-coverage)); Hamlet (~$10M, [TechCrunch](https://techcrunch.com/2025/12/05/new-streaming-channel-launches-to-give-viewers-a-peek-into-city-council-meetings/)); Apify "Legistar Agenda Radar" at ~$1/1k ([Apify](https://apify.com/opalescent_game/legistar-agenda-radar)) | Horizontal SLED intel is **crowded and VC-funded**. Trade-specific SMB feeds are **thin**. |
| Bid and RFP data | State and local portals | GovWin ~$13k–$119k/yr ([Civic IQ](https://civiciq.com/blog/govwin-iq-pricing-2026), secondary); GovSpend median ~$11.6k ([BidSparq](https://bidsparq.com/alternatives/starbridge), secondary); Bid Banana $49.99/mo ([pricing](https://thebidlab.com/pricing/)); BidPrime, GovTribe, HigherGov | **Red** |
| Building permits | ~20k jurisdictions | Shovels $599–$999/mo ([ColdIQ](https://coldiq.com/tools/shovels)); Construction Monitor ~$62–$1,250 per market per month ([PermitLedger](https://permitledger.com/compare/construction-monitor), secondary); CurateBUILD (private construction from minutes, [Curate](https://www.curatesolutions.com/)) | **Red** |
| Energy (interconnection queues, EIA-860M, PUC dockets) | Free (LBNL, ISOs, EIA) | Paces ($11M A, [Paces](https://www.paces.com/news/paces-raises-11-million-to-accelerate-clean-energy-development)); Halcyon ($21M A, [BusinessWire](https://www.businesswire.com/news/home/20260316032633/en/Halcyon-Raises-$21-Million-Series-A-To-Bring-AI-Powered-Intelligence-to-the-Energy-Industry)); HData + Insight Engine; Heatmap Pro; Transect; LandGate | **Red** for developers. **Open but no willingness to pay** for local trades and landowners. |
| FDDs (franchise disclosure) | Free WI DFI, MN CARDS, CA DFPI, IN portals | FRANdata (FUND score used by lenders making >60% of SBA franchise loans, [FRANdata](https://frandata.com/fund-franchise-credit-score/)); GetFDD $199/mo ([GetFDD](https://getfdd.com/)); Frandera $750/mo ([Frandera](https://frandera.com/for-vendors)); Blueprint $50/mo; ~8 AI FDD analyzers | **Red** |
| Insurance rate filings (SERFF) | Free per state, **but the terms prohibit automated download** ([SFA help PDF](https://filingaccess.serff.com/sfa/static-web/OnlineHelp.pdf)) | S&P RateFilings; Akur8 (bought Matrisk, Jan 2026, [Akur8](https://www.akur8.com/pricing/discover)); Insuraviews; Zesty; Quadrant | **Red, and the terms block it** |
| FAA aircraft registry | Free daily download | JETNET (which now also owns ADS-B Exchange, [JETNET](https://www.jetnet.com/products/adsb-exchange)); AMSTAT; NextMark lists; Apify at $10/1k ([Apify](https://apify.com/scrapemint/aircraft-owner-leads)) | Data is **commodity**. A service layer is thin. |
| USDA payments | FSA payment files are public (names allowed under §1619) | DTN / Farm Market iD; EWG and OpenSubsidies (free) | **Red** |
| IRS 990 | Free (IRS TEOS XML, ProPublica API) | Instrumentl ($55M raise, 4,500+ customers, [BusinessWire](https://www.businesswire.com/news/home/20250423312598/en/Instrumentl-Raises-$55M-from-Summit-Partners-to-Accelerate-Their-AI-Grant-Fundraising-Platform)); Candid; Granted AI $18–29/mo | **Red** |
| Customs and trade | Bill-of-lading data (ImportGenius $149–$449/mo, [pricing](https://www.importgenius.com/pricing)) | Drawback brokers; IEEPA refund shops | **Moderate** |
| Assessor and property-tax data | County by county, often open (e.g. Cook County BOR history, 6.9M rows, [Socrata](https://datacatalog.cookcountyil.gov/Property-Taxation/Board-of-Review-Appeal-Decision-History/7pny-nedm)) | Ownwell ($50M Series B, Feb 2026; "10k+ businesses" on its commercial page, [Ownwell](https://www.ownwell.com/commercial)); O'Connor; Ryan; local attorneys | **Moderate**; the long tail of small parcels is underserved |

### 1.2 Structural gaps found

1. **The unstructured long tail.**
   - The big agenda platforms (Granicus ~6,500–7,000 agencies, [GlobeNewswire](https://www.globenewswire.com/news-release/2025/01/27/3015791/0/en/Granicus-2025-Semiannual-Update-features-AI-innovation-and-new-solutions-for-modernizing-the-government-experience.html); CivicPlus; BoardDocs ~5,000) cover **an estimated <25k of ~91k bodies [EST]**.
   - The **39,555 special districts** (water, sewer, fire, transit) are mostly scattered PDFs.
   - This is precisely the work LLM agents do cheaply and humans or regex scrapers do badly.
2. **Small vendors are priced out.** Starbridge and Pursuit are demo-only enterprise sales, and GovSpend runs about $8k–$49k/yr. Bid Banana at $50/mo sells raw bids, not pre-RFP signals. That leaves a **$150–$600/mo gap** for a trade-specific signal *plus* outreach.
3. **Service, not software, where licensing scares tech companies away.** Tax appeals, drawback and trademark filing all require a licensed partner (attorney, customs broker, registered tax consultant). Funded SaaS firms avoid these. A small operator with partners can run an agent back-office.
4. **Delta signals beat static lists.** Every incumbent sells snapshots. Change events (a new agenda line item, a year-over-year roster change, a status flip to "under construction") are rarer and worth more per record. However, the incumbents can also copy them cheaply.

---

## 2. Candidate ideas (8 detailed)

### Idea 1: Trade-specific "agenda-to-pipeline" for small public-sector vendors ★ top pick

**Pitch:** "Every water and sewer district, city council and school board in your territory, read every week. You get the 5 line items that mean a purchase is coming, the contact, and a drafted pitch."

**Data sources**

| Source | Access | Cost | ToS and licensing |
|---|---|---|---|
| Legistar Web API ("70% of the largest cities and counties", [Granicus PDF](https://granicus.com/pdfs/product_legistar.pdf)) | REST/OData, 1,000 rows per call; some clients need a token ([docs](https://webapi.legistar.com/Home/Examples)) | Free | Public records. Use a polite rate. |
| CivicPlus AgendaCenter (claims >10k local-gov customers, [CivicPlus](https://www.civicplus.com/)) | `/AgendaCenter/ViewFile/Agenda/_MMDDYYYY-id`, `?html=true`, RSS `ModID=65`; robots.txt does not block /AgendaCenter (checked on one tenant) | Free | Check robots.txt per tenant |
| BoardDocs (~5k, mostly school districts, [The74](https://www.the74million.org/article/school-districts-unaware-boarddocs-software-published-their-private-files/)) | Bot-protected (CloudFront 403) | Free, but needs a headless browser | **Risk:** Diligent ToS. A 2025 misconfiguration exposed ~64k private files, so filter out anything that looks non-public. |
| Special-district and township PDFs | Agent crawls the district website | Compute only | Public records |
| State revolving fund (SRF) intended-use plans | State PDFs | Free | Public. These list water projects that are *funded but not yet bid* [EST, standard SRF practice]. |
| Budgets and capital improvement plans | PDFs | Free | Public |

**The data combination:** an agenda line item ("authorize engineering services for lift station #3 rehab") + the capital improvement plan ($ and year) + SRF funding status + the district's existing vendor (from minutes and warrant lists) + contact (clerk or utility director from the site). Together these give a **pre-RFP opportunity, sized and dated, with the decision-maker named**. Bid feeds only see the RFP. This sees it 3–18 months earlier.

**Buyer persona:** an owner or sales manager at a 5–50 person firm that sells to local governments in one trade. For example:
- a water/wastewater manufacturer's rep agency (pumps, valves, SCADA)
- a playground and athletic surfacing dealer
- school HVAC, roofing or controls contractors
- a municipal fleet or equipment dealer
- small civil engineering firms

They currently rely on relationships and Bid Banana or BidNet.

**Evidence of willingness to pay**
- Enterprise version: GovSpend median ~$11.6k/yr; GovWin ~$29k average (secondary, links above).
- Low end: Bid Banana $480/yr; GovTribe ~$1,900/yr with state and local ([Pursuit](https://www.pursuit.us/blog/starbridge-alternatives-and-competitors), secondary); BidPrime regional ~$1.5k–$3k/yr ([govbid.ca](https://govbid.ca/compare/bidprime), secondary).
- Construction Monitor charges ~$62–$1,250 per month per market for permits (secondary). That shows trades pay recurring fees for early project signals.
- The labor it replaces: SLED sales reps average ~$81.6k ([ZipRecruiter](https://www.ziprecruiter.com/Jobs/Sled-Sales)); government-relations analysts ~$82k–$107k ([ZipRecruiter](https://www.ziprecruiter.com/Salaries/Government-Relations-Analyst-Salary)).
- VC conviction in the category: Starbridge $42M Series A, Pursuit $22M Series A. That validates the signal, but those firms sell to enterprise.

**Market size (bottom-up) [EST]**
- Target firms: water/wastewater rep agencies and equipment distributors (~3–5k), park/playground/surfacing dealers (~1–2k), school facility trades that sell to districts (~10k+), municipal equipment dealers (~2–3k), small civil and environmental engineering firms with a public practice (~10k).
- That is **~25–30k firms** in total. Assume a realistic serviceable 10% (2,500) × $3.6k/yr ≈ **$9M ARR ceiling** for a single-operator niche business. That is a good small business, not a venture-scale one.
- **These counts are [EST]**: I did not find an authoritative count of water-equipment rep agencies.

**Deliverable and pricing**
- A weekly territory brief: scored opportunities, the source excerpt and link, the contact, and a drafted email.
- Optional "we send it for you" outreach in the vendor's name.
- Price: **$300–$600/mo per trade per territory** (state or metro), or $150/mo for alerts only. Recurring, with annual prepay offered.

**Automation pipeline**
1. **Find prospects:** the vendor lists are themselves in the minutes. Approved vendor payments, warrant registers and bid tabulations name the vendors that won. Losing bidders on bid tabs are the warmest prospects.
2. **Build the deliverable:** crawl → LLM classifies each line item by trade taxonomy → enriches with the capital plan and SRF data → scores → writes the brief. The sample brief for the prospect's own territory *is* the outreach asset, the same trick as building the website before the pitch.
3. **Personalized outreach:** "You bid on X in Fresno last spring. Here are 4 upcoming pump-station projects in your territory, with dates and contacts."
4. **Handle replies:** an agent answers coverage questions, sends a 14-day trial, and books a call only when asked.
5. **Deliver and renew:** weekly brief; monthly "won/lost" survey; renewal agent shows the opportunities surfaced versus bids won.

**Percent automatable:** ~85% [EST]. Humans still:
- spot-check the classifier for each new trade (taxonomy tuning),
- handle a few enterprise-ish sales calls,
- fix crawlers on hostile portals.

**First 90 days**
- **Weeks 1–3:** pick ONE trade (water/wastewater is best: SRF money plus aging infrastructure) and ONE state (CA or TX). Build a crawler for ~1,500 bodies there.
- **Weeks 4–6:** backtest. Did the agenda signals precede actual RFPs on BidNet and state portals? Measure precision and lead time. **If lead time is under 60 days or precision is under 50%, kill.**
- **Weeks 7–12:** mine bid tabs for ~300 vendors and send sample briefs. Goal: 10 paying at $300+/mo.

**Unit economics [EST]**
- CAC: ~$150–400. The outreach is automated, and a sample brief costs about $2 in LLM spend to produce.
- Price: $4.2k/yr average.
- Data cost: ~$0. Compute ~$30–80/mo per state for crawling plus LLM classification (assuming ~1,500 bodies × ~4 docs/mo × ~30 pages, with cheap-model triage and premium-model scoring).
- Gross margin: ~85–90%.
- Payback: under 2 months if churn stays below 3%/mo.

**Competitors and crowding**
- Curate (CurateBUILD and project-type alerts; pricing not public; [Capterra](https://www.capterra.com/p/253803/Curate/) shows 1 review, which suggests a small SMB footprint).
- Starbridge and Pursuit (enterprise).
- Hamlet (civic, free tier).
- Bid feeds for the post-RFP stage.
- **Crowding: moderate.** The signal exists, but nobody packages it per trade with done-for-you outreach for small vendors (no dedicated product found).

**Legal and regulatory**
- Public records, low risk.
- **CAN-SPAM:** B2B email allowed with a physical address, an opt-out, and honest headers.
- If sending in the client's name, the client is the "sender" for CAN-SPAM, so the contract must allocate responsibility.
- **TCPA:** avoid calls and texts.
- **Portal ToS:** BoardDocs/Diligent and some Granicus pages may prohibit scraping. Prefer the API and RSS.
- GDPR: not applicable (US, B2B).

**Kill risks**
1. **Curate, Starbridge or Pursuit launch a $199/mo SMB tier.** They have the corpus already, so the moat is only the trade workflow plus outreach.
2. **Signal-to-noise:** most agenda items are routine, and small vendors churn if a month has nothing actionable. Thin territories cannot sustain $300/mo.
3. **Relationship-driven buying:** small public-works purchases often go to incumbents or sole-source. The vendor may not win even with early notice, so perceived ROI is slow and churn is high.

---

### Idea 2: Small-commercial property-tax appeal evidence engine (through licensed partners)

**Pitch:** "For every small commercial parcel in the county, we compute the assessment gap and build the appeal packet. A licensed consultant or attorney files it, and the owner pays only if they save."

**Data sources**

| Source | Access | Cost | Limits |
|---|---|---|---|
| County assessor rolls plus sales | Open-data portals (e.g. Cook County Assessed Values, [Socrata](https://datacatalog.cookcountyil.gov/Property-Taxation/Assessor-Assessed-Values/uzyt-m557)) or bulk files; varies by county | Free to ~$500 per county [EST] | Some counties restrict commercial use of bulk rolls [EST, varies] |
| Board of Review appeal history (Cook: 6.93M rows, 2010–present, updated June 2026) | [Socrata OData](https://datacatalog.cookcountyil.gov/Property-Taxation/Board-of-Review-Appeal-Decision-History/7pny-nedm) | Free | Shows which property classes and arguments win |
| Income and market proxies (rents, cap rates) | Paid CoStar is out of budget. Use listing data and public RE investment trust (REIT) disclosures. | $0–$ | **Weakest link** for income-approach appeals |
| Owner contact | Assessor mailing address + Secretary of State LLC registered agent | Free | LLC owners hide behind registered agents |

**The data combination:** assessed value versus (recent comparable sales + the appeal success history for that class and township + the parcel's own past appeals + the county equalization ratio). The output is a *pre-computed, parcel-specific dollar savings estimate before first contact*. That is the same "show the value before the sale" trick as the website model.

**Buyer persona:** two options.
- **(a) B2B, safer:** a small property-tax consultancy or attorney who wants more cases without hiring analysts.
- **(b) B2B2C:** an owner of 1–5 small commercial parcels (strip retail, small office, light industrial, mixed-use) valued at roughly $300k–$3M. These owners are below the minimum for Ryan or Marvin Poer.

**Evidence of willingness to pay**
- Contingency fees of **25–50% of first-year savings** are standard: Ownwell 25%; O'Connor 50% on commercial; Texas regionals 40% ([AppealDesk](https://www.appealdesk.com/compare/best-property-tax-appeal-services), secondary).
- Ownwell raised a $50M Series B in Feb 2026 ([HousingWire](https://www.housingwire.com/articles/ownwell-property-tax-appeal-funding/)). It claims an 88% success rate and "1MM appeals since 2021" ([Ownwell commercial](https://www.ownwell.com/commercial)).
- Cook County alone has 6.9M historical appeal rows, which shows the volume of appeals people pay for.

**Market size**
- ~5.9M US commercial buildings ([EIA CBECS 2018](https://www.eia.gov/consumption/commercial/)).
- [EST] Suppose ~60% are small ($<3M) and owner-held, ~30% sit in reassessment-heavy, appeal-friendly jurisdictions, and ~20% are over-assessed by enough to matter. That gives **~200k actionable parcels a year**.
- At an average savings of ~$3k [EST] and a 30% fee, that is ≈ **$180M/yr fee pool**, served today mostly by local firms.
- For the B2B tool path [EST]: ~3–5k property-tax consultants and attorneys nationally.

**Deliverable and pricing**
- Path (a): a SaaS evidence packet at $50–$150 per parcel, or $500–$2k/mo per firm.
- Path (b): a revenue share of 30–50% of the partner's contingency fee.
- **Recurring?** Partly. Reassessment cycles repeat (annually in many states, every 2–4 years in others), and multi-year representation agreements are common.

**Automation pipeline**
1. **Find prospects:** rank parcels by (assessed value ÷ modeled value).
2. **Build the deliverable:** comparable-sales grid, equity analysis, a narrative drafted by an LLM, and a pre-filled county form.
3. **Personalized outreach:** postal mail to the owner of record is best. Email only if the registered agent or company site gives one. Message: "Your 1,200 Main St assessment is ~18% above comparable sales. Estimated savings $4,100."
4. **Handle replies:** agent answers questions and collects the signed authorization / letter of authority.
5. **Deliver and renew:** the partner files and attends hearings. Renewal is triggered by the new notice of value each cycle.

**Percent automatable:** ~65% [EST]. Humans still:
- file and appear as the licensed representative,
- attend hearings and negotiate with assessors,
- handle income-approach appeals, which need owner financials.

**First 90 days**
- Choose **one county with online appeals, open data, and no attorney requirement for entities.** Cook County is *not* that: its BOR Rule 1 requires LLC and corporate owners to be represented by counsel ([Cook BOR FAQ](https://www.cookcountyboardofreview.com/about/frequently-asked-questions)).
- Texas requires a TDLR-registered consultant ([TDLR](https://www.tdlr.texas.gov/ptc/ptcfaq.htm)). Partner with an existing Texas registrant instead.
- Sign one licensed partner. Backtest the model against the county's past appeal outcomes. Mail 1,000 packets ahead of the next appeal window.

**Unit economics [EST]**
- Customer acquisition: postal mail ~$1 per piece; 1% conversion → **~$100 per customer** plus packet compute (~$0.50).
- Revenue: ~$3k savings × 40% fee = $1.2k; our share at 50% = **$600 per win**.
- Win rate ~60%, so expected revenue is ~$360 per signed client.
- Gross margin ~70% after partner hearing time.

**Competitors and crowding**
- Ownwell (venture-funded, expanding into commercial in 7 states).
- O'Connor (45 states).
- Thousands of local attorneys and consultants.
- DIY tools at $49–$100.
- **Crowding: moderate to high in TX, IL, NY, CA; lower elsewhere.**

**Legal and regulatory**
- **Licensing:** Texas TDLR registration; Cook County attorney rule; Connecticut bars attorney contingency fees on commercial appeals over $500k ([CGA](https://www.cga.ct.gov/2015/jfr/h/2015HB-06945-R00PD-JFR.htm)); other states cap or prohibit contingency fees for consultants ([Chicago-Kent L. Rev.](https://scholarship.kentlaw.iit.edu/cgi/viewcontent.cgi?article=3998&context=cklawreview)).
- **Unauthorized practice of law** if we advise directly in attorney-only venues.
- **Fee-sharing:** attorneys cannot split fees with non-lawyers (ABA Model Rule 5.4). So in attorney venues use path (a), a flat-fee SaaS, **not** a revenue share.
- CAN-SPAM for email; postal mail is the safer channel.

**Kill risks**
1. **The licensing and fee-split maze makes each county a bespoke legal project.** This does not scale like a website business.
2. **Ownwell moves downmarket** with $50M and the same AI-plus-local-advisor model.
3. **Seasonality and slow cash:** appeal windows are short, decisions take 3–12 months, and fees are collected after the tax bill. The first dollar may be 6–12 months away.

---

### Idea 3: Done-for-you aircraft-owner outreach for avionics and maintenance shops

**Pitch:** "We find the 300 aircraft based near your shop whose avionics or airworthiness directives (ADs) make them due for your service, and we run the personalized outreach."

**Data sources**

| Source | Access | Cost | Limits |
|---|---|---|---|
| FAA Releasable Aircraft Database (owner, address, make/model/year; ~269k–301k records) | Free daily download ([Apify description](https://apify.com/scrapemint/aircraft-owner-leads); FAA page 403'd for me) | Free | **Privacy opt-out:** since 2025, owners can withhold their address ([Aero Law Group](https://aerolawgroup.com/recent-faa-privacy-protections-for-private-aircraft/)) |
| FAA AD database plus type certificate data | Free (DRS) | Free | Applicability parsing is complex. LLM extraction works, but needs QA. |
| Flight activity (ADS-B) | ADS-B Exchange is now a **JETNET product** ([JETNET](https://www.jetnet.com/products/adsb-exchange)); OpenSky is research-licensed | Paid / restricted | **Commercial-use licensing needed**, or skip activity data |
| ADS-B equipage | FAA public ADS-B performance reports [EST] | Free | Partial coverage |

**The data combination:** registry (who owns what and where) + AD applicability (what is due on that make and model) + the panel age implied by model year + an optional activity filter. The result is a *specific upgrade or inspection pitch per tail number*.

**Buyer persona:** the owner of a Part 145 repair station or avionics shop. There are 5,038 Part 145 stations ([faa145stations](https://faa145stations.com/)) and ~1,300 AEA member companies ([WAI](https://www.wai.org/corporate-members/aircraft-electronics-association)).

**Evidence of willingness to pay**
- Agencies already sell lead generation to avionics shops: "20–30 qualified leads/month" campaigns ([OutboundClick](https://outboundclick.com/industries/aviation); [Off The Ground](https://www.offthegroundmarketing.com/avionics-marketing)).
- Panel upgrades run from thousands to more than $100k per ticket ([LinkedIn](https://www.linkedin.com/pulse/avionics-market-segmentation-overview-biz-av-mike-ingram)).
- Owner lists are sold by NextMark and DM Databases.

**Market size [EST]**
- ~6k shops × 20% adoption × $500/mo ≈ **$7M ARR ceiling**. Small.

**Deliverable and pricing:** $400–$800/mo per shop for a territory list, outreach sequences (postal plus email), and reply handling. Recurring.

**Automation pipeline**
1. **Find prospects (shops):** FAA repair station list plus Google Maps; many shops have weak websites, so the website business is an obvious cross-sell.
2. **Build the deliverable:** a "your top 50 tails" sample report.
3. **Personalized outreach:** to the shop, with the sample report.
4. **Handle replies.**
5. **Deliver and renew:** monthly refresh, plus new ADs as triggers.

**Percent automatable:** ~85%. AD-applicability QA by someone who knows aviation is the main human touchpoint.

**First 90 days**
- Build an AD × registry join for the top 10 piston types (C172, PA-28, SR22, …).
- Pitch 200 shops in 3 states. Goal: 8 paying.

**Unit economics [EST]**
- Data cost ~$0, or a JETNET licence if activity data is wanted.
- CAC ~$300.
- Gross margin ~85%.

**Competitors:** aviation marketing agencies; JETNET and AMSTAT (business-jet focused, expensive); Apify registry scrapers. **Moderate crowding** in the piston and general-aviation shop segment.

**Legal and regulatory**
- Registry use is lawful, but honour the FAA privacy opt-outs.
- CAN-SPAM; postal mail is safest.
- Pilots are vocal on privacy (AOPA is lobbying for more, [AOPA](https://www.aopa.org/news-and-media/all-news/2025/june/06/aopa-asks-faa-to-enhance-aircraft-registry-privacy)), so creepy outreach backfires on the shop.

**Kill risks**
1. **Tiny market** with a ~$7M ceiling.
2. **Registry addresses are postal only:** email enrichment for individuals is weak, which means mail costs plus a CAN-SPAM/consumer-privacy grey zone.
3. **Owners already know about ADs** through their mechanic and annual inspection, so the "news" value may be low.

---

### Idea 4: Franchise trigger engine (emerging franchisors, plus Item 20 deltas)

**Pitch:** "Every week, new franchisors registered in WI, MN and CA get a ready-built franchise-development site plus a lead engine. Every year, local vendors get a feed of *new* franchisees (year-over-year Item 20 diffs)."

**Data sources**

| Source | Access | Cost | Limits |
|---|---|---|---|
| WI DFI franchise search | Free online, PDF download ([DFI](https://dfi.wi.gov/Pages/Securities/Filings/Franchising.aspx)) | Free | No published ToS on automation found; be polite |
| MN CARDS | Free, ~10 years, PDFs "public and may be copied" ([CARDS](https://cards.web.commerce.state.mn.us/franchise-registrations)) | Free | — |
| CA DFPI Unified Search | Free; includes examiner comment letters ([DFPI](https://dfpi.ca.gov/search/)) | Free | Exact-name search makes discovery harder |
| SBA 7(a) loan data | Free | Free | Shows which brands get financed |

**The data combination**
- New registration + no Item 20 units / few units + a weak website = an **emerging franchisor that needs franchise sales infrastructure**.
- Item 20 roster in year N versus year N−1 = **new franchisees, transfers and closures**. Static list vendors do not sell these as events.

**Buyer persona**
- A founder or CEO of an emerging franchisor (fewer than 50 units). ~300–414 new brands a year ([FRANdata](https://frandata.com/new-brands-rising-conditions-converge-to-grow-the-number-of-brands/)).
- Secondary: vendors that sell to new franchisees (insurance agents, CPAs, signage, POS).

**Evidence of willingness to pay**
- Broker commissions of **$15–30k per franchise sold** ([Franzy](https://franzy.com/blog/how-do-franchise-consultants-make-money/)) show what a franchisor will pay per franchisee acquired.
- Franchise Ninja ad campaigns run ~$1.5–2k ([Franchise Ninja](https://www.franchiseninja.ai/pricing)).
- Data side: GetFDD $199/mo, Frandera $750/mo.

**Market size:** ~1,500–2,000 emerging franchisors [EST] × $1–2k/mo marketing retainer ≈ $18–48M theoretical. Realistic capture is a few hundred clients.

**Deliverable and pricing:** a franchise-development microsite + candidate lead nurturing + broker-network listing prep, at $750–$1,500/mo. Delta feeds for vendors at $99–$299/mo per state.

**Automation pipeline:** registry poll → FDD parse (fee, investment range, Item 19 if any) → generate a franchise-sales site → outreach to the founder → handle replies → monthly lead reports.

**Percent automatable:** ~75%. Franchise-sales copy needs franchise-law care: no unauthorized earnings claims beyond Item 19.

**First 90 days:** backfill 2025–26 registrations (~400 brands), score them by website quality, and send 100 demo sites. Goal: 5 retainers.

**Unit economics [EST]:** CAC ~$500; ARPA $1k/mo; gross margin ~70%; churn is likely high because emerging franchisors fail often.

**Competitors:** franchise marketing agencies (1851, Franchise Ninja, many others); FRANdata, GetFDD, Frandera, Franchimp. **Blueprint GTM already sells a 142,579-operator, Claude-built franchisee dataset at $50/mo** ([Blueprint](https://edge.blueprintgtm.com/p/142579-franchise-operators-built)). **Crowding: high on data, moderate on emerging-franchisor services.**

**Legal and regulatory**
- **FTC Franchise Rule and state franchise laws:** marketing materials can count as "advertising" that some states (e.g. CA, NY historically) require to be filed or reviewed. Any earnings representation outside Item 19 is a violation risk.
- CAN-SPAM applies.
- Using Item 20 contacts for unrelated vendor marketing is lawful but reputationally sensitive.

**Kill risks**
1. **Data commoditized to $50/mo**, so only the agency service holds value, and agencies are crowded.
2. **Emerging franchisors have high failure rates and thin budgets**, so churn is high.
3. **Regulatory exposure** if generated sales copy implies earnings.

---

### Idea 5: Amazon brand-protection gap: unregistered brands → trademark filing and monitoring (attorney-partnered)

**Pitch:** "Your Amazon brand 'X' has no live US trademark, so you can't join Brand Registry and you're exposed to hijackers. A partner attorney files it for a flat fee, and we watch for conflicting filings."

**Data sources**
- **USPTO trademark daily XML:** free ([bulk data](https://bulkdata.uspto.gov/data/trademark/dailyxml/applications/)).
- **Seller and brand data:** licensed from SmartScout ($29–$239/mo; API on Enterprise ~$399+, [RevenueGeeks](https://revenuegeeks.com/software/smartscout/pricing), secondary) or Keepa (€49+/mo).
- **Do NOT scrape Amazon.** Its Conditions of Use ban data-extraction tools, and Amazon won a preliminary injunction against Perplexity's agent in March 2026 (secondary report, [AI CERTs](https://www.aicerts.ai/news/amazon-v-perplexity-ai-web-scraping-showdown/)).
- **INFORM Act seller name and address** appear on seller profiles ([Marketplace Pulse](https://www.marketplacepulse.com/articles/amazon-now-lists-sellers-business-name-and-address)).

**The data combination:** a storefront brand string + seller legal entity and country + the absence of a live USPTO mark + recent conflicting filings. The output is a *specific trademark gap or risk per seller*.

**Buyer persona:** a US-based private-label Amazon seller doing $250k–$5M a year. ~51k sellers on Amazon.com exceed $1M ([seller forum citing Marketplace Pulse](https://sellercentral.amazon.com/seller-forums/discussions/t/1949a6a7-d5e5-4a62-be7e-81d2c0f6f3d0), verify). US sellers are a minority of the top 10k ([Marketplace Pulse](https://www.marketplacepulse.com/articles/china-won-amazons-top-10000-america-kept-its-top-100)).

**Evidence of willingness to pay**
- Trademark filing: Trademarkia $499–$699 plus fees; Fiverr attorneys ~$375; USPTO fee $350 per class.
- Appeals and reinstatement: $1,397–$3,950 ([Seller Resolve](https://www.sellerresolve.com/account-reinstatement/), [Reinstateamz](https://reinstateamz.com/)).

**Market size [EST]:** ~20–40k US-based brand sellers without a registered mark × $600 one-time + $20/mo monitoring. Roughly $15–25M one-time plus small recurring revenue.

**Deliverable and pricing:** a flat-fee filing through a partner attorney (we keep a marketing or tech fee, structured lawfully) + a $15–30/mo watch service. **Mostly one-time.**

**Pipeline:** licensed brand list → USPTO join → gap report → email to the seller's business address (INFORM data) → reply handling → attorney files → monitoring alerts.

**Percent automatable:** ~70%. The attorney reviews and signs every filing. USPTO requires identity-verified filers.

**First 90 days:** one category (e.g. pet supplies). Sign an attorney partner. 500 gap reports. Goal: 25 filings.

**Unit economics [EST]:** CAC ~$80; gross ~$250 net per filing after attorney and USPTO fees; monitoring margin 90%.

**Competitors:** LegalZoom, Trademark Engine, Trademarkia, Amazon IP Accelerator (Amazon's own attorney network), Corsearch and CompuMark for watching. **Crowded.**

**Legal and regulatory**
- **Unauthorized practice of law:** only attorneys can give trademark legal advice. Non-lawyers can file only for themselves.
- **Fee-splitting** with non-lawyers is prohibited (Model Rule 5.4).
- **USPTO actively warns about solicitations exploiting public trademark records** ([USPTO](https://www.uspto.gov/trademarks/protect/how-avoid-scams-trademark-services)). Our outreach would look exactly like those scams.
- CAN-SPAM; Amazon ToS on data.

**Kill risks**
1. **Scam-adjacent optics.** Unsolicited trademark outreach is the #1 trademark-scam vector the USPTO warns about, so response rates and trust will be poor.
2. **Amazon IP Accelerator already pipes sellers to vetted attorneys** at negotiated rates.
3. **Mostly one-time revenue**, and the attorney rules prevent clean economics.

---

### Idea 6: Duty-drawback discovery for small importer-exporters (licensed-broker partnered)

**Pitch:** "You paid Section 301/232 duties on inputs and you export. You're owed up to 99% back. We find it, build the claim, and our licensed broker files it. Contingency only."

**Data sources**
- **Bill-of-lading import data** (ImportGenius $149–$449/mo, enterprise $1,999; [pricing](https://www.importgenius.com/pricing)). Ocean only; consignee confidentiality requests exist [EST].
- **Export indicators** (AES data is not public). Proxies: company website "we ship worldwide", trade-show exhibitor lists, export.gov directories [EST].
- **Census:** 240,535 importers in 2024, 234,023 of them small and mid-size, holding ~$884B of import value ([Census EDB](https://www.census.gov/foreign-trade/Press-Release/edb/edbrel2024.pdf)).

**The data combination:** imports of goods under Section 301/232 HTS codes (bills of lading) × evidence of exports or manufacturing (web plus directories) × no drawback history. The output is a *drawback-eligible SMB with an estimated refund*.

**Buyer persona:** the CFO or owner of a US small manufacturer or distributor that imports Chinese components and exports some product.

**Evidence of willingness to pay**
- Drawback contingency fees run **15–35%** ([AJOT](https://www.ajot.com/news/best-duty-drawback-companies-in-2026-compared-by-speed-cost-recovery), secondary).
- Section 301 duties remain drawback-eligible ([Alliance CHB](https://alliancechb.com/duty-drawback/section-301-drawback/)) and survived the IEEPA ruling ([Baker Donelson](https://www.bakerdonelson.com/trade-policy-shifts-ieepa-tariffs-end-section-122-begins-and-sections-301-and-232-activity-grows)).

**Market size [EST]:** perhaps 5–10% of 234k SMB importers also export or destroy goods, so ~12–23k firms. If ~$50k average annual recoverable × 25% fee = ~$12.5k per client per year, the addressable fee pool is ~$150–290M. **This is the weakest-sourced number in the doc.**

**Deliverable and pricing:** annual or quarterly drawback claims on 20–25% contingency, shared with the broker partner. **Recurring** while duties persist.

**Pipeline**
- Bills of lading → HTS and duty estimate → export evidence → estimated refund letter.
- Outreach → collect ACE reports and export docs → the agent matches imports to exports (the 5-year window, 8-digit substitution rules) → the broker reviews and files.

**Percent automatable:** ~55%. The licensed customs broker must file; document collection from the client is manual and slow.

**First 90 days:** partner with a drawback-capable broker. Target one HTS family (e.g. steel and aluminium parts under 232). 300 estimate letters. Goal: 5 signed clients.

**Unit economics [EST]:** CAC ~$1–2k because the sale is longer; revenue ~$6k per client per year (after the broker split); gross margin ~60%; first cash 6–12 months out because of CBP processing time.

**Competitors:** established drawback brokers (Alliance CHB, Expeditors, Livingston, Baker Tilly). IEEPA refund shops are now pivoting into drawback [EST]. **Moderate crowding.**

**Legal and regulatory**
- **Customs business requires a licensed customs broker** (19 USC 1641) [knowledge, not verified this session].
- **False-claim risk:** drawback claims carry penalty exposure.
- CAN-SPAM applies.

**Kill risks**
1. **Export data is not public**, so prospect precision is poor and most estimate letters miss.
2. **Tariff policy whiplash.** The IEEPA tariffs were struck down ([CRS](https://www.congress.gov/crs-product/LSB11398)) and the Section 122 surcharge expired, so the duty base can shrink fast.
3. **Long time to first dollar plus a hard dependence on the broker.**

*(The IEEPA refund wave itself is rejected in §3: it is one-time, ~80% already claimed, and crowded.)*

---

### Idea 7: Private land-use approval triggers → local service vendors

**Pitch:** "Every approved site plan, variance and conditional-use permit in your county, read weekly. You get the businesses about to build or open, matched to what you sell."

**Data:** planning commission, zoning board and city council agendas and minutes (the same crawler as Idea 1), plus staff reports in agenda packets. Cook County even publishes ZBA hearings as open data ([data.gov](https://catalog.data.gov/dataset/zoning-board-of-appeals-public-hearings)).

**The combination:** approval item + applicant (often an LLC) + parcel + project type (drive-thru, self-storage, daycare, medical office, car wash) + staff-report conditions (landscaping, fencing, signage, stormwater). The output is *trade-specific leads 3–12 months before permits*.

**Buyers:** commercial fence, sign, landscaping, paving and sealcoating, low-voltage/security, commercial cleaning, and insurance agents. Also POS and payroll vendors for new restaurants.

**Willingness to pay**
- Opening Alerts charges $49–$99/mo for new-business and liquor-license leads to POS, insurance, linen and payroll vendors ([Opening Alerts](https://www.openingalerts.com/)).
- DineTracer charges $0.50 per lead ([DineTracer](https://dinetracer.com/)).
- Construction Monitor charges $62–$1,250 per market per month.
- **So buyers pay, but at low price points.**

**Market size [EST]:** hundreds of thousands of local trade firms; realistic serviceable ~10k × $150/mo ≈ $18M.

**Pricing:** $99–$249/mo per county per trade; recurring.

**Pipeline and automation:** same as Idea 1, ~85% automatable. Prospects (trade firms) come from Google Maps, often with bad websites, which suits the existing business.

**Competitors:** CurateBUILD (private construction from minutes); Shovels and Construction Monitor (permits, later stage); Opening Alerts and DineTracer (licenses). **Moderate to high crowding.**

**Legal:** low; public records; CAN-SPAM.

**Kill risks**
1. **Low price points with high churn**, typical of local-trade lead products.
2. **CurateBUILD and permit vendors already cover the higher-value construction trades.**
3. **Applicant LLCs are hard to contact.** The lead is "a project", not "a person", so value depends on the buyer hustling.

*Note: Ideas 1 and 7 share 80% of the infrastructure. Build Idea 1 first, then add Idea 7 as a low-price add-on tier.*

---

### Idea 8: "Construction is coming to your county" (EIA-860M + BEAD + data-center filings → local trades and hospitality)

**Pitch:** "A 300 MW solar farm and a BEAD fiber build just went 'under construction' 20 miles from you. Here's who's building, when, and how to get on their vendor list."

**Data**
- **EIA-860M** monthly: every planned generator ≥1 MW with county, capacity, technology and status, including codes U/V for under construction ([EIA-860M instructions](https://www.eia.gov/survey/form/eia_860m/instructions.pdf)). Free.
- **BEAD:** all 56 final proposals approved ([StateScoop](https://statescoop.com/all-states-and-territories-secure-approvals-from-ntia-on-bead-final-proposals/)); ~519 subgrantees, $19.28B ([Broadband Expanded](https://broadbandexpanded.com/posts/beadfccprovidermatch)); construction peak 2027–29.
- **Local data-center approvals:** from minutes (Idea 1 crawler).

**The combination:** project status flip + county + EPC/subgrantee name. The output is a *local opportunity for crew housing, equipment rental, aggregate, fencing, security, vegetation management, and boring/splicing subs*.

**Buyers:** rural hotels and RV parks, equipment rental branches, aggregate and concrete suppliers, fencing and security firms, small fiber contractors, surety brokers (BEAD performance bonds run 2–6% of project cost, [Ready.net](https://ready.net/blog/everything-broadband-pros-need-to-know-about-performance-bonds)).

**Willingness to pay:** **weak evidence.** I found no product selling this to local trades, and BEAD winner lists are free (Telecompetitor, [beadtracker.com](https://www.beadtracker.com/)). The absence of competitors may mean absence of demand.

**Market size [EST]:** a few thousand projects a year nationally; buyers in each affected county number in the dozens. Total ARR is likely under $3M.

**Pricing:** $49–$149/mo per county alert, or a one-time $500 "project dossier".

**Automation:** ~90%.

**Competitors:** none for local trades; Paces, Enverus and Orennia for developers. **Blue ocean, but probably because it's a puddle.**

**Legal:** low.

**Kill risks**
1. **No proven willingness to pay.** Local trades hear about big projects through word of mouth anyway.
2. **EPCs buy nationally.** Local vendors capture little.
3. **BEAD money is one-time and politically volatile** (NTIA claimed ~$21B in "savings", [NTIA](https://www.ntia.gov/press-release/2026/assistant-secretary-arielle-roth-announces-50-bead-final-proposals-approved)).

---

## 3. Ideas considered and rejected

| Idea | Why rejected (evidence) |
|---|---|
| **SERFF insurance rate-filing intel** | SFA terms prohibit automated download ([SFA help](https://filingaccess.serff.com/sfa/static-web/OnlineHelp.pdf)). The legal route is an NAIC licence at an unpublished price. Crowded: S&P, Akur8/Matrisk, Insuraviews (claims 9 of the top 25 P&C carriers), Zesty, Quadrant. |
| **PUC rate-case and docket tracking** | Halcyon ($32M raised, all 50 PUCs), HData + Insight Engine, S&P RRA. Closed to a small team. |
| **Utility tariff data** | Arcadia/Genability own the installer market. The OpenEI URDB gap (only ~150 utilities updated per year) is real but small. |
| **Interconnection queues → landowner leads** | Landowners don't pay (LandGate makes them free supply). Developer side: Paces, Transect, LandGate, Grid Status, Apify at $6/1k. Parcel ↔ POI matching is guesswork. |
| **Data-center and renewable moratorium trackers** | Free trackers already exist: SAVRN (1,118 moratoria), Sabin/Opposition Report, NLC, EticaAG BESS DB. Enterprise: Heatmap Pro, Transect, Paces. |
| **BEAD winner lists** | Free (Telecompetitor, beadtracker.com, state portals). Folded into Idea 8 as a minor input. |
| **USDA FSA payments → ag dealers** | DTN / Farm Market iD (2.4–2.8M operators); EWG and OpenSubsidies are free. Data lags by a year and goes to entities. |
| **EU CBAM for US exporters** | US exposure is ~$1.4B of exports ([Third Way](https://www.thirdway.org/blog/what-does-the-eus-new-carbon-border-adjustment-mean-for-the-us)). The obligation sits with the EU importer. EU software starts at €79/mo. |
| **CA SB 253 supplier Scope 3** | Scope 3 isn't due until 2027; SB 261 is enjoined; spend-based estimates are allowed, so SMB suppliers aren't forced to buy. Revisit in 2027. |
| **EPA TRI / GHGRP standalone** | Only useful as an input to the SB 253 idea above. |
| **Generic SMB RFP writer** | GovDash ($30M B), Vultron ($22M), AutoRFP, Inventive, Arphie, plus $0–$199/mo tools (Bidscope, Caprix, GovBidWriter). |
| **Horizontal SLED intelligence** | Starbridge, Pursuit, Curate, GovSpend, GovWin, Quorum. |
| **990 funder matching / grant prospecting** | Instrumentl ($55M), Candid, Granted AI ($18/mo), Grantable (free). Schedule B donors are redacted. |
| **Church data** | Churches don't file 990s ([IRS Pub 1828](https://www.irs.gov/pub/irs-pdf/p1828.pdf)). List brokers sell 118k contacts for $699. Commodity. |
| **Liquor and cannabis license leads** | Opening Alerts $49–99/mo, DineTracer $0.50/lead, Cannabiz $3.6k+/yr, 5+ Apify actors. *Small sub-angle not pursued:* CA ABC weekly disciplinary and surrender reports ([ABC](https://www.abc.ca.gov/licensing/licensing-reports/)) as distress signals for license brokers. Niche, under $1M. |
| **FMCSA new-authority leads** | 6+ Apify actors at $3.50–$20/1k; new carriers are swamped by insurance, factoring and ELD calls; the Motus migration broke the data feed ([Overdrive](https://www.overdriveonline.com/channel-19/article/15827334/fmcsa-new-authorities-fall-to-zero-after-motus-not-quite)). |
| **UCC filings → equipment and MCA leads** | State access ranges from free (CO) to $24k (AZ), and GA/NC ban scraping ([Quintel](https://quintel.ai/blog/ucc-filing-search-by-state)). EDA owns heavy equipment; MCA outreach is saturated and reputationally toxic. |
| **Boat and vessel registrations** | No free bulk USCG download found; state registrations are privacy-restricted [EST]. |
| **Probate leads** | Crowded ($69–$799/mo per county; some vendors cap at 3 subscribers per county). Targets grieving families; automated AI outreach is an ethics and reputation landmine. **Rejected on ethics.** |
| **Shopify store detection** | Store Leads, BuiltWith, StoreCensus $49, StoreIndex $29, Apify. Red ocean. |
| **App-store review mining** | AppFollow, Appbot $39, Sensor Tower; LLM summaries are now a standard feature. |
| **Amazon suspended-seller reinstatement** | No public list of suspended sellers to prospect from; referral-driven and crowded. |
| **COI tracking** | BCS is free up to 25 vendors and then ~$0.95/vendor/mo; Jones ($38M) does full service with AI agents; TrustLayer, CertFocus at $6–29/vendor/yr. **No public data hook** to pre-compute value. |
| **Lien waivers and notices** | Procore/Levelset ($500M acquisition); LienWaiver.pro $49/mo; unauthorized-practice-of-law rulings on lien filing (NC Business Court). |
| **Parcel late-delivery refunds** | FedEx suspended Ground/Home/2Day guarantees ([LateShipment](https://www.lateshipment.com/blog/fedex-refund/)); UPS Ground isn't guaranteed and inbound international was suspended in Oct 2025 ([Supply Chain Dive](https://www.supplychaindive.com/news/ups-de-minimis-money-back-policy-suspension/802508/)). The refund pool has shrunk. |
| **IEEPA tariff refund recovery** | *Learning Resources v. Trump* (Feb 20, 2026) → about $165B in refunds. By Sept 2026 ~$134.7B was already in CAPE ([tracker](https://www.tariffstool.com/tariff-refund-tracker), secondary). One-time, crowded, needs a broker or attorney. |
| **Chargebacks** | Chargeflow ($49M, 20k merchants, 25% fee), Justt (~$100M). No public hook. |
| **Sales-tax nexus** | Kintsugi (free monitoring, $18M from Vertex), Numeral; free nexus studies (Galvix). |
| **1099 / W-9 compliance** | $0.63–$3.10 per form; the OBBBA raised the 1099-NEC threshold to $2,000, which shrinks the pool ([Avalara](https://www.avalara.com/blog/en/north-america/2025/07/one-big-beautiful-bill-act-1099-reporting-threshold.html)). |
| **Unclaimed property finder** | Fee caps of 10–20%, 24–36-month bans on finder agreements, median claim ~$100, and treasurers advertise "never a cost" ([NAUPA](https://nast.org/wp-content/uploads/naupa-release-annual-report-oct-29-2024.pdf)). |
| **Vet-clinic data play** | ~34k vet establishments ([JAVMA](https://avmajournals.avma.org/view/journals/javma/263/12/javma.263.12.1491.pdf)); ownership is already mapped (privateequityvet.org). Better as a website-business vertical, below. |

### Adjacent quick wins (not new businesses, but cheap lead sources for the existing website business)
- **Nonprofits:** the IRS 990 XML has a website field plus multi-year revenue. Filter for no or dead website with revenue of $250k–$5M. ~1.5M 501(c)(3)s exist ([NCN](https://www.councilofnonprofits.org/files/media/documents/2025/ncn-about-the-nonprofit-sector-2025.pdf)).
- **Independent vet clinics:** state vet board premises lists (e.g. [AZ](https://vetboard.az.gov/licensing/premises)), minus PE-owned clinics. The pitch: compete with the chains.
- **Emerging franchisors:** new WI/MN/CA registrations with weak franchise-development sites. This is the easy first step of Idea 4.
- **Churches:** ~357–373k congregations ([Hartford](https://hirr.hartfordinternational.edu/fast-facts-on-american-religion/)); detect stale sites. Budgets are small, but there are very many of them.
- **Aircraft maintenance and avionics shops** (5,038 Part 145 stations) with weak websites. This is also the entry point for Idea 3.

---

## 4. Ranked shortlist

Each score runs 1–10, where higher is better. For **Competition**, 10 means blue ocean. For **Time to $1**, 10 means fastest. **Overall** is the unweighted mean of the seven scores, rounded to one decimal, plus my judgement note.

| Rank | Idea | Market | WTP | Data access | Automation | Competition | Recurring | Time to $1 | **Overall** | Confidence |
|---|---|---|---|---|---|---|---|---|---|---|
| 1 | **#1 Trade-specific agenda-to-pipeline** | 6 | 7 | 6 | 8 | 5 | 9 | 6 | **6.7** | Medium-low: the willingness-to-pay analogues are solid, but no proof that small vendors pay for *pre*-RFP signals; the backtest is the gate |
| 2 | **#2 Property-tax appeal evidence engine** | 8 | 8 | 6 | 6 | 4 | 6 | 3 | **5.9** | Medium: willingness to pay is clearly proven, but legal scaling and Ownwell are real threats |
| 3 | **#3 Aircraft-owner outreach for avionics/MRO** | 3 | 7 | 7 | 8 | 6 | 7 | 7 | **6.4** | Medium-low: closest to the current playbook, but the market is tiny (ranked below #2 because the ceiling is ~$7M) |
| 4 | #7 Land-use approval triggers | 6 | 5 | 6 | 8 | 4 | 7 | 6 | 6.0 | Low-medium; best as an add-on to #1 |
| 5 | #4 Franchise trigger engine | 5 | 6 | 8 | 7 | 3 | 6 | 6 | 5.9 | Low: data already commoditized to $50/mo |
| 6 | #8 Construction-coming-to-county | 4 | 3 | 9 | 9 | 9 | 5 | 5 | 6.3 | **Low**: high score is a mirage; willingness to pay is unproven, so it is ranked down |
| 7 | #6 Duty drawback discovery | 6 | 8 | 4 | 5 | 5 | 7 | 2 | 5.3 | Low: export-side data is missing |
| 8 | #5 Amazon trademark gap | 6 | 7 | 6 | 6 | 3 | 3 | 6 | 5.3 | Low: scam optics, attorney rules, one-time revenue |

**Why the ranking deviates from the raw mean.** I ranked by *expected value adjusted for evidence*, not by the mean:
- #8 and #3 score well on automation and competition, but their small markets and unproven willingness to pay cap their value.
- #2 has the strongest willingness-to-pay evidence of anything in this lane (contingency fees paid at scale, a $50M raise), so it stays #2 despite slow time to cash.

### Honest bottom line
- **None of these is a slam-dunk replica of the website business.** The website model works because the deliverable (a site) can be built *before* the sale with zero data cost and no licence. Here:
  - **#1 comes closest:** the sample brief is built before the sale, the data is free, no licence is needed, and revenue is recurring.
  - **#2 has the most money** but needs licensed partners.
  - **#3 is a tidy niche** with a hard ceiling.
- **Recommended next step:** a 3-week, ~$0 backtest of #1 for water/wastewater in one state. Do agenda and capital-plan signals lead actual RFPs by 60 days or more with at least 50% precision? Go or no-go on that number before any outreach.
- In parallel, add the "adjacent quick wins" lead sources to the existing website pipeline. They cost almost nothing to add.
