# Verify-2: Adversarial verification of compliance and public-records ideas

*Research date: 2026-10-01. Desk research only: no emails, signups, outreach or purchases. Live API queries were run against NYC, Chicago, King County, Austin, SF, LA County, WA L&I, OR CCB, CA CSLB and data.ca.gov (SMARTS) on 2026-10-01. Two findings were re-checked by hand in this session:*
- *NYC had 919 distinct restaurants with 04K/L/M/N pest citations in Aug 2026.*
- *The WA L&I insurance dataset `ciwg-agsx` has the columns `InsuranceCompany, InsurancePolicyNo, InsuranceAmt, EffectiveDate, ExpirationDate, CancelDate, InsuranceAgencyName`.*

*Original write-ups checked:*
- *`origin/research/04-compliance:research/04-compliance.md` (ideas #1, #2, #3, #4)*
- *`origin/research/03-public-records:research/03-public-records.md` (ideas #1, #2)*

---

## Verdict summary

| # | Idea | Original score | Verdict | Revised score | Confidence |
|---|---|---|---|---|---|
| 1 | Prop 65 "Next Defendant" alerts + catalog scan | 7.4 | **KILLED as specified** (multi-brand retailer buyer); pivot is weak | **3.0** | Medium-high (0.7) |
| 2 | Restaurant inspection → pest/hood/refrigeration vendor router / DFY outbound | 6.8 (lane 04); ranked #2 (lane 03) | **WEAKENED** | **3.5** | Medium-high |
| 3 | Contractor coverage X-date engine | ranked #1 in lane 03 | **WEAKENED** | **4.0** | Medium-high |
| 4 | OSHA SST target predictor | 6.5 | **KILLED** (as a predictor) | **2.5** | Medium-high (0.75) |
| 5 | CA stormwater citizen-suit risk monitor | 6.4 | **WEAKENED** (data better than claimed; a direct competitor exists) | **5.0** | Medium (0.65) |

**Main pattern.** In every idea the public data turned out to be real, free and often *better* than claimed. Every idea failed instead on the **buyer side**, for one of three reasons:
- the buyer has little legal exposure (Prop 65 retailers)
- the account value is too small to pay for the deliverable (micro-contractor GL)
- the event is too rare to sell fear around (SST at about 0.1% per year)

On top of that, cheap Apify actors or a lookalike startup already sell the data layer in four of the five ideas, and those actors show **one or two monthly active users**. That is evidence of weak demand for the raw signal, not of an open field.

---

## 1. Prop 65 "Next Defendant" alerts + catalog scan (lane 04, #1)

**Verdict: KILLED as specified.** The product as written alerted 10–200-employee multi-brand retailers and charged $99/$299 a month. **Revised score 3/10** for the best pivot. Confidence medium-high.

### Claims checked

| Original claim | Finding | Source | Holds? |
|---|---|---|---|
| AG 60-day notice pages name brand, product, violators and chemical | Confirmed. Notice 2026-00064 lists the chemical (Lead), product ("Nuri Spiced Sardines in Tomato Sauce"), violators (Pinhais & Companhia; World Market, LLC), noticing party, attorney and docket. Some notices later carry an AG "No Merit" letter, as on 2025-04539. | https://oag.ca.gov/prop65/60-day-notice-2026-00064 ; https://oag.ca.gov/prop65/60-Day-Notice-2025-04539 | Yes |
| "No documented bulk export" | True for notices: the search UI shows up to 100 rows per page, with no CSV or RSS. Settlement reports do have per-year export links for 2016–2026. | https://oag.ca.gov/prop65/60-day-notice-search ; https://oag.ca.gov/prop65/report/out-of-court-settlements | Yes |
| "No explicit restriction" on use | Correct. Site terms say content is "considered in the public domain. It may be distributed or copied as permitted by law." | https://oag.ca.gov/conditions | Yes |
| "about 5,398 notices in 2024" | Confirmed: 5,398 in 2024, up from 4,142 in 2023. | https://natlawreview.com/article/prop-65-year-end-highlights-2024s-key-regulatory-changes-legal-battles-and | Yes |
| "$27.08M in 2024 out-of-court settlements, $23.55M attorneys' fees" | Confirmed: 1,082 settlements, $3.54M penalties and $23.55M fees (87%). Average about $24.6k. | https://ceitoday.com/conference-materials/2025/05-Settlement%20Hot%20Topics/Prop.%2065%20Out-of-Court%20Settlements%20in%202024-%20Year%20in%20Review.pdf | Yes |
| "2025: 1,545 out-of-court settlements worth $66.3M, plus 293 in-court worth $19.85M" | **Not traced to a primary report.** The AG page shows only year tabs and its CSV did not download as data. The figure implies a jump in average settlement from about $25k to about $43k. Plausible, but unverified. | https://oag.ca.gov/prop65/report/out-of-court-settlements ; https://www.gtlaw-consumerproductscounselor.com/2026/02/2025-california-proposition-65-trends/ | Unverified |
| "Amazon-product settlements typically $10k–$20k" | A law firm cites the same range. One forum anecdote: a $7.5k settlement, about $14.5k all-in. | http://www.tedlawfirm.com/what-amazon-sellers-should-know-about-californias-proposition-65/ ; https://terms.law/forum/thread/california-prop65-warning-requirement.html | Partly |
| "A retailer has 5 business days after receiving a notice to cure… so the urgency is concrete" | The 5-day cure exists (27 CCR §25600.2(f)(2)). **It cuts against the idea**: a noticed retailer can escape cheaply by posting a warning or pulling the SKU. The separate 14-day cure in H&S §25249.7(k) covers only four premises exposures, not product sales. | https://www.p65warnings.ca.gov/sites/default/files/2025-03/GuideSmallBusiness60day.pdf ; https://california.public.law/codes/health_and_safety_code_section_25249.7 | Partly, and against the thesis |
| Implicit: the multi-brand retailer is the liable party | **Wrong.** Under 27 CCR §25600.2(e), retailers must warn only in narrow cases: they sell their own or private-label brand, they received warning materials and didn't post them, they obscured a label, or they have "actual knowledge" and no manufacturer, importer or distributor is reachable in CA. Primary duty sits with the manufacturer or importer. | https://www.law.cornell.edu/regulations/california/27-CCR-25600.2 | **No** |
| Short-form warnings must name a chemical from 1 Jan 2028 | Confirmed. OAL approved the change 26 Nov 2024, effective 1 Jan 2025 with a 3-year phase-in. Products labeled under the old rules before 2028 can still be sold, so there is **no forced catalog-wide relabel**. | https://www.sgs.com/en-us/news/2024/12/safeguards-17724-california-approves-amendment-to-prop-65-warning-methods | Partly |
| Fewer than 10 employees are exempt | True. However, Amazon requires warnings from all sellers regardless of size. | https://www.goatconsulting.com/amazon-policy/california-prop-65-label-requirements-for-amazon-listings | Yes |
| "I found **no retailer-facing product that matches notices to catalogs.** Crowding: **low**" | **Wrong.** Prop65Radar (fetched 2026-10-01) is "a free lookup and alerting layer for California Prop 65 60-day notices affecting ecommerce sellers… Built for DTC, Amazon, Walmart, and Shopify sellers". It holds 17,271 stored notices with data updated 2026-09-19, and advertises brand, category, chemical and "twin" matching alerts. Its paid tier is about $29 one-off. | https://prop65radar.com | **No** |
| Sellers pay *before* a notice | No evidence found. The Reddit and forum posts we found are all from sellers asking for help after a notice arrived. Proactive spend is tiny: Warnify Pro (Shopify warning popups) costs $9.95–$17.95/mo with 240 reviews, and Shopify ships a native free "Product disclosures" feature for Prop 65. | https://apps.shopify.com/product-warnings ; https://shopify.dev/docs/apps/build/product-merchandising/product-disclosures | **No** |
| Defendants are SMB retailers | Concentrated at the top. In the June 2026 sample of 519 notices, about 163 named large chains: Amazon 82, TJX 26, Walmart 21, Whole Foods 18, Aldi 16. Lead accounted for 313, mostly food. Many other defendants are foreign manufacturers. | https://jurislawgroup.com/prop-65-violations-newsletter-june-2026/ | Partly |

### Competitors the original missed
- **Prop65Radar**: the same idea, already live, at about $29 (https://prop65radar.com).
- **Apify** "Prop 65 60-Day Notice Search + Settlement Benchmark": about $0.01 per 1,000 results, 2 users (https://apify.com/malekh/prop-65-60-day-notice-settlement-benchmark).
- **Free trackers**:
  - Hunton 60-Day Notice Tracker (https://www.hunton.com/proposition-65-notice-tracker)
  - Juris Law Group's monthly newsletter, which names defendants
  - Intertek and Bureau Veritas notice bulletins
- **Prop 65 Clearinghouse**: $1,150/yr Basic, or $1,800/yr Premier with email alerts (https://www.prop65clearinghouse.com/subscribe).
- **Certivo**: raised a $4M seed in Feb 2026, about $770k ARR, AI supply-chain compliance aimed at manufacturers (https://www.geekwire.com/2026/seattle-startup-certivo-raises-4m-to-automate-supply-chain-compliance-with-ai/).
- **Sustalium**: €10 per document per month (https://sustalium.com/blog/prop-65-compliance-software-california-warnings/).
- **Enhesa, 3E, UL/WERCSmart and Assent**: enterprise tools, quote-only. Not SMB competitors, but they own brand-side chemical compliance at mid-market and above.

### New risks
1. **The alert itself can create liability.** §25600.2(f) defines retailer "actual knowledge" as knowledge from "any reliable source" that identifies the specific product. A cold email naming the SKU could *be* that source. Defense counsel will tell recipients to ignore it or not subscribe.
2. **Much of the volume can't be matched to a catalog.**
   - About 20% of 2025 notices were BPS receipt paper. Entorno Law alone sent 600+ to restaurants and stores (https://www.10news.com/news/team-10/completely-blindsided-retailers-restaurants-threatened-with-lawsuits-over-receipt-paper).
   - Lead in generic or private-label food is the largest category, and lot-specific testing means a matching product name does not mean a matching exposure.
3. **Legislative headwinds.**
   - AB 2577 (signed 27 Sep 2026, effective 1 Jan 2027) lets judges cut fee awards in court-approved settlements (https://natlawreview.com/article/new-california-law-reshapes-court-approval-proposition-65-settlements).
   - The acrylamide injunction was upheld and acrylamide warnings were held to violate the First Amendment (https://www.bclplaw.com/en-US/events-insights-news/ninth-circuit-upholds-the-injunction-against-new-cal-prop-65-acrylamide-cases.html ; https://www.fdli.org/2026/06/cal-chamber-of-com-v-bonta/).
4. **Unauthorized practice of law and unfair-competition exposure.** Telling a business how to cure, or that it is "likely next", is risky (Cal. B&P §6125). Naming third-party brands in fear-based email risks trade libel. This is our inference, not sourced.

### Single most likely failure
Cold email to multi-brand retailers converts at about 0%. They are not the primary duty-holder, they can cure in 5 days, the alert may create the very knowledge that makes them liable, and a free or $29 alternative exists.

### What would make it viable
- **Retarget to private-label brands and importers.** These are Amazon private-label, DTC and specialty-food importers, where §25600.2 places the duty. Pitch "a twin of your SKU was just noticed" as supplier-risk intelligence.
- **Or sell the data to the defense side.** That means defense firms and testing labs, as a flat-fee lead and benchmark feed (no per-referral fees, per ABA 7.2(b)).
- **Price at $29–$49/mo.** Validate with 20 paid pre-notice pilots before building catalog matching.
- **Consider a separate BPS receipt-paper SKU.** The play is "BPS-free paper + signage" sold through paper and POS resellers to brick-and-mortar SMBs. It is a one-off product, not a monitoring subscription.

---

## 2. Restaurant inspection → pest / hood / refrigeration vendor router (lane 04 #2 and lane 03 #2)

**Verdict: WEAKENED. Revised score 3.5/10.** Confidence medium-high.

### Claims checked

| Original claim | Finding | Source | Holds? |
|---|---|---|---|
| NYC data has 04L/04K/04M/08A codes with about a 2-day lag | Confirmed. Latest `inspection_date` is 2026-09-28 and `record_date` is 2026-09-30, across 295,653 rows. The data includes `phone` (only 52 CAMIS are null) but **no email**. **Codes have been reused over time**: old 04K meant "thermometer", so filter by date and description. | https://data.cityofnewyork.us/resource/43nn-pn8j.json | Yes, with caveat |
| "Evidence of mice is 6.8% of NYC violations, harborage 10.4%" (lane 03) | Since 2025-10-01: 04L is **4.3%** (4,148 / 97,262) and 08A is **8.0%**. | same API | Partly (lower) |
| Lead volume | NYC had 423–919 distinct restaurants a month cited for 04K/L/M/N, roughly 700 on average. Over 12 months that is 6,649, or 32% of the 20,784 restaurants inspected. **We re-verified Aug 2026 = 919.** Chicago had about 203–322 a month by keyword. | NYC API; https://data.cityofchicago.org/resource/4ijn-s7e5.json | Yes, volume is real |
| Chicago has free-text numbered violations | Confirmed, pipe-delimited. Latest is 2026-09-30. **No phone field.** The format changed on 1 Jul 2018. | https://data.cityofchicago.org/Health-Human-Services/Food-Inspections/4ijn-s7e5 | Yes |
| "King County 237 days stale" (lane 03) | **Wrong now.** The latest inspection in r878-4sxa is 2026-09-29. There is no phone field. | https://data.kingcounty.gov/resource/r878-4sxa.json | **No** |
| LA County listed as a "clean API" launch metro (lane 04) | The violations dataset is **updated quarterly**, covers a 3-year window and excludes Pasadena, Long Beach and Vernon. That is too stale for "cited this week". | https://data.lacounty.gov/datasets/environmental-health-restaurant-and-market-violations-07-01-2023-to-06-30-2026 | **No** |
| SF publishes | The legacy LIVES dataset pyih-qa8i ends 2019-11-28. Replacement datasets for 2020–2023 and 2023 onward exist. | https://data.sf.gov/resource/pyih-qa8i.json ; https://catalog.data.gov/dataset/health-inspections-2020-2023 | Partly |
| Austin | Lag of about 3 weeks (latest 2026-09-08). Scores only; violations are in another dataset. | https://data.austintexas.gov/resource/ecmv-9xxi.json | Partly |
| Hood/grease violations are a trigger (both lanes) | **Barely.** In Sep 2026 only **41** NYC restaurants were cited 10D and 59 were cited 10E. Hood cleaning is driven by fire code (NFPA 96), not health inspections. | NYC API | **No** |
| Commercial pest leads at "$40–$75 CPL… booked about $340… contracts $200–$800/mo" (lane 04) and "$50–$200" (lane 03) | Both come from a marketing agency's self-published, internally inconsistent pages. One says commercial is cheaper than residential, another says commercial exclusive leads cost $100–$300. Its regional-data page has no commercial figures. Google LSA pest CPL is about $69. | https://cubecreative.design/blog/pest-control-marketing/pest-control-cost-per-lead-benchmarks ; https://cubecreative.design/blog/pest-control-marketing/cost-per-lead-2026-regional-data ; https://99calls.com/LSA-Cost-Estimator/pest-control-contractor | Partly (weak sourcing) |
| "16,565 pest-control firms" (NPMA) | Not independently confirmed. NPMA describes itself as having ">4,000 member companies". | https://en.wikipedia.org/wiki/National_Pest_Management_Association | Unverified |
| A violation means the restaurant needs a vendor | **No.** NYC Health Code requires every food service establishment to keep a contract with a licensed pest professional on file. The pitch is therefore *displacement of an incumbent* who was notified on inspection day, about 2 days before the data posts. | https://codelibrary.amlegal.com/codes/newyorkcity/latest/NYCrules/0-0-0-46269 | **No** |
| "Nobody I found sells it to vendors as a switch signal" (lane 03) | **Wrong.** Two Apify actors already do this. One (scrapemint) sells lead feeds to pest and hood vendors at $10 per 1,000 rows. The other (c0rrupt3d) does LLM "service-need classification" (pest, deep cleaning) at $5 per 1,000. Each has **1 monthly active user**. | https://apify.com/scrapemint/restaurant-inspection-leads ; https://apify.com/c0rrupt3d/restaurant-health-inspection-intelligence | **No** |

### Competitors the original missed
- **Origami**: natural-language prospecting such as "restaurants with recent health code violations", returning owner email and phone. Free tier, then $29/mo (https://origami.chat/blog/restaurant-operators-food-safety-compliance-signals).
- **hoodcleaningleads.com**: "10–20 new customers in 30 days". Third-party snippets report about $997 setup plus $500/mo (https://www.hoodcleaningleads.com/).
- **Ecolab Health Department Intelligence** (ex-Hazel): covers 300k+ locations. Ecolab also sells pest elimination (https://ecolab.com/offerings/ecolab-hdi).
- **RatRadar**: consumer-facing, 541k establishments (https://ratradar.com/restaurants).
- **Puzzle Inbox**: a free DIY commercial-pest cold-email playbook with $40–$60/mo infrastructure, claiming 4–7% reply rates (https://puzzleinbox.com/blog/cold-email-for-pest-control). This sets the price anchor for a done-for-you service.
- **Generic outbound agencies**: $1.5–$3k retainer plus $100–$250 per meeting (https://salesbread.com/appointment-setting-services-cost/).
- **Large commercial pest firms**: Rentokil-Terminix, Rollins/Orkin and Ecolab dominate commercial accounts (https://www.ibisworld.com/united-states/industry/pest-control/1495/). Chains are locked into national contracts.

### New risks
- **Budget fit.** Pest firms spend about 6.6% of revenue on marketing (https://cubecreative.design/blog/pest-control-marketing/marketing-budget-guide-2026). A $1M firm has about $5.5k/mo in total, so a $1–$2.5k retainer is 18–45% of its whole budget.
- **Contact gap.** No dataset has email, and Chicago and King County have no phone either. Hospitality cold email averages about 6–7% replies (https://instantly.ai/cold-email-benchmark-report-2026), and independent restaurant owners skew below that.
- **Government lookalike.** Mail or email referencing a health inspection must not resemble a DOH notice. The FTC Impersonation Rule (16 CFR 461) applies, and the FTC has already warned about fake government notices to businesses (https://www.ftc.gov/legal-library/browse/rules/impersonation-government-businesses-rule ; https://consumer.ftc.gov/consumer-alerts/2024/02/government-impersonators-mail-fake-notices-business-owners).
- **TCPA.** No autodialed or AI-voice calls or texts to owners' cells without prior express written consent.

### Single most likely failure
Pest firms trial the service and get low close rates. The cited restaurant's existing exterminator fixes the problem before re-inspection, and owners don't answer email. Firms churn in 2–3 months, because the same list costs $10 per 1,000 rows.

### What would make it viable
- **Drop hood cleaning.** If you keep it, source it from fire-inspection or FDNY data instead.
- **Use only repeat offenders** (2 or more consecutive pest citations). That is direct evidence the incumbent vendor is failing.
- **Sell to commercial-focused firms with more than $3M revenue.** Price per *held* inspection appointment ($150–$300), with no radar SaaS tier.
- **Combine email with manual landline calling**, using copy that is clearly not from the health department.
- **Gate the build on a 60-day NYC pilot** with one firm and at least 3 signed contracts.

---

## 3. Contractor coverage X-date engine (lane 03, #1)

**Verdict: WEAKENED. Revised score 4/10.** Confidence medium-high.

### Claims checked

| Original claim | Finding | Source | Holds? |
|---|---|---|---|
| WA L&I publishes "insurance carrier, agency name and expiration/cancel dates… updated 3×/day" | **Confirmed by our own query.** Columns: `InsuranceCompany, InsurancePolicyNo, InsuranceAmt, EffectiveDate, ExpirationDate, CancelDate, InsuranceAgencyName`. The metadata gives update times of 8:00, 12:15 and 17:15. There are 77,288 rows. Of active, unexpired policies, 81% (59,489) have an agency name, across 2,542 distinct agencies. 8,958 policies expire Nov–Dec 2026. | https://data.wa.gov/resource/ciwg-agsx.json ; https://data.wa.gov/api/views/ciwg-agsx.json | Yes |
| It is a GL/WC/bond engine | WA data is **GL only**. WA workers' comp is a monopolistic state fund, so there is no private WC renewal to sell. **89% of WA policies carry exactly $1M limits**, which marks micro-contractors. Some expiration dates are junk (years 2098, 3013, 8027). | https://app.leg.wa.gov/rcw/default.aspx?cite=18.27&full=true ; WA API | Partly |
| WA bond expiration and impairment as a signal | The bond file (bzff-4fmt, 177k rows) shows `bondexpirationdate: "Until Canceled"`. Bonds are continuous, so there is no X-date. | https://data.wa.gov/resource/bzff-4fmt.json | **No** |
| OR CCB includes liability insurer and expiration, 56k active | Confirmed: `ins_company, ins_amount, ins_exp_date`, plus `phone_number` and `exempt_text`. There are 56,392 rows, and 50,005 have `ins_exp_date`. **No agency field.** 23,870 rows are "Exempt" (no employees). | https://data.oregon.gov/resource/g77e-6bhs.json | Yes, but no agency |
| CSLB file includes "WC carrier, policy number and policy dates" | Confirmed. The live file is "as of 10/1/2026" with header `WCInsuranceCompany, WCPolicyNo, EffectiveDate, ExpirationDate, CancellationDate, WCSuspendDate`. State Fund is the largest carrier. **The data portal has no GL data.** "Email addresses are not provided (B&P Code §27)." | https://www.cslb.ca.gov/onlineservices/dataportal/ContractorList | Yes for WC; no GL |
| "FL DBPR offers free weekly licensee files with expiration dates" listed as an insurance-data source | **Misleading.** Those are *license* expirations, with no insurance fields. The actual FL source is the DFS Division of Workers' Comp Proof of Coverage portal, which gives a downloadable 5-year list of WC policies filterable by expiration date and county. | https://www2.myfloridalicense.com/construction-industry/public-records/ ; https://dwcdataportal.fldfs.com/POCData.aspx | **No**, with a better substitute |
| "Buyers demonstrably pay **$300–$550 per booked meeting**" (VA Horizon) | **Not credible.** VA Horizon appears to be an SEO content site: no named people or address, a single personal-name contact address (youssef@vahorizon.site), and it ranks itself first in its own "best companies" lists. This is the original's single load-bearing price claim. | https://www.vahorizon.site/b2b/guides/what-x-dates-are-and-how-to-source-them/ ; https://www.vahorizon.site/b2b/compare/best-commercial-insurance-appointment-setting-companies/ | **No** |
| $150–$250 per held meeting is sustainable | Construction GL averages about $1,069/yr (39% pay under $75/mo) at 10–15% commission, which is about $107–$160 a year. A meeting costs more than the first-year commission on a typical WA account. Large WA GL writers include E&S and direct online carriers (State National 4,313; Next 1,811+; Hiscox 1,364). | https://www.insureon.com/construction-contracting-business-insurance/cost ; WA API | **No** for micro accounts |
| An unlicensed appointment setter is fine if pay is not tied to policy sales | **FL** (§626.112) and the **NAIC** model (§13) allow fixed, non-sale-contingent referral fees. **WA** (RCW 48.17.490) allows them only if no representations are made about terms or need. **CA's** unlicensed exemptions (Ins. Code §1635; 10 CCR 2193) are written for salaried *employees*, and 10 CCR 2193.3 requires a license for opinions on "coverages, exposures, limits, premiums". An outside AI vendor is in a gray zone. | https://www.flsenate.gov/Laws/Statutes/2025/626.112 ; https://app.leg.wa.gov/rcw/default.aspx?cite=48.17.490 ; https://www.law.cornell.edu/regulations/california/10-CCR-2193.3 ; https://content.naic.org/sites/default/files/inline-files/Chapter%202.pdf | Partly |
| Done-for-you tier has "few competitors using real-time state data" | The data layer is commoditized. One Apify actor sells "California Contractor Insurance Leads – WC X-Dates" with 30/60/90-day windows, and WA L&I scrapers exist. InsuranceXDate covers WC in 28 states with carrier, agency and experience mod. | https://apify.com/deadwood_data_solutions/california-contractor-directory-leads-scraper ; https://apify.com/scrapers_lat/washington-lni-contractors-scraper ; https://www.insurancexdate.com/ | Partly |

### Competitors and pricing
- **InsuranceXDate**: WC in 28 states. A search snippet says "from $200/lead"; we did not confirm this on the live site (https://www.insurancexdate.com/).
- **Zywave miEdge**: third-party reports put it at about $785/mo plus $3k onboarding on a 3-year term (https://softwarefinder.com/resources/how-much-does-zywave-cost).
- **Canopy Connect**: dec-page intake at $120/$250/$500 per month, already productizing the "collect dec pages" step (https://www.usecanopy.com/agencies/agency-pricing).
- **Generic AI SDRs for insurance**: for example, those listed at https://www.anybiz.io/blogs/best-ai-sdr-tools-for-insurance-companies-for-lead-generation-and-prospect-outreach/.
- **Direct online insurers**: Next, Hiscox and Simply Business take micro-contractors out of the agent channel entirely.
- **Not verified**: XDate.io and Ennabl. Ennabl is agency book-of-business analytics, not prospecting, so we found no evidence it competes for new-business X-dates.

### New risks
- **WA's agency name exposes the poaching.** In a small territory of 2,542 agencies, outreach that obviously comes from reading the incumbent agent's name invites retaliation and reputation damage.
- **Contact data and privacy.** No source has email. Sole-proprietor contractor data is personal data under CCPA, so reselling records raises CA Delete Act data-broker registration exposure.
- **Reply handling.** "What would it cost?" and "Am I covered for X?" are likely the most common replies, and answering either is licensed activity. Realistic automation is therefore closer to 50–60% than the claimed 75%.

### Single most likely failure
Producers churn after 1–2 months. Meetings are with $1M-limit sole proprietors paying about $1k a year who compare against Next or Hiscox online, and the commission doesn't cover the meeting fee.

### What would make it viable
- **Lead with CA and FL workers' comp X-dates, not WA GL.** WC premium scales with payroll. Filter for private-carrier WC (not State Fund), multiple classifications and permit volume, targeting $10k+ total premium accounts (WC + GL + auto + umbrella).
- **Sell software to the agency.** $300–$500 per producer per month for the X-date feed, sequenced email and dec-page intake. The agency's licensed staff answer replies, with AI drafts only. This removes the CA vendor-licensing gray zone.
- **If selling meetings:** use a fixed fee not tied to sale, hard-route any premium, limit or coverage question to a producer, and get CA/WA counsel sign-off first.
- **Drop bond X-dates.**

---

## 4. OSHA SST target predictor (lane 04, #3)

**Verdict: KILLED as a predictor. Revised score 2.5/10.** Confidence medium-high (0.75).

### Claims checked

| Original claim | Finding | Source | Holds? |
|---|---|---|---|
| CPL 02-01-067 is the SST directive | Confirmed: signed 8 Apr 2025, effective 20 May 2025, expiring about May 2027 unless replaced. | https://www.osha.gov/sites/default/files/enforcement/directives/CPL-02-01-067.pdf | Yes |
| The selection logic is public | Confirmed: four strata (high DART CY2023, upward trend 2021–23, non-responder sample, low-rate sample). **The lists use CY2021–2023 data**, so newer ITA filings do not drive the current cycle. | same, §IX.A | Yes |
| DART cut-offs are not published | Correct. Lists sit on an internal "OSHA Tools Dashboard" that only OSHA and State Plans can access (§X). The last published cut-offs date from about 2010. | same; https://www.fdrsafety.com/numbers-that-will-put-you-on-oshas-inspection-list/ | Yes |
| Calibrate on SST-coded inspections | Possible. Inspections are coded **SSTARG23** in the NEP and emphasis fields (§XIV). The DOL API v4 needs a free key, and enforcedata.dol.gov now redirects to data.dol.gov. ITA records carry EIN but inspections likely don't, so matching is fuzzy (data dictionary not confirmed). | same; https://data.dol.gov/ | Partly |
| More than 390k ITA filers | Confirmed: 392,735 filed 300A for 2024. | https://www.aiha.org/news/250424-osha-releases-2024-workplace-illness-and-injury-data | Yes |
| "SST lists have historically run about 10–15k" and "likely may mean a 5–15% chance" | **Far too high.** OSHA reports **652 SST inspections from 7 Apr 2023 to 12 Dec 2024**, about 390 a year. That is a base rate of about 0.1% of filers. Even if lists hold 10–15k sites, a listed site has about a 3–4% annual chance. | CPL-02-01-067 §VIII; https://www.osha.gov/foia/hot_14 | **No** |
| Program continuity is a risk | Worse than stated. Compliance officers fell from 812 to 629 between FY24 and FY25, and Apr–Sep 2025 inspections were down about 20% year on year. | https://www.businessinsurance.com/osha-inspector-ranks-fell-sharply-before-projected-2026-increase-agency-says/ ; https://ehsleaders.org/2026/02/senators-demand-answers-after-osha-inspections-drop-in-2025/ | Yes, and worse |
| "I found no SST-prediction product… Crowding for the predictive layer: low" | **Partly wrong.** Apify sells ITA 300A records with TRIR/DART and a 0–100 lead score, explicitly for safety consultants, at $5 per 1,000. Another actor sells an OSHA violation risk score. OSHALookup, smartqhse and basincheck give away DART benchmarks free. | https://apify.com/scrapesage/osha-injury-data-scraper ; https://apify.com/scrapebench/osha-violation-risk ; https://oshalookup.org/ ; https://www.smartqhse.com/osha-recordable-rates-by-industry-2026 | **No** |
| $1,500 mock inspection is a reasonable price | Consultants already sell mock inspections at about $2,250+ per half day, so the price holds. But the buyer can buy one without our score. | https://evolutionsafetyresources.com/mock-osha-inspection-services-guide-steps-costs/ | Yes, but not differentiated |

### Single most likely failure
A 0.1% a year event can't carry a fear-based subscription. Customers never see the predicted outcome, the score can't be validated in their time horizon, and the consultant-feed version already exists at $5 per 1,000 records.

### What would make it viable (as a different product)
- **ITA recordkeeping QA and peer DART benchmarking.** Include 300A error and non-filer detection: non-filers are an explicit SST stratum and the 2 March deadline recurs every year. Bundle it with contractor-prequalification readiness (ISN and Avetta use TRIR/DART).
- **Deliver through safety-consultant partners.** Use SSTARG23 history in the client's NAICS and county only as marketing color, not as the product.

---

## 5. California stormwater citizen-suit risk monitor (lane 04, #4)

**Verdict: WEAKENED. Revised score 5/10.** Confidence medium (0.65).

### Claims checked

| Original claim | Finding | Source | Holds? |
|---|---|---|---|
| SMARTS offers text downloads by region | **Better than claimed.** data.ca.gov carries Industrial Facility Info, **Industrial Monitoring Data (2,312,303 rows)**, Inspections, Violations and Enforcement Actions, all with a SQL API. Refreshed 2026-09-28; latest sample 2026-09-10. Level 1/2 status and annual reports were not found in the open data. | https://data.ca.gov/dataset/stormwater-regulatory-including-enforcement-actions-information-and-water-quality-results ; https://smarts.waterboards.ca.gov/smarts/SwPublicUserMenu.xhtml | Yes (Level status: partly) |
| "20,332 active facilities" | SQL count on the 2026-09-28 file: **20,429 active** (20,378 industrial plus 51 Region 8 scrap metal). | data.ca.gov SQL API | Yes |
| Target SICs | Active facilities: SIC 5015 = 676, 5093 = 791, 4212 = 464, for **1,931 core targets**. | same | Yes, but small |
| Settlements of $624k, $312k and $325k (incl. $185.5k fees) | All verified in the source. That article, written by defense counsel, also cites "150+ federal consent judgments since 2010" and a $775k case. These are the **high end**, so do not treat them as typical. | https://natlawreview.com/article/cottage-industry-economics-cwa-citizen-suit-enforcement | Yes, but cherry-picked |
| Volume of citizen-suit notices | **No statewide count is published.** The Water Board stopped its tracking report after 2010, when 60 notices were tracked. Brodsky & Smith alone sent 98 notices in 2017, and notices rose 43% and 52% in 2015–17. 150+ consent judgments since 2010 is about 10 a year, so most cases settle pre-suit. Our estimate is low hundreds of notices a year, at low confidence. | https://www.waterboards.ca.gov/water_issues/programs/enforcement/rpts_citizensuits.shtml ; https://www.mapistry.com/blog/explaining-the-drastic-increase-in-stormwater-citizen-lawsuits | Partly |
| Plaintiffs mine SMARTS; the plaintiff bar is concentrated | Confirmed: LA Waterkeeper, EDEN/CVEED, Coastkeepers, Ecological Rights Foundation, California River Watch; firms include Aqua Terra Aeris, Coast Law Group and Brodsky & Smith. | https://natlawreview.com/article/environmental-plaintiffs-guide-organizations-filing-stormwater-citizen-suits ; https://congress.net/california-industrial-facilities-face-familiar-cast-of-stormwater-litigants-report-finds/ | Yes |
| Competitors are "local QISP firms; californiastormwater.com", crowding "low" | **Wrong on crowding.** **Mapistry** sells CA stormwater compliance software plus consulting with exceedance alerts. Its own blog says its "litigation intel group uses a comprehensive database of nationwide citizen suits to develop a facility-based risk analysis and alert customers of potential legal action." That is this idea. Also: CloudCompli, CDMS SMARTS reporting, GSI Environmental, and californiastormwater.com (statewide NAL/TMDL monitoring, refreshed monthly). | https://www.mapistry.com/blog/citizen-lawsuits-and-stormwater-compliance-a-primer ; https://www.cloudcompli.com/industrial.html ; https://cdms.com/smarts-reporting-california/ ; https://californiastormwater.com/ | **No** |
| The IGP could change | The operative permit is still 2014-0057-DWQ as amended (TMDL/NEL effective 1 Jul 2020), with no reissuance scheduled. LA Region's 2026 draft commercial/industrial/institutional permit (R4-2026-0226) could *expand* the universe of regulated sites. No citizen-suit-limiting bill was found. | https://www.waterboards.ca.gov/water_issues/programs/stormwater/industrial.html ; https://www.waterboards.ca.gov/losangeles/water_issues/programs/stormwater/Commercial_Industrial_and_Institutional/None_R4-2026-0226_WDR_PKG.pdf | Partly (mild tailwind) |

### New risks
- **The alert comes too late to prevent the violation.** CWA liability is strict, and plaintiffs read the *same* self-reported exceedances (https://natlawreview.com/article/strict-liability-under-cwa-what-it-means-industrial-stormwater-dischargers). By the time we can see an exceedance, the violation is on record. The value lies in stopping recurrence and fixing records gaps (rain-event sampling), not in prevention.
- **Dual use.** The ranked list is a target list for plaintiffs, so do not sell it to them.
- **Advice boundary.** Remediation advice drifts into QISP-signed and legal territory.

### Single most likely failure
Facilities buy only after a 60-day notice arrives, and then they buy lawyers and QISPs. Before that point, Mapistry and incumbent QISPs already own the relationship.

### What would make it viable
- **Sell through QISP firms and defense counsel** (white-label portfolio screen), or to environmental-liability insurers. Don't sell direct to scrap yards.
- **Replicate plaintiff notice math.** Combine data.ca.gov monitoring data with NOAA rainfall to find rain days without samples and repeated NAL/NEL exceedances, then sell a fixed-fee "pre-notice audit" priced against the roughly $300k settlement benchmark.
- **Validate before building.** Back-test the features against historical notices pulled from PACER or EPA notice copies.

---

## 6. Cross-idea ranking (verify-2 batch)

| Rank | Idea | Revised score | Verdict | Why it ranks here |
|---|---|---|---|---|
| 1 | CA stormwater citizen-suit risk monitor | **5.0** | WEAKENED | Best data (an open SQL API with 2.3M monitoring rows) and the highest pain per incident. The buyer universe is small (about 1,931 core targets, about 20k total), and Mapistry already competes. Viable only as a channel product for QISPs and counsel. |
| 2 | Contractor X-date engine | **4.0** | WEAKENED | Data confirmed in WA, OR, CA (WC) and FL (WC), and agents do buy prospecting data. The per-meeting economics fail on micro-contractor GL, and the key $300–$550 price source is not credible. The CA/FL WC pivot sold as agency software is the most plausible business in this batch. |
| 3 | Restaurant inspection → vendor router | **3.5** | WEAKENED | The lead volume is real (about 700 pest-cited NYC restaurants a month). But every one already has a mandated exterminator, the hood signal is close to zero, and the same feed sells at $5–$10 per 1,000 rows to one monthly active user. Closest to the brothers' skill set, but the economics are thin. |
| 4 | Prop 65 Next Defendant | **3.0** | KILLED as specified | Wrong buyer: retailers mostly aren't liable and can cure in 5 days. A lookalike (Prop65Radar) is live, proactive spend is $10–$18/mo, and the alert may itself create "actual knowledge" for the recipient. |
| 5 | OSHA SST predictor | **2.5** | KILLED | About 390 SST inspections a year against about 390k filers, a 0.1% base rate. The cut-offs are confidential, inspector headcount is falling, and DART lead scores already sell at $5 per 1,000. |

### Notes for the brothers
1. **None of these is a better next bet than a stronger idea from another lane.** If forced to pick from this batch, take the **contractor workers' comp X-date pivot sold as software to commercial agencies in CA and FL**. Its recurring revenue is clean and its regulatory exposure is manageable once licensed agency staff handle all coverage conversations.
2. **Stormwater is the highest-value niche but needs a partner channel.** Treat it as a QISP and counsel white-label, not as direct cold outreach.
3. **Systemic lesson.** Search Apify, and search for lookalike startups, *before* scoring "crowding: low". In this batch, four of five "open" data layers were already productized, and each had near-zero users. Treat that as a demand warning.
