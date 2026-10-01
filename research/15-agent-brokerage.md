# Lane 15: Agent-run brokerages, matchmaking and commission models

*Round-2 research lane. Date: 2026-10-01. Desk research only: no emails, signups, outreach or purchases. About 100 web searches and fetches, plus one live download and parse of the Florida DBPR quota-license files. **(est.)** marks my own arithmetic or judgement, not a sourced figure. Round-1 failure patterns (cheap incumbent vendors, free data, late triggers, licensing, guarded professionals) were used as a checklist for every idea.*

---

## 1. Lane overview

**The thesis.** In fragmented, illiquid markets the money is a commission, often paid by the side that is *not* being cold-emailed. The expensive labor is finding counterparties, qualifying them and chasing them, and that is the part agents can automate. The brothers' edge, per the round-1 verifiers, is a done-for-you outbound and reply machine, not data. Brokerage converts that machine directly into commission dollars without having to sell a SaaS subscription.

**What the evidence says, in one paragraph.** Commission pools are real and well documented across the board. Examples:
- Main Street business brokers charge 8–12% with $10–15k minimums ([Nav](https://www.nav.com/blog/how-much-do-brokers-charge-to-sell-a-business-4232647/)).
- Franchisors pay $13,757 per non-broker sale and $48,903 per broker sale ([franchising.com / 2025 AFDR](https://www.franchising.com/articles/studying_the_numbers_the_2025_afdr_reveals_crucial_brand_data.html)).
- Liquor-license brokers take 8–15% of $80k–$1M+ licenses ([liquorlicensecost.com](https://liquorlicensecost.com/guides/liquor-license-broker)).

But the same pattern as round 1 repeats. **Almost every pool already has a cheap or free intermediary**:
- Milly charges 3% for insurance books, and Oak Street Funding's exchange is free.
- McKesson RxOwnership and Cardinal Health match pharmacy buyers and sellers for free.
- Baton charges 6% and Rejigg is free to sellers on Main Street.
- Franzy, IFPG and FranNet already work franchise placement.

On top of that, **licensing pushes most of these models into "one brother gets a real-estate license and hangs it with a sponsoring broker"**:
- 17 states require a real-estate license for business brokerage ([BizBuySell](https://www.bizbuysell.com/learning-center/article/business-broker-licenses-certifications/)).
- Florida bars sharing a commission with an unlicensed referrer ([Fla. Stat. ch. 475](https://www.flsenate.gov/Laws/Statutes/2025/Chapter475/All)).

The commissions are also almost all **one-off, not recurring**.

**The best idea in this lane** is a narrow one. **Quota liquor-license brokerage** has both sides findable in free state data:
- Florida publishes a daily-refreshed Excel of every inactive quota license.
- California publishes surrendered licenses monthly.
- New Jersey just loosened pocket-license transfers again (S4404, July 2026).

Deal sizes ($80k–$500k) justify the commission. It is still a **5/10, not a 7**. Listing marketplaces (LiquorLicense.com, Florida Liquor License Market with 206 live 4COP listings) already exist, the volume is small (est. a few hundred Florida quota transfers a year) and the income is not recurring. The only recurring idea, an SMB technology-advisor residual book sold to the brothers' existing website customers, is a modest upsell rather than a new business.

**Ideas evaluated (kept as candidates):**
1. Quota liquor-license brokerage (FL first, then PA / MI / NJ / CA)
2. Restaurant exit desk: FSBO restaurant sales plus second-generation space
3. Insurance micro-book and captive "economic interest" brokerage
4. Independent pharmacy exit / prescription-file brokerage
5. Franchise resale and conversion placement (franchisor-paid)
6. SMB technology-advisor residual book (telecom, UCaaS, payments), as an upsell
7. Small-business tenant representation (landlord-paid)

**Rejected (section 3):** Main Street micro-brokerage; used restaurant, heavy, lab and dental equipment; freight; website and domain brokerage; dental and vet practice brokerage; solar and roofing appointments; solar land origination; commercial energy brokerage; excess-inventory liquidation; government surplus; home-services lead marketplaces; janitorial account brokering.

---

## 2. Candidate ideas

### Idea 1: Quota liquor-license brokerage ("License Desk")

**Pitch.** In quota states, a full liquor license is a scarce, tradeable asset. Florida 4COP licenses list at $80k to $1.3M. A Pennsylvania R license has a median ask of about $115k. New Jersey Class C licenses sell for $150k–$400k+, sometimes over $1M. Hundreds of these licenses sit idle ("inactive", "escrow", "pocket", "surrendered") in the hands of people who closed a bar years ago. Meanwhile new bar and small-restaurant operators need one and don't know where to look. The agent does three things:
- reads the state files to find idle-license holders;
- finds operators who will need a license, from new food-service licenses, seat counts and lease signals;
- runs outreach to both sides, prices the license from listing comps and manages the transfer checklist.

A licensed associate signs the paperwork.

**Data and inputs (verified).**
- **Florida (supply).** DBPR publishes *Active* and *Inactive* quota-license lists as PDF and Excel ([DBPR quota page](https://www2.myfloridalicense.com/alcoholic-beverages-and-tobacco/quota-license-information/)). I downloaded and parsed both on 2026-10-01:
  - **4,350 active quota licenses** (2,224 are 4COP) and **597 inactive** (298 are 4COP). Inactive statuses: 321 "Inactive", 149 "Automatic Waiver", 36 "Conditional Waiver", 9 "Litigation".
  - Inactive 4COPs are concentrated in county code 23 (79 licenses, Miami-Dade), 39 (35), 60 (28) and 16 (26).
  - Fields include licensee name, owner, series and **mailing address**, but no email or phone.
  - DBPR also publishes daily license extracts in CSV ([DBPR ABT data](https://www2.myfloridalicense.com/alcoholic-beverages-and-tobacco/daily-license-status-reporting-data/)).
- **Florida (demand).** The Hotels & Restaurants food-service extract includes a **"Number of Seats"** field ([DBPR H&R public records](https://www2.myfloridalicense.com/hotels-restaurants/public-records/); [field listing](https://myfloridalicense.custhelp.com/app/answers/detail/a_id/1925/~/can-i-get-a-report-that-lists-the-licensed-restaurants-or-lodging-in-an-area)). That matters because restaurants with fewer than 150 seats or 2,500 sq ft cannot use Florida's SFS exemption and need a quota license for full liquor (rule as summarized by [Premium Blend](https://premiumblend.com/which-florida-liquor-license-do-you-actually-need-2cop-vs-4cop-vs-sfs/)).
- **California.** ABC publishes a monthly "Surrendered Licenses" report and daily raw data for all pending and active licenses ([ABC licensing reports](https://www.abc.ca.gov/licensing/licensing-reports); [surrendered](https://www.abc.ca.gov/licensing/licensing-reports/surrendered-licenses/)). In FY2020-21 there were about 15.5k Type 47 and 2.5k Type 48 licenses ([ABC state totals](https://www.abc.ca.gov/licensing/licensing-reports/annual-report-archives/license-summary-counts-for-fy-2020-21/state-totals/)).
- **New Jersey.** About 8,900 active retail consumption licenses and about 1,400 inactive or pocket licenses ([ICSC](https://www.icsc.com/news-and-views/icsc-exchange/governor-signs-legislation-overhauling-new-jerseys-liquor-license-laws-for-the-first-time-in-nearly-a-century)). **S4404 (July 2026)** extended the inactive-license deadlines, revived expired licenses, and created inter-municipal sale, redevelopment and RFP transfer paths ([Redevelop NJ](https://www.redevelopnj.com/2026/08/newly-enacted-nj-law-significantly-expands-transferability-of-inactive-restaurant-liquor-licenses-revives-expired-licenses-and-more.html)). That is a fresh, unpriced catalyst.
- **Michigan.** Escrowed licenses can sit for up to 2 years, and Class C licenses trade at $20k–$150k ([liquorready](https://www.liquorready.com/articles/state-guides/cost-of-a-liquor-license-in-michigan); [Plunkett Cooney](https://www.plunkettcooney.com/publications-Michigan-liquor-license-quota-system)).
- **Pennsylvania.** R licenses run $50k–$550k, median ask about $115k; a January 2026 snapshot showed 34 R and 9 D licenses listed ([Liquor License HQ](https://liquorlicensehq.com/pennsylvania-liquor-license-inventory-january-2026/)).

**Buyer (who pays).**
- Usually the seller pays 8–15%, with $5–10k minimums.
- The liquorlicensecost guide says buyer-paid commissions are standard in Florida and New Jersey ([liquorlicensecost.com](https://liquorlicensecost.com/guides/liquor-license-broker)). That claim is unverified against a primary source.
- Either way, **the cold-emailed side (the idle-license holder) is offered money, not a bill**.

**Evidence that money moves today.**
- Florida Liquor License Market lists **206 active 4COP listings across 37 counties** (as of 2026-10-01) and has a "Recent Florida Transactions" section ([FLLM](https://www.floridaliquorlicensemarket.com/florida-4cop-liquor-license-for-sale)).
- Miami-Dade asks run $185k–$495k, median $210k ([liquorready 4COP](https://www.liquorready.com/articles/state-guides/buy-a-fl-liquor-license); [FLLM](https://www.floridaliquorlicensemarket.com/florida-4cop-liquor-license-for-sale)).
- California's resale market is described as "thousands of transactions per year" ([liquorlicensecost.com](https://liquorlicensecost.com/guides/liquor-license-broker)); that figure is unverified.
- California person-to-person transfers carry a $1,565 ABC fee, a routine transaction ([ABC fee schedule](https://www.abc.ca.gov/licensing/license-fees/application-fee-schedules)).

**Market size, bottom-up (est.).**
- **Florida:** about 4,950 quota licenses. Assume 5% turn over each year: about 250 transfers × about $200k = $50M in value × 10% = **about $5M a year in commission**.
- **Pennsylvania:** quota of 1 R license per 3,000 residents gives about 4,300 R licenses. Same 5% turnover: about 215 transfers × $115k × 10% = **about $2.5M**.
- **California:** Type 47/48 at about 18k licenses, assuming 3% trade at a median of about $80k: **about $4M**.
- **New Jersey:** high value but few trades. **About $2–4M**.
- **Total addressable commission in five states: est. $15–20M a year.** That is enough for a $300k–$1M brokerage, not a venture business.

**Deliverable and pricing.**
- For sellers: a free valuation built from live comps, then a listing and buyer outreach. Commission 8–10% of the sale ($8k minimum). The brothers' net after the sponsoring broker's split is roughly 80% until a cap.
- For buyers: free "find me a license in county X" search.
- **Not recurring.** A small recurring add-on is possible (renewal and compliance calendar, inactive-status deadline tracking), but no evidence anyone pays for it.

**Automation pipeline.**

| Step | What happens | Automatable |
|---|---|---|
| Find (supply) | Nightly diff of the FL inactive and active lists, CA surrendered list and MI escrow; flag new inactive, waiver and deadline cases | 95% |
| Find (demand) | New FL food-service licenses under 150 seats with no beverage license; new bar LLCs; LoopNet second-gen bar listings | 80% |
| Build deliverable | One-page valuation: county comps from FLLM and other listing sites, days on market, a net-proceeds estimate | 90% |
| Outreach | Direct mail (Lob) to the mailing address, plus skip-traced email and SMS where lawful | 85% |
| Replies | Agent answers FAQs, collects documents and books the call | 70% |
| Deliver | Price negotiation, escrow, DBPR/ABC transfer forms, landlord and municipal approvals (NJ) | 30% |

Human touchpoints that remain: the licensed associate's signature and negotiation, escrow coordination, and the NJ municipal hearings. **Overall about 65% automatable.**

**90-day GTM.**
- Days 1–30: one brother enrolls in Florida's 63-hour sales-associate pre-license course and hangs the license with a broker (eXp Commercial is 80/20 with a $20k cap ([buildingbetteragents](https://buildingbetteragents.com/exp-realty/exp-commercial/)), or a specialist liquor-license broker). In parallel, build the nightly diff and the valuation generator.
- Days 31–60: mail all 298 inactive 4COP holders and about 255 inactive 3PS holders; email new small-seat restaurants in Miami-Dade, Broward and Palm Beach.
- Days 61–90: list the first 10–20 licenses; work the buyer side; target 1–2 deals in escrow.

**Unit economics (est.).**
- $200k license × 8% = $16k gross. If split with a co-broker, about $8k. Sponsoring broker's 20% leaves $6.4–12.8k net to the brothers.
- Direct mail costs about $1.50 per piece, so 600 pieces is about $900. Skip-tracing runs about $0.10–0.50 per record.
- A $20k-a-year tool and data budget pays back on 2–3 deals.
- **Sales cycle:** Florida transfers take weeks to months. Expect first commission at 4–6 months.

**Competitors (8+ searches).**

| Competitor | What it does | Price |
|---|---|---|
| [LiquorLicense.com](https://www.liquorlicense.com/marketplace) | "Nation's largest liquor license brokerage"; LA HQ; online marketplace in nearly all 50 states | Commission, not published |
| [Florida Liquor License Market](https://www.floridaliquorlicensemarket.com/florida-4cop-liquor-license-for-sale) | 206 live 4COP listings, exchange board, valuations | Not published |
| [LiquorLicenseFL](https://www.liquorlicensefl.com/Florida-Liquor-License-Fees.html) | Fort Myers brokerage | Not published |
| [Liquor License Auctioneers](https://liquorlicenseauctioneers.com/california/types/type-47) | CA online "24/7" license buying | Commission |
| [License Locators](https://licenselocators.com/liquor-licenses-for-sale-in-california/), [Liquor License Brokers](https://liquorlicensebrokers.com/), [Liquor License Network](https://liquorlicensenetwork.com/) | CA brokers and consultants | 8–15% (industry) |
| [Liquor License HQ](https://liquorlicensehq.com/pennsylvania-liquor-license-inventory-january-2026/) | PA and NJ inventory | Not published |
| [Northbridge Acquisitions](https://northbridgeacquisitions.com/liquor-license/) | Broker and consultant | Not published |
| BizBuySell, [BizQuest](https://www.bizquest.com/liquor-licenses-for-sale-in-california/), BizBen | Generic listing sites carrying license listings | $59–$300/mo FSBO |
| AI or startup entrants | **None found** in searches for liquor-license marketplace startups ([search](https://www.liquorlicense.com/marketplace)); funded "liquor" startups are retail tech (Scotch $20M A, [Crunchbase News](https://news.crunchbase.com/venture/scotch-raises-ai-funding-liquor-retail-tech/)) | n/a |

What differs here: incumbents *list* licenses that owners bring them. I found none that systematically mines the state inactive and surrendered lists or new-restaurant seat counts. That claim is weak, because a broker could do this by hand and probably some do.

**Legal and licensing.**
- **Florida:** brokering a "business enterprise or business opportunity" for compensation requires a real-estate license, and commissions can't be shared with unlicensed referrers ([ch. 475](https://www.flsenate.gov/Laws/Statutes/2025/Chapter475/All)). Whether a bare liquor license counts as a business opportunity is untested in my sources. **Assume a license is required.**
- **New Jersey:** a liquor-license transfer for compensation requires a licensed real-estate broker ([liquorlicensecost.com](https://liquorlicensecost.com/guides/liquor-license-broker); secondary source).
- **California:** DRE brokers handle "business opportunity" sales ([DRE](https://www.dre.ca.gov/LicenseList.html)), and the guide above says California requires a business-broker license.
- **Compliant structure:** a brother becomes a licensed associate under a sponsoring broker. The brothers' entity is paid only through that broker. No referral fees go to unlicensed parties.
- Outbound to license holders is ordinary B2B or B2C solicitation. CAN-SPAM applies to email, and TCPA applies to SMS, so use opt-in or manual dial only.
- **Licensing cost:** the Florida course is about 63 hours plus an exam. California is 135 hours (3 courses) and slower. New Jersey is 75 hours.

**Kill risks.**
- **Volume is small, and the market already has listing sites.** If the 206 FLLM listings are stale inventory with few buyers, the binding constraint is demand, and demand can't be manufactured.
- **Price compression.** NJ S4404 and Florida's annual quota drawings add supply.
- **One-off income** with a 4–6 month cycle.
- **Mailing-address-only data** for many holders, and older owners, mean response leans on direct mail.

**Cheapest validation test (2–3 weeks, about $1,500, no license needed for the test).**
1. Mail a "what's your idle license worth?" letter to the 298 inactive Florida 4COP holders. Link to a free valuation page (no offer to broker yet).
2. In parallel, email 200 new small-seat Florida food-service licensees to ask whether they need a full-liquor license.
3. **Kill if** fewer than 10 holders (3.4%) request a valuation, **or** fewer than 5 operators say they would buy in the next 6 months, **or** you can't confirm 20+ closed Florida 4COP transfers in the last 12 months (from DBPR transfer statuses or FLLM's "recent transactions").

**Cold-email reply rate.** The 2026 average for cold email is **3.43%** and the top quartile is 5.5% ([Instantly benchmark](https://instantly.ai/cold-email-benchmark-report-2026)). For idle-license holders offered a free valuation of an asset they are paying fees on, I estimate **3–8% response to mail plus email (est.)**. Bar and restaurant operators on the buy side: **1–3% (est.)**.

---

### Idea 2: Restaurant exit desk (FSBO restaurants + second-generation space)

**Pitch.** Independent restaurants are closing: the count fell 2.3% in 2025, a net loss of about 9,500 locations ([NRN](https://www.nrn.com/independent-restaurants/the-independent-restaurant-sector-shrunk-by-2-3-in-2025)). Most owners walk away from a built-out kitchen worth $40k–$120k in equipment, and a second-generation space saves the next operator $100k–$400k ([pepperlot](https://pepperlot.com/second-generation-restaurant-space)). The agent finds owners trying to sell by themselves and pitches a full asset sale (lease assignment plus FF&E plus key money). It then finds operators who want second-generation space.

**Inputs.**
- FSBO restaurant listings on BizBuySell, Craigslist and FB Marketplace (scraping is ToS-sensitive; use public listing pages carefully).
- Health-department permit status, Google "temporarily closed" flags, and LoopNet second-gen listings.
- Buyers: food trucks with growing reviews, multi-unit independents, and new restaurant LLCs.

**Buyer and money.**
- The seller pays a restaurant broker **8–15%, with $15–25k minimums** ([We Sell Restaurants](https://blog.wesellrestaurants.com/what-does-it-cost-to-sell-your-restaurant); [CT Acquisitions](https://ctacquisitions.com/restaurant-broker-explained/)).
- BizBuySell 2025 median restaurant sale price: **$220k** ([BizBuySell 2025 recap](https://www.bizbuysell.com/news/bizbuysell-2025-fourth-quarter-insight-report/)).

**Market size (est.).** Assume 20k restaurant asset sales a year nationally at about $150k × 10% = $300M a year in commission. Even a 0.1% share is $300k.

**Deliverable and pricing.** Free valuation and teaser page (the brothers' website skill applies directly), then 10% or a $15k minimum. Not recurring.

**Automation.** Finding: 85%. Teaser and valuation: 85%. Outreach: 85%. Replies: 60%. Delivering (showings, landlord assignment, negotiation, escrow, equipment walkthroughs): 20%. **Overall about 55%.**

**90-day GTM.** Get licensed (as in idea 1), then work one metro. Scrape FSBO restaurants and pitch "we'll get you 20–40% more and handle the landlord". Run buyer outreach to food trucks and growing independents.

**Unit economics (est.).** $15k minimum fee × 80% = $12k net per deal. One metro might yield 6–12 deals a year, or $72–144k.

**Competitors (8 searches).**

| Competitor | Model | Price |
|---|---|---|
| [We Sell Restaurants](https://www.wesellrestaurants.com/franchise/why-us) | Largest restaurant-only broker franchise; about $420M of listings online | 8–15% |
| [Restaurant Realty](https://restaurantrealty.com/faqs/) | Restaurant broker | Commission |
| [Pepperlot](https://pepperlot.com/second-generation-restaurant-space) | Second-gen space marketplace, 330 spaces, 10 metros | Undisclosed |
| [EATS Broker (TX)](https://eatsbroker.com/) | Regional restaurant broker | Commission |
| Sunbelt / Transworld / Murphy | Generalist franchises | 10–12%, $10–15k min |
| [BizBuySell FSBO](https://bizbuysell.com/fsbo/sellerfaq.aspx) | DIY listing | $59–$300/mo |
| [Iconic](https://iconic.co/blog/sell-my-restaurant-business/), [CT Acquisitions](https://ctacquisitions.com/restaurant-broker-explained/) | "No broker fee" buyer-side models | Free to seller |
| [Tupelo, Smobi (YC)](https://www.ycombinator.com/launches/J1b-smobi-new-age-marketplace-for-businesses-for-sale) | Main Street marketplaces | Varies |

**Legal.** Restaurant sales include lease assignments, so a real-estate license is needed in the 17 states that require one (FL, CA, GA, AZ, among others) ([BizBuySell](https://www.bizbuysell.com/learning-center/article/business-broker-licenses-certifications/)). Use the same sponsoring-broker structure as idea 1.

**Kill risks.**
- Labor-heavy delivery (showings, landlords).
- Distressed sellers with little equity.
- The FSBO trigger is decent, since the owner has already decided to sell, but many FSBO sellers chose FSBO to avoid paying 10%.

**Validation test.**
1. Email or call 100 FSBO restaurant sellers in one metro, offering a free teaser page plus buyer outreach at 8%.
2. **Kill if** fewer than 5 sign a listing agreement within 30 days of licensing, or 0 LOIs from the first 5 listings within 60 days.

**Reply rate.** Restaurant owners are hard to reach by cold email. FSBO sellers with a published listing email will respond at **5–10% (est.)**, because the listing invites inquiries. Cold outreach to closing owners: **1–2% (est.)**.

---

### Idea 3: Insurance micro-book and captive "economic interest" brokerage

**Pitch.** About **30,000 independent agencies have under $1.25M in revenue, "the vast majority with no ability to perpetuate"** ([Insurance Journal, Dec 2025](https://www.insurancejournal.com/magazines/mag-features/2025/12/01/848708.htm)). Up to 83% have no written succession plan ([Nationwide summary of the Big "I" study](https://agentblog.nationwide.com/managing-your-business-and-clients/managing-industry-trends/succession-planning-for-insurance-agencies/)). Aggregators recorded only 695 deals in 2025 ([Insurance Journal / OPTIS](https://www.insurancejournal.com/news/national/2026/01/22/855124.htm)), almost all of them larger agencies. Books between $100k and $1M trade privately or not at all. The agent finds aging owners and lines up local buyers (other agencies, aggregators' tuck-in desks, captive agents going independent).

**Inputs.** State producer and agency license databases (NIPR lookups; several states publish CSVs), agency websites, and LinkedIn tenure. Allstate exclusive agents' "economic interest" sales trade at about 1.5–2.1× commissions, and Allstate must approve the buyer ([agencychecklists](https://agencychecklists.com/2013/11/18/allstate-agency-contract-10619/); [BizBuySell listing](https://www.bizbuysell.com/Business-Opportunity/well-established-allstate-agency-average-commission-350000/2014468/)).

**Money.** Books sell at about 1.5–3× commission revenue ([Iconic](https://iconic.co/blog/selling-commercial-insurance/); [Sonant](https://www.sonant.ai/blog/insurance-book-of-business-for-sale)). Brokers charge 5–12% ([AgencyEquity](https://www.agencyequity.com/agency-management/does-it-matter-what-type-of-business-broker-you-use-to-sell-your-insurance-agency)). A $300k book × 2× = $600k × 6% = $36k.

**Market (est.).** Assume 1,500 micro-book trades a year × $500k × 5% = about $37M a year.

**Deliverable.** A free book valuation, then a 4–6% success fee. Not recurring.

**Automation.** Finding: 90%. Valuation teaser: 80%. Outreach: 85%. Replies: 60%. Delivering (carrier consents, broker-of-record letters, retention terms, earn-outs): 25%. **Overall about 60%.**

**Competitors (8 searches).**

| Competitor | Model | Price |
|---|---|---|
| [Milly](https://www.millybooks.com/) | Marketplace for the "84% of agencies brokers won't touch", books of $300k–$5M | **3% at close**; buyers' Pro tier $40/mo |
| [Oak Street Funding Agency Exchange](https://exchange.oakstreetfunding.com/agency-exchange) | Anonymous buyer-seller exchange run by a lender | **Free** |
| [AgencyEquity](https://www.agencyequity.com/listings/book-of-business-for-sale/insurance-books-of-business-for-sale-new-york-26-1073) | Listings and brokerage | Commission |
| [Insurance Journal agencies for sale](https://www.insurancejournal.com/agencies-for-sale/) | Classifieds | Listing fee |
| [CT Acquisitions](https://ctacquisitions.com/sell-your-business/insurance-agency/) | "No broker fee" | Free to seller |
| Aggregators (BroadStreet 69 deals, Hub 49, Inszone 45, World 34) | In-house M&A teams cold-calling owners ([Insurance Journal](https://www.insurancejournal.com/news/national/2026/01/22/855124.htm)) | Pay sellers directly |
| [Sonant AI](https://www.sonant.ai/blog/insurance-book-of-business-for-sale) | AI vendor publishing book-sale content | n/a |
| BizBuySell / BizQuest | Listings | $59–300/mo |

**Legal.**
- Selling the agency asset is not "selling insurance". But splitting P&C commissions with unlicensed people is illegal almost everywhere, and renewal commissions only flow to people who were licensed at the time of sale ([IA Magazine](https://www.iamagazine.com/strategies/read/2011/06/16/can-agents-pay-for-referrals-); [NY DFS OGC 04-04-10](https://www.dfs.ny.gov/insurance/ogco2004/rg040410.htm)).
- So the fee must be a flat or percentage **M&A advisory fee on the purchase price**, never a cut of renewals.
- In the 17 real-estate-license states, business brokerage needs the RE license.
- Getting a P&C producer license is cheap (about a week of study) and removes the ambiguity.

**Kill risks.** Milly's 3% sets the price ceiling, Oak Street is free, and aggregators chase the same sellers. Insurance agents are also heavily solicited.

**Validation test.** Email 500 agency owners aged 60+ (inferred from license dates) in two states with a free valuation offer. **Kill if** fewer than 10 valuations are requested, or fewer than 2 sign at 4%+ within 60 days.

**Reply rate.** Insurance and financial services run 3.4–7.9% ([Instantly benchmarks via search summary](https://instantly.ai/cold-email-benchmark-report-2026)). Owners already flooded by aggregators: **2–4% (est.)**.

---

### Idea 4: Independent pharmacy exit / prescription-file brokerage

**Pitch.** Pharmacy closures more than doubled from 1,764 in 2021 to 3,929 in 2025, and 30.3% of independent owners said they were considering closing in 2025 ([NCPA flyer](https://ncpa.org/sites/default/files/2026-01/IndependentsClosing_2025FlyerEdit.pdf); [search summary](https://www.drugtopics.com/view/q-a-as-closures-mount-independent-pharmacies-must-diversify-services)). A closing pharmacy's prescription files are worth money to chains and nearby independents: about $5–15 per annual script, or 15–25% of Rx revenue ([Sofer Advisors](https://soferadvisors.com/insights/blog/independent-pharmacy-valuation-a-guide-to-dir-fees-and-2026-multiples/); [Iconic](https://iconic.co/blog/pharmacy-sale/)). CVS bought files from 626 Rite Aid pharmacies in 2025 ([PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC13329706/)). The agent runs a competitive bid among the few file buyers within range.

**Inputs.** NPI/NPPES pharmacy taxonomy, state board pharmacy licenses, NCPDP (paid), and Medicare Part D pharmacy network files. The buyer list is small and identifiable: CVS, Walgreens, Walmart, Kroger, regional chains and nearby independents.

**Money.** Brokers charge 8–12% under $1M ([Iconic](https://iconic.co/blog/pharmacy-sale/)). A 40k-script file at $8 is $320k × 8% = $25.6k (est.).

**Competitors (8 searches).**

| Competitor | Model | Price |
|---|---|---|
| **[McKesson RxOwnership](https://ncpa.org/ow-mckesson-rxownership)** | No-fee, no-contract succession and matching; **7,400+ owners helped since 2008** | **Free** |
| **[Cardinal Health Pharmacy Transition Services](https://www.cardinalhealth.com/en/services/retail-pharmacy/pharmacy-ownership/pharmacy-transition-services/seller.html)** | Helps sellers find buyers, any wholesaler affiliation | **Free** |
| [Pharmacy CBS](https://www.pharmacycbs.com/faq) | Licensed broker and RPh; 200+ deals in 42 states | Negotiable |
| [Hayslip Pharmacy Brokers](https://rxinsider.com/virtual-trade-show/finance/pharmacy-ma-buying-selling-franchising/) | 50+ years | Commission |
| [PRS Pharmacy Services](https://prsrx.com/brokerage/) | Brokerage | Commission |
| [Center Growth](https://centergrowth.com/sell-my-pharmacy), [Palmstone](https://www.palmstone-capital.com/sell-my-company/pharmacies), [Sofer](https://soferadvisors.com/insights/blog/independent-pharmacy-valuation-a-guide-to-dir-fees-and-2026-multiples/) | M&A advisors | Commission |
| [cvsbuysellpharmacy.com](https://cvsbuysellpharmacy.com/) | Chain file-buy intake | Free to seller |

**Legal.** File sales are asset sales. The pharmacy board must approve record transfers and patient-notice rules apply. HIPAA allows transfer of PHI in the sale of a covered entity's business (a "health care operations" exception), but **the broker must not touch PHI before an NDA and BAA are in place**. Business-broker real-estate licensing applies in 17 states only if real property or leases are involved.

**Why low.** The two largest wholesalers match buyers and sellers **for free**, and chains buy files directly. The broker's value is the competitive bid, but the buyer pool within a few miles is often only 2–3 stores.

**Validation test.** Email or call 300 independents in states with high closure rates. **Kill if** fewer than 3 agree to a bid process within 45 days.

**Reply rate.** Pharmacists are less guarded than physicians, but phone works better. Email: **1–3% (est.)**.

---

### Idea 5: Franchise resale and conversion placement (franchisor-paid)

**Pitch.** Franchisors pay a consultant 40–50% of the initial fee, typically **$20–25k per placement** ([Franzy](https://franzy.com/blog/how-do-franchise-consultants-make-money/); [CT Acquisitions](https://ctacquisitions.com/franchise-consultants-how-to-vet/)). The average cost per broker sale is **$48,903**, and the average non-broker cost per sale is **$13,757** ([2025 AFDR](https://www.franchising.com/articles/studying_the_numbers_the_2025_afdr_reveals_crucial_brand_data.html)). The brothers' machine finds local independents (HVAC, plumbing, sign shops, salons) that fit a **conversion franchise**, where fees are discounted 25–75% ([AFC](https://afcfranchising.com/blog/conversion-franchise/)). It also finds buyers for **franchise resales**, which pay the seller-side broker 8–12%.

**Inputs.** The same local-business discovery stack the brothers already run, plus FDD Item 20 unit counts (public in registration states) and franchisor conversion programs (Neighborly, Authority Brands, Service Experts, 1-800-Plumber) ([Neighborly](https://franchise.neighborly.com/blog/conversion-franchise); [Authority](https://www.authoritybrands.com/franchising/convert-your-business/)).

**Money.** 2025 development budgets averaged $1.02M; brokered sales cost $48.9k; broker budgets are set to roughly double to $157,740 ([AFDR](https://www.franchising.com/articles/studying_the_numbers_the_2025_afdr_reveals_crucial_brand_data.html)). Food franchises cost $25,145 per sale ([franchising.com 2026](https://www.franchising.com/articles/20260923_tracking_average_costs_per_lead_and_costs_per_sale.html)).

**Competitors (8+ searches).**

| Competitor | Model | Price |
|---|---|---|
| [IFPG](https://www.ifpg.org/self-employed-careers/self-employed-income/) | 650 consultants, 620 franchisors | Consultant pays $39.5k + $260/mo; franchisor about $1k/mo |
| [FranNet](https://franzy.com/blog/how-do-franchise-consultants-make-money/), FranChoice, The Entrepreneur's Source | Consultant networks | 40–50% of franchise fee |
| [Franzy](https://franzy.com/for-brands) | AI franchise matching; $3.33M seed (2025) | Flat fee from franchisors |
| FSOs ([Franchise Performance Group](https://franchiseperformancegroup.com/comparing-your-options-for-outsourced-franchise-sales/), others) | Outsourced sales | $5–20k/mo + 40–50% |
| [Franchise Flippers resale network](https://franchiseflippers.com/selling-a-franchise/services/resale-broker-network/), [FBA Resale Ready](https://resales.franchiseba.com/), [Small Business Deal Advisors](https://www.smallbusinessdeal.com/franchise-resale-partnership-program/) | Resale brokers | 8–12%, or greater of 8%/$10k |
| [FranchiseResales.com](https://www.franchiseresales.com/faq/) | Listing site | Listing fee |
| Portals (Franchise Gator etc.) | Pay per lead | Average CPL $271 |

**Legal.**
- **New York and Washington** require franchise-broker registration.
- **California SB 919** requires annual broker registration with DFPI and a broker disclosure document ([Fox Rothschild](https://franchiselaw.foxrothschild.com/2024/04/articles/regulatory-compliance/california-paves-way-for-franchise-broker-registration-model/)).
- NASAA has a model broker act pending ([NASAA](https://www.nasaa.org/76508/nasaa-public-comment-proposed-nasaa-model-franchise-broker-registration-act/)).
- Agents must never make earnings claims outside FDD Item 19.
- Resales count as business brokerage, so the 17-state real-estate rule applies.

**Kill risks.**
- Consultative sales take 3–6 months; most consultants place 4 or fewer a year; the top 20% make 63% of placements ([Entrepreneur](https://www.entrepreneur.com/business-news/new-study-finds-one-in-five-franchise-consultants-responsible-for-nearly-two-thirds-of-all-placements)).
- Conversion fees are discounted, so payouts shrink to about $5–12k.
- Independent contractors are skeptical of franchise royalties.

**Validation test.**
1. Sign 2–3 franchisors with conversion programs to a referral agreement. Without a consultant network that is unlikely; this is a kill signal by itself.
2. Run 1,000 conversion-pitch emails to independent HVAC and plumbing owners.
3. **Kill if** fewer than 10 discovery calls, or 0 discovery days within 90 days.

**Reply rate.** Trades owners are heavily solicited: **1–2% (est.)**.

---

### Idea 6: SMB technology-advisor residual book (an upsell to existing website customers)

**Pitch.** Carriers and SaaS vendors pay technology advisors **10–22% of monthly recurring charges for the life of the contract** ([telecom.directory](https://www.telecom.directory/resources/agent-commissions); [Modero](https://mymodero.com/blog/how-to-start-a-telecom-agency/)). Merchant-services agents earn 50–70% of the processing markup; one example is a $30k/month merchant paying the agent about $45/month ([Unison](https://www.unisonpayment.com/blog/merchant-services-agent-program-residual-income)). Comcast and Spectrum pay one month's MRC per referral, up to $1,500 or $5,000 ([Comcast](https://business.comcast.com/partner/authorized-connector-program); [Spectrum](https://www.spectrum.com/business/referral)). The brothers already have local SMB customers. An agent audits each customer's internet, phone, POS and processing bills and switches them where it saves money. The vendor pays a residual. **This is the only recurring model in the lane.**

**Money moves.** The TSD channel billed **$16.6B in 2024**, and technology advisors are 86% of partner types ([Omdia](https://omdia.tech.informa.com/blogs/2026/jan/key-insights-from-the-16point6bn-dollars-technology-services-distribution-tsd-market)).

**Unit economics (est.).** Internet at $150 MRC × 15% = $22. UCaaS for 5 seats at $150 × 20% = $30. Processing at $45. That is **about $60–100/month per fully switched customer**, starting 60–150 days after signing ([Modero](https://mymodero.com/blog/how-to-start-a-telecom-agency/)). Two hundred customers × 30% conversion × $75 = about $4.5k/month recurring.

**Competitors.**

| Competitor | Model | Price |
|---|---|---|
| Telarus, Intelisys, Avant, AppDirect, Sandler, BridgePointe | TSDs with thousands of advisors; top six hold 72.3% share | Pay advisors about 80% of supplier commission |
| [Lightyear](https://lightyear.ai/faq) | AI telecom procurement, $31M raised; free procurement funded by commissions | Free to buyer |
| Merchant ISOs (North American Bancard, etc.) | Agent programs | 50–70% split |
| MSPs | Bundle connectivity | Margin |
| Commercial energy brokers (adjacent) | 1–2 mils/kWh, about $400/yr per small office ([Diversegy](https://diversegy.com/energy-brokers/energy-broker-fees/); [Jaken](https://jakenenergy.com/article-108-commercial-energy-broker-fees-2026.html)) | Supplier-paid |

**Legal.** No license is needed for telecom or SaaS agency. Merchant services needs a sponsor-bank or ISO agreement. **Commercial energy brokering needs state registration** in TX, PA, IL, OH, NY and others, so leave energy out. Disclose vendor compensation to the customer.

**Automation.** Bill OCR and comparison: 85%. Outreach to the brothers' own customers: 90%. Order provisioning and porting: 40% (carrier portals). **Overall about 65%.**

**Kill risks.** Small dollars per account, carrier-dependent payouts, chargebacks on early churn, and a 2–5 month lag before the first check.

**Validation test.** Offer a free "bill audit" to 100 existing site customers. **Kill if** fewer than 15 upload bills, or fewer than 5 switch within 60 days.

**Reply rate.** Existing customers: **15–30% (est.)**. Cold SMBs: **1–3%**.

---

### Idea 7: Small-business tenant representation (landlord-paid)

**Pitch.** The landlord pays 4–6% of total lease value and the tenant rep gets about half ([Aquila](https://aquilacommercial.com/learning-center/cost-to-use-tenant-broker-austin/); [CEG](https://www.cegspaces.com/broker-payment)). The agent finds SMBs that are growing (hiring, new locations) and offers free representation.

**Why it scores low.**
- **Small deals are where co-broke breaks down.** For deals under 3,500 sq ft and rents under $5k/month, direct-with-owner is common ([MT Commercial](https://mtcommercialpropertyservices.com/blog/direct-with-owner-vs-broker-commercial-lease/)).
- A $3k/month × 5-year lease at 2–3% is only **$3.6–5.4k** per deal.
- **The trigger is unobservable.** Lease expirations aren't public, and by the time hiring signals show, the SMB has often already toured.
- **Competitors:** [SquareFoot](https://www.squarefoot.com/blog/best-office-space-brokers-nyc/) (small and mid-size tenants up to 20k sq ft, free to tenant) and [TenantBase](https://www.tenantbase.com/blog/tenant-representation-2026/) (70+ markets, AI search). [Truss](https://www.chicagobusiness.com/innovators/zillow-commercial-real-estate/), an SMB marketplace, ended up with its IP inside Avison Young ([Truss/Buildout](https://www.buildout.com/blog-posts/truss-buildout-find-the-perfect-tenant-for-your-perfect-space)), which suggests the SMB-online tenant-rep model is hard.

**Legal.** A real-estate license is required; use the same sponsoring-broker structure.

**Validation test.** Email 300 SMBs with expansion signals. **Kill if** fewer than 3 sign a representation agreement in 60 days.

---

## 3. Rejected ideas

| Idea | Reason | Evidence |
|---|---|---|
| Main Street micro-brokerage (under $500k) | Saturated with low-fee and AI entrants. Baton charges 6% plus $1k/mo; Rejigg is free to sellers; OffDeal (YC W24) is an AI-native investment bank; Tupelo and Smobi (YC) are marketplaces; Flippa, Acquire and BizBuySell FSBO are DIY. 17-state license burden. | [Baton](https://www.baton.com/pricing), [Rejigg](https://www.rejigg.com/owners/pricing), [TechCrunch OffDeal](https://techcrunch.com/2024/09/12/offdeal-wants-to-help-small-businesses-find-big-exits-with-ai-agents), [YC Smobi](https://www.ycombinator.com/launches/J1b-smobi-new-age-marketplace-for-businesses-for-sale) |
| Used restaurant equipment | Dealer buyouts recover 10–30%, auctions take 10–20% (up to 40%), and logistics such as rigging and removal can't be automated. TAGeX, KitchenEquipmentTrader and local dealers are incumbents. | [TAGeX](https://www.tagexbrands.com/restaurant-equipment-liquidation-guide-2/) |
| Heavy, construction and lab equipment | RB Global/IronPlanet takes 8–14% plus inspection; EquipNet, BioSurplus and LabX cover lab equipment. Capital and logistics heavy. | [IronPlanet](https://www.ironplanet.com/pop/consignment_printable_aus.jsp), [Lab Manager](https://www.labmanager.com/a-guide-to-selling-used-lab-equipment-2022) |
| Dental equipment | 10–20% brokers, zero-commission auctions, ABC Dentalworks buyouts | [Operatory Auctions](https://www.operatoryauctions.com/resources/where-to-sell-used-dental-equipment) |
| Freight capacity matching | Needs $75k BMC-84 bond (premiums $938–$9k a year); margins under 15% for small brokers; AI-agent vendors (Vooma, HappyRobot, FleetWorks) already sell to brokers | [SuretyBonds](https://www.suretybonds.com/license-permit/freight-broker-bond), [DAT](https://www.dat.com/blog/2025-keys-to-success-brokers), [FreightCaviar](https://www.freightcaviar.com/these-three-companies-are-creating-freight-broker-ai-agents/) |
| Website and domain brokerage | Flippa 5–10% plus listing fee; Empire Flippers 15%; Motion Invest 7–20%. Crowded, and "AI search" is eroding content-site values. | [Flippa fees](https://exitbid.io/blog/flippa-fees-explained-2026), [Empire Flippers](https://investors.club/empire-flippers-fees-buyers-sellers/), [Motion Invest](https://www.motioninvest.com/sell-site/) |
| Dental and vet practice brokerage | 6–12% established brokers, DSO buyers with in-house teams, and the guarded-professional problem | [Dental Transitions](https://dentaltransitions.com/articles/dental-practice-broker-commission-rates/) |
| Solar and roofing appointments | Commodity at $72–$300 per appointment; residential solar forecast to fall 33% in 2026 | [vahorizon](https://www.vahorizon.site/solar/blog/solar-appointment-setting-cost-2026/), [pv magazine](https://www.pv-magazine.com/2026/03/18/us-residential-solar-set-for-33-decline-in-2026-says-roth-capital-partners/) |
| Solar land origination | OBBBA start-of-construction cliff (July 4, 2026); LandGate and SolarLandLease already sell landowner leads per acre | [Kirkland](https://www.kirkland.com/publications/kirkland-alert/2025/08/one-big-beautiful-bill-act-brings-big-changes-to-green-energy-tax-credits), [SolarLandLease](https://www.solarlandlease.com/find-landowners), [LandGate](https://www.landgate.com/energy-markets) |
| Commercial energy brokerage | About $400 a year per small account; state registration in most deregulated states; thousands of brokers | [Jaken](https://jakenenergy.com/article-108-commercial-energy-broker-fees-2026.html) |
| Excess-inventory liquidation and government surplus | B-Stock and Liquidity Services/GovDeals ($4B+ in sales) own both sides; arbitrage needs capital | [Liquidity Services](https://investors.liquidityservices.com/news-releases/news-release-details/govdeals-achieves-4-billion-sales), [B-Stock](https://bstock.com/supplystore/seller-summary-of-charges/) |
| Home-services lead marketplace | Angi charges $15–$120 per lead and Thumbtack $10–$80; contractors hate shared leads. Legal outside RESPA, but saturated. | [Housecall Pro](https://www.housecallpro.com/resources/homeadvisor-vs-angi-full-comparison-which-is-the-better-lead-generation-service/), [CFPB RESPA FAQ](https://www.consumerfinance.gov/compliance/compliance-resources/mortgage-resources/real-estate-settlement-procedures-act/real-estate-settlement-procedures-act-faqs/) |
| Janitorial account brokering | Jani-King and Coverall model with misclassification litigation history; pay-per-appointment vendors at about $135 | [court filing](https://www.govinfo.gov/content/pkg/USCOURTS-ctd-3_16-cv-01990/pdf/USCOURTS-ctd-3_16-cv-01990-3.pdf), [Janitorial Appointment](https://www.janitorialappointment.com/) |

---

## 4. Self-verification results

*(Filled in after two adversarial sub-agents attacked the ideas; see the bottom of the file.)*

---

## 5. Ranked shortlist

*(Final scores after self-verification; see the bottom of the file.)*
