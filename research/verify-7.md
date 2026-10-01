# Verify-7: Adversarial verification of round-2 standalone ideas, plus a second opinion on the round-1 survivors

*Independent verifier session, 2026-10-01. Research only: no outreach, signups, records requests or purchases. I read the source write-ups with `git show origin/research/<branch>:research/<branch>.md` for branches 13, 14, 15, 12, 04, 08 and 01, and for verify-1, -2, -4 and -5. Five parallel sub-agents then attacked the ideas, each with its own search cap. In total they ran about **170 web searches and fetches**: 36 (RateLift), 40 (sales tax + Prequal), 30 (Overdue Feed), 27 (liquor licenses) and 37 (round-1 survivors). On top of that I ran a few direct queries against the data.ca.gov CKAN SQL API to re-check the stormwater data myself. Claims a sub-agent could not confirm are marked **unverified**.*

---

## Verdict summary

| # | Idea (source branch) | Prior score | Verdict | **Revised** | Single most likely failure |
|---|---|---|---|---|---|
| 1 | RateLift: RV and heavy-truck warranty retail-rate uplift (13) | 4.0 | **KILLED (RV) / WEAKENED (truck)** | **2.0** | The statutory lever is weak or missing. RV acts guarantee only the "lowest retail rate, if reasonable" plus a fixed 30% parts handling charge, with no 100-RO mechanism. Truck OEMs (DTNA) already run their own annual labor-rate process capped at posted rate. |
| 2 | Vendor-side sales-tax overcharge recovery (13) | 4.0 | **WEAKENED** | **3.0** | Recoveries at $2–30M manufacturers are too small to support 30% contingency, and the "vendor route" adds no value. Buyers can claim directly in OH, WI, IN, NC, MI and PA. In vendor-only states (IL) the vendor can just say no. |
| 3 | Overdue Feed: fire ITM overdue lists (14) | 4.0 | **WEAKENED** | **3.0** | Brycer (TA Associates-backed, bought IROL in Jan 2026) owns the data supply and already sells contractors "inbound demand without cold outreach". Our email arrives after the official notice and looks like a known scam. |
| 4 | Quota liquor-license brokerage, FL/PA/MI (15) | 3.5 | **WEAKENED (near KILLED)** | **2.5** | The bottleneck is buyers, not sellers. FL does only about 150–250 4COP deals a year against about 206 live listings. First commission is 9–15 months out. |
| 5 | Prequal Desk: ISN/Avetta/Veriforce DFY (12) | 4.0 | **WEAKENED** | **3.0** | The proposed $449 multi-platform price sits above published competitors (Contractor Compliance Pros: $350 for three platforms, with guarantees; QuickComply about $150/mo). Avetta is automating the labor itself, and ISN can terminate affiliated users. |
| 6a | CA stormwater citizen-suit risk monitor (04 / verify-2) | 5.0 | **BETTER THAN THOUGHT** | **5.5** | Owners ignore pre-notice risk mail. Unsolicited "you look like a lawsuit target" mail can itself read like the shakedown. |
| 6b | Pro-se trademark office-action feed (08 / verify-4) | 4.5 | **WORSE** | **3.5** | The USPTO now names "letters offering to represent you after an Office Action" as a scam pattern. The workbench pivot is already crowded (ActionResponder, Questel Qthena). |
| 6c | Trades M&A per-meeting origination with staleness score (01 / verify-1 / verify-5) | 3.5–4.5 | **AS THOUGHT (slightly worse)** | **3.5** | The staleness score never shows lift over tenure, so the offer is one more $350–600 meeting in a market with Axia, SourceCo/CAPTARGET, DealSource, CT Acquisitions and Collar AI (YC F26). |

**Headline.** None of the five round-2 standalone ideas survives above 3. Each source lane already graded them 3.5–4. This independent pass lowers every one, because each has a structural defect the lane missed:
- a wrong statute (RateLift);
- a needless legal workaround (sales tax);
- a data supplier that is also the competitor (Overdue Feed);
- a demand-side bottleneck (liquor);
- a price above the published market (Prequal).

The only idea that moved **up** is the round-1 **CA stormwater monitor**. It moved up because the open data turned out to be richer than reviewers knew. It carries a contact email for almost every active facility, and its smallest targets look very much like the brothers' existing small-business customer base.

---

## 1. RateLift: RV and heavy-truck dealers (13-found-money)

**Verdict: KILLED for RV, WEAKENED for heavy truck. Revised score 2/10** (was 4.0). Confidence: medium-high on the statutes, medium on the economics.

### Claims checked

| Claim (lane 13) | Finding | Source | Holds? |
|---|---|---|---|
| "FL 320.696 ties RV warranty pay to retail charges" | RVs fall under Florida's **separate RV act**. §320.3207 says labor "may not be less than the **lowest** retail labor rates actually charged… as long as such rates are reasonable". Parts get "actual wholesale cost plus a minimum 30-percent handling charge". There is no sequential-RO submission mechanism. | https://florida.public.law/statutes/fla._stat._320.3207 | **No.** Wrong statute, and a weaker standard than auto. |
| Auto franchise acts cover RVs in many states | PA's warranty statute: "This section shall not apply to recreational vehicle warrantors or dealers." RVIA lobbies for RV-specific laws in every state, describing auto acts as a "misfit". | https://www.dealeruplift.com/state-retail-warranty-reimbursement-laws/pennsylvania-warranty-reimbursement-law/ ; https://www.rvia.org/advocacy/policies/franchise | **No** |
| CA gives RV dealers the retail rate | Veh. Code §3075 (RV) requires only "reasonable" compensation. The retail rate is one factor among "all other relevant criteria". | https://www.nmvb.ca.gov/protest/protests_warranty_parts.html | **No** |
| New legislation is a tailwind | Maryland's 2024 RV franchise law was negotiated by RVIA and "specifies rates of reimbursement and handling charges". In other words, it writes the weaker model into law. | https://mgaleg.maryland.gov/2024RS/fnotes/bil_0004/sb0504.pdf ; https://www.rvia.org/news-insights/marylands-rv-specific-franchise-bill-signed-law | **No.** The trend runs against the idea. |
| The RV dealer's pain is the hourly rate | Dealer and forum evidence points to **flat-rate times** (e.g., Forest River) as the main complaint. The average RV shop rate is about $199/hr. What OEMs actually pay per hour is **unverified**. | https://www.mygrandrv.com/threads/prevailing-labor-rates.71481/ | Partly |
| "SD amended its truck statute in 2021 to require retail labor and parts" | SB 101 applies the dealer-compensation section to makers of **separately warranted engines, transmissions and axles** in medium/heavy trucks. It is one state, and it targets component makers, not truck OEMs in general. | https://mylrc.sdlegislature.gov/api/Documents/217732.pdf | **Overstated** |
| Truck dealers need a third party to win retail rate | DTNA (Freightliner) Warranty Manual WAR406 already sets out an **annual labor-rate request** with a 100-consecutive-RO appeal. The rate is capped at posted retail and depends on a 50-mile competitive analysis. Parts handling is a fixed 33%. Dealers do this in-house. | https://static.nhtsa.gov/odi/tsbs/2019/MC-10161129-9999.pdf (2019 edition) | **Mostly no.** Parts markup is the only possible gap. |
| Truck market size | ATD Data 2025: 3,798 new-truck dealerships (about 2,104 M/HD). Warranty is about $2.51B of labor and $2.90B of parts, so roughly $0.7–1.2M of warranty labor per M/HD store. | https://www.nada.org/media/5008/download | Holds (the money is real, the rate gap is not shown) |
| About 2,980 RV dealerships | VerticalIQ says 2,980. IBISWorld says 8,123 under a broader definition. No RVDA count was found. | https://verticaliq.com/product/rv-dealers/ ; https://www.ibisworld.com/united-states/number-of-businesses/recreational-vehicle-dealers/1006/ | Roughly |
| Incumbents are "auto-focused", leaving RV and truck open | **Centralized Warranty Management Group** already sells RV dealers "manufacturer-specific labor rate increase requests built from your own repair order data". It is bundled with outsourced claims across Thor, Forest River, Winnebago, Lippert and Dometic. Bellavia Blatt has run an RV retail-reimbursement webinar. Armatus reports 15,500+ approvals with 29 OEMs (RV and truck coverage unconfirmed). | https://centralizedwmg.com/ ; https://www.dealerlaw.com/2022/03/applying-for-retail-parts-markups-labor-rates-for-warranty-work-in-the-rv-industry/ ; https://www.dealeruplift.com/retail-warranty-reimbursement/ | **No** |
| "Thor paid $85.7M of claims in one quarter" | Not re-verified within budget | — | Unverified |

**Hidden competitors:** CWMG (RV warranty administration plus rate requests, price not published); Bellavia Blatt (law firm); Armatus (contingent); Warranty Consulting Services (heavy equipment, since 1997); QB Business Solutions, Withum ($7,500 flat), Warranty Part/Wooden and Dealer360 (auto, but able to extend); and truck dealers' own in-house filings.

**Most likely failure.** The legal lever doesn't exist in the form the pitch assumes. Whatever uplift remains is small and contested, which can't support a 30% contingency sold by cold email.

**What could salvage a piece of it.** A contingency **RV claims-recovery** service (denied claims, flat-rate time disputes, supplier-portal filings) addresses the real pain, but it competes head-on with CWMG. Only after a dealer-law attorney's state survey shows statutory retail markup beating DTNA's 33% would a **truck parts-markup** test be worth running. Neither is worth the brothers' time ahead of the ideas below.

---

## 2. Vendor-side sales-tax overcharge recovery (13-found-money)

**Verdict: WEAKENED. Revised score 3/10** (was 4.0). Confidence: medium.

| Claim | Finding | Source | Holds? |
|---|---|---|---|
| Going through the vendor avoids licensing and is the practical route | In most large manufacturing states the **buyer can claim directly**. WI allows it for claims of $50+ in tax, a closed seller or a closed period. OH has Form ST AR. IN allows it if the retailer refuses. NC has E-588. MI allows it since 2019 when the exemption wasn't claimed at purchase. PA also allows it. (OH, IN, NC, MI and PA come from search summaries; the statutes weren't read in full.) | https://www.revenue.wi.gov/DOR%20Publications/pb216.pdf ; https://tax.ohio.gov/portals/0/forms/sales_and_use/Appeals2012/ST_STAR_FI.pdf ; https://www.in.gov/dor/i-am-a/business-corp/sales-use-tax-refunds/ ; https://www.ncdor.gov/taxes-forms/sales-and-use-tax/refund-claims ; https://www.salestaxinstitute.com/resources/michigan-issues-guidance-on-sales-and-use-tax-refund-procedures | **No.** The workaround adds little. |
| Vendors will issue credits | **Illinois:** only the retailer can claim, and the state "has no authority to compel a retailer to refund". **Virginia:** dealers may refuse if they consider the sale taxable or the refund exceeds about 2× their average monthly liability. | https://taxarchive.illinois.gov/content/dam/soi/en/web/taxarchive/research/legal/letter-rulings/sales-tax/2018/st-18-0039-gil.pdf ; https://www.tax.virginia.gov/sites/default/files/inline-files/retail-sales-and-use-refund-procedures-guidelines-june-2017.pdf | **Weak** |
| A partner CPA files the state claims | The AICPA code and several state boards bar CPA contingent fees on "ordinary refund claims". | https://www.njcpa.org/stayinformed/hubs/topics/commissions-and-contingent-fees ; https://www.thetaxadviser.com/issues/2014/nov/tax-clinic-04-nov-2014/ | **Risky** for the partner structure |
| An AI-native entrant would be differentiated | **Arthiva** already does AI review of all purchases with no upfront fee. Thomson Reuters launched ONESOURCE Sales & Use Tax AI (Jan 2026). InvoiceDataExtraction targets this exact manufacturer reverse audit, with a free tier. | https://arthiva.ai/ ; https://www.thomsonreuters.com/en/press-releases/2026/january/thomson-reuters-launches-ai-tax-compliance-solution-that-saves-time-and-reduces-risk ; https://invoicedataextraction.com/blog/manufacturer-reverse-sales-tax-audit | **No** |
| Recoveries are meaningful at $2–30M firms | The published cases are $350k, $385k and $200k, all from firms that look larger. No SMB benchmark for % of AP overpaid was found. | https://www.cbh.com/services/tax/state-local-tax/sales-use-tax/reverse-sales-tax-audit-services/ ; https://thesaltgroup.com/a-costly-oversight-turned-into-a-385k-sales-tax-refund/ | **Unverified** for SMBs |
| About 60k firms in the band | 239,265 manufacturing *firms* (2022). About 93% have fewer than 100 employees, so 45–60k in the band is plausible. The lane's "250k" counted establishments, not firms. | https://nam.org/mfgdata/facts-about-manufacturing-expanded/ | Roughly |
| Cold email works with controllers | No data. Asking for AP data upfront is a trust barrier. | — | Unverified |

**Hidden competitors:** Arthiva; The Sales Tax People (sales.tax); The SALT Group; McKonly & Asbury, LBMC, MGO, Aprio, KPMG; AppZen (T&E); InvoiceDataExtraction (DIY).

**Most likely failure.** The recovery per client is probably $5–40k over the lookback (unverified guess), which makes the fee a few thousand dollars. Meanwhile in vendor-only states the vendor can refuse, and in direct-claim states specialist firms and Arthiva get there first.

---

## 3. Overdue Feed: fire ITM overdue lists (14-proprietary-data)

**Verdict: WEAKENED. Revised score 3/10** (was 4.0). Confidence: medium.

Records access turned out *better* than the lane feared. Market structure turned out *worse*.

| Claim | Finding | Source | Holds? |
|---|---|---|---|
| TCE, LIV, IROL and BuildingReports are independent sources | **Brycer acquired IROL on 8 Jan 2026** and took a TA Associates growth investment in Jan 2025 | https://www.thecomplianceengine.com/post/brycer-expands-fire-safety-compliance-market-reach-with-the-acquisition-of-inspectionreportsonline ; https://www.businesswire.com/news/home/20250130398374/en | **No.** The vendors are consolidating, and the PE owner has a motive to sell the demand itself. |
| TCE covers 2,000+ AHJs | Brycer's own Jan 2026 release says "over 1,420 AHJs" | same as above | **Overstated** |
| Brycer is not a lead competitor | The May 2026 campaign says: "consistent, trackable source of inbound demand… Without cold outreach, inspection companies increase… revenue". The 2026 roadmap adds Premises Portal and Compliance Sync, with no paid lead routing *yet*. | https://ground.news/article/the-compliance-engine-expands-access-to-compliance-driven-work-for-inspection-companies ; https://www.thecomplianceengine.com/post/brycer-continues-to-expand-the-compliance-engine-with-new-2026-services | **No.** Our pitch is Brycer's marketing line, and Brycer gives it away free. |
| The vendor's contract blocks disclosure | City contracts say "clients own all the data". | https://www.papillion.org/DocumentCenter/View/8825/C11-R21-0104-Fire-Inspection-Database-Agreement-Brycer ; https://www.littlerock.gov/city-administration/board-of-directors/meeting-agenda/AGENDA%20-%20WEB%20-%204-2-2024/O%20-%20Brycer%20Compliance%20Engine%20Agreement.pdf | Good for us. The data is an AHJ record. |
| Texas security exemptions block it | §418.182 covers anti-terror *security systems*, and §418.181 covers critical-infrastructure vulnerabilities. Neither names sprinklers or alarms. A 2006 AG ruling **ordered release** of high-rise fire-safety plans. | https://texas.public.law/statutes/tex._gov't_code_section_418.182 ; https://www2.texasattorneygeneral.gov/opinions/openrecords/50abbott/orl/2006/htm/or200614574.htm | **Mostly no** |
| Florida is out | §119.071(3)(a) makes records "revealing… firesafety systems" of private property confidential | https://www.flsenate.gov/Laws/statutes/2025/119.071 | **Yes.** FL is the only state found with an explicit fire-system exemption. |
| CA and IL exemptions | CA Gov Code 7929.210 covers IT security, not fire systems. IL 7(1)(v) is narrow and needs clear and convincing proof. | https://law.justia.com/codes/california/code-gov/title-1/division-10/part-5/chapter-17/section-7929-210/ ; https://illinoisattorneygeneral.gov/Page-Attachments/FOIAPAC/Non-Binding-PAC-Opinions/FOIA/7_1/Exemptions-which-permit-redacting-withholding-exempt-information-records/7_1_v/70212,%20issued%20October%2013,%202022.pdf | No block |
| Owners hit by notices have no vendor | TCE notices go out automatically and carry AHJ fees of $100 rising to $250, and they print the contractor of record. | https://www.chinovalleyfire.org/faq.aspx?TID=16 ; https://www.sedalia.com/wp-content/uploads/compliance-implementation-plan.pdf | **No** |
| Contractors want more demand | Labor is the top problem (41.9% overall; 47.1% of Inspect Point users). "Qualified technicians are the constraint". | https://www.inspectpoint.com/2026-fire-life-safety-industry-report-key-trends-shaping-fire-protection/ | **No.** Many buyers are capacity-limited. |
| Buyer pool of independents | Pye-Barker made 22 acquisitions in H1 2026 and now operates in 47 states | https://internationalfireandsafetyjournal.com/pye-barker-acquisitions-2026/ | Shrinking |
| Owners will trust a "you're overdue" email | Green Bay (2025), Culver City and the NV AG all warn about fake fire-inspection notices | https://www.wbay.com/2025/06/02/green-bay-metro-fire-department-warns-about-fake-fire-inspector-scam/ ; https://www.culvercityfd.gov/News-articles/Fraud-Awareness-Fake-Fire-Inspectors | **No** |
| No one sells this kind of list | **BuildDocket** sells NYC violation and compliance-deadline owner lists at **$199/mo per trade per borough**. ViolationWatch charges $9 per building per month and DOBGuard from $14.99/mo. Some cities publish fire inspection data openly (SF, Detroit, Norfolk, NYC FDNY). | https://builddocket.com/ ; https://violationwatch.nyc/ ; https://dobguard.com/ ; https://data.sf.gov/Housing-and-Buildings/Fire-Inspections/wb4c-6hwj/data | **No.** A data-only price anchor of about $200/mo sits far below the proposed $750–1,500. |

**Most likely failure.** Our data supply depends on AHJs that are Brycer's customers and revenue-share partners. Brycer can ship lead routing whenever it chooses. The pool left after its notices is small, cold and wary of scams.

**Best salvage.** Sell **open-deficiency repair** follow-up rather than overdue inspections, because repair is higher-ticket and the incumbent doesn't get it back automatically. Charge per booked visit, sell only to contractors with spare technicians, and prove conversion first on open city data (SF, NYC).

---

## 4. Quota liquor-license brokerage, FL / PA / MI (15-agent-brokerage)

**Verdict: WEAKENED, close to KILLED. Revised score 2.5/10** (was 3.5). Confidence: medium.

| Claim | Finding | Source | Holds? |
|---|---|---|---|
| FL brokerage needs a real-estate licence | §475.01: "broker" covers "business enterprises or business opportunities… or any interest in or concerning the same", and §475.41 voids commission contracts made by unlicensed brokers. **Attorneys are exempt**, so lawyer-brokers compete without the licence. | https://www.leg.state.fl.us/statutes/index.cfm?App_mode=Display_Statute&URL=0400-0499/0475/Sections/0475.01.html ; https://www.flsenate.gov/Laws/Statutes/2010/0475.41 | Holds |
| PA needs a licence | 63 P.S. §455.201 defines real estate as an interest in land and doesn't mention business opportunities. **No licence is needed** to broker a bare liquor licence (PLCB broker rules unverified). | https://codes.findlaw.com/pa/title-63-ps-professions-and-occupations-state-licensed/pa-st-sect-63-455-201/ | Easiest state legally |
| MI | MCL 339.2501 covers anyone who negotiates "the purchase or sale or exchange of a business, business opportunity". That means a **second, Michigan** licence. | https://www.legislature.mi.gov/Laws/MCL?objectName=mcl-339-2501 | Adds friction |
| FL list counts | Re-downloaded: 4,350 active (2,224 4COP) and 596 inactive (298 4COP) | https://www2.myfloridalicense.com/abt/licensing/quota_license_lists/documents/ActiveQuotasforInternetwithSecondaryStatus20.xlsx | Holds |
| Inactive holders are motivated sellers | 92% are LLCs or corporations. Repeat holders include Florida Fine Wine & Spirits (4), Publix (3), a mortgage holding company (4) and The Villages (2), who are land-bankers. The realistic pool is about 150–200 holders. | same file (sub-agent analysis) | Partly |
| Transfer volume about 250 a year in FL | 4COP status-date changes per year: 159 (2023), 188 (2024), 239 (2025), 200 (2026 YTD). This is an **upper bound** that also counts reactivations. The state adds about 52 new quota licences a year by lottery. | same file ; https://www.gloverlaw.net/articles/quotalottery2025 | **About 150–250.** With about 206 live listings, that is roughly 12 months of inventory. |
| Commission of 8–15% | The market is 5–10%, or $3–10k flat from attorneys | https://liquorlicensecost.com/guides/liquor-license-broker ; https://koronapos.com/blog/how-much-does-a-liquor-license-cost-in-florida/ | 15% won't hold |
| PA private market is open | PLCB auctions expired R licences itself. The 15th auction averaged $284k, and a 2026 round offers 20 more. | https://www.pa.gov/agencies/lcb/about-us/press-room/plcb-names-top-bidders-in-first-excess-restaurant-license-auctio ; https://tuckerlaw.com/2026/08/12/pennsylvania-liquor-license-opportunity-plcb-opens-bidding-for-20-expired-restaurant-licenses/ | The state competes for buyers |
| MI values are worth brokering | Class C runs $25k rural to $50–150k metro. Redevelopment licences cost a flat $20k from the state, which caps prices. | https://michigan-liquorlicense.com/liquor-licenses-for-sale/ ; https://www.michiganbusiness.org/globalassets/documents/reports/fact-sheets/redevelopment-liquor-licenses-pa-16.pdf | A 10% commission is only $5–13k |
| Demand is stable | Gallup 2025: 54% of US adults drink, a 90-year low. FL's SFS route takes small restaurants out of the quota market. | https://news.gallup.com/poll/693362/drinking-rate-new-low-alcohol-concerns-surge.aspx ; https://business-law-review.law.miami.edu/floridas-game-changing-alcohol-licensing-reform-a-win-for-small-restaurants/ | Weakening |

**Additional competitors:** MI: Michigan Liquor License Connection, MyLiquorLicense.com, LiquorLicenseFast. PA: paliquorlicensebroker.com, BizQuest and DealStream listings. FL: Liquor License Professionals, ProVantage, alcohol-license.com, and lottery attorneys (Glover, Rubert, Jimerson). AI/SEO sites (liquorlicensecost.com, liquorready.com) already rank for buyer search terms.

**Unit economics.** One FL deal is about $300k × 8% = $24k, leaving $12–17k after the sponsoring broker's split. A new shop might close 2–6 deals a year by year 2. Counting licensing, a buyer search and DBPR approval, the **first commission is 9–15 months out**.

**Most likely failure.** The shop signs idle-licence holders easily but can't find buyers before incumbents with buyer lists and search rankings do.

**Best salvage.** Flip the model to **buyer-side lead generation**: new bar and package-store openings, near-threshold SFS applicants. Sell those leads to incumbent brokers (no licence needed in PA). It is still small and non-recurring.

---

## 5. Prequal Desk: ISNetworld / Avetta / Veriforce done-for-you (12-dfy-backoffice)

**Verdict: WEAKENED. Revised score 3/10** (was 4.0). Confidence: medium.

| Claim | Finding | Source | Holds? |
|---|---|---|---|
| $750 setup + $299/mo ($449 multi-platform) is competitive | **Contractor Compliance Pros** charges $900 setup per platform and **$250/$300/$350 a month for 1/2/3 platforms**, with an "approved or setup fee back" guarantee and "first month free if not submitted in 5 days". | https://contractorcompliancepros.com/ | **No.** Our multi-platform price is above market and has no guarantee. |
| Same | **QuickComply** charges $1,800/yr (about $150/mo) for 1–10 hiring clients, up to $7,800/yr. It covers ISN, Avetta and Veriforce with human account managers. | https://quickcomplyms.com/ | **No** |
| Same | SafetyPro's survey: basic $100–300/mo, enhanced $250–500/mo, full outsourcing $1–6k/mo | https://www.safetyproresources.com/blog/what-does-it-cost-to-hire-a-good-isnetworld-consultant | Mid-market only |
| Platforms don't crowd it out | Avetta **Vetify Expedited Compliance Support** offers a dedicated expert, renewals and monitoring (price not published). **Avetta One AI** reuses a supplier's past answers and adds the AskAva assistant, which automates the labor we'd sell. | https://www.avetta.com/suppliers-contractors/vetify ; https://www.avetta.com/blog/avetta-expands-ai-capabilities-to-accelerate-the-future-of-global-supply-chains | **No** |
| ISN tolerates multi-client consultants | ISN "may terminate a User's access… if we suspect the individual has an affiliation with another ISNetworld subscriber" | https://www.isnetworld.com/en/user-agreements/contractor-supplier | **Platform risk** |
| ISN RAVS Plus costs | $500–2,500 per document (Capterra; not confirmed on ISN's own site) | https://www.capterra.com/p/145737/ISNetworld/pricing/ | Unverified |
| A large pool of small contractors | ISN has 70k+ contractors (global) and Avetta claims 360k+ businesses in 120 countries. The US small-firm share was not found. | https://ehs.inc/ehs/isnetworld-vs-veriforce | Partial |
| No AI-native entrant | **Framework AI** (Canada) drafts Avetta and ISN forms. BasinCheck sells AI SaaS at $149–1,200/mo. CrewCompliance sells programs for $149. | https://frameworkai.ca/blog/what-is-avetta-canada ; https://basincheck.com/resources/best-software-isnetworld-compliance ; https://crewcompliance.org/isnetworld-ravs-safety-programs/ | **No** |
| Churn, reply rate, saturation | Not found. A dense consultant SEO field (Evolution, OccuPros, EHS Inc, JobQualified and others) suggests saturation. | https://evolutionsafetyresources.com/avetta-compliance-support-for-contractors/ | Unverified |

**Most likely failure.** It is a commodity service priced above guaranteed incumbents. The labor shrinks each time Avetta ships AI, and a multi-client operator's logins are revocable at ISN's discretion.

**Best salvage.** Only as a module inside the brothers' existing customer bundle (lane 12's Idea 5), priced at or below $150–250 a month for all platforms. The contractor's own employee should hold the login, with the agent preparing the work behind it.

---

## 6. Second opinion on the round-1 survivors

### 6a. CA industrial stormwater citizen-suit risk monitor (04-compliance, verify-2)

**Verdict: BETTER THAN verify-2 THOUGHT. Revised score 5.5/10** (verify-2: 5.0; the sub-agent proposed 6). Confidence: medium.

I re-ran part of the data check myself against the data.ca.gov CKAN SQL API (`datastore_search_sql`, resource `33e69394-83ec-4872-b644-b9f494de1824`, Industrial Facility Information, queried 2026-10-01):

- **20,429 Active** facilities. This matches verify-2. The full status mix also includes 29,867 Terminated, 1,777 NOI Required and 886 NEC Required.
- **20,359 of the Active facilities have a `FACILITY_EMAIL` containing "@"**, which is about 99.7%. There are 16,274 distinct addresses. Contact name, title and phone are also published.
- **3,436 Active facilities use consumer email domains** (gmail, yahoo, aol, sbcglobal, hotmail, att and similar), which marks them as owner-operated small businesses. **500 of the 676 SIC 5015 auto wreckers** and **278 of the 791 SIC 5093 scrap yards** fall in this group. This is my own query; the sub-agent's 20,308 figure covers industrial records only.

| Claim | Finding | Source | Holds? |
|---|---|---|---|
| Mapistry already competes | It has a "Litigation Intelligence Group", but that is bundled into an enterprise platform at about **$11k–27k per location per year** (third-party listing) | https://www.mapistry.com/blog/explaining-the-drastic-increase-in-stormwater-citizen-lawsuits ; https://subscribed.fyi/mapistry/reviews/ | Partly. The single-site owner-operator tier is **open**. |
| Contacts must be enriched | Contacts are already in the open data (my query above) | https://data.ca.gov/dataset/stormwater-regulatory-including-enforcement-actions-information-and-water-quality-results | **Better than thought** |
| Sampling gaps can be detected | Sub-agent query: 11,563 Active facilities enrolled before July 2024 have no 2024/25 monitoring rows (830 of them in the core SICs). This is noisy, since it includes no-exposure and no-discharge sites. The Violations table has 90,637 rows. Plaintiffs use NOAA rainfall to rebut "no qualifying storm" claims. | data.ca.gov resources 7871e8fe… and 9b69a654… ; https://natlawreview.com/article/el-nino-coming-what-california-industrial-facilities-need-know-about-stormwater | Holds |
| Settlements of $300k–625k | These are the high end. The **average across CA consent decrees since 2015 is about $79k per facility**, more than half of it attorney fees. | https://natlawreview.com/article/cottage-industry-economics-cwa-citizen-suit-enforcement ; https://www.allenmatkins.com/real-ideas/only-rain-not-dollars-down-the-drain-minimizing-industrial-stormwater-permit-litigation-risks.html | Weakened, but $79k still supports a $500–1,500 audit |
| Notice volume | No current public count. Board tracking ended in 2010. One plaintiff firm sent 98 notices in 2017. | https://www.waterboards.ca.gov/water_issues/programs/enforcement/rpts_citizensuits.shtml | Unverified for 2024–26 |
| Regime stability | The 2014 IGP is administratively continued, and no bill to limit citizen suits was found | https://www.frogenv.com/blogs/post/california-industrial-stormwater-compliance-in-2026 | Holds |
| QISPs as a channel | QISP training is $505, so the field is fragmented. No count was found. | https://www.casqa.org/training/igp-training/qisp-overview | Unverified WTP |
| New competitor | **californiastormwater.com** ("Your Data Our Science") covers 19,703 registrations with NAL comparisons, aimed at QISPs and lawyers. It has **no risk scoring yet**. | https://californiastormwater.com/ | The closest clone |

**Why it ranks higher than the reviewers said.** Three findings were missed.
1. The data *includes* the buyer's email, which removes the enrichment cost and deliverability risk of scraped contacts.
2. The incumbent prices itself out of single-site yards.
3. The bottom of the market is about 3,400 owner-operators on Gmail-type addresses, who look a lot like the brothers' existing small-business customer base. Many of them will also have weak websites, which opens a cross-sell.

**Why it is still not a 7.**
- Demand is reactive.
- "You look like a lawsuit target" from a stranger reads like extortion.
- The QISP channel's willingness to pay is untested.

**Most likely failure.** Owners ignore pre-notice mail and buy only lawyers and QISPs after a 60-day notice arrives.

**Best variant.**
- Sell a fixed-fee **pre-notice self-audit ($500–1,500)** that covers sampling gaps against NOAA rain days, late annual reports and NAL exceedances over the plaintiffs' 5-year lookback.
- Sell it **white-labelled through QISP firms**, with a **$50–100/mo watch** for single-site 5015/5093 operators.
- Validate first by back-testing against notices or consent decrees from PACER, then a 200-site letter test.

### 6b. Pro-se trademark office-action feed (08-legal-ip, verify-4)

**Verdict: WORSE than verify-4 thought. Revised score 3.5/10** (verify-4: 4.5). Confidence: medium.

| Claim | Finding | Source | Holds? |
|---|---|---|---|
| Pro-se emails remain visible | Unrepresented owners' emails are "still viewable in the correspondence email address field" | https://content.govdelivery.com/accounts/USPTO/bulletins/28837b5 | Holds |
| Volume is growing | FY2025: 824,192 classes (+57k) | https://www.uspto.gov/sites/default/files/documents/fy25pbr.pdf | Holds |
| AI examination raises OA volume | First-action pendency fell to about 4.45 months, and the Class ACT auto-classifier launched (Mar 2026). AI "scam detection" is planned. No evidence of more OAs. | https://iipla.org/news/uspto-advances-trademark-application-efficiency-cuts-pendency-times-in-fy-2026 ; https://www.sternekessler.com/news-insights/insights/uspto-launches-ai-examination-tools-what-this-means-for-trademark-applicants/ | Not shown |
| The scam channel is a manageable risk | The USPTO's scam page tells applicants that "after an Office Action is issued, applicants may receive letters offering to represent them". FY2026 brought 11 sanctions orders and about 10k filings purged. | https://www.uspto.gov/trademarks/protect/recognizing-common-scams ; https://www.swlaw.com/publication/fighting-back-against-trademark-scams-what-the-usptos-enforcement-push-means-for-brand-owners-and-their-counsel/ | **Worse.** The exact outreach is now on the regulator's scam list. |
| Attorneys want raw leads | A new Apify actor sells pro-se leads at $6 per 1k and has **10 total users, 2 monthly active** | https://apify.com/foxlabs/uspto-trademark-leads | Demand looks weak |
| The workbench pivot is open | **ActionResponder** (USPTO sync, AI drafts, batch client notices), **Questel Qthena**, Trademarkraft | https://actionresponder.ai/ ; https://www.questel.com/trademark-office-action-response-management-with-ai/ | **No** |
| Price floor | L4SB from $89 | https://www.l4sb.com/services/trademark-office-action-response/ | Holds |

**Most likely failure.** Attorneys won't buy into a channel the USPTO publicly labels a scam pattern, and applicants treat the outreach as fraud. Deprioritise.

### 6c. Trades M&A per-meeting origination with a website-staleness succession score (01, verify-1, verify-5)

**Verdict: AS THOUGHT, slightly worse. Revised score 3.5/10.** Confidence: medium.

| Claim | Finding | Source | Holds? |
|---|---|---|---|
| Website staleness predicts sale or retirement | No published evidence. Incumbents score owner age, tenure of 15+ years, reviews and dealer status. | https://dealsourcesystems.com/blog/hvac-company-acquisitions-sourcing/ | Unproven |
| Search funders are a long-tail buyer | Stanford 2026: 862 funds tracked, about 181–190 launches in 2024–25, about 48% acquire. That is about 90 new searchers a year. | https://www.caldergr.com/acquisition-search-is-getting-harder-takeaways-from-stanfords-2026-search-fund-study/ | Tiny market |
| Independent sponsors are a buyer | About 1,400–1,500 active (twice the 2019 level), 27% of Axial closed deals | https://www.axial.net/forum/axials-2025-independent-sponsor-report/ ; https://www.peony.ink/blog/independent-sponsor-guide | **The better segment** |
| $350–600 per meeting | Pay-per-appointment runs $300–600; managed programs $4–25k a month | https://axiagrowth.com/blog/in-house-bdr-vs-outsourced-deal-sourcing | Commoditised |
| Owner reply of about 0.57% is unworkable | DealSource reports 133 owner conversations in 90 days for one client | https://dealsourcesystems.com/blog/hvac-company-acquisitions-sourcing/ | Workable at volume, but incumbents have that volume |
| Competition | Newly found: **CT Acquisitions** (home-services buy-side, 2,000+ operator relationships, paid at close) and **Collar AI** (YC F26). Q2Q (YC W26) is confirmed inactive. | https://ctacquisitions.com/guides/deal-origination-home-services/ ; https://www.extruct.ai/data-room/ycombinator-companies-f26/ ; https://www.ycombinator.com/companies/q2q | Worse |
| Licensing | CA and FL treat business sales as real estate. About 23 states have M&A broker exemptions. Flat per-meeting fees with no negotiation are probably lead-gen (unverified). | https://www.ibba.org/articles/the-state-line-trap/ ; https://www.dre.ca.gov/files/pdf/refbook/ref24.pdf | A constraint |

**Most likely failure.** The staleness score shows no lift, so the offer is one more $400 meeting against incumbents with deeper owner relationships.

**Best variant.** Run a **back-test first**. Score CSLB licences later cancelled or transferred, or BizBuySell "owner retiring" listings, against a control group. Only if that shows lift should the score be sold as a data add-on to the existing originators (DealSource, Axia, SourceCo) or to independent sponsors.

---

## 7. Cross-cutting lessons

1. **The source lanes' self-verification was too generous, and every idea dropped another 0.5–2 points.** The recurring blind spots:
   - Statutes paraphrased from secondary sources (RateLift's FL citation pointed at the wrong act).
   - Price comparisons made against "consultants charge $100–6,000" ranges rather than the cheapest *published* competitor (Prequal).
   - Not checking whether the data holder had *just* consolidated (Brycer + IROL, Jan 2026).
2. **"Regulator scam warnings" is a new kill pattern.** Fire departments warn about fake inspection notices and the USPTO lists post-OA solicitation letters as scams. When the regulator has publicly described our outreach as a scam template, the cold-email model breaks however good the data is. The brothers should search "[industry] scam warning" before scoring any trigger-based outreach idea.
3. **Demand-side bottlenecks beat supply-side automation.** In both the liquor-licence and fire cases the agents are best at the part that isn't scarce: finding sellers or finding overdue buildings. The scarce part is the buyer, or the technician's capacity.
4. **Open data that includes contact emails is rare and valuable.** The stormwater dataset publishes a contact email for 99.7% of facilities. That is the only "data moat" in this batch that isn't owned by a would-be competitor.

---

## 8. Final ranking (all ideas in this verification)

Scores are 1–10. Competition: 10 = blue ocean.

| Rank | Idea | Verdict | Market | WTP | Data | Automation | Competition | Recurring | Time to $ | **Overall** |
|---|---|---|---|---|---|---|---|---|---|---|
| 1 | **CA stormwater pre-notice audit and watch** (white-label via QISPs; direct to about 3,400 owner-operated sites) | BETTER THAN THOUGHT | 4 | 6 | 9 | 8 | 5 | 6 | 4 | **5.5** |
| 2 | Pro-se TM office-action feed or workbench | WORSE | 4 | 3 | 8 | 8 | 3 | 5 | 4 | **3.5** |
| 2 | Trades M&A per-meeting origination + staleness score | AS THOUGHT | 5 | 6 | 6 | 7 | 2 | 4 | 3 | **3.5** |
| 4 | Overdue Feed (fire ITM) | WEAKENED | 3 | 4 | 5 | 7 | 3 | 6 | 3 | **3.0** |
| 4 | Prequal Desk (ISN/Avetta/Veriforce) | WEAKENED | 5 | 5 | 5 | 5 | 2 | 8 | 5 | **3.0** |
| 4 | Vendor-side sales-tax recovery | WEAKENED | 5 | 4 | 3 | 6 | 3 | 3 | 3 | **3.0** |
| 7 | Quota liquor-licence brokerage (FL/PA/MI) | WEAKENED (near KILLED) | 2 | 5 | 8 | 5 | 3 | 1 | 2 | **2.5** |
| 8 | RateLift: RV + heavy-truck warranty uplift | KILLED (RV) / WEAKENED (truck) | 2 | 3 | 3 | 6 | 3 | 3 | 3 | **2.0** |

**Recommendation.**
1. **Fund one cheap test from this batch: the stormwater pre-notice audit.**
   - Back-test the gap and exceedance features against 20–30 historical 60-day notices (PACER or plaintiff-group copies).
   - If the features separate noticed from non-noticed facilities, send a 200-letter/email test to owner-operated SIC 5015 and 5093 sites, plus 10 QISP-firm conversations.
   - **Kill if** the back-test shows no separation, fewer than 4 of 200 owners request the audit, or no QISP firm agrees to pilot.
2. **Drop RateLift, liquor-licence brokerage and the pro-se TM feed.**
3. Fold Prequal Desk and the sales-tax monitor into the brothers' existing-customer bundle **only** if the customer mix supports it. Do not pursue them as cold-outbound businesses.
4. For the fire and M&A ideas, run **only the zero-cost validations** already named: the 40-AHJ records test and the staleness back-test. Revisit only if they pass.
