# Lane 02 — Trade, Shipping & Supply-Chain Competitive Intelligence

*Research date: 2026-10-01. Research only; no outreach, signups or purchases were made. Every material claim has a link. Anything marked **(est.)** is my own estimate, not a sourced figure.*

---

## TL;DR

- **Raw US bill-of-lading (BOL) data is a commodity.** ImportYeti gives it away. Selling "search over manifests" is a dead end. The money is in **pre-built answers tied to an event that costs the importer money**: a new tariff, a bond insufficiency, a refund or drawback right, or a supplier landing on an enforcement list. The brothers' website model ("build the deliverable before first contact") maps onto this cleanly.
- **Best idea: the Tariff Exposure Brief.** BOL × Census unit values × the live tariff stack. For each mid-size importer, we pre-compute "your HS codes and origins and what the latest 301/232 action costs you". We send it cold and upsell a monthly monitor. 2026 has produced a new tariff regime almost every quarter (IEEPA struck down → §122 → §301 "forced-labor" tariffs on 60 economies, plus §232 derivative expansions), so there is a steady supply of triggers.
- **The second and third ideas are lead engines for licensed professionals** (drawback brokers, first-sale consultants, surety and bond agencies, freight forwarders), paid **per lead or by flat retainer**. They can't be paid on contingency, because [19 CFR 111.36](https://www.customsmobile.com/rulings/docview?doc_id=114404&highlight=HQ+114654) bars brokers from sharing customs-business fees with unlicensed people.
- **The seed idea, "your competitor switched suppliers" monthly reports, is real but weak on willingness to pay** because ImportYeti is free. It works as a free hook, not as the product.
- **The IEEPA refund angle has mostly closed.** By 11 Sept 2026, $122B of the ~$166B pool had been certified for repayment. The remaining Phase 3 money is reserved for importers who had already sued ([Wharton](https://budgetmodel.wharton.upenn.edu/p/2026-02-20-supreme-court-tariff-ruling/), [ALS](https://www.als-int.com/insights/posts/cape-phase-3-ieepa-refunds-litigation-requirement-2026/), [tariffstool tracker](https://www.tariffstool.com/tariff-refund-tracker)). Rejected as a stand-alone business.

---

## 1. Lane overview

### 1.1 What the raw data is and how you get it

**US inbound ocean manifests are public by statute.** Under [19 CFR 103.31](https://www.law.cornell.edu/cfr/text/19/103.31), the press may copy everything on the cargo declaration (CBP Form 1302). CBP sells the AMS manifest data, compiled daily, to the public "at the government's production cost", by day or by subscription. Orders go through CBP's National Finance Center in Indianapolis. **No public price is published**: you have to call the Collections Section ([Cornell LII text](https://www.law.cornell.edu/cfr/text/19/103.31); search summary of 103.31(e)). Vendors describe this as FOIA/Tariff-Act-sourced raw material that they clean and resell ([Flaaen et al. BOL paper](https://www.aaronflaaen.com/uploads/3/1/2/4/31243277/bol.pdf); [ecomcrew](https://www.ecomcrew.com/a-secret-weapon-for-doing-competitor-and-supplier-research/)).

- **Evidence that direct acquisition is affordable:** ImportYeti is **unfunded, about 13 employees, founded 2020**, and gives the core search away free ([Tracxn/Crunchbase summary](https://tracxn.com/d/companies/importyeti/__MLEp0TDcJiKTeu5fiJhSAJqw47BxQoq0mEtBJbvsC68)). A bootstrapped team can clearly carry the data cost. **(est.)** Plan for low-thousands of dollars a month, and confirm by phone with CBP before committing.
- **Outbound (export) manifests** release only shipper name and address, general character of cargo, packages, weight, vessel, port of exit and destination ([103.31](https://www.law.cornell.edu/cfr/text/19/103.31)). CBP proposed mandatory electronic export manifests for vessels in Feb 2026, but that is a security rule, not a publication rule ([CBP CSMS](https://content.govdelivery.com/accounts/USDHSCBP/bulletins/409c771)). A finalized rail export-manifest rule (Aug 2026) explicitly exempts that data from disclosure ([FR 2026-17390](https://www.federalregister.gov/documents/2026/08/26/2026-17390/automated-commercial-environment-ace-electronic-export-manifest-for-rail-cargo)).

**Confidentiality (masking).** Importers, consignees and shippers can file a free certification that hides their name and address, plus their shippers' names, for **2 years** before renewal ([103.31](https://www.law.cornell.edu/cfr/text/19/103.31)). CBP processes about **12,000 confidentiality requests a year** ([FR 2020-10802](https://www.govinfo.gov/content/pkg/FR-2020-05-22/html/2020-10802.htm)). In Panjiva's US import data, **consignee IDs were missing on 12–17% of records and shipper IDs on 31–34%** in 2019–2021. **Value was missing on about 64–68%**. **HS codes are imputed** from free-text descriptions (BOLs don't carry HS) and are missing on only about 4–7% ([Flaaen et al., Fed FEDS 2021-066, Table 3](https://www.federalreserve.gov/econres/feds/files/2021066pap.pdf)).

**Coverage gaps (important):**
- **Ocean only.** Vessel trade is about **50% of US import value** (64% for China, 72% for Japan, 52% for Germany). Mexico and Canada are mostly missing because land trade isn't covered. **Air cargo isn't in the public data at all** ([Fed paper](https://www.federalreserve.gov/econres/feds/files/2021066pap.pdf); [ecomcrew](https://www.ecomcrew.com/a-secret-weapon-for-doing-competitor-and-supplier-research/)).
- **No values.** You have to impute them, for example weight × Census unit value by HS10 and country.
- **NVOCC/forwarder consignees and trading-company shippers hide the real parties** ([ecomcrew](https://www.ecomcrew.com/a-secret-weapon-for-doing-competitor-and-supplier-research/)).

### 1.2 Incumbents and price points

| Vendor | Price (public or reported) | Positioning |
|---|---|---|
| ImportYeti | Free core; Pro ~$50/mo ($600/yr); 30-day pass $130; Enterprise from $1,000/org/mo ([GetApp](https://www.getapp.com/business-intelligence-analytics-software/a/importyeti/), [SoftwareAdvice](https://www.softwareadvice.com/bi/importyeti-profile/)) | US ocean BOL since 2015, SMB/Amazon sellers |
| ImportGenius | USA Essentials $229/mo, Pro $449/mo; Global Enterprise from $1,999/mo; API on enterprise ([pricing](https://www.importgenius.com/pricing), [API page](https://www.importgenius.com/features/api-integration)) | SMB-to-mid, logistics sales |
| Descartes Datamyne | USA Import $6,995/yr; Global $12,995–$19,995/yr ([Scribd price sheet](https://www.scribd.com/document/891384028/Datamyne-Global-US) via search) | Mid-market, global |
| Panjiva (S&P) | Quote only; "mid five figures annually" reported ([suppliers.ai](https://suppliers.ai/blog/importgenius-vs-panjiva)); redistribution restricted ([Flaaen BOL paper data note](https://www.aaronflaaen.com/uploads/3/1/2/4/31243277/bol.pdf)) | Enterprise, finance |
| Volza | $1,500 / $4,500 / $9,600 per yr ([suppliers.ai](https://suppliers.ai/alternatives/volza)) | Global exporters/SMB |
| Trademo | $12.5M seed; ~150 staff ([PRN](https://www.prnewswire.com/news-releases/global-supply-chain-intelligence-start-up-trademo-raises-12-5-million-seed-round-301421272.html), [crustdata](https://profiles.crustdata.com/company/trademo)) | Intel + sanctions + compliance |
| Sayari | ~$42M revenue; TPG majority investment up to $235M; CBP $7.8M contract ([search summary/Zoominfo, BusinessWire](https://www.businesswire.com/news/home/20240104260647/en/U.S.-Department-of-Labor-Selects-Sayari-to-Combat-Forced-Labor)) | Gov/enterprise risk graph |
| Altana | $322M raised, $1B valuation; CBP UFLPA contract ([Altana](https://altana.ai/resources/series-c-valuation), [Latka](https://getlatka.com/companies/altana.ai)) | Gov/enterprise |
| Flexport | Free tariff simulator; Feb 2026 AI "audit your broker" and refund prep ([BusinessWire](https://www.businesswire.com/news/home/20260226536552/en/Flexport-Launches-Technology-to-Automate-Tariff-Refunds)) | Broker + platform |
| Gaia Dynamics / TariffLens / GingerControl | Gaia self-serve $0–$1,399/mo; ACE-data tariff audit engine ([TariffLens compare](https://www.tarifflens.ai/blog/best-ai-hts-classification-tools-2026)) | Importer-side tariff tooling (needs the importer's own data) |
| Ubico, Freight Genie, Revenue Vessel | Unpublished ([Ubico](https://www.ubico.io/post/how-to-find-shippers-using-import-data), [Freight Genie](https://freightgenie.com/), [Revenue Vessel](https://www.revenuevessel.com/blogs/sites-like-importyeti)) | BOL-powered outbound for brokers/forwarders |

### 1.3 Where the gaps are

1. **Everyone sells search. Almost nobody sells a pre-computed answer pushed to the company it's about.** Gaia, Flexport and TariffLens all need the importer to onboard and upload ACE data. Nobody walks up cold with "here is your exposure, already computed from your public shipments". That is exactly the brothers' playbook.
2. **Policy churn is extreme and recurring.** In 2026 alone:
   - SCOTUS voided the IEEPA tariffs (20 Feb).
   - A 10% §122 surcharge ran until 24 July ([Global Trade Alert](https://globaltradealert.org/blog/from-ieepa-to-section-122)) and was struck down for three plaintiffs only ([Skadden](https://www.skadden.com/insights/publications/2026/05/us-trade-court-strikes-down-section-122-tariffs)).
   - New **§301 "forced-labor" tariffs of 10–12.5% on 60 economies (99.4% of imports)** have applied since 24 July and are already being challenged in court ([GTA](https://globaltradealert.org/blog/forced-labour-section-301-final-action), [USTR fact sheet](https://ustr.gov/about/policy-offices/press-office/fact-sheets/2026/july/fact-sheet-ustr-section-301-action-response-failure-60-economies-ban-imports-produced-forced-labor)).
   - §232 now applies to full customs value; HTS codes keep being added (428 codes in one action) and 14 more derivative categories were proposed on 6 Aug 2026 ([AFS](https://www.afslaw.com/perspectives/customs-import-compliance-blog/us-commerce-adds-428-hts-codes-section-232-steel-and), [search summary/Foley](https://www.foley.com/insights/publications/2026/05/what-every-multinational-should-know-about-the-new-rules-for-section-232-tariffs-on-steel-aluminum-and-copper-derivatives/)).
   - The UFLPA Entity List grew by 43 to 187 entities on 3 Aug 2026 ([Covington](https://www.cov.com/en/news-and-insights/insights/2026/08/dhs-expands-uflpa-entity-list-amid-intensifying-enforcement-landscape)).

   Every one of these events creates a fresh set of affected importers.
3. **Second-order money flows are under-served at the SMB end.**
   - **Bond insufficiencies:** 27,479 flagged in FY2025, worth about $3.6B ([Sourcing Journal/WWD](https://wwd.com/sourcing-journal/trade/cbp-customs-bond-insufficiencies-importers-tariffs-1238863074/)).
   - **Drawback:** CBP processed only about $0.9–1B a year (2011–2018 average $896M per [GAO-20-182](https://www.gao.gov/products/gao-20-182), via search summary) even though tens of thousands of firms both import and export.
   - **First-sale valuation:** worth 10–30% of dutiable value on eligible goods ([Carra Globe](https://carraglobe.com/first-sale-for-export/)).

   Licensed professionals capture this money. They need targeted leads, and the public data can identify likely candidates.
4. **Combining regulatory enforcement lists with the shipper→consignee graph is rare below the enterprise tier.** FDA Import Alerts, UFLPA additions and CPSC recalls all name *foreign firms*. BOL data maps those firms to *US importers*. Sayari, Altana and Kharon do this for governments and enterprises at £550k+/instance pricing ([search summary of UK G-Cloud listing](https://www.applytosupply.digitalmarketplace.service.gov.uk/g-cloud/services/497937330966590)). Nobody does it for a 40-person food importer.

### 1.4 Buyer universe (bottom-up counts)

- **US importers:** 240,535 identified in 2024; 94% of import value is attributable to 2.7% of them (500+ employees).
  - **47,306 importers have 20–499 employees.** That's the mid-size target band: 22,013 + 11,526 + 9,607 + 4,160.
  - 87,749 are wholesalers and 41,824 are manufacturers.
  - **87,016 companies both import and export** (the drawback pool).
  - Source: [Census Profile of US Importing & Exporting Companies, 2024](https://www.census.gov/foreign-trade/Press-Release/edb/edbrel2024.pdf).
- **About 330,000 importers of record paid IEEPA duties** ([tariffstool tracker](https://www.tariffstool.com/tariff-refund-tracker)). The gap from Census's 240,535 is mostly IORs Census can't match to companies.
- **Customs brokers:** about 11,000–11,400 active licenses ([customsbrokerindex](https://customsbrokerindex.com/blog/customs-broker-list-how-to-find/)) and roughly 2,500 brokerage firms ([directory](https://customsbrokerindex.com/blog/us-customs-broker-list-find-licensed/)).
- **FMC-licensed OTIs (NVOCC/OFF):** 9,078 ([FMC list](https://www2.fmc.gov/oti/NVOCC.aspx)). IBISWorld counts 75,407 freight-forwarding brokerages and agencies, a much wider definition ([IBISWorld](https://www.ibisworld.com/united-states/number-of-businesses/freight-forwarding-brokerages-agencies/1209/)).
- **FDA-regulated:** about 55,000 importers and 300,000 foreign facilities (search summary of FDA dashboard data, [FDA OII dashboards](https://datadashboard.fda.gov/oii/index.htm)). Registrar Corp alone claims 32,000+ clients ([Registrar](https://www.registrarcorp.com/about-us/)).

### 1.5 Complementary data (access, cost, terms)

| Source | Access | Cost | ToS / limits |
|---|---|---|---|
| Census International Trade API (HS10 × country × port × month: value, weight, mode) | `api.census.gov/data/timeseries/intltrade/imports/porths` ([Census](https://www.census.gov/data/developers/data-sets/international-trade.html), [data.commerce.gov](https://data.commerce.gov/time-series-international-trade-monthly-us-imports-port-and-harmonized-system-hs-code)) | Free (key) | Public domain; aggregate only, used here for unit values |
| HTS schedule + Ch. 99 (301/232/122) | USITC HTS / Federal Register / CBP CSMS | Free | Public |
| FDA Import Alerts / refusals | [accessdata.fda.gov](https://www.accessdata.fda.gov/cms_ia/importalert_189.html), [FDA Data Dashboard](https://datadashboard.fda.gov/oii/index.htm); API needs an OII Unified Logon key | Free | Public; dashboard datasets are yearly, alerts are live |
| CPSC recalls | SaferProducts.gov / Recalls API ([data.gov](https://catalog.data.gov/dataset/recalls-api)); includes manufacturer, importer, country | Free | Public |
| UFLPA Entity List | DHS ([DHS 2026-07-31](https://www.dhs.gov/news/2026/07/31/dhs-announces-addition-43-companies-uflpa-entity-list)); CBP UFLPA dashboard | Free | Public |
| FMC OTI list | [fmc.gov](https://www2.fmc.gov/oti/NVOCC.aspx), downloadable | Free | Public |
| AIS vessel positions | MarineTraffic/Spire (now Kpler): ~$100/mo per vessel up to enterprise; Spire ~$2–8k+/mo ([datadocked](https://datadocked.com/ais-api-providers), [usesentinel](https://usesentinel.io/blog/ais-data-providers-comparison)) | $$ | Commercial license; **not needed for any shortlisted idea** |
| Contact data | Apollo $49–$119/user/mo, 1–4k export credits, overage $0.20/credit ([Saleshandy](https://www.saleshandy.com/blog/apolloio-pricing/)) | $ | Vendor ToS; CAN-SPAM compliance on sends |
| LLM processing | Anthropic API: Sonnet 5.5 $2/$10 per M tokens in/out; Opus 5.5 $4/$20; Haiku 4.5 $1/$5 (Anthropic pricing as of 2026-09-25) | ~cents per brief | — |

**Data ToS reality check.** Panjiva is "subject to third party restrictions on its redistribution" ([Flaaen paper data appendix](https://www.aaronflaaen.com/uploads/3/1/2/4/31243277/bol.pdf)). ImportGenius's and ImportYeti's terms pages were blocked to automated fetch (403), so I couldn't verify them. **Assume subscription seats ban redistribution and scraping** (Apify scrapers of ImportYeti exist, but using them is a ToS risk). OEM or redistribution licenses typically need $50K+ minimums and 6–12 months of negotiation ([Explorium](https://www.explorium.ai/blog/data-for-gtm/b2b-data-api-resale-rights-licensing-what-product-builders-need-to-know-now-in-2026/)). **Recommended path:**
- **Phase 0 (validation):** use one ImportGenius or ImportYeti seat to research a few hundred prospects by hand, sending only *derived insights about the recipient's own shipments*, never raw records.
- **Phase 1:** buy the AMS feed directly from CBP so you own the dataset outright.

---

## 2. Candidate ideas

### Idea 1 — Tariff Exposure Brief + Monitor *(rank #1)*

**Pitch.** "You shipped 212 containers of HS 9403 from Vietnam last year. The 24 July §301 action adds about 12.5%, so roughly $410k a year of new duty." We send a free one-page brief built from public data, then sell a $199–$499/mo monitor that re-runs the exposure every time a tariff action drops.

**Data sources.**
- US BOL: importer, shipper, origin, weight, TEU and imputed HS. Access via CBP AMS direct (cost unknown; confirm by phone) or a vendor seat for phase 0 ($229–$449/mo; [ImportGenius](https://www.importgenius.com/pricing)).
- Census HS10 × country unit values, used to impute value (free API).
- HTS Chapter 99 / Federal Register for the 301, 232 and AD/CVD layers (free).

**Value-creating combination.** BOL shows *who* imports *what* from *where*, but has no values. Census shows *$/kg* by HS10 and origin, but no company names. The tariff schedule shows *the rate change*. Combined, they give a firm-level estimate of the duty delta that no single source contains. The incumbents with deeper data (Gaia, Flexport) need the importer to onboard. **We can compute it before first contact.**

**Buyer persona.** CFO, owner, or VP of supply chain at a 20–499-employee wholesaler or manufacturer that imports by ocean from Asia. These firms have no trade-compliance staff and depend on their broker.

**Willingness-to-pay evidence.**
- Tariff exposure assessments for small importers sell at **$2,500–$7,500** per project; consulting runs $150–$400/hr ([Importivity/Camtom search summary](https://importivity.com/blog/tariff-consulting-turns-customs-complexity/)).
- Gaia charges up to **$1,399/mo** self-serve ([TariffLens compare](https://www.tarifflens.ai/blog/best-ai-hts-classification-tools-2026)).
- Trade-compliance staff cost real money: drawback/compliance specialists earn $57k–$93k, with postings up to $125–150k ([Glassdoor search summary](https://www.glassdoor.com/Job/united-states-duty-drawback-specialist-jobs-SRCH_IL.0,13_IN1_KO14,38.htm)).
- Customs-bond premiums are being forced up by tariffs ([Trucordia](https://www.trucordia.com/blog/how-tariff-changes-are-driving-up-u.s.-customs-bond-requirements)).

**Market size.**
- 47,306 importers with 20–499 employees ([Census 2024](https://www.census.gov/foreign-trade/Press-Release/edb/edbrel2024.pdf)). **(est.)** About 50–60% bring meaningful volume by ocean from tariffed origins, so **~25k reachable accounts**.
- **(est.)** At 2% penetration and $300/mo that's 500 accounts and **~$1.8M ARR**. The serviceable ceiling at 10% is about $9M ARR.

**Deliverable and pricing.**
- Free PDF/HTML brief as the hook.
- Monitor at $199/mo (one entity, alerts on every tariff action, quarterly exposure re-cast, bond-sufficiency estimate) or $499/mo (multiple entities, competitor benchmark, first-sale/drawback flags).
- One-off "deep audit" at $1,500, with the importer's own ACE data uploaded. **Recurring: yes.**

**Automation pipeline.**
1. **Find prospects:** filter BOL by consignee (≥N TEU/yr, tariffed origin, not masked) and resolve the company domain.
2. **Build deliverable:** imputed value, then rate stack, then delta. Claude writes a plain-English brief with caveats.
3. **Personalized outreach:** an email that cites three specific facts from the recipient's own shipments, plus a brief link.
4. **Handle replies:** Claude triages, answers methodology questions and books a call or starts a trial.
5. **Deliver and renew:** a cron job re-runs on every Federal Register or CSMS tariff notice and pushes alerts; renewals are automatic.

**% automatable:** about 85%. **Human touchpoints:**
- QA of HS imputation on each new vertical.
- Sales calls for the $499 tier.
- An annual review of rate logic by a licensed broker or attorney.

**GTM, first 90 days.**
- **Days 1–30:** pick two verticals (furniture HS 94; outdoor/sporting goods HS 95). Build the rate engine and hand-verify 50 briefs.
- **Days 31–60:** send 2,000 briefs and target a 1–2% trial conversion **(est.)**.
- **Days 61–90:** convert trials, publish a free public "tariff hit list by HS" page for SEO, and partner with 2–3 customs brokers who resell the monitor to their clients.

**Unit economics (est.).**

| Item | Estimate |
|---|---|
| Data | $500–$3,000/mo (seat → CBP feed) |
| LLM per brief | Under $0.20 (30k in / 3k out on Sonnet 5.5 ≈ $0.09) |
| Contact enrichment | ~$0.20 per contact ([Apollo](https://www.saleshandy.com/blog/apolloio-pricing/)) |
| Email infrastructure | ~$200/mo |
| CAC | ~$150–$400 (2,000 sends → ~10 paying, so outbound cost ≈ $1.5–4k) |
| Price | $200–$500/mo |
| Gross margin | ~85–90% |
| Payback | 1–2 months |

**Competitors and crowding.** Moderately crowded on the importer-onboarded side: Flexport, Gaia, TariffLens, GingerControl, and brokers' own advisories. The **pre-computed outbound approach is uncrowded**. **Competition score 5.**

**Legal and regulatory.**
- CAN-SPAM covers B2B email: honest headers and subjects, physical address, opt-out honored within 10 business days, penalties up to $53,088 per email ([FTC-based summary](https://iscoldemaillegal.com/blog/can-spam-act-explained/)).
- Keep the brief as **analysis, not customs advice**. Classification and filing for others is "customs business" that needs a broker license ([19 USC 1641](https://www.law.cornell.edu/uscode/text/19/1641)).
- Estimates must carry disclaimers. Don't republish raw manifest records, especially for masked firms. No TCPA exposure if there are no calls or SMS.

**Kill risks.**
1. **Accuracy.** Missing values plus imputed HS and unknown FTA/exclusion status can make briefs wrong. One embarrassing number kills trust. Mitigation: show ranges and methodology, and make "upload your entry summary to tighten this" the upsell.
2. **Policy whiplash cuts both ways.** If tariffs stabilize or get struck down, urgency fades (the §301 FL tariffs are already in court).
3. **Brokers and Flexport give similar alerts away free to their own clients.** Mitigation: sell through brokers (white-label) rather than against them.

---

### Idea 2 — Duty-Recovery Lead Engine for licensed partners *(drawback + first-sale + bond)* *(rank #2)*

**Pitch.** We find importers who are probably leaving money on the table and sell those leads, pre-qualified and with a computed estimate, to the licensed people who can recover it. There are three trigger types:
- **(a) Drawback candidates:** the same company both imports and exports goods in matching HS chapters.
- **(b) First-sale candidates:** the BOL shipper is a trading company or HK intermediary, not the factory, on goods from a high-tariff origin.
- **(c) Bond-insufficiency candidates:** estimated trailing-12-month duties exceed about 10× the minimum bond band.

**Data sources.**
- US import BOL plus outbound manifest shipper data (public subset under [103.31](https://www.law.cornell.edu/cfr/text/19/103.31)).
- Census unit values.
- Tariff stack.
- A trading-company name classifier (Claude), flagging names containing "Trading", "Imp & Exp", or an HK/SG address.

**Value-creating combination.**
- Import ∩ export by the same entity in related HS gives a drawback probability (87,016 firms both import and export: [Census](https://www.census.gov/foreign-trade/Press-Release/edb/edbrel2024.pdf)).
- Shipper type × origin tariff × volume gives a first-sale savings estimate (10–30% of dutiable value on eligible goods: [Carra Globe](https://carraglobe.com/first-sale-for-export/), [newbuyingagent](https://www.newbuyingagent.com/resources/first-sale-rule-explained-how-to-legally-reduce-tariffs-on-chinese-goods-in-2026)).
- Duty estimate vs. the 10%/$50k bond rule gives a bond flag ([gingercontrol](https://gingercontrol.com/tools/customs-bond-calculator)).

**Buyer persona.**
- Business-development heads at drawback specialists: C.J. Holt, Zollback, Charter, Descartes drawback ([Zollback list](https://www.zollback.com/blog/duty-drawback-companies)).
- First-sale and valuation consultants and customs law firms.
- Customs-bond agencies and MGAs. Avalon writes about 35% of continuous bonds on file with CBP ([Avalon](https://www.avalonrisk.com/customs-bonds)); Roanoke handles 200,000+ bonds a year ([Roanoke](https://www.roanokegroup.com/solutions/transportation-bonds/)).

**Willingness-to-pay evidence.**
- Drawback providers keep **15–25% contingency** (and up to "50/50" at traditional firms) on refunds ([LightSource](https://lightsource.ai/blog/duty-drawback-practical-guide-recovering-import-duties-2026), [Zollback](https://www.zollback.com/blog/duty-drawback-companies)).
- First-sale setup costs **$7,500–$15,000** ([search summary of Peacock/Carra](https://www.peacocktariffconsulting.com/customs-valuation-consultant/)).
- 27,479 bond insufficiencies in FY2025, worth about $3.6B ([WWD](https://wwd.com/sourcing-journal/trade/cbp-customs-bond-insufficiencies-importers-tariffs-1238863074/)). A $50k bond costs $250–$1,000/yr in premium ([FreightFigures](https://www.freightfigures.com/articles/customs-bond-guide)), so a single bond lead is low value but volume is high.
- One qualified drawback client is worth tens of thousands of dollars to the provider.

**Market size.**
- **Buyers:** **(est.)** about 50–150 drawback, first-sale and bond firms worth selling to.
- **(est.)** 30 partners × $2,500/mo retainer ≈ **$900k ARR**. Plus per-lead sales at $150–$750 per qualified, appointment-set lead.
- **Lead pool:** 87k import-export firms, plus tens of thousands of China-origin importers buying through intermediaries.

**Deliverable and pricing.** A monthly feed of scored accounts with an evidence pack (shipment summary, estimated recoverable dollars), with optional appointment setting. **Price per qualified lead, or a flat monthly retainer. Never a percentage of recovery** (see legal below). **Recurring: yes (retainers).**

**Automation pipeline.**
1. **Find prospects:** batch scoring on the BOL graph.
2. **Build deliverable:** a per-prospect evidence pack.
3. **Personalized outreach:** email to the *importer*, offering a free "money-left-on-table" estimate on behalf of a named partner, or to the partner's BD team with the pack.
4. **Handle replies:** Claude qualifies (exports confirmed? annual duty paid?) and books the partner's calendar.
5. **Deliver and renew:** CRM push; monthly retainer invoicing.

**% automatable:** about 75%. **Human touchpoints:**
- Partner contracting (by hand).
- Dispute handling on lead quality.
- Legal review of the referral structure.

**GTM, first 90 days.**
- Interview 10 drawback and first-sale firms.
- Pilot free with 2 of them (50 leads each).
- Convert to paid on proven meeting-to-engagement rates.
- Add bond agencies after the October 2026 FY data cycle.

**Unit economics (est.).** CAC for partners ~$1–3k (founder-led sales). Price $2–5k/mo per partner. Data and LLM costs are shared with Idea 1. Gross margin ~80%.

**Competitors and crowding.** Drawback providers market themselves heavily (Zollback, Tariff Refund HQ, Passport) but generate leads with content and SEO, not data. Data-driven lead supply to them is **largely uncontested**. **Competition score 6.**

**Legal and regulatory.**
- **[19 CFR 111.36(a)](https://www.customsmobile.com/rulings/docview?doc_id=114404&highlight=HQ+114654) bars a broker from any arrangement where fees for customs business, which includes drawback, "inure to the benefit of an unlicensed person". Unlicensed persons conducting customs business face penalties up to $10,000 per violation ([19 USC 1641](https://law.justia.com/codes/us/2006/title19/chap4/subtitleiii/partvi/sec1641/)).** Use flat marketing fees not tied to recovery, and have counsel confirm.
- Law-firm partners: ABA Model Rule 7.2 bars paying for recommendations but allows paying lead generators that don't recommend. Structure it as a fixed per-lead fee.
- Surety referrals: many states bar sharing commissions with unlicensed persons. Flat lead fees are usually allowed; confirm state by state.
- CAN-SPAM applies to all outbound.

**Kill risks.**
1. The fee-structure restriction caps upside: no contingency share means we never capture the big recovery dollars.
2. False positives. Drawback needs documentary proof of exports and substitution, and first sale needs factory invoices plus a genuine middleman. Many leads will fail diligence.
3. Policy: the **Last Sale Valuation Act** (introduced Feb 2026, in Senate Finance) would abolish first sale ([KPMG](https://kpmg.com/us/en/taxnewsflash/news/2026/02/tnf-us-senators-introduce-bill-to-change-computation-of-import-duties.html)). Separately, GAO and DHS-OIG findings on weak drawback controls could tighten claims ([oversight.gov](https://www.oversight.gov/reports/lack-internal-controls-could-affect-validity-cbps-drawback-claims)).

---

### Idea 3 — Forwarder & Customs-Broker Trigger Engine *(angle b; rank #3)*

**Pitch.** Done-for-you pipeline for small and mid freight forwarders, NVOCCs and customs brokers. Each week we hand them importers on their lanes with a *trigger*: a new importer, a volume spike, a lane or port shift, a forwarder or NVOCC change on the BOL, a new origin country after a tariff shift, or a bond-insufficiency risk. Each lead comes with a drafted personalized email.

**Data sources.** BOL (consignee, notify party, carrier, port, origin, TEU), the FMC OTI list (identifies NVOCC consignees and the competitor forwarder: [FMC](https://www2.fmc.gov/oti/NVOCC.aspx)), and the tariff stack.

**Value-creating combination.** A time-series diff of each importer's routing joined to the forwarder that currently handles them (notify party or NVOCC). That surfaces "importer X moved from forwarder A to B" and "importer Y started shipping from Vietnam into Savannah", which are the moments when a forwarder can win the account.

**Buyer persona.** Owner or sales manager at a 5–100-person forwarder or broker. Their BD staff cost $83k base plus ~$23k commission ([Glassdoor DHL BDM](https://www.glassdoor.com/Salary/DHL-Global-Forwarding-Freight-Business-Development-Manager-Salaries-E32266_D_KO30,58.htm)) and prospect by hand from PIERS, Datamyne or ImportGenius ([search summary](https://www.importgenius.com/industries/logistics-freight-forwarding)).

**Willingness-to-pay evidence.** ImportGenius explicitly sells to logistics firms at $229–$1,999+/mo ([pricing](https://www.importgenius.com/pricing)). Datamyne charges $6,995+/yr. Gumroad "shipper lead" lists sell ([gumroad](https://freightleads.gumroad.com/l/shipper-leads-2025)). Ubico and Freight Genie exist as venture-backed or commercial products.

**Market size.** 9,078 OTIs, about 2,500 brokerage firms, and a 75k "forwarding agencies" upper bound ([FMC](https://www2.fmc.gov/oti/NVOCC.aspx), [customsbrokerindex](https://customsbrokerindex.com/blog/us-customs-broker-list-find-licensed/), [IBISWorld](https://www.ibisworld.com/united-states/number-of-businesses/freight-forwarding-brokerages-agencies/1209/)). **(est.)** 5% of ~11k core firms at $500/mo ≈ **$3.3M ARR**.

**Deliverable and pricing.** $300–$1,000/mo by lanes and volume, or $150–$400 per booked meeting. **Recurring: yes.**

**Automation pipeline.**
1. **Find prospects** (forwarders): from the FMC list plus their own BOL footprint. We know which lanes each forwarder runs.
2. **Build deliverable:** a sample of 10 live triggers on *their* lanes.
3. **Personalized outreach:** to the forwarder, built around that sample.
4. **Handle replies:** Claude demos, answers questions and starts a trial.
5. **Deliver and renew:** a weekly trigger feed plus drafted emails, monthly billing.

**% automatable:** about 90%. **Human touchpoint:** occasional account management.

**GTM, first 90 days.** Target NVOCCs in 2–3 port metros (LA/LB, NY/NJ, Savannah). Offer 30 free triggers and convert at the end of the trial. Partner with forwarder associations or newsletters.

**Unit economics (est.).** CAC $300–$800. Price $500/mo. Gross margin 85%+. Churn is the big risk: lead tools typically lose 3–6% a month **(est.)**.

**Competitors and crowding.** **Crowded:** ImportGenius, Datamyne, Ubico, Freight Genie, Revenue Vessel, Volza, plus generic AI SDR tools. **Competition score 2.**

**Legal and regulatory.** CAN-SPAM covers both us and our customers' sends. Forwarder emails to importers make importers *more* likely to file confidentiality certifications, which gradually erodes the data source. No broker-licensing issue, since this is sales, not customs business.

**Kill risks.**
1. Crowded, and the importers on the receiving end are already saturated with forwarder cold email, so response rates decay.
2. High churn typical of lead-gen tools.
3. Differentiation is hard to defend: anyone with the same data can copy the triggers.

---

### Idea 4 — Regulatory-Contagion Alerts *(FDA Import Alert / UFLPA / CPSC × BOL graph)* *(rank #4)*

**Pitch.** When FDA puts a foreign facility on "Red List" detention-without-examination, DHS adds an entity to the UFLPA list, or CPSC recalls a product from a factory, we tell **every US importer that has received shipments from that firm**. We also tell the professionals who can help them: FDA consultants, private labs, and customs attorneys.

**Data sources.**
- FDA Import Alerts, live and public ([example IA 66-40](https://www.accessdata.fda.gov/cms_ia/importalert_189.html)).
- UFLPA Entity List: 187 entities after the 3 Aug 2026 addition of 43 ([DHS](https://www.dhs.gov/news/2026/07/31/dhs-announces-addition-43-companies-uflpa-entity-list), [Mallory](https://www.mallorygroup.com/blog-posts/uflpa-entity-list-hits-187-entities-largest-ever-expansion-includes-companies-located-outside-xinjiang)).
- CPSC Recalls API with manufacturer, importer and country fields ([data.gov](https://catalog.data.gov/dataset/recalls-api)).
- BOL shipper→consignee graph.

All of these are free except the BOL data.

**Value-creating combination.** The enforcement lists name foreign firms. Only BOL data shows which US companies buy from them. Fuzzy matching on the names (Claude plus addresses) produces the "exposed importer" list. **This combination is genuinely new value below enterprise tier.**

**Buyer persona.**
- **(A) Professional services (lead buyers):** FDA regulatory consultants; Registrar Corp has 32k+ clients and about $30–47M revenue ([Registrar](https://www.registrarcorp.com/about-us/), [Owler/Zoominfo search summary](https://www.zoominfo.com/c/registrar-corp/44058224)). Also private labs that test shipments for DWPE release (5 consecutive clean shipments are needed: [thefdaexpert](https://thefdaexpert.com/blog/fda-import-alerts-detention-without-physical-examination-explained/)) and customs and forced-labor attorneys.
- **(B) Importers (subscription):** QA and compliance leads at food, supplement and cosmetic importers, and at apparel or electronics importers sourcing via China.

**Willingness-to-pay evidence.** UFLPA detentions take 90+ days to resolve ([search summary](https://kisunshipping.com/uflpa-enforcement-2026-china-importers-compliance-guide/)). 13,000+ shipments worth about $229M were detained since Jan 2025, 63% of them denied entry ([search summary](https://www.kelleydrye.com/viewpoints/blogs/trade-and-manufacturing-monitor/u-s-government-announces-largest-expansion-of-the-uflpa-entity-list-in-history-continues-focus-on-forced-labor-trade-enforcement)). An entire consulting industry sells DWPE removal ([fdahelp](https://www.fdahelp.us/fda-detention-dwpe-removal/), [Certified Labs](https://certified-laboratories.com/blog/fda-import-alerts-how-to-get-off-a-red-list/)). Sayari has about $42M revenue doing enterprise-grade versions of this.

**Market size.**
- **Lead buyers:** **(est.)** 200–500 consultancies, labs and law firms. At 40 paying × $1,500/mo ≈ **$720k ARR**.
- **Importer subscription:** 55k FDA importers. **(est.)** 0.5% × $99/mo ≈ $330k ARR.
- **Overall:** a modest market.

**Deliverable and pricing.** Real-time alert feed plus exposure lists. $500–$2,500/mo for professional buyers; $49–$149/mo per importer for supplier-watchlist monitoring. **Recurring: yes.**

**Automation pipeline.**
1. **Find prospects:** a daily diff of the enforcement lists.
2. **Build deliverable:** BOL match and exposure brief.
3. **Personalized outreach:** to the exposed importer ("your supplier X was added on 3 Aug") and/or to partner professionals.
4. **Handle replies:** Claude triage and routing to the partner.
5. **Deliver and renew:** watchlist monitoring.

**% automatable:** about 85%. **Human touchpoints:** entity-match review (false positives are costly), plus partner contracting.

**GTM, first 90 days.** Backtest the August 2026 UFLPA additions and the last 90 days of FDA Import Alert additions, and publish anonymized "N US importers exposed" research for PR. Pilot with 3 FDA consultancies and 2 trade law firms.

**Unit economics (est.).** Data is almost all free apart from BOL. CAC $500–$2k for professional buyers. Gross margin about 90%.

**Competitors and crowding.** Sayari, Altana, Kharon and Exiger dominate the enterprise end. Nobody does event-driven, SMB-priced, outbound versions. **Competition score 8.**

**Legal and regulatory.**
- **Defamation risk** if we mis-match an importer to a sanctioned or forced-labor entity. Use careful "shipments from an entity with a matching name" language plus human review.
- CAN-SPAM applies.
- Law-firm lead rules: ABA Rule 7.2, fixed fees only.

**Kill risks.**
1. Low event frequency per vertical. UFLPA detentions dropped sharply after Jan 2025 ([search summary of CBP dashboard trend](https://www.cov.com/en/news-and-insights/insights/2026/08/dhs-expands-uflpa-entity-list-amid-intensifying-enforcement-landscape)), so urgency is episodic.
2. Name-matching quality on Chinese and Indian firm names. Shippers are often trading companies, so exposure is ambiguous.
3. Importers usually learn at detention anyway; the window to be useful may be only days.

---

### Idea 5 — Competitor Sourcing-Shift Monthly *(angle a; the seed idea; rank #5)*

**Pitch.** "Your top 5 competitors' sourcing this month": for a niche such as outdoor furniture, pet products or bike parts, mid-size importers get a monthly Claude-written report. It covers which competitor added a Vietnamese supplier, who is shrinking, new entrants, and what each move implies for tariff cost.

**Data sources.** BOL; Census HS10 trends for niche-level context; the tariff stack.

**Value-creating combination.** BOL company-level moves plus Census market totals (share estimates) plus tariff deltas (whether the competitor gained a cost advantage).

**Buyer persona.** Owner, CEO or head of sourcing at a 20–200-employee importer in a defined niche, and also sourcing agents and private-equity operating partners in consumer products.

**Willingness-to-pay evidence.**
- **Weak at SMB level, because ImportYeti gives the raw data away free** and power users pay only $50/mo for Pro ([GetApp](https://www.getapp.com/business-intelligence-analytics-software/a/importyeti/)).
- Mid-market competitive intelligence does command money: Klue and Crayon median around **$30k/yr** ([Vendr via search](https://caelian.ai/blog/klue-vs-crayon-2026)), but that is SaaS-focused.
- Competitive intelligence analysts earn $77k–$120k ([ZipRecruiter](https://www.ziprecruiter.com/Jobs/Competitive-Intelligence-Analyst)).
- **Why anyone pays us when ImportYeti is free:**
  - The buyer doesn't want search. They want someone else to watch 30 competitors monthly, de-duplicate the entity aliases, read the masked-shipper gaps, and translate it all into "what this means".
  - ImportYeti's free tier doesn't do Census market-share context or tariff deltas.
  - It costs the owner's time, about 4–8 hrs/mo **(est.)**.

  That is a convenience premium, so price it at $99–$299/mo, not $2k.

**Market size.** **(est.)** 47k mid-size importers, of which perhaps 10k are in niches with clear competitor sets. 2% × $149/mo ≈ **$360k ARR**. The per-niche model makes it a portfolio of micro-markets.

**Deliverable and pricing.** Monthly PDF plus email alerts. $99–$299/mo by niche; a $1,500 one-time "competitive sourcing map" for PE diligence. **Recurring: yes, but churn-prone.**

**Automation pipeline.**
1. **Find prospects:** cluster consignees by HS and description to build niches.
2. **Build deliverable:** an auto-generated niche report with the recipient highlighted.
3. **Personalized outreach:** "here's where you rank against 4 named competitors".
4. **Handle replies:** Claude.
5. **Deliver and renew:** monthly cron.

**% automatable:** about 95%. **Human touchpoint:** niche entity-resolution QA.

**GTM, first 90 days.** Launch 3 niches. Send free month-one reports to every mid-size importer in each niche. Convert 2–3%.

**Unit economics (est.).** CAC $200–$500. Price $150/mo. Gross margin 90%. Churn likely 5%+/mo.

**Competitors and crowding.** ImportYeti (free), ImportGenius, Panjiva, plus Amazon-seller tools. **Competition score 4.**

**Legal and regulatory.** Reports describe *other* companies' shipments. That is legal, since the data is public, but it is a reputational risk for the competitors named. Respect masked records and don't try to unmask them.

**Kill risks.**
1. A free substitute exists.
2. The insight goes stale. Once you know your competitor's suppliers, the monthly delta is often "nothing changed", which drives churn.
3. Masking rises among the best competitors: 12k confidentiality requests a year, and consignee IDs missing on 12–17% of records ([FR 2020](https://www.govinfo.gov/content/pkg/FR-2020-05-22/html/2020-10802.htm), [Fed paper](https://www.federalreserve.gov/econres/feds/files/2021066pap.pdf)).

**Better use:** keep it as the *free hook* inside Idea 1's monitor, not as a stand-alone product.

---

### Idea 6 — Manifest Privacy Check *(rank #6)*

**Pitch.** "Your suppliers are visible to your competitors on ImportYeti. Here's the proof, and here's how to hide it." We run an automated exposure check and send the importer a pre-filled confidentiality certification that they submit themselves. Then we monitor for leakage on a recurring plan: renewal reminders every 2 years, and alerts on shipments under misspelled names or new entities that escape the mask.

**Data sources.** BOL (the exposure itself); CBP's online confidentiality application ([CBP](https://www.cbp.gov/trade/automated/electronic-vessel-manifest-confidentiality)).

**Value-creating combination.** Exposure evidence (competitor-visible supplier list) plus a filing workflow plus leak monitoring. Masking only applies to names exactly as certified, so misspellings and variants keep leaking.

**Buyer persona.** Owner or ops lead at a DTC brand or SMB importer that worries about supplier poaching.

**Willingness-to-pay evidence.** Brokers charge about **$298–$300** per request every 2 years ([usacustomsclearance](https://usacustomsclearance.com/product/manifest-confidentiality/), search summary). Customs Data Lock sells this for **$199/yr** ([customsdatalock](https://customsdatalock.com/blog/what-is-manifest-confidentiality-why-should-you-care)). CBP gets about 12k requests a year ([FR 2020](https://www.govinfo.gov/content/pkg/FR-2020-05-22/html/2020-10802.htm)).

**Market size.** **(est.)** 12k filers a year × ~$200 ≈ $2.4M total current spend, much of it done free by brokers or DIY. Realistic capture is **$100–300k ARR**. A small business.

**Deliverable and pricing.** $199/yr monitor, or $299 one-time plus $99/yr. **Recurring: weakly** (a 2-year cycle).

**Automation pipeline.** Exposure scan → brief → email → Claude answers → the customer self-files from a pre-filled form → renewal and leak cron. **% automatable:** about 95%.

**GTM, first 90 days.** Target DTC brands with recognizable consumer names in BOL data. Content and SEO on "how competitors see your suppliers".

**Unit economics (est.).** CAC must stay under $100, so outbound needs a ≥1% conversion. Gross margin 95%.

**Competitors and crowding.** Customs Data Lock, every customs broker, and free DIY. **Competition score 6.**

**Legal and regulatory.**
- **Only the importer, or its authorized employee or official, may certify.** The regulation doesn't explicitly allow third parties ([FR 2020-10802](https://www.govinfo.gov/content/pkg/FR-2020-05-22/html/2020-10802.htm)). We must be "software that helps you file", not the filer.
- Reputation: a business that monetizes the same data it teaches people to hide.

**Kill risks.**
1. Tiny market.
2. The filing is free and simple, so DIY substitutes.
3. Success shrinks the BOL coverage that all the other ideas depend on.

---

### Idea 7 — SMB Supplier-Risk / Forced-Labor Screening Subscription *(angle d; rank #7)*

**Pitch.** $99–$499/mo continuous screening of an SMB importer's supplier list. It checks suppliers against the UFLPA list, OFAC/BIS lists, FDA alerts and CPSC recalls. It also infers tier-1 exposure from BOL (who ships to you) and flags newly listed entities.

**Data sources.** Public lists (free); BOL; OFAC SDN and BIS Entity List (free).

**Value-creating combination.** The same graph match as Idea 4, but sold *defensively* to the importer rather than as leads.

**Buyer persona.** Compliance or ops manager at a 50–500-employee importer in apparel, electronics, solar or auto parts.

**Willingness-to-pay evidence.** Enterprise spend is proven: Altana enterprise pricing is £550k/instance/yr; Sayari has about $42M revenue. SMB spend is **unproven**. UFLPA detentions trended down after Jan 2025, and the new §301 "forced-labor" tariffs are country-wide rates that no screening can avoid ([Honigman](https://www.honigman.com/alert-3462)).

**Market size.** **(est.)** 10–20k importers in UFLPA high-priority sectors. 1% × $199/mo ≈ $360k ARR.

**Deliverable and pricing.** SaaS dashboard plus alerts. **Recurring: yes.**

**Automation pipeline.** Similar to Idea 4. About 85% automatable; entity resolution needs human QA.

**GTM, first 90 days.** Lead with an "August 2026 UFLPA additions: are your suppliers affected?" free check.

**Unit economics (est.).** CAC $300–$800. Gross margin 85%.

**Competitors and crowding.** Sayari, Altana, Kharon, Exiger, Trademo, Prewave, FRDM, and descartes/Visual Compliance for list screening, which is a commodity. **Competition score 3.**

**Legal and regulatory.** Defamation and false-positive risk. It is screening, not legal advice.

**Kill risks.**
1. Screening against lists is commoditized; trade-compliance suites bundle it free.
2. Real UFLPA defense needs tier-3+ tracing (cotton, polysilicon) that BOL data can't provide.
3. Low SMB urgency outside an active detention.

---

## 3. Ideas considered and rejected

| Idea | Why rejected |
|---|---|
| **IEEPA refund lead-gen / refund audits (angle c, IEEPA part)** | The window has mostly closed. CAPE launched 20 Apr 2026. By 11 Sep, $134.7B was accepted and $122B certified out of a ~$166B pool ([tariffstool](https://www.tariffstool.com/tariff-refund-tracker)). Phase 3 (from 6 Oct, $11.4B) is **limited to CIT plaintiffs who submitted their IOR by 30 July 2026** ([ALS](https://www.als-int.com/insights/posts/cape-phase-3-ieepa-refunds-litigation-requirement-2026/), [HKLaw](https://www.hklaw.com/en/insights/publications/2026/07/file-now-cits-order-confirms-only-importers-that-have-sued)). The field is saturated with law firms charging 15–25% and recovery firms charging 1.5–30% ([search summary](https://tariffrecoverygroup.com/)), plus Flexport and Gaia automation. Fee-sharing with brokers is barred ([111.36](https://www.customsmobile.com/rulings/docview?doc_id=114404&highlight=HQ+114654)) and with lawyers is restricted. **Keep watching:** a §122 or §301-FL refund wave would revive this. That is a feature inside Idea 1 (alert importers to preserve protest rights), not a business. |
| **Hedge-fund / alt-data shipping signals** | The buyers are real: alt-data spend ~$2.8B in 2025, and the average dataset is bought by only about 20 firms ([Neudata via search](https://www.neudata.co/blog/state-of-the-alternative-data-market-2026)). But Panjiva, ImportGenius and Descartes already supply BOL to funds. It needs ticker mapping, backtests, MNPI/compliance diligence and long sales cycles. That's a poor fit for an outbound-automation shop, and redistribution rights are needed. |
| **Re-selling raw BOL search (ImportYeti clone)** | ImportYeti is free with an unlimited 2015+ dataset ([mywifequitherjob](https://mywifequitherjob.com/importyeti/)), and a dozen paid incumbents exist. No moat. |
| **Supplier discovery for Amazon/DTC sellers** | ImportYeti is the default free tool for this audience. Very low WTP. |
| **AIS / port-congestion product** | Data is expensive and consolidated under Kpler (MarineTraffic + Spire: [search summary](https://datadocked.com/ais-api-providers)). Port congestion is widely published free (Descartes Global Shipping Report, port authorities). No firm-level edge. |
| **Industrial real-estate tenant leads from import growth** | Plausible combination (TEU growth plus consignee address gives warehouse demand), but I found no evidence that CRE brokers buy this ([search](https://www.biscred.com/guides/industrial-real-estate)). Large brokerages have research teams. Park it as a later spin-off of Idea 3's data. |
| **Non-US customs data (LatAm, India, Vietnam)** | Volza, ExportGenius and Eximpedia sell it cheaply ($1.5–9.6k/yr, [Volza](https://suppliers.ai/alternatives/volza)). Quality and legality vary by country. Out of scope for a first product. |
| **Stand-alone customs-bond lead business** | The evidence is strong: 27,479 insufficiencies, and Avalon writes ~35% of continuous bonds. But a single lead is worth little ($250–$1,000 premium on a $50k bond), and state insurance referral rules apply. Folded into Ideas 1 and 2 as a signal. |

---

## 4. Ranked shortlist

Scores run 1–10 (10 is best; for Competition, 10 means blue ocean). Overall is a judgment-weighted score, not a simple average: it double-weights willingness to pay and competition, because those are what killed most ideas in this lane.

| # | Idea | Market size | WTP | Data access | Automation | Competition | Recurring | Time to $1 | **Overall** | Confidence |
|---|---|---|---|---|---|---|---|---|---|---|
| 1 | Tariff Exposure Brief + Monitor | 8 | 7 | 6 | 8 | 5 | 7 | 7 | **7.0** | Medium-low (estimate accuracy is untested) |
| 2 | Duty-Recovery Lead Engine (drawback / first-sale / bond) for licensed partners | 5 | 8 | 6 | 7 | 7 | 6 | 6 | **6.4** | Medium-low (legal fee structure; lead precision) |
| 3 | Forwarder / Broker Trigger Engine | 7 | 7 | 7 | 9 | 2 | 8 | 7 | **5.9** | Medium (WTP proven, but crowded) |
| 4 | Regulatory-Contagion Alerts (FDA / UFLPA / CPSC × BOL) | 4 | 6 | 7 | 8 | 8 | 6 | 5 | **5.8** | Low (demand unproven; episodic) |
| 5 | Competitor Sourcing-Shift Monthly (seed idea) | 5 | 3 | 7 | 9 | 4 | 6 | 7 | **5.0** | Medium (ImportYeti caps WTP) |
| 6 | Manifest Privacy Check | 2 | 5 | 8 | 9 | 6 | 4 | 8 | **4.8** | Medium |
| 7 | SMB Forced-Labor / Supplier-Risk Screening | 4 | 3 | 7 | 7 | 3 | 7 | 5 | **4.3** | Medium |

### Recommendation

Build **one data spine** (BOL + Census unit values + live tariff stack + enforcement lists + FMC list) and launch **Idea 1** first, because it is the most direct copy of the brothers' "build it before you pitch it" model.

Run **Idea 2** as a second revenue line on the same spine once 2–3 licensed partners have signed flat-fee agreements, after counsel reviews them against 19 CFR 111.36.

Use Idea 5's report as the free hook and Idea 4's alerts as a feature, not as separate companies.

**Do not lead with the seed idea:** "competitor switched suppliers" alone loses to free ImportYeti.

**Validate before building:**
1. Get a CBP NFC quote for the AMS data feed.
2. Hand-build 50 Tariff Exposure Briefs and have 2 licensed brokers check them for accuracy.
3. Send 500 and measure reply and trial rates. Go/no-go threshold: ≥1% trial conversion **(est.)**.
