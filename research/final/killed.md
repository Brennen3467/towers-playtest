# Appendix: Considered and killed / downgraded

*Compiled from lane reports 01–15 and verifier reports verify-1 to verify-5 (all dated 2026-10-01). No new research was done. Every figure in the tables comes from those files.*

## Counts

| Measure | Count |
|---|---|
| Ideas considered across lanes 01–15 | **333** |
| Shortlisted (scored) by a lane | **110** |
| Rejected outright by a lane (listed in its "considered and rejected" table) | **223** |
| Shortlisted ideas independently verified by verify-1 to verify-5 | **33** unique lane ideas (35 verdict entries, because verify-1 and verify-5 both re-checked lane 01 #1 and #2) |
| Verifier verdict: CONFIRMED | **0** |
| Verifier verdict: WEAKENED | **28** unique ideas (30 verdict entries) |
| Verifier verdict: KILLED | **5** (Prop 65 Next Defendant; OSHA SST predictor; FL elevator Conveyance Intel; restaurant commission-leak site; drawback discovery with broker contingency split) |

**How to read the counts**
- Counts are per-lane entries and are not de-duplicated. Some ideas appear in more than one lane. Examples: the restaurant inspection → pest-vendor router (lanes 03 and 04), ADA website-suit plays (lanes 03, 04, 08 and 09) and trucking insurance renewal data (lanes 04, 09 and 10).
- One verdict sometimes covers several lane ideas. verify-3 merged 07-B with 11-#1. verify-5 bundled 09-#1 with 09-#2, and its trucking verdict covers 04, 09 and 10.
- The round-2 lanes (12–15, 25 shortlisted ideas) ran after verify-1 to verify-5 and were not independently verified. Each was attacked by the lane's own sub-agents, and their post-check scores are shown in those tables as "lane self-check".
- Lane scores are each lane's own overall score, out of 10. Some lanes used an unweighted mean and others a judgment-weighted score. For lanes 12–15 the score shown is the post-self-check score.
- "n.i.v." means not independently verified.

## Cross-cutting failure patterns the verifiers identified

1. **"No competitor found" was wrong almost every time.**
   - verify-3: "every write-up said something like 'no direct competitor found.' In every case one existed."
   - Example: Prop 65 catalog matching was claimed as uncrowded, but Prop65Radar is live at about $29 (verify-2).
   - Example: Actable already sells a "Practice Radar" to billing firms for $39/mo (verify-4).
2. **Raw public data is commoditized, and near-zero usage of the cheap resellers signals weak demand.**
   - Restaurant-inspection lead actors sell at $5–10 per 1,000 rows and have 1 monthly active user each (verify-2).
   - The revalidation-list, new-NPI, USPTO and CA unclaimed-property actors have about 2–57 users (verify-4).
3. **The data was shallower than claimed, and some load-bearing fields do not exist.**
   - TX TDLR open data has no license issue date (verify-1, verify-5).
   - The CMS revalidation list has no addresses, so an address-mismatch check cannot be computed (verify-4).
   - Bills of lading carry no values or HTS codes (verify-1).
   - In the FL condo CSV, "managing entity" is the association itself (verify-3).
4. **Wrong buyer, or a buyer without liability or leverage.**
   - Prop 65 multi-brand retailers are mostly not the duty-holder under 27 CCR §25600.2 and can cure within 5 days (verify-2).
   - A micro-contractor's GL commission of about $107–160 a year cannot pay for a $150–250 meeting (verify-2).
5. **The trigger arrives after the purchase decision.**
   - A single-audit corrective action plan is already written and filed when the finding goes public (2 CFR 200.511(c)) (verify-3).
   - SRF-listed projects already have an engineer, because a preliminary engineering report is required to get listed (verify-3).
   - The FMCSA Motus cutover removed future-dated cancellations from the public bulk data (verify-5).
6. **Licensing and fee-split rules block the contingency or revenue-share model.**
   - A drawback contingency split is barred by 19 CFR 111.36(b) and CBP ruling H276784 (verify-1).
   - A 50/50 unclaimed-property split with CPAs is barred by FL §717.1322 and CA B&P 5061 (verify-4).
   - Texas Occ. Code 1152 reaches anyone who "assists" a property-tax consultant (verify-3).
7. **The outbound channel is scam-adjacent, and reply rates are far below the modeled conversion.**
   - MACs warned in Jan 2026 about fraudulent Medicare enrollment letters (verify-4).
   - USPTO impersonation scams are ongoing (verify-4).
   - Healthcare cold email gets about 0.56–0.6% replies against the 2% paid conversion assumed in lane 06 (verify-4). Owners and founders reply at 0.57% (verify-1).
8. **Platforms and agencies give the deliverable away free, and tailwinds were overstated.**
   - DoorDash's Starter tier includes a free branded site with commission-free ordering (verify-5).
   - BrightLocal includes AI-visibility tracking from $31/mo (verify-5).
   - BIL water money ended in FY26, and the FY27 request cuts the SRFs to $305M (verify-3).
   - About 390 OSHA SST inspections a year against about 390K filers is a 0.1% base rate (verify-2).

---

## Lane 01: M&A deal origination (16 ideas)

| Idea | Lane score | Verifier verdict and revised score | Reason it failed or was downgraded |
|---|---|---|---|
| #1 Vertical Roll-up Target Intelligence ("SuccessionMap") | 6.4 | WEAKENED → 3.5 (verify-1); WEAKENED → 4.0 (verify-5) | TX TDLR file has no issue date. Inven and TradeBridge sell retirement/age filters. DealSource sells succession-scored sourcing at $4,000/mo. |
| #2 Flat-fee add-on origination (seed idea) | 6.0 | WEAKENED → 3.0 (verify-1); WEAKENED → 4.5 (verify-5) | Priced above CAPTARGET ($2,000/mo) and Axia ($350/meeting, money-back). Owner reply rate 0.57%. YC's Q2Q, with the same pitch, is inactive. |
| #3 Sell-side mandate generation for brokers | 5.5 | n.i.v. | Brokers judge on closings that lag 6–12 months. ~$1.0B industry revenue across ~11K brokers means thin budgets. Hypergen from $4,500/mo. |
| #6 Strategic tuck-in radar | 5.0 | n.i.v. | Buyers are hard to identify (CAC $3–8K). Need is episodic. Competes with buy-side boutiques and CAPTARGET/SourceCo. |
| #4 Search-funder Deal Desk | 4.8 | n.i.v. | Searchers churn by design once they acquire. Kumo anchors at $30–149/mo. Interns cost $23–42/hr. DIY Clay/Instantly stacks. |
| #5 Wealth-advisor liquidity signals | 4.5 | n.i.v. | Aidentified starts at $49/mo with 16 wealth-event alerts. Advisors want events now, not 12–36-month predictions. |
| #7 AI-native micro sell-side bank | 3.5 | n.i.v. | Success fees need §15(b)(13) compliance plus state registration or a real-estate licence. Non-recurring. OffDeal has raised $17M. |
| Success-fee finder for PE (unregistered) | — | rejected by lane | §29(b) makes contracts voidable. ~27 states lack an aligned M&A broker exemption, so the fee may be uncollectable. |
| AI-voice cold-calling of owners | — | rejected by lane | FCC Feb-2024 ruling treats AI voices as "artificial" under TCPA. Prior express consent required; class-action exposure. |
| Owner-age scoring from voter files | — | rejected by lane | 23 states forbid commercial use. Misuse is a Class C felony in WA. |
| LinkedIn-scraped tenure/age data | — | rejected by lane | hiQ lost on breach of contract: permanent injunction plus $500K. |
| Horizontal private-company database (Grata competitor) | — | rejected by lane | Datasite consolidated Grata, Sourcescrub and Blueflame with $500M from CapVest. |
| Two-sided deal marketplace (Axial competitor) | — | rejected by lane | Network effects favor Axial, the SourceCo marketplace and BizBuySell. Success-fee legal issues; cold start on both sides. |
| Broken-deal / re-trade recycler | — | rejected by lane | The data is private and held by bankers. No access path. |
| EU/UK owner outreach | — | rejected by lane | GDPR legitimate-interest balancing and PECR limits on B2B email to sole traders. Adds cost, no advantage. |
| Generic "AI SDR for PE" agency | — | rejected by lane | Saturated (Hypergen, Danish Lead Co, Axia, Inboxsniper, Puzzle Inbox). 3.43% average reply rate. No moat. |

## Lane 02: Trade, shipping and supply-chain intelligence (15 ideas)

| Idea | Lane score | Verifier verdict and revised score | Reason it failed or was downgraded |
|---|---|---|---|
| #1 Tariff Exposure Brief + Monitor | 7.0 | WEAKENED → 3.5 (verify-1) | BOLs lack values and HTS, so dollar figures may be 2–5× off. Datamyne, Altana, Flexport and Gaia already sell tariff-exposure tools. |
| #2 Duty-Recovery Lead Engine (drawback/first-sale/bond) | 6.4 | WEAKENED → 3.0 (verify-1) | CBP H276784 and 19 CFR 111.36 block per-lead or outcome-linked fees. Only a flat retainer survives. No evidence drawback firms buy leads. |
| #3 Forwarder / customs-broker trigger engine | 5.9 | n.i.v. | Crowded: ImportGenius ($229–1,999+/mo), Datamyne ($6,995/yr), Ubico, Freight Genie, Revenue Vessel. Lead-tool churn est. 3–6%/mo. |
| #4 Regulatory-contagion alerts (FDA/UFLPA/CPSC × BOL) | 5.8 | n.i.v. | Episodic: UFLPA detentions fell after Jan 2025. Fuzzy matching of Chinese/Indian names; defamation risk. Sayari/Altana own enterprise. |
| #5 Competitor Sourcing-Shift Monthly (seed idea) | 5.0 | WEAKENED → 4.0 (verify-5) | ImportYeti is free (Pro ~$50). Shipment alerts are commoditized. Consignee masking runs 8–35%. CBP feed price unknown. |
| #6 Manifest Privacy Check | 4.8 | n.i.v. | Tiny market (~12K filings/yr). Filing is free and DIY; Customs Data Lock $199/yr. Erodes the BOL data the other ideas need. |
| #7 SMB forced-labor / supplier-risk screening | 4.3 | n.i.v. | List screening is commoditized and bundled free. SMB demand unproven. §301 forced-labor tariffs are country-wide, so no screening avoids them. |
| IEEPA refund lead-gen / refund audits | — | rejected by lane | $122B of ~$166B certified by 11 Sep 2026. Phase 3 limited to CIT plaintiffs who filed by 30 July. Law firms charge 15–25%. |
| Hedge-fund alt-data shipping signals | — | rejected by lane | Panjiva, ImportGenius and Descartes already supply funds. Needs ticker mapping, MNPI diligence and redistribution rights. |
| Raw BOL search (ImportYeti clone) | — | rejected by lane | ImportYeti is free with a 2015+ dataset, and a dozen paid incumbents exist. |
| Supplier discovery for Amazon/DTC sellers | — | rejected by lane | ImportYeti is this audience's default free tool. Very low willingness to pay. |
| AIS / port-congestion product | — | rejected by lane | AIS consolidated under Kpler (Spire ~$2–8K+/mo). Congestion data is published free. No firm-level edge. |
| Industrial real-estate tenant leads from import growth | — | rejected by lane | No evidence CRE brokers buy this. Large brokerages have their own research teams. |
| Non-US customs data (LatAm, India, Vietnam) | — | rejected by lane | Volza, ExportGenius and Eximpedia sell it at $1.5–9.6K/yr. Quality and legality vary by country. |
| Stand-alone customs-bond lead business | — | rejected by lane | A lead is worth only $250–1,000 of premium on a $50K bond. State insurance referral rules apply. |

## Lane 03: Public-records signals and combinations (19 ideas)

| Idea | Lane score | Verifier verdict and revised score | Reason it failed or was downgraded |
|---|---|---|---|
| #1 Contractor coverage X-date engine | 7.0 | WEAKENED → 4.0 (verify-2) | WA GL commission ~$107–160/yr is below the meeting fee. The $300–550/meeting source (VA Horizon) isn't credible. WA has no private WC. |
| #2 Restaurant violation-to-vendor router | 6.7 | WEAKENED → 3.5 (verify-2) | NYC requires every restaurant to hold a pest contract. Apify sells the same feed at $5–10/1K (1 MAU). Only 41 hood (10D) citations in Sep. |
| #3 Good-standing rescue (dissolved but operating) | 6.6 | n.i.v. | Category polluted by deceptive mailers (TN, GA, MS SOS warnings). CA B&P §17533.6 disclaimers apply; one AG complaint kills it; ~$150/yr recurring. |
| #4 ADA web-suit radar | 6.1 | n.i.v. | Crowded (accessiBe, UserWay, UsableNet). FTC fined accessiBe $1M. Lane judged it a feature for the website business, not a lane. |
| #5 Pre-opening restaurant signals (done-for-you) | 6.0 | n.i.v. | Data tier crowded: CHD Expert $59–119K/yr, RestaurantData, Recordpipe from $5K, Apify actors at $3–50/1K. Opening dates slip. |
| #6 Verified new-business feed | 5.9 | n.i.v. | Apify sells new filings at $4/1K and Data Axle $0.07–0.30/record. Scam association (TN warning, Sept 2026). |
| #7 Construction payment-distress radar | 5.7 | n.i.v. | Coverage gaps across 3,000+ recorders. NACM, NCS and BICA are incumbents. Per-page image fees erode margin. |
| #8 Equipment refresh windows from UCC | 5.3 | n.i.v. | EDA/Fusable entrenched for decades. AZ bulk UCC costs $24K; NC and GA ban scraping. Collateral is often just "all assets". |
| Probate leads → investors | — | rejected by lane | Dozens of vendors at $69–1,200+/county/mo; per-lead prices down to $0.10. |
| Divorce filings → realtors/lenders | — | rejected by lane | Sold by PropStream. Heavy TCPA/DNC exposure, high reputational risk, no recurring B2B angle. |
| Tax liens → tax-resolution firms | — | rejected by lane | $0.16–0.40/record across 3,000+ counties, aggregated daily. FTC and AG enforcement against the buyer industry. |
| Residential code violations → contractors | — | rejected by lane | GetCodeViolations $49/mo across 56+ cities; Apify from $2/1K. |
| MCA UCC lead lists → brokers | — | rejected by lane | $0.005–0.30/record. Regulatory churn from TX HB 700. Broker TCPA risk. |
| MCA stacking/default monitoring | — | rejected by lane | DataMerch $695–945/mo, Middesk and Cobalt. Virginia lists only ~115 registered sales-based financing providers. |
| Judgments → judgment recovery | — | rejected by lane | Collection-agency licences and bonds (FL $50K, NY $25K). Unlicensed collection can void judgments. |
| New-lawsuit alerts → attorneys | — | rejected by lane | Trellis $69.95–199.95/mo, UniCourt $59–399/mo. Attorney solicitation rules. Tyler/judyrecords access issues. |
| Professional-licence expirations → CE providers | — | rejected by lane | Boards publish free weekly files (FL DBPR). CE providers can self-serve. Low value per lead. |
| Elevator/boiler inspection deadlines → service firms | — | rejected by lane | Small buyer universe, state-by-state coverage, and a free TX aggregator (elevatordatabase.com). |
| Raw new-business lists sold as data | — | rejected by lane | Commoditized. Lane kept it for internal prospecting only. |

## Lane 04: Regulatory and compliance monitoring (25 ideas)

| Idea | Lane score | Verifier verdict and revised score | Reason it failed or was downgraded |
|---|---|---|---|
| #1 Prop 65 "Next Defendant" alerts + catalog scan | 7.4 | **KILLED** → 3.0 (verify-2) | Retailers are mostly not liable (27 CCR §25600.2) and can cure in 5 days. Prop65Radar is live at ~$29. An alert could create "actual knowledge". |
| #2 Restaurant inspection → pest/hood done-for-you outbound | 6.8 | WEAKENED → 3.5 (verify-2) | Every restaurant already has a mandated exterminator; same feed sells at $5–10/1K. A $1–2.5K retainer is 18–45% of a $1M firm's marketing budget. |
| #3 OSHA SST target predictor | 6.5 | **KILLED** → 2.5 (verify-2) | ~390 SST inspections/yr against ~390K filers (0.1%). Cut-offs are confidential. Apify sells DART lead scores at $5/1K. |
| #4 CA stormwater citizen-suit risk monitor | 6.4 | WEAKENED → 5.0 (verify-2) | Mapistry already sells facility-level citizen-suit risk alerts. Only ~1,931 core-SIC targets. Exceedances are visible only after strict-liability violation. |
| #5 Small-government Title II PDF/web remediation | 6.0 | n.i.v. | AI PDF remediation already sells at $0.30–12/page. CivicPlus, Granicus and AudioEye compete. DOJ has already extended the deadline once. |
| #6 Supplement/cosmetic claims scanner | 5.8 | n.i.v. | FDA letters number in the dozens a year, so fear is weak. Dicentra and EAS compete. Founders keep claims that convert. |
| #7 OSHA "just cited" kit / consultant feed | 5.5 | n.i.v. | Apify OSHA citation scrapers and safetyrecord.org exist. About 10 working days to act. Mostly one-off revenue. |
| #9 FMCSA insurance-lapse feed for agents | 5.3 | WEAKENED → 3.5 (verify-5, trucking verdict) | Carrier IQ at $149–249/mo and 8+ other vendors. The Motus cutover (14 May 2026) removed future-dated cancellations from bulk data. |
| #8 10DLC website compliance fixer | 4.5 | n.i.v. | SMS platforms bundle free AI rejection fixers. TCR fees are $4–44. One-off value of $50–200 per SMB. |
| ADA/WCAG lawsuit-risk scans | — | rejected by lane | AudioEye has ~131K customers at ~$305 ARPU. FTC's $1M accessiBe order. 28% of 2025 suits hit sites with overlays. |
| Cookie-consent / state-privacy scans | — | rejected by lane | Termly $14/mo, CookieYes $8–46/mo. Most SMBs fall below the 100K-consumer thresholds of state laws. |
| CIPA pixel/chat wiretap-risk scans | — | rejected by lane | SB 690, signed 30 Sep 2026, ends private pen-register claims (about two-thirds of the suits) from 1 Jan 2027. |
| BIPA exposure scans | — | rejected by lane | The 2024 amendment capped damages; ~107 new class actions in 2025. Illinois only. |
| TSCA 8(a)(7) PFAS reporting help | — | rejected by lane | Window pushed to 31 Jan 2027 or later. EPA proposed exempting article importers. One-time work. |
| Minnesota PFAS-in-products reporting | — | rejected by lane | One-time $800 report. Deadline (15 Sep 2026, extendable to 14 Dec) largely passed. Enterprise tools own it. |
| FMCSA new-authority "DOT compliance" packages | — | rejected by lane | Scam-saturated; FMCSA issues fraud alerts about impersonators. Reputational poison. |
| FDA 483/warning-letter intelligence for SMBs | — | rejected by lane | SMBs don't buy intelligence. Redica owns enterprise ($289 per 483). FDA dashboard data is free. |
| FDA import-refusal → US-agent services | — | rejected by lane | Registrar Corp dominates (20K+ clients). Overseas buyers complicate outreach under GDPR and foreign rules. |
| CFPB complaint monitoring | — | rejected by lane | 13.8M complaints dominated by bureaus and big banks. The CFPB itself said volume reduced the data's usefulness (June 2026). |
| NHTSA recall outreach for dealers | — | rejected by lane | Recall Masters already sells a turnkey, OEM-reimbursed recall department with a guaranteed ROI. |
| MSHA violation feeds | — | rejected by lane | Data is free and weekly; MshaScan exists. Small mine universe with entrenched trainers. |
| State AG action monitoring | — | rejected by lane | Unstructured press releases mostly target large companies. No repeatable SMB trigger. |
| Generic EPA ECHO violator lists | — | rejected by lane | Already resold by Apify actors. |
| CSLB licence/bond/WC lapse leads | — | rejected by lane | The free CSVs are already scraped on Apify, and bond and insurance agents already mine them. |
| ADA "just sued" alerts to defendants | — | rejected by lane | Defendants need lawyers, not scans. 46% of federal cases are against repeat defendants. |

## Lane 05: Real estate, construction and property (22 ideas)

| Idea | Lane score | Verifier verdict and revised score | Reason it failed or was downgraded |
|---|---|---|---|
| #1 FL Condo Capital-Event Feed | 7.0 | WEAKENED → 4.5 (verify-3) | HOA Contact Lists (200K+ FL contacts), PropFusion and CAMbrands exist. SIRS deadline passed. Engineers gatekeep restoration. Realistic $0.1–0.4M ARR. |
| #2 Association switch-signal for CAM firms | 6.3 | WEAKENED → 3.0 (verify-3) | The condo CSV's "managing entity" is the association (5,818 of 5,821 rows); the CAM firm appears only as a C/O line in 50.2% of rows. |
| #4 Conveyance Intel for independent elevator companies | 5.8 | **KILLED** → 2.0 (verify-3) | Otis, KONE, TKE and Schindler maintain 65.5%; only 80 independents hold 50+ units. Convex sells renewal windows. No contract-expiry field. |
| #3 Agent-run benchmarking filing | 5.8 | n.i.v. | Crowded: Envigilance, Beacon ($95/mo), Elevate ($800/building). Cities run free help desks. Paper utility forms add labor. |
| #5 FL municipal lien / open-permit search | 5.0 | n.i.v. | PropLogix and many small firms charge $100–125. Much of the municipal-request work stays human. E&O liability for missed liens. |
| #6 Solar-orphan service leads | 4.8 | n.i.v. | Under the dealer model the permit contractor isn't the bankrupt brand. SunStrong absorbs customers. Ohm gives installer data away free. |
| #7 Tax-consultant evidence packets | 4.5 | n.i.v. | Saturated: O'Connor, Ryan, Ownwell, TaxNetUSA QuickAppeal. Seasonal; TX notices go out April–May, so 6+ months to first dollar. |
| #8 Pre-bid specialty-sub lead engine | 4.0 | n.i.v. | cityminutes.ai, GatherGov, Dodge, ConstructConnect, PlanHub and free BuildingConnected. Price pressure toward $39/mo. |
| Lender/insurer property-risk feed | — | rejected by lane | Verisk/BuildFax (10M+ roofs), Moody's/CAPE and ZestyAI hold regulatory model approvals. Long enterprise sales cycles. |
| LL97/BPS fine-avoidance retrofit outreach | — | rejected by lane | First-year LL97 penalties were ~$270K citywide; 93% filed. Compliance needs a PE's attestation. |
| Short-term-rental compliance service | — | rejected by lane | Granicus and Deckard own the city side. Host permit fees are only $64–308. |
| Rental-registry enforcement | — | rejected by lane | Low per-unit fees; Deckard already markets registry enforcement; landlords resist paying. |
| Pre-foreclosure / deed / mortgage lists | — | rejected by lane | PropStream $99/mo, BatchLeads $119/mo, ATTOM API from ~$95/mo. |
| CRE maturity-wall refinance leads | — | rejected by lane | Trepp, CompStak, Reonomy and MSCI already map maturities. Recorder data lacks maturity dates. |
| Utility interconnection-queue intelligence | — | rejected by lane | Enverus bought Pearl Street; Paces raised $11M; Interconnection.fyi sells feeds; LBNL publishes free. |
| Tax-sale/foreclosure surplus recovery | — | rejected by lane | Florida caps assignee compensation at 12%. Consumer-facing, with a predatory reputation and "course" competitors. |
| Texas BPP rendition-as-a-service | — | rejected by lane | HB 9 raised the exemption to $125K from tax year 2026. |
| NYC violation/compliance monitoring | — | rejected by lane | ViolationWatch $9/building/mo, DOBGuard ~$50/mo. The price floor has collapsed. |
| Fire-inspection deficiency leads | — | rejected by lane | Brycer's Compliance Engine already sits between AHJs and contractors. The data isn't public in bulk. |
| NYC elevator/boiler raw lead lists | — | rejected by lane | Already on Apify at $2.50/1K, with 2 users. |
| Residential property-tax appeal | — | rejected by lane | Ownwell ($74M raised, 1M+ appeals) plus AI clones. Texas protests are already 81% agent-filed. |
| Certificate-of-occupancy "new tenant" leads | — | rejected by lane | Shovels and BuildZoom already expose COs. Vendors (cleaning, security) have low willingness to pay for leads. |

## Lane 06: Healthcare data (20 ideas)

| Idea | Lane score | Verifier verdict and revised score | Reason it failed or was downgraded |
|---|---|---|---|
| #1 Rate Gap Report (TiC × Part B) | 6.4 | WEAKENED → 3.5 (verify-4) | MGMA Rates, PayerPrice, Turquoise's free tier and Rivet ($6K/yr) already serve small practices. CMS-9882-P would commoditize the ghost-rate filter. |
| #2 Medicare Enrollment Guard | 6.3 | WEAKENED → 3.5 (verify-4) | Public files have no addresses, so the mismatch check is impossible. MACs send 2 letters + 2 emails. Shared PECOS logins prohibited. |
| #3 Practice-acquisition screener for LMM roll-ups | 6.2 | WEAKENED → 3.0 (verify-1) | No CMS practice-ownership file exists. Medicare is ~16% of optometry billings. Alpha Sophia and Provyx ($750/1K records) compete. |
| #4 Nursing-home survey-window lead feed | 5.6 | n.i.v. | Buyers are fragmented 1–5-person consultancies. AHCA Trend Tracker is free to members. The federal staffing rule was repealed Dec 2025. |
| #5 IDR prep for small out-of-network providers | 5.4 | n.i.v. | Payer RICO suits (Anthem alleges 55% of HaloMD filings ineligible). PHI/BAA burden and heavy working capital. |
| #6 Employer network-rate benchmark via brokers | 5.0 | n.i.v. | Serif launched this exact product for brokers on 16 July 2026. Payerset and Turquoise also compete. Brokers are conflicted. |
| #7 Exclusion/licence monitoring | 4.6 | n.i.v. | Commodity price of $30–40/mo (ExclusionScreening). Bundled free in HR and credentialing suites. |
| #8 340B rebate-pilot reconciliation | 3.6 | n.i.v. | Pilot already enjoined once. Beacon and TPAs own the data pipes. Needs EHR and pharmacy integration plus PHI. |
| New-NPI "new practice" lead lists | — | rejected by lane | Apify at $0.50–10/1K; PostcardMania $0.21–0.30/record. Most new Type 1 NPIs are residents or non-billing staff. |
| Hospital price-transparency compliance monitoring | — | rejected by lane | CMS publishes a free validator; free compliance trackers exist. Only 28 CMPs in about 4 years. |
| Standalone credentialing service | — | rejected by lane | Labor-heavy; CAQH is free. Offshore services charge $99–300/application. Medallion and Verifiable have raised $100M+. |
| MA/Part D Star-ratings consulting | — | rejected by lane | Few buyers (small MA plans), entrenched actuarial consultancies, no data advantage. |
| Open Payments KOL / pharma targeting | — | rejected by lane | IQVIA, H1 and Komodo serve enterprise buyers at $50K–200K+. |
| Nursing-home deficiency leads for plaintiff attorneys | — | rejected by lane | Attorneys use free CMS and ProPublica data. Consumer lead-gen (~$625/lead) is regulated attorney solicitation. |
| Medicaid fee-schedule aggregator | — | rejected by lane | States must publish their own Medicare comparisons. Buyers are few, with unclear willingness to pay. |
| HCPCS / code-change alerting | — | rejected by lane | Free from CMS quarterly; AAPC and EHR vendors already push it. |
| T-MSIS-based Medicaid analytics | — | rejected by lane | PHI under a research-only DUA at ~$25K per seat. Commercial use not permitted. |
| Hospice/HHA licence brokerage during the moratorium | — | rejected by lane | The moratorium also freezes ownership changes. Fraud-heavy segment (~800 LA providers suspended). |
| Plan-side (TPA) IDR exposure analytics | — | rejected by lane | Buyers are a few large TPAs and carriers with in-house analytics; long sales cycles. |
| Revalidation lists sold as leads | — | rejected by lane | Already on Apify; selling the list is a race to zero. |

## Lane 07: Government contracting, procurement and grants (22 ideas)

| Idea | Lane score | Verifier verdict and revised score | Reason it failed or was downgraded |
|---|---|---|---|
| A. Single-audit Finding Fixer | 7.1 | WEAKENED → 3.0 (verify-3) | CAP already filed (2 CFR 200.511(c)). Only 8,187 of 46,650 audits have findings. Templates free or $72–100. Single Audit Intelligence exists. |
| B. Water Pipeline Radar (SRF IUPs + SDWIS/PFAS/LCRI) | 6.9 | WEAKENED → 3.0 (verify-3, merged with 11-#1) | EPIC normalizes SRF lists free and Bluefield sells them. BIL ended FY26; FY27 request $305M. Engineers are hired before listing. |
| C. Town Grant Desk (flat retainer) | 6.6 | WEAKENED → 4.0 (verify-3) | Syncurrent free/$49/mo; MA GrantWell free. California Consulting's $1.5K per-grant fee undercuts Starter. Grass Valley extended only 6 months. |
| D. Grant-Funded Pipeline for public-sector vendors | 6.3 | n.i.v. | 2 CFR 200.319(b) can exclude vendors that draft applications. Lexipol GrantFinder dominates attention. Grant programs at risk of cuts. |
| E. Trade bid concierge + price-to-win | 5.6 | n.i.v. | Discovery commoditized (Bidscope $45/mo, CLEATUS $39/mo, Euna/Bonfire free to bidders). Thin janitorial margins cap value. |
| G. Subcontracting-plan partner matcher | 5.0 | n.i.v. | Bundled in GovWin, HigherGov and GovTribe; SBA SubNet free. SDB goal cut. Primes choose subs by relationship. |
| F. SAM registration renewal desk | 4.9 (lane: effectively reject) | n.i.v. | GSA/BBB warn about fake SAM renewal notices built from expiration data. SAM terms bar marketing use. Registration is free. |
| H. Statutory incentive recovery (referral) | 4.3 | n.i.v. | 174A retroactive window closed 2026-07-06. Circular 230 contingent-fee limits. Ryan, the Big 4 and Strike (20%) own it. |
| Generic SLED bid aggregator for a niche | — | rejected by lane | Starbridge ($52M) and Bidscope (claims 50K sites); $39–45/mo price floors; Euna/Bonfire free for bidders. |
| Bid matching + AI proposal subscription | — | rejected by lane | GovDash ($30M), CLEATUS, Sweetspot and HigherGov AI tools. |
| Federal recompete / expiring-contract finder | — | rejected by lane | Free API, Apify actors and the BidSparq index. |
| ERC recovery | — | rejected by lane | OBBBA bars late Q3/Q4 2021 claims. 20% penalty; $1,000 promoter penalty per due-diligence failure. |
| WOTC screening service | — | rejected by lane | Lapsed 2025-12-31 and not reauthorized; payroll providers (ADP) dominate. |
| IRA credit-transfer marketplace | — | rejected by lane | $42B market run by Crux, banks and brokers. FEOC diligence. Wind/solar construction cutoff 2026-07-04. |
| 179D designer-allocation hunting | — | rejected by lane | Deduction ended for construction begun after 2026-06-30. KBKG and ETS are incumbents. |
| Farm grant writing (USDA REAP) on success fee | — | rejected by lane | REAP grant notice rescinded 2026-04-15. Success fees violate GPA ethics. |
| Grant writing on contingency for nonprofits | — | rejected by lane | GPA Code item 19 bans percentage compensation; many funders forbid it. |
| SBIR proposal writing on success fee | — | rejected by lane | Crowded ($4–17K plus 3–5% success fee). A recent 5.5-month lapse shows policy risk. |
| DBE recertification narrative writing | — | rejected by lane | One-time window; $79 AI tools; final rule published 2026-09-25. The narrative must be the owner's own. |
| E-Rate Form 470 vendor alerts | — | rejected by lane | FRNHQ, ERateSignal and Apify. FCC is building a bidding portal (FY2028). |
| CA DIR public-works registration renewal | — | rejected by lane | Same scam-adjacent dynamics as SAM. Manual export only. Low value per firm. |
| Certified payroll for prevailing-wage subs | — | rejected by lane | LCPcertified from $145/mo; QuickBooks add-ons $50–200/mo. Payroll processing, not data interpretation. |

## Lane 08: Legal, litigation and IP (21 ideas)

| Idea | Lane score | Verifier verdict and revised score | Reason it failed or was downgraded |
|---|---|---|---|
| #1 Pro-se trademark office-action feed for attorneys | 6.6 | WEAKENED → 4.5 (verify-4) | Scam-poisoned channel. ~30 Apify USPTO actors from $2.79/1K. Responses from $89 (L4SB). 5% of attorneys file 79% of applications. |
| #2 B2B found-money sweep via CPA firms | 6.2 | WEAKENED → 4.0 (verify-4) | 50/50 split barred by FL §717.1322, CA B&P 5061 and AICPA attest rules. Median claim $100. NY list has no dollar values. |
| #3 ADA lawsuit signals → site rebuild | 6.0 | n.i.v. | AudioEye ARPU ~$305/yr. Overlays anchor pricing at $25–100/mo. Defense lawyers' vendors reach sued businesses first. |
| #4 Trade-claim sourcing engine for claims buyers | 5.8 | n.i.v. | Only 30–60 relationship-driven buyers who treat sourcing as their edge. Creditors are already swamped with offers. |
| #5 Creditor-side bankruptcy action briefs | 5.5 | n.i.v. | Epiq AACER, Creditsafe, CreditRiskMonitor and NACM bundle alerts. Value is episodic; ERP integration friction. |
| #6 Settlement-eligibility radar and filing for SMBs | 5.2 | n.i.v. | Per-restaurant payouts likely hundreds of dollars, paid 1–2 years later. Courts police filers (EDNY Dkt. 7260). |
| #7 Name-conflict watch for local businesses | 4.8 | n.i.v. | SMBs won't pay to watch an unfamiliar risk. "Someone filed your name" reads like USPTO scam mailers. |
| Visa/MC interchange claims filing | — | rejected by lane | Deadline passed 4 Feb 2025. Court-mandated disclosures for filers. |
| Securities class-action claims filing | — | rejected by lane | Chicago Clearing (2,900+ clients), Broadridge and ISS SCAS. Custodians such as Schwab bundle it. |
| Mass-tort signal intelligence | — | rejected by lane | Crowded by AI-native players: Darrow, TortIntel, LexGenius, TortSignal, Velocity Justice. |
| White-label trademark docketing and renewal monitoring | — | rejected by lane | Alt Legal from $60/mo; Corsearch and CompuMark own watch services. |
| Direct-to-owner Section 8/9 renewals | — | rejected by lane | 37 CFR 11.14 bars non-attorneys. Matches the convicted renewal scam (4+ years prison, $4.5M restitution). |
| Brand-protection monitoring subscription | — | rejected by lane | Red Points $15–70K/yr; Brand Protector $199/mo; Amazon Brand Registry is free. |
| DMCA takedown for creators | — | rejected by lane | Rulta, BranditScan and 18+ others. Adult-creator concentration adds platform risk. |
| Copyright-infringement recovery (Pixsy-style) | — | rejected by lane | Pixsy and Copytrack take 45–50%. Troll backlash; only 35 of 1,222 CCB claims reached final determination. |
| UCC-filing lead lists (MCA) | — | rejected by lane | Commoditized at $0.005–0.75 per lead; MCA is heavily scrutinized. |
| Bankruptcy claims brokering as broker of record | — | rejected by lane | 0.5–1% commissions. Relationship-driven, with securities-law ambiguity. |
| Preference-suit defendant feed | — | rejected by lane | Narrow and episodic; waves arrive ~2 years after the petition from a few dozen trusts. |
| Construction lien-deadline tool | — | rejected by lane | Procore bought Levelset for $500M. |
| Judgment-recovery origination | — | rejected by lane | State data is fragmented and costly (UniCourt/Trellis APIs by quote). FDCPA and collection-law exposure. |
| Generic "you've been sued" alerts | — | rejected by lane | Defense firms already monitor. Selling legal outcomes to defendants edges toward UPL. |

## Lane 09: Adjacent plays on the local-SMB website pipeline (21 ideas)

| Idea | Lane score | Verifier verdict and revised score | Reason it failed or was downgraded |
|---|---|---|---|
| #1 AI + Maps Visibility Plan | 7.0 | WEAKENED → 5.0 as upsell / 3.5 cold (verify-5) | BrightLocal includes AI tracking from $31/mo. API answers overlap the consumer UI only 15.5–23.8%, and LLM lists rarely repeat. |
| #2 Review engine | 6.6 | WEAKENED → 5.0 as upsell / 3.5 cold (verify-5, bundled with #1) | Very crowded: Podium $399–599, Birdeye, NiceJob $75 and GHL bundles. Owners often never upload customer lists. |
| #4 Trucking insurance renewal intelligence (FMCSA) | 6.4 | WEAKENED → 3.5 (verify-5) | 8+ vendors (Carrier IQ $149–249, PollyAI, TruckingSignal). Motus removed future cancellations. The renewal anniversary is a guess. |
| #3 Restaurant commission-leak site + ordering | 6.0 | **KILLED** → 2.5 (verify-5) | DoorDash Starter includes a free branded site and commission-free ordering. Menufy now costs $149–179/mo; GloriaFood shuts 30 Apr 2027. |
| #7 Self-storage vertical | 5.9 | n.i.v. | ~15–25K independent facilities caps it at ~$5M ARR. Storable bundles websites with storEDGE/SiteLink. |
| #6 Free valuation lead feed into M&A | 5.6 | n.i.v. | Most owners won't sell within 12 months. Wrong numbers insult owners. Brokers are cheap; not recurring. |
| #8 Small-401(k) Form 5500-SF benchmarking | 5.5 | n.i.v. | Judy Diamond $795–3,900/yr, BenefitFlow ~$14.5K/yr. SF filings show aggregate fees only. Adviser compliance friction. |
| #5 Merchant-processing bolt-on | 4.9 | n.i.v. | No public proof of effective rate. ~$30/mo residual; 24.6%/yr attrition. Toast and Clover lock merchants in. |
| AI phone receptionist / missed-call text-back | — | rejected by lane | Most saturated category; prices falling to $49 (Rosie). Not provable without test calls (TCPA, recording consent). |
| Standalone GBP optimization | — | rejected by lane | Paige $99 and every GHL agency bundle it. The GBP API forbids lead generation. |
| Standalone local SEO audits | — | rejected by lane | The oldest agency lead magnet; delivery is labor-heavy. |
| Google/Meta ads audits | — | rejected by lane | Meta's Ad Library API covers US political ads only; Google's transparency data covers only the EEA and Turkey. |
| Website ADA compliance (standalone) | — | rejected by lane | A scan isn't proof of compliance. accessiBe FTC case. AudioEye took years to reach $40M. |
| Broken/missing booking flows | — | rejected by lane | Jobber affiliate pays $50–300 one-off; Housecall Pro up to $180–320; Square pays nothing. |
| Restaurant price/menu monitoring | — | rejected by lane | Buyers are chains and CPG brands (Datassential, Technomic). DoorDash/Uber terms ban scraping. |
| Utility bill audits / energy brokerage | — | rejected by lane | Needs bill upload (UtilityAPI $15/meter). Brokerage pays ~$220–370/yr per account; only ~18 choice states. |
| Telecom and SaaS spend audits | — | rejected by lane | SMB spend is ~$300–1,500/mo. Expense Reduction Analysts franchises average ~$165K sales per licence. |
| Payroll / PEO / health-benefit audits | — | rejected by lane | Small insured health plans don't file Form 5500. Needs uploads and a life-and-health licence. |
| Insurance benchmarking for micro-SMB BOPs | — | rejected by lane | ~$100–400/yr commission. Next, CoverWallet and Huckleberry compete. CA/NY WC lookups block automation. |
| Health-inspection data + reviews | — | rejected by lane | The fix isn't automatable, and "you failed inspection" is an adversarial opener. |
| Expired SSL/domain, hours mismatch | — | rejected by lane | Trivial to detect. Good timing triggers for the core pitch, not products. |

## Lane 10: B2B intent and trigger signals (24 ideas)

| Idea | Lane score | Verifier verdict and revised score | Reason it failed or was downgraded |
|---|---|---|---|
| #1 New Practice Radar (NPPES + SOS) | 6.5 | WEAKENED → 3.0 (verify-4) | Actable sells a "Practice Radar" at $39/mo. 72% of billing firms grow by referral. 44% of new practices are solo behavioral LLCs. |
| #4 FTC Safeguards gap-brief engine for MSPs | 6.0 | n.i.v. | Outside-in reports are free (Coalition, Guardz, EasyDMARC, ThreatMate). Preparers buy $749–999 WISP templates instead. |
| #2 Multi-state Pre-Opening Radar | 5.5 | n.i.v. | Per-buyer willingness to pay is $29–199/mo (Restaurant Activity Report $99, Liquor License Leads $29). Reps churn. |
| #3 Event-layered 401(k)/benefits benchmark | 5.5 | n.i.v. | FiduciarySignal $90/mo, 401kHunter $100, Form5500Search $49; RiXtrema drafts emails. FINRA 2210 compliance approval friction. |
| #5 Defense-industrial-base CUI readiness radar | 4.5 | n.i.v. | DoD suspended CMMC Phase 2 on 13 July 2026. GCC High detection is a weak proxy. Only 387 RPOs. |
| #6 Trucking insurance renewal/lapse radar | 4.0 | WEAKENED → 3.5 (verify-5) | TruckingSignal, PollyAI and TruckerDB ($49) already do it. The Motus cutover froze legacy feeds on 14 May 2026. |
| #7 Operating-company Form D feed for fractional CFOs | 3.5 | n.i.v. | Funding is the most commoditized signal (Fundz from $49). The Apify Form D actor has 2 users. Fewer than 10K real leads a year. |
| WARN notices → outplacement/staffing | — | rejected by lane | Outplacement is chosen before the layoff. ~3–4.5K notices/yr. API at $9/mo. State Rapid Response is free. |
| State AG breach notices → cyber MSPs | — | rejected by lane | Under 2K notices/yr in structured states. Breached firms already have counsel and incident response. |
| Generic outside-in cyber risk reports | — | rejected by lane | Free from Coalition, UpGuard, SecurityScorecard and EasyDMARC. |
| CRE tenant-rep from hiring growth | — | rejected by lane | Lease expiry is proprietary (CompStak, CoStar). Scayled at $59–119/mo already exists. |
| Building permits → contractors/solar | — | rejected by lane | Prices compressed to $19–39/mo. A pulled permit usually means a contractor is already hired. |
| New business formation lists | — | rejected by lane | Fractions of a cent per record; most filings are holding LLCs. |
| OSHA citations → safety consultants/P&C agents | — | rejected by lane | OSHAlert $49–399/mo plus 6+ Apify actors; 30–60 day lag. |
| RIA / Form ADV triggers | — | rejected by lane | AdvizorPro ($5–15K/yr), FINTRX ($10–20K) and Discovery Data already sell these alerts. |
| 8-K exec changes / Form 4 liquidity | — | rejected by lane | sec-api.io extracts Item 5.02 at $49–199/mo. Public companies only. |
| Earnings-call transcript mentions | — | rejected by lane | Seeking Alpha terms ban redistribution. AlphaSense ~$18K/seat. |
| Podcast/YouTube transcript signals | — | rejected by lane | Third-party captions not downloadable; 30-day storage cap. Podscan sells alerts at $100–2,500/mo. |
| Conference exhibitor lists | — | rejected by lane | $0.25–4/1K on Apify. A list, not a trigger. |
| Job-posting tech-stack intelligence | — | rejected by lane | Sumble ($38.5M raised, free/$99), TheirStack, PredictLeads, Coresignal. |
| ClinicalTrials.gov → CROs | — | rejected by lane | Registration is due up to 21 days after first enrollment, after CROs are chosen. Citeline dominates. |
| DNS/SSL/app-store change feed | — | rejected by lane | An MX move means a partner is already chosen. crt.sh is unreliable under load. |
| Generic signal-as-a-service newsletter | — | rejected by lane | No revenue disclosures found. Any raw feed can be replicated by an Apify actor in a weekend. |
| Pure Form 5500 data product | — | rejected by lane | Six or more vendors at $25–199/mo with fee grades and switch prediction. |

## Lane 11: Wildcards (39 ideas)

| Idea | Lane score | Verifier verdict and revised score | Reason it failed or was downgraded |
|---|---|---|---|
| #1 Trade-specific agenda-to-pipeline | 6.7 | WEAKENED → 3.0 (verify-3, merged with 07-B) | Civic IQ $299/mo plus a $2K/mo done-for-you service; Curate from $295/user/mo; Starbridge $53.8M; Hamlet free tier. |
| #3 Aircraft-owner outreach for avionics/MRO | 6.4 | WEAKENED → 4.0 (verify-5) | Owner lists cost $0.14/name (Datamasters). ADs are handled at annual inspections. Shops are backlogged. ~$0.4–1.2M ARR ceiling. |
| #8 Construction-coming-to-your-county | 6.3 | n.i.v. | No proven willingness to pay. BEAD winner lists are free. EPCs buy nationally. Lane called it "a puddle". |
| #7 Private land-use approval triggers | 6.0 | n.i.v. | Opening Alerts $49–99/mo; DineTracer $0.50/lead; CurateBUILD covers construction. Applicant LLCs are hard to contact. |
| #2 Property-tax appeal evidence engine | 5.9 | WEAKENED → 3.0 (verify-3) | AppealDesk sells $49 packets. TX Occ. Code 1152 covers paid assistants. ~49% TX ARB success; ~$130 expected per signed client. |
| #4 Franchise trigger engine | 5.9 | n.i.v. | Blueprint GTM sells a Claude-built 142,579-operator dataset at $50/mo. Agencies crowded. FTC Franchise Rule earnings-claim risk. |
| #6 Duty-drawback discovery (broker partnered) | 5.3 | **KILLED** → 1.5 (verify-1) | A contingency split from a licensed broker to an unlicensed party is prohibited by 19 CFR 111.36(b) and CBP H276784. |
| #5 Amazon trademark gap → filing | 5.3 | n.i.v. | Unsolicited trademark outreach is the scam pattern the USPTO warns about. Amazon IP Accelerator exists. Rule 5.4 bars fee-splitting. |
| SERFF insurance rate-filing intel | — | rejected by lane | SFA terms prohibit automated download. S&P, Akur8/Matrisk and Insuraviews are already in the market. |
| PUC rate-case/docket tracking | — | rejected by lane | Halcyon ($32M raised, all 50 PUCs), HData and S&P RRA. |
| Utility tariff data | — | rejected by lane | Arcadia/Genability own the installer market. The OpenEI gap is real but small. |
| Interconnection queues → landowner leads | — | rejected by lane | Landowners don't pay (LandGate is free to them). Paces, Transect and Apify ($6/1K) serve developers. |
| Data-center/renewable moratorium trackers | — | rejected by lane | Free trackers (SAVRN with 1,118 moratoria, Sabin, NLC). Heatmap Pro and Paces serve enterprise. |
| BEAD winner lists | — | rejected by lane | Free (Telecompetitor, beadtracker.com, state portals). |
| USDA FSA payments → ag dealers | — | rejected by lane | DTN/Farm Market iD covers 2.4–2.8M operators; EWG is free. Data lags a year. |
| EU CBAM for US exporters | — | rejected by lane | US exposure is only ~$1.4B. The obligation sits with the EU importer. EU software from €79/mo. |
| CA SB 253 supplier Scope 3 | — | rejected by lane | Scope 3 not due until 2027; SB 261 enjoined; spend-based estimates allowed. |
| EPA TRI/GHGRP standalone | — | rejected by lane | Useful only as an input to the SB 253 idea. |
| Generic SMB RFP writer | — | rejected by lane | GovDash ($30M B), Vultron ($22M), AutoRFP, plus $0–199/mo tools. |
| Horizontal SLED intelligence | — | rejected by lane | Starbridge, Pursuit, Curate, GovSpend, GovWin, Quorum. |
| 990 funder matching / grant prospecting | — | rejected by lane | Instrumentl ($55M), Candid, Granted AI ($18/mo), Grantable (free). Schedule B donors redacted. |
| Church data | — | rejected by lane | Churches don't file 990s. List brokers sell 118K contacts for $699. |
| Liquor and cannabis licence leads | — | rejected by lane | Opening Alerts $49–99/mo, DineTracer $0.50/lead, Cannabiz $3.6K+/yr, 5+ Apify actors. |
| FMCSA new-authority leads | — | rejected by lane | 6+ Apify actors at $3.50–20/1K. New carriers are swamped with calls. Motus broke the feed. |
| UCC filings → equipment and MCA leads | — | rejected by lane | Access from free (CO) to $24K (AZ); GA/NC ban scraping. EDA owns equipment; MCA outreach is toxic. |
| Boat and vessel registrations | — | rejected by lane | No free bulk USCG download found. State registrations are privacy-restricted. |
| Probate leads | — | rejected by lane | $69–799/mo per county. Targets grieving families; rejected on ethics. |
| Shopify store detection | — | rejected by lane | Store Leads, BuiltWith, StoreCensus ($49), StoreIndex ($29), Apify. |
| App-store review mining | — | rejected by lane | AppFollow, Appbot ($39), Sensor Tower. LLM summaries are now a standard feature. |
| Amazon suspended-seller reinstatement | — | rejected by lane | No public list of suspended sellers. Referral-driven and crowded. |
| COI tracking | — | rejected by lane | BCS free to 25 vendors then ~$0.95/vendor/mo; Jones ($38M). No public data hook. |
| Lien waivers and notices | — | rejected by lane | Procore/Levelset ($500M); LienWaiver.pro $49/mo. UPL rulings on lien filing (NC). |
| Parcel late-delivery refunds | — | rejected by lane | FedEx suspended Ground/Home/2Day guarantees; UPS Ground isn't guaranteed. The refund pool has shrunk. |
| IEEPA tariff refund recovery | — | rejected by lane | ~$134.7B already in CAPE by Sept 2026. One-time, crowded, needs a broker or attorney. |
| Chargebacks | — | rejected by lane | Chargeflow ($49M, 25% fee) and Justt (~$100M). No public hook. |
| Sales-tax nexus | — | rejected by lane | Kintsugi (free monitoring), Numeral, free nexus studies (Galvix). |
| 1099/W-9 compliance | — | rejected by lane | $0.63–3.10 per form. OBBBA raised the 1099-NEC threshold to $2,000. |
| Unclaimed property finder | — | rejected by lane | 10–20% fee caps, 24–36-month finder bans, median claim ~$100. Treasurers advertise "never a cost". |
| Vet-clinic data play | — | rejected by lane | Ownership already mapped (privateequityvet.org). Better as a vertical for the website business. |

## Lane 12: Deadline-driven back office, done for you (round 2; 20 ideas)

| Idea | Lane score (post self-check) | Verifier verdict and revised score | Reason it failed or was downgraded |
|---|---|---|---|
| #5 Contractor Back-Office Bundle (upsell) | 4.5 | n.i.v. | Works only if the brothers' customers are commercial or public-works trades; otherwise it shrinks to ~$20/mo reminders. Offshore VAs cost $8/hr. |
| #2 Prequal Desk (ISNetworld/Avetta/Veriforce) | 4.0 | n.i.v. (lane self-check: competition cut 4→2) | Avetta sells its own done-for-you Vetify; EHS Inc Bronze $1,950/yr. ISN may terminate users linked to other subscribers. |
| #1 Prevailing-Wage Desk (CA) | 3.5 | n.i.v. (lane self-check: 4.5→3.5) | Wellstanding already sells CA done-for-you certified payroll at $995 setup + $249/mo. QBO Premium now produces WH-347. |
| #4 Get-Paid Desk (prelims, NOI, retainage) | 3.0 | n.i.v. | The barrier is behavioral (fear of the GC). Levelset $59/recipient. Collection licensing; CA SB 1286 Rosenthal rules. |
| #3 Audit-Ready Desk (FL WC premium audits) | 2.5 (rejected) | n.i.v. (lane self-check) | FL runs a free Construction Policy Tracking Database. FS 624.10/626.015 make fee-based audit review a licensing risk. |
| #6 Small-fleet compliance desk | 2.5 (rejected) | n.i.v. | ExpressIFTA $24.95/qtr; MCS-150 free to file. FMCSA warns of lookalike $149 mailers, which poison cold outreach. |
| Lien-deadline SaaS / notice service | — | rejected by lane | Levelset $59/recipient; FL NTO services $25–65; Handle, NCS, NACM, CNS. |
| COI collection and tracking | — | rejected by lane | BCS ≈$0.95/vendor/mo with licensed reviewers; CertFocus $13–29/vendor/yr; TrackMyVendor $39/mo unlimited. |
| Property-manager vendor compliance | — | rejected by lane | Same COI vendors plus AI property-manager startups (Brickwise, CentralComs). |
| Sales-tax filing for micro-sellers | — | rejected by lane | Numeral and Kintsugi $75/filing; Zamp managed; heavily funded. |
| Annual reports / registered agent | — | rejected by lane | Northwest $125/yr; RAI $200/yr including annual reports; some from $49. |
| Permit expediting / packages | — | rejected by lane | GreenLancer from $199; Permitio.ai HVAC agent (Mar 2026); PermitFlow; expediters $35–70/hr. |
| Prior authorizations for small practices | — | rejected by lane | $4–15/auth outsourced; offshore staff $399/week. Physicians are a guarded buyer. |
| IRS/state notice response, penalty abatement | — | rejected by lane | IRS moving first-time abatement to automatic from 2026. Representation needs a CPA, EA or attorney (Circular 230). |
| Contractor licence renewal and CE tracking | — | rejected by lane | CA CSLB renewal is a form plus a fee; CE is coursework the licensee must take. |
| DBE/MBE certification applications | — | rejected by lane | Application is free by federal rule; consultant prep is $300–1,000 one-time. |
| Provider credentialing / CAQH re-attestation | — | rejected by lane | Dense credentialing-services market; guarded healthcare buyers; PECOS login-sharing prohibitions. |
| AR collections for consumer-facing trades | — | rejected by lane | FDCPA and state collection licensing. AR outsourcing from $350/mo; LedgerUp and other AI tools. |
| WC premium-audit dispute on contingency | — | rejected by lane | Possible insurance-consultant licensing. Thin market (cutcomp ~$30M lifetime). |
| TX/FL business-personal-property renditions | — | rejected by lane | Low stakes (10% late penalty on small bills). Paid TX consulting likely needs TDLR registration. |

## Lane 13: Contingency "found money" recovery (round 2; 23 ideas)

*RateLift (idea #1) takes two rows because the lane scored its narrowed and non-narrowed versions separately.*

| Idea | Lane score (post self-check) | Verifier verdict and revised score | Reason it failed or was downgraded |
|---|---|---|---|
| #2 Co-op claim desk + co-op-funded marketing | 4.5 (5.0 as upsell; ~3 cold) | n.i.v. (lane self-check: WEAKENED) | Pre-approval and 30–60-day windows make retroactive recovery "mostly fiction". OEM approved-agency gating (Yamaha, Lennox). Dealer Spike, CoopReclaim compete. |
| #1 RateLift narrowed to RV and heavy-truck dealers | 4.0 | n.i.v. (lane self-check: WEAKENED) | 100-RO submission rights exist only under auto franchise acts, where Armatus, Wooden and Withum ($7,500 flat) already operate. |
| #1 RateLift for equipment, OPE, marine, powersports | 3.0 | n.i.v. (lane self-check: WEAKENED, near-killed) | Equipment statutes need only a rate notice; parts fixed at net +15%. Garmin pays posted rates up to $190/hr. Per-store pools ~$3–10K. |
| #3 Vendor-side sales-tax overcharge recovery | 4.0 | n.i.v. (lane self-check: WEAKENED) | Vendor credits are voluntary; in CA only the retailer can claim. NY/OH UPL rules for appeals. Arthiva AI tool exists. |
| #4 §45B FICA tip credit for salons | 3.5 | n.i.v. (lane self-check: WEAKENED) | 2025 is the first eligible year, so no lookback refunds; nonrefundable. 80% of barbers self-employed. CA B&P 5061 bans CPA referral fees. |
| #5 Workers'-comp premium-audit recovery | 3.0 | n.i.v. (not separately self-checked) | 8+ firms at ~50% of recovery (CompRecover, WC Audit Recovery). Fee-based insurance advice is licensed in some states. |
| #6 Restaurant Settlement Desk | 2.5 | n.i.v. | Payouts of $100–2,500. 685 third-party filers in Payment Card. Courts police filers; class members can file free. |
| Tax-deed/foreclosure surplus recovery | — | rejected by lane | TX bars non-attorney fees; FL 12% cap; CA $2,500/5%. Post-*Tyler* reforms push counties to pay owners directly. |
| Parcel audit (GSR, DIM) | — | rejected by lane | Dozens of 50%-contingency incumbents (Refund Retriever). FedEx Ground GSR mostly suspended. |
| LTL freight audit and damage claims | — | rejected by lane | Cass, CTSI, Loop crowd audit. 50–60% claim denial rate. Labor-heavy. |
| Telecom/SaaS/waste/merchant expense reduction | — | rejected by lane | Schooley Mitchell franchise (50/50 across 14 categories); IMG Audit, Cost Analysts, Dyrt. |
| Utility rate-class and tax-exemption audits | — | rejected by lane | Many contingency firms. Predominant-use studies need on-site inventories; TX restaurants excluded. |
| CAM/lease audits | — | rejected by lane | Leases often ban contingency auditors. CAMAudit sells $29–49 AI audits. |
| IEEPA tariff refunds | — | rejected by lane | Filing is customs business for the IOR or a broker. Carriers refund informal entries automatically. Fees down to 1.5%. |
| Amazon/Walmart FBA reimbursements, chargebacks | — | rejected by lane | 25% incumbents (GETIDA). Amazon auto-reimburses at manufacturing cost within a 60-day window. |
| Restaurant delivery-app disputes | — | rejected by lane | Voosh, Loop and DisputeDog (20%). |
| SMB property-claim underpayment | — | rejected by lane | Public-adjuster licence and fee caps (TX 10%, FL 20%/10%); referral bans. |
| Healthcare credit balances and payer underpayments | — | rejected by lane | Conduent, Optum and Trend Health dominate. HIPAA; guarded buyers. |
| Federal R&D credit | — | rejected by lane | Crowded; IRS Tier-1 issue; contingency under Circular 230 scrutiny. |
| IRA energy credits (179D/45L/45W) | — | rejected by lane | OBBBA terminated 45W (30 Sep 2025), 179D and 45L (30 Jun 2026). |
| Utility prescriptive rebates | — | rejected by lane | Captured by contractors at sale. CLEAResult and Encentiv dominate. |
| Texas BPP "ghost asset" renditions | — | rejected by lane | Crowded TX consultant market; the round-1 property-tax kill applies. |
| SUTA rate and benefit-charge audits | — | rejected by lane | Bundled by payroll providers; small dollars per SMB. |
| Merchant-processing overcharge refunds | — | rejected by lane | Mostly prospective savings, not refunds. Dozens of ISOs offer free statement analysis. |

## Lane 14: Data that can be obtained but isn't on the open web (round 2; 26 ideas)

| Idea | Lane score (post self-check) | Verifier verdict and revised score | Reason it failed or was downgraded |
|---|---|---|---|
| #1 Overdue Feed (fire ITM overdue lists via records requests) | 4.0 | n.i.v. (lane self-check, Verifier A: 4/10) | Brycer began marketing TCE as "inbound demand" (May 2026). Notices name the incumbent contractor. FL §119.071 exempts the data; Fort Worth withheld under TX 418.181. |
| #2 ITM Book Index (roll-up origination) | 3.0 | n.i.v. (lane self-check, Verifier B: 3/10) | Grata published a fire-safety playbook covering 118K targets (Aug 2026). Shovels sells contractor market share. DealSeam is buyer-paid. |
| #3 Linen and waste co-op (upsell only) | 3.0 | n.i.v. (lane self-check: 3/10 upsell, 2/10 standalone) | Cintas uses a 60-month auto-renewal with a 50% early-termination fee. AuditMyWaste is free; SaveOnServices $247 audit. |
| #4 Due-list feeds (backflow, FOG, hood) | 2.0 | n.i.v. (lane self-check: 2/10) | Backflow tests cost $75–200. Utilities send due notices with approved-tester lists. BackflowRates $39.99/mo. |
| #5 Shop Panel (AI web-form mystery shops) | 2.0 | n.i.v. (lane self-check: 2/10) | CDD firms (Woozle, Baker Tilly) run shops themselves. Speed-to-lead audits are free. Nevada requires a PI licence for mystery shoppers. |
| #6 Collections-contract map (EMS billing etc.) | 1.0 | n.i.v. (lane self-check: 1/10, killed) | Starbridge already FOIAs full contracts with pricing and expirations. Civic IQ sells done-for-you pipeline at $2K/mo. |
| General SLED contract-expiration FOIA database | — | rejected by lane | GovSpend (96M contracts), Starbridge ($52M), Civic IQ ($2K/mo), HigherGov ($50/FOIA). |
| School-district vendor contracts | — | rejected by lane | Starbridge, DistrictIQ and Burbio cover K-12. |
| Police and fire equipment inventories | — | rejected by lane | Sold through territory-exclusive dealers who already know their departments. AFG grant data is public. |
| Alarm-permit and false-alarm lists | — | rejected by lane | Statutorily confidential in many states (NC, FL, Providence RI). |
| Utility account data | — | rejected by lane | Customer-confidential; not obtainable. |
| Pre-opening restaurant leads from plan reviews | — | rejected by lane | RestaurantData.com, Restaurant Activity Report and RestaurantPOSLeads already sell them. |
| Dental supply price co-op | — | rejected by lane | ZenOne $49/mo, Alara free, Method. |
| Small-space commercial lease comps | — | rejected by lane | CompStak's give-to-get exchange has 40K+ members. |
| HVAC equipment price benchmark | — | rejected by lane | Pricing is account-specific and contractors won't share invoices. Cold start. |
| Restaurant food-cost price co-op | — | rejected by lane | GPOs, MarginEdge, xtraCHEF and many invoice tools. |
| Merchant-processing statement benchmark | — | rejected by lane | Swipesum, Rombis and PayBlox give it away free. |
| SMB insurance-premium benchmark co-op | — | rejected by lane | Monetization runs into producer licensing and referral-fee limits. Cold start. |
| Website-quality index for lenders/insurers | — | rejected by lane | Middesk `web_presence_quality`, Carpe Data (45M profiles), Enigma, PredictLeads ($40/mo+). |
| Selling reply-derived owner intent | — | rejected by lane | Destroys trust with the brothers' own prospects; privacy issues; M&A origination already crowded. |
| Multifamily AI mystery shopping | — | rejected by lane | Rev Leasing and EliseAI sell AI shops; Funnel replaces shops with 100% call scoring. |
| Insurance quote-shopping by AI | — | rejected by lane | Requires misrepresenting risk details to carriers; producer licensing applies. |
| Funeral price panel by phone | — | rejected by lane | Weak WTP; Parting.com and Funeralocity exist; AI-voice and CIPA risk. |
| Child-care market-rate surveys for states | — | rejected by lane | Surveys already get 70%+ response. Only 56 buyers, on slow RFP cycles. |
| Public-meeting and hearing transcription | — | rejected by lane | GovSpend (2.3M transcripts), Hamlet, CitizenPortal ($15/mo), Starbridge, Curate. |
| Court hearing audio / earnings / webinars | — | rejected by lane | Court audio rarely public. Trellis/UniCourt cover dockets; AlphaSense, Tegus, Quartr cover earnings. |

## Lane 15: Agent-run brokerage and commission models (round 2; 20 ideas)

| Idea | Lane score (post self-check) | Verifier verdict and revised score | Reason it failed or was downgraded |
|---|---|---|---|
| #6 SMB technology-advisor residual book (upsell) | 5.0 upsell / 3.0 cold | n.i.v. (lane self-check: holds at 5 as upsell) | Comcast/Spectrum pay one-time bounties, not residuals. ~6-month chargeback windows. ~$60–100/mo per switched customer. Lightyear ($31M) is free. |
| #1 Quota liquor-licence brokerage (FL first) | 3.5 | n.i.v. (lane self-check: competition 4→3) | FL's 2023 SFS change (2,000 sq ft / 120 seats) lets small restaurants use a 2COP. Dozens of FL brokers; PLCB auctions. One-off. |
| #2 Restaurant exit desk | 3.0 | n.i.v. (lane self-check: 4→3) | BizBuySell recorded 9,586 closed deals across all categories in 2025. Restaurant resales −11.7% YoY. We Sell Restaurants has 1,375 listings. |
| #3 Insurance micro-book brokerage | 3.0 | n.i.v. (lane self-check: 4→3) | Milly 3%, Insurance Agency Trader 2%, Oak Street exchange free. State Farm agents don't own their books. |
| #5 Franchise resale/conversion placement | 3.0 | n.i.v. (lane self-check) | Franzy ($2.2M seed) is a resale marketplace. Some conversion programs waive the fee. CA SB 919 broker registration from July 2027. |
| #4 Independent pharmacy exit / file brokerage | 2.0 | n.i.v. (lane self-check: 3.5→2) | McKesson RxOwnership is free (7,400+ owners helped); Cardinal also free. Chains buy files directly. |
| #7 SMB tenant representation | 2.0 | n.i.v. (lane self-check: 3→2) | Small deals go direct with owners. $3.6–5.4K per deal. Lease expirations aren't observable. SquareFoot and TenantBase compete. |
| Main Street micro-brokerage | — | rejected by lane | Baton 6% + $1K/mo; Rejigg free to sellers; OffDeal, Tupelo, Smobi. 17-state real-estate licence burden. |
| Used restaurant equipment | — | rejected by lane | Dealer buyouts recover 10–30%; auctions take 10–20%. Rigging and removal can't be automated. |
| Heavy, construction and lab equipment | — | rejected by lane | RB Global/IronPlanet takes 8–14%; EquipNet, BioSurplus, LabX. Capital and logistics heavy. |
| Dental equipment | — | rejected by lane | 10–20% brokers, zero-commission auctions, ABC Dentalworks buyouts. |
| Freight capacity matching | — | rejected by lane | Needs a $75K BMC-84 bond. Margins under 15%. AI-agent vendors (Vooma, HappyRobot) already sell to brokers. |
| Website and domain brokerage | — | rejected by lane | Flippa 5–10%, Empire Flippers 15%, Motion Invest 7–20%. AI search is eroding content-site values. |
| Dental and vet practice brokerage | — | rejected by lane | Established brokers at 6–12%; DSO in-house teams; guarded professionals. |
| Solar and roofing appointments | — | rejected by lane | Commodity at $72–300 per appointment. Residential solar forecast to fall 33% in 2026. |
| Solar land origination | — | rejected by lane | OBBBA construction cliff (4 July 2026). LandGate and SolarLandLease sell landowner leads. |
| Commercial energy brokerage | — | rejected by lane | ~$400/yr per small account; state registration in most deregulated states. |
| Excess-inventory liquidation and government surplus | — | rejected by lane | B-Stock and Liquidity Services/GovDeals ($4B+ sales) own both sides. Arbitrage needs capital. |
| Home-services lead marketplace | — | rejected by lane | Angi $15–120/lead, Thumbtack $10–80. Contractors hate shared leads. Saturated. |
| Janitorial account brokering | — | rejected by lane | Jani-King/Coverall model with misclassification litigation history. Pay-per-appointment vendors at ~$135. |
