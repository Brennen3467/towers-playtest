# Verify-1: adversarial check of five shortlisted ideas

*Verification date: 2026-10-01. Research only: no outreach, signups or purchases. I re-checked every load-bearing claim against independent sources, primary ones where I could reach them (statutes, CFR, CBP rulings, open-data APIs, vendor pricing pages). "Unverified" means I could not confirm it, not that it is false. Some primary sites (eCFR, federalregister.gov) blocked automated fetches, so for those I used law.cornell.edu, govinfo.gov and the CBP rulings API.*

**Ideas in this batch**

| # | Idea | Source write-up |
|---|---|---|
| 1 | Tariff Exposure Brief + Monitor | `research/02-trade-intel.md`, shortlist #1 |
| 2 | Duty-Recovery Lead Engine | `research/02-trade-intel.md`, shortlist #2, and `research/11-wildcards.md`, idea #6 (drawback discovery) |
| 3 | Vertical Roll-up Target Intelligence ("SuccessionMap") | `research/01-ma-origination.md`, #1 |
| 4 | Flat-fee add-on origination (the seed idea) | `research/01-ma-origination.md`, #2 |
| 5 | Practice-acquisition screener for LMM healthcare roll-ups | `research/06-healthcare.md`, #3 |

## Verdict summary

| # | Idea | Original score | Verdict | Revised score | Confidence |
|---|---|---|---|---|---|
| 1 | Tariff Exposure Brief + Monitor | 7.0 | **WEAKENED** (close to killed as specified) | **3.5** | Medium |
| 2a | Duty-Recovery Lead Engine (flat-fee leads to licensed partners) | 6.4 | **WEAKENED** | **3.0** | Medium |
| 2b | Drawback discovery (contingency shared with broker) | 5.3 | **KILLED** | **1.5** | High |
| 3 | Vertical Roll-up Target Intelligence | 6.4 | **WEAKENED** | **3.5** | Medium |
| 4 | Flat-fee add-on origination (seed idea) | 6.0 | **WEAKENED** (legal OK; commercially commoditized) | **3.0** | Medium-high |
| 5 | Practice-acquisition screener (healthcare) | 6.2 | **WEAKENED** (two data claims are false) | **3.0** | Medium |

**The pattern across all five:**
- **The data is real and cheap, but it is shallower than the write-ups claimed.** Three examples:
  - Texas licence data has no issue date.
  - CMS publishes no practice-ownership file.
  - Bills of lading have no values or HTS codes.
- **Every buyer group already has a funded tool or a free substitute,** so no idea scored above 3.5 after checking.

---

## Idea 1: Tariff Exposure Brief + Monitor. **WEAKENED: 3.5/10 (medium confidence)**

### Claims checked

| Original claim | Finding | Source | Holds? |
|---|---|---|---|
| CBP sells AMS manifest data "at the government's production cost", price not published; order via NFC | Confirmed: the regulation names CD-ROM sales at production cost and gives the NFC Indianapolis phone line. No price is published anywhere. **New:** the Feb 2026 proposed rule (2026-02662) would move delivery to SFTP with wire payment. It still names no price. | [19 CFR 103.31](https://www.law.cornell.edu/cfr/text/19/103.31); [FR 2026-02662](https://www.govinfo.gov/content/pkg/FR-2026-02-10/html/2026-02662.htm) | Yes; price unverified |
| Free 2-year confidentiality certification; ~12,000 requests/yr | Confirmed. An online tool now approves requests within about 24 hours. | [CBP](https://www.cbp.gov/trade/automated/electronic-vessel-manifest-confidentiality); [FreightWaves](https://www.freightwaves.com/news/cbp-makes-it-easier-for-shippers-to-obtain-manifest-data-confidentiality) | Yes |
| Consignee missing 12–17%, value missing 64–68%, HS codes imputed | Confirmed in Fed FEDS 2021-066, Table 3: 12.3–16.8% and 64.6–68.3%. HS codes are Panjiva's algorithmic guesses, "not official HS codes"; manifests require only descriptions. | [Flaaen et al.](https://www.federalreserve.gov/econres/feds/files/2021066pap.pdf) | Yes |
| "BOL × Census unit values × tariff stack" gives a credible firm-level duty figure ("roughly $410k a year of new duty") | **Not supported.** Manifests carry neither value nor HTS. Census unit values vary widely within an HS10 cell ([Fed IFDP 991](https://www.federalreserve.gov/pubs/ifdp/2010/991/ifdp991.htm)). Ocean covers only about 50% of import value, and Mexico and Canada are mostly overland. Consignees are often NVOCCs or forwarders. I found no published error rate. **My estimate (unsourced): firm-level dollar figures will often be off by 2–5×.** The recipient sees exact duties in ACE, so a wrong number is visible immediately. | [Fed FEDS 2021-066](https://www.federalreserve.gov/econres/feds/files/2021066pap.pdf) | **No** |
| "Pre-computed outbound approach is uncrowded"; competition score 5 | Partly false. Several firms already combine trade data with tariff schedules: **Descartes Datamyne Tariff Insights** (BOL platform plus tariff exposure and landed cost), **Altana** (Tariff Calculator / Scenario Planner, plus IEEPA refund automation), **ImportGenius** (sells BOL data "for lead generation"), **Flexport** (free simulator, no login), **Gaia Dynamics** ($7M seed Sept 2026, ~800 accounts, works on the importer's own ACE data) and **Tarifflo** (YC, entry audits and refunds). Nobody sends cold, unsolicited per-firm briefs, but that is a narrow gap and probably the reason the briefs would fail. | [Datamyne](https://www.datamyne.com/our-product/tariff-insights/); [Altana](https://altana.ai/tariff-calculator); [ImportGenius](https://www.importgenius.com/landing-page/trade-data-for-lead-generation); [Flexport](https://tariffs.flexport.com/); [Gaia PR](https://www.prnewswire.com/news-releases/gaia-dynamics-raises-7m-to-expand-ai-platform-keeping-businesses-ahead-of-tariffs-and-trade-risk-302880240.html); [YC](https://www.ycombinator.com/companies/industry/legaltech) | Partly |
| SMBs will pay $199–$499/mo for monitoring | **Unverified.** Gaia's $0–$1,399/mo self-serve tier is the nearest comparable, and it works on exact ACE data. Brokers and Flexport give alerts to clients free. I found no evidence of SMBs paying for monitoring derived from BOL data. | [GingerControl compare](https://gingercontrol.com/compare/gaia-dynamics-vs-gingercontrol) | Unverified, leaning no |
| 47,306 importers with 20–499 employees | The Census EDB table was cited correctly. Usable reach is smaller: about half of import value is not ocean freight, 12–17% of consignees are masked, and many named consignees are forwarders. | [Census EDB 2024](https://www.census.gov/foreign-trade/Press-Release/edb/edbrel2024.pdf) | Partly |
| Brief is "analysis, not customs advice"; no licence needed | Mostly holds. 19 USC 1641 defines customs business as activity involving *transactions with CBP*. An estimate sent to a prospect is outside that. Preparing protests, CAPE claims or classifications for others is inside it. | [19 USC 1641](https://www.law.cornell.edu/uscode/text/19/1641); [19 CFR 111.1](https://www.law.cornell.edu/cfr/text/19/111.1) | Yes |
| Unit economics: CAC $150–$400, 1–2% trial conversion | Optimistic. Vendor reply-rate benchmarks put manufacturing at about 2–4% replies (low-trust sources), and replies are not paid trials. One 2026 dataset puts owner/founder replies at 0.57%. | [RevenueFlow](https://www.revenueflow.com/blog/manufacturing-cold-email-benchmarks); [Cleanlist](https://www.cleanlist.ai/blog/2026-02-18-cold-email-response-rate-statistics) | Doubtful |

### New risks
- **The brief tells recipients to hide.** Any importer that receives "we can see your shipments" can file a free confidentiality request in about 24 hours ([CBP](https://www.cbp.gov/trade/automated/electronic-vessel-manifest-confidentiality)). The product shrinks its own dataset, and the most sophisticated payers go dark first.
- **The trigger supply is in court.** The §301 "forced-labour" tariffs are being challenged. §122 was held unlawful by the CIT (relief limited to 3 plaintiffs) and stayed by the Federal Circuit ([Skadden](https://www.skadden.com/insights/publications/2026/05/us-trade-court-strikes-down-section-122-tariffs); [GT Law](https://www.gtlaw.com/en/insights/2026/5/us-tariff-update-section-122-duties-found-unauthorized-by-law-ieepa-refunds-under-way)).
- **There is no data moat.** ImportYeti is free and ImportGenius starts at $229/mo. The direct CBP feed price is unknown.

### Most likely failure
The first number a CFO reads is visibly wrong against their ACE statement or broker invoice. Replies are mostly "that's not right" or a confidentiality filing, and the paid monitor never gets past month one against free broker and Flexport alerts.

### Changes that would make it viable
1. **Drop the dollar figure.** Lead with *exposure categories* ("you import HS 9403 from Vietnam; the 24 July §301 action applies at 12.5%; here's what to ask your broker") and give dollars only as a range with the method shown.
2. **Sell to brokers and forwarders, not importers.** Ship it as a white-label client-alert engine sold to customs brokers ([~11k licences](https://customsbrokerindex.com/blog/customs-broker-list-how-to-find/)). They hold the exact ACE data and the client relationship. This competes with ImportGenius's lead-gen tier, so differentiate on automated alerts, not on data.
3. **Gate the paid tier on the importer uploading its ACE ES-003 report.** At that point it competes directly with Gaia, so expect lower pricing power.

---

## Idea 2: Duty-Recovery Lead Engine. **2a WEAKENED 3.0/10; 2b KILLED 1.5/10**

### Claims checked

| Original claim | Finding | Source | Holds? |
|---|---|---|---|
| 19 CFR 111.36 bars brokers from sharing customs-business fees with unlicensed persons | Confirmed; it is still §111.36 after the 2022 rewrite. §111.36(b) says a broker must not enter an agreement where "the fees or other benefits resulting from the services rendered for others inure to the benefit of the unlicensed person". §111.36(c) allows compensation only to **freight forwarders**, with conditions. | [19 CFR 111.36](https://www.law.cornell.edu/cfr/text/19/111.36) | Yes |
| Flat per-lead or retainer fees avoid the problem ("Price per qualified lead, or a flat monthly retainer") | **Only the flat retainer is defensible.** CBP ruling **H276784** (2016) refused a broker's plan to pay referral organisations a fee "only once a business relationship… is formed" and held that "unlicensed independent agents may not accept commissions… for promoting its brokerage services". CBP added, citing HQ 113965, that "a flat amount… not tied to any particular transaction" *might* not trigger the rule. A **per-qualified-lead or per-signed-client fee paid by a licensed broker is grey to prohibited.** A flat monthly retainer not tied to outcomes is the only structure with any CBP support, and that support is dicta. I read the ruling text myself through the rulings API. | [CBP H276784](https://rulings.cbp.gov/ruling/H276784) | Partly |
| 11-wildcards #6: "annual or quarterly drawback claims on 20–25% contingency, **shared with the broker partner**" | **Prohibited for the drawback piece.** Drawback is expressly customs business ("the refund, rebate, or drawback thereof"; preparing documents for CBP filing). A contingency split from a licensed broker to an unlicensed party is exactly what H276784 and §111.36(b) forbid. **Penalties fall on the broker's licence**, so no reputable broker will sign. | [19 CFR 111.1](https://www.law.cornell.edu/cfr/text/19/111.1); [H276784](https://rulings.cbp.gov/ruling/H276784) | **No; this kills 2b** |
| Drawback firms would buy leads | **Not evidenced.** The SMB drawback players run *partner* programs aimed at brokers, 3PLs and accountants: Zollback (amounts undisclosed) and **Pax** (YC, $4.5M seed, which gives brokers "a share of every successful refund", consistent with the forwarder carve-out). I found no published per-lead prices. | [Zollback](https://www.zollback.com/); [Pax](https://www.paxai.com/customs-brokerages) | Unverified, leaning no |
| Drawback paid ~$0.9–1B/yr | Confirmed for 2011–2018: $629M (2011) to $1.25B (2018), averaging $896M. I found no official FY25/26 figure. The "80–85% of drawback goes unclaimed" line appears only in vendor marketing, with no primary source. | [GAO-20-182](https://www.gao.gov/products/gao-20-182) | Yes; "unclaimed" is folklore |
| Drawback fees run 15–35% contingency | The common range is 10–25%. | [Zollback blog](https://www.zollback.com/blog/tariff-refunds-for-smbs) | Partly |
| 27,479 bond insufficiencies in FY2025 (~$3.6B) | Confirmed (CNBC, citing CBP data). | [CNBC](https://www.cnbc.com/2026/02/12/trump-tariffs-us-customs-record-bond-funding-issues-flagged.html) | Yes |
| IEEPA: ~$166B pool; $122B certified by 11 Sep 2026; Phase 3 (from 6 Oct) limited to CIT plaintiffs who submitted their IOR by 30 July | Confirmed: about 330k importers and 53M entries; $134.7B accepted into CAPE. Phase 3 is about $11.4B of finally liquidated entries. About **$25B** sits outside all phases, and about **$1.3B** (20,184 refunds) is on hold for missing ACH details. Hedge funds and private credit bought refund claims at **$0.50–0.90 on the dollar**. | [tariffstool tracker](https://www.tariffstool.com/tariff-refund-tracker); [ALS](https://www.als-int.com/insights/posts/cape-phase-3-ieepa-refunds-litigation-requirement-2026/); [Thompson Hine](https://www.thompsonhinesmartrade.com/2026/07/cit-orders-cbp-to-process-ieepa-tariff-refunds-for-phase-3-finally-liquidated-entries/); [Troutman](https://www.troutman.com/insights/phase-one-ieepa-tariff-refunds-are-hitting-bank-accounts-what-importers-should-do-now-and-implications-for-the-secondary-market-in-refund-rights/); [Fortune](https://fortune.com/2026/03/07/winners-supreme-court-tariff-ruling-hedge-funds-creating-100-billion-secondary-market-refunds-brandon-howard-lutnick/) | Yes; the original's rejection of an IEEPA play stands |
| Last Sale Valuation Act overhangs first sale | S.3841 was introduced 11 Feb 2026 and referred to Senate Finance. I found no later action. | [govinfo S.3841](https://www.govinfo.gov/app/details/BILLS-119s3841is) | Yes (pending) |
| Export side: drawback candidates can be found by matching import and export manifests | **Weak today.** Outward manifests disclose only shipper, cargo character, weight and route, not consignee. The Feb 2026 proposed rule would publish more fields, but it is not final. | [103.31](https://www.law.cornell.edu/cfr/text/19/103.31); [FR 2026-02662](https://www.govinfo.gov/content/pkg/FR-2026-02-10/html/2026-02662.htm) | Partly |

### Who is already chasing the residual IEEPA and §122 money
Flexport (refund automation), Altana, Gaia, Tarifflo (YC), GingerControl, Caspian, CBIZ/BDO, trade law firms, and claim-buying funds ([Hedgeweek](https://www.hedgeweek.com/tariff-refunds-how-hedge-funds-are-structuring-a-new-short-duration-credit-trade/); [Caspian](https://www.meetcaspian.com/blog/cape-phase-3-ieepa-refunds-october-6)). The only remaining leftovers are the ~$1.3B ACH-hold refunds and the ~$25B of out-of-phase money. The ACH-hold refunds need importer action only, so there is no fee room. The out-of-phase money needs litigation, which is lawyers' work.

### Most likely failure
Licensed drawback brokers won't sign a lead deal in any form that tracks outcomes, because their licence is at risk. A flat retainer for leads guessed from BOL data, with no export-side evidence, doesn't clear the brokers' bar for value. Surety agencies (bond-insufficiency leads) are the one buyer outside §111.36, but each lead is worth only $250–$1,000 in premium, and state insurance-referral rules (unverified) apply.

### Changes that would make it viable
1. Use only a **flat monthly data subscription**, not per-lead or per-client, and get a CBP binding ruling under 19 CFR 177 *before* launch. A ruling is free and is the strongest possible cover.
2. Target buyers **outside §111.36**: surety/bond MGAs (check state producer-referral rules) and first-sale consultants. First sale has its own legislative overhang (S.3841).
3. Re-evaluate if the export-manifest rule is finalised with consignee disclosure. That would make drawback matching genuinely data-driven.

---

## Idea 3: Vertical Roll-up Target Intelligence ("SuccessionMap"). **WEAKENED: 3.5/10 (medium confidence)**

### Claims checked

| Original claim | Finding | Source | Holds? |
|---|---|---|---|
| TX TDLR open data gives "state trade-license first-issue date" (1.01M rows) | **False.** I pulled the dataset's column metadata myself. The only date field is `license_expiration_date_mmddccyy`; there is **no issue date**. Licence numbers look roughly sequential, so a crude tenure guess is possible, but the licence belongs to the individual holder, not the business. **TX plumbing is not in this file at all** (a separate board, TSBPE). | [data.texas.gov API metadata](https://data.texas.gov/api/views/7358-krk7.json) | **No** |
| Other states give tenure | California CSLB's License Master has `ORIGINAL-ISSUE-DT` (free download). Florida DBPR construction files have "Original Licensure Date". Tenure therefore works in CA and FL, not TX. | [CSLB layout](https://cslb.ca.gov/Resources/FormsAndApplications/License_Master_Record_Layout_LBL780J1.pdf); [CSLB portal](https://www2.cslb.ca.gov/onlineservices/dataportal/ContractorList); [FL DBPR](https://www2.myfloridalicense.com/construction-industry/public-records/) | Partly |
| PPP FOIA gives size (jobs, NAICS) | Still downloadable, but frozen: files dated 30 Sep 2024, loans from 2020–21. `BusinessAgeDescription` is coarse ("Existing or more than 2 years old"), and there is no owner age. | [data.sba.gov PPP FOIA](https://data.sba.gov/dataset/ppp-foia) | Partly (stale) |
| SBA 7(a) FOIA gives ownership-change history | Current to 2026-06-30 and refreshed quarterly. It covers only SBA borrowers, a small slice of shops. | [data.sba.gov 7a/504](https://data.sba.gov/dataset/7a-504-foia) | Yes, sparse |
| A succession-likelihood score is a gap ("Horizontal databases do not join these sources") | **False as positioned.** Inven sells "Intent-to-sell" filters including **"Nearing Retirement: owners or founders approaching retirement age"** and "Long-Held by PE" (I confirmed the page text myself). **TradeBridge** sells contractor data tagged Independent / PE-backed / Franchise and promotes "founder age 55+" targeting. I found no owner-age signal in Grata. | [Inven help](https://help.inven.ai/using-the-intent-to-sell); [Inven article](https://www.inven.ai/articles/how-to-find-businesses-for-sale-by-retiring-owners); [TradeBridge](https://gettradebridge.com/resources/pe-backed-home-services-companies/); [Grata HVAC playbook](https://grata.com/resources/hvac-pe-playbook-2025) | **No** |
| 22 named HVAC consolidators | Confirmed by DealSeam (21 PE-backed). A CT Acquisitions blog says 27. | [DealSeam](https://dealseam.com/hvac-pe-rollup-tracker-2026) | Yes |
| ~800 HVAC/plumbing/electrical companies acquired since 2022 | DealSeam attributes this to WSJ/PitchBook and Capstone. Second-hand only. | [DealSeam](https://dealseam.com/hvac-pe-rollup-tracker-2026) | Yes (secondary) |
| Apex closed ~60 add-ons in 2025 | Confirmed by a primary source: Apex completed "60 add-on acquisitions" across 5 regions. Its parent Alpine closed 190 deals. | [Alpine 2025 review](https://alpineinvestors.com/update/2025-year-in-review/) | Yes |
| ~500–900 roll-up platforms across ~15 verticals; SAM $15–70M | Too high for a first product. Capstone counts **38 PE add-on HVAC deals and 9 new platforms YTD 2026**. Sizing the original's own vertical bottom-up gives tens of HVAC/plumbing/electrical buyers, not hundreds. | [Capstone HVAC update](https://www.capstonepartners.com/insights/article-hvac-services-ma-update/) | **No** (overstated) |
| Kill risk "platforms already know every shop in their radius" | No direct quotes found. The most active buyer (Apex) runs an in-house M&A team with "a successful M&A playbook", and free trackers already list who has been acquired ([Craftflow](https://www.craftflow.com/dossier/what-companies-has-apex-service-partners-acquired)). | [Alpine](https://alpineinvestors.com/update/alpine-launches-apex-service-partners/) | Plausible |

### New risks
- **Hostile sellers.** Nexstar Network expelled its PE-backed members (about a third of ~800) in Sep 2025, and trade press tells owners that the PE calls are real ([Forbes](https://www.forbes.com/sites/brandonkochkodin/2025/09/16/a-group-for-small-building-trade-businesses-tells-private-equity-to-get-lost/); [ACHR News](https://www.achrnews.com/articles/165527-the-50-million-handshake-why-hvac-owners-are-cashing-out-to-private-equity)). The score is predicting willingness to sell from owners who increasingly resent being asked.
- **Thin data in the launch state.** The original planned TX first, but TX lacks an issue date and plumbing coverage.

### Most likely failure
A platform's corp-dev lead sees a state licence dump plus a retirement flag that Inven or TradeBridge already provides, decides an analyst could build it in a week, and declines. With only a few dozen buyers per vertical, the business never reaches enough $1.5–3K/mo accounts.

### Changes that would make it viable
1. **Launch in CA and FL, not TX** (real issue dates there).
2. **Back-test before selling:** score the companies acquired since 2022 and show lift over plain tenure. Without measured lift there is no product.
3. **Sell to the long tail Inven ignores** (independent sponsors, search funders, small family offices) at a $300–800/mo self-serve price, or sell to sell-side business brokers who need mandates. **Do not** price against Inven for PE platforms.
4. Lead with the brothers' unique signal: **website and review staleness from their existing crawler**. It is the one input competitors don't obviously have.

---

## Idea 4: Flat-fee add-on origination (seed idea). **WEAKENED: 3.0/10 (medium-high confidence)**

### Claims checked

| Original claim | Finding | Source | Holds? |
|---|---|---|---|
| §15(b)(13) M&A broker exemption: <$25M EBITDA or <$250M revenue, private target, control transfer; no holding funds or buyer groups | Confirmed from the statute text. It places **no restriction on the form of compensation**. | [15 USC 78o](https://www.law.cornell.edu/uscode/text/15/78o) | Yes |
| A flat or per-meeting fee is the safe structure; "pay-per-meeting is probably fine" | **Directionally right, but the cited authority is weaker than implied.** Transaction-based pay is the hallmark of a broker, so a fee independent of closing helps. But *Paul Anka* (1991) actually **allowed a percentage fee** for supplying names only, so it does not specifically support flat fees. What triggers broker status is **conduct**: negotiating, valuing or screening deals, not just the fee type. Per-meeting is low risk as long as the shop sets up meetings and nothing more. | [Anka letter](https://business.cch.com/srd/VL-SECStaffNoActionLetter-PaulAnka-072491.pdf); [Wiggin](https://www.wiggin.com/publication/sec-casts-doubt-on-issuers-ability-to-pay-transaction-based-compensation-to-finders/) | Partly |
| ~23 states have an M&A broker exemption; the federal exemption does not pre-empt states | Confirmed: IBBA says "roughly 23 states", leaving "close to half the country without a clear safe harbor". Other trackers say 21. | [IBBA](https://www.ibba.org/articles/the-state-line-trap/) | Yes |
| Contracts can be void under §29(b) | Confirmed: contracts made in violation of the Act "shall be void" (15 USC 78cc(b)). | [15 USC 78cc](https://www.law.cornell.edu/uscode/text/15/78cc) | Yes |
| Real-estate licence in FL/CA/TX | Confirmed as a risk for **commissions** when real estate or a lease is involved. A flat meeting fee mostly avoids it. | [IBBA](https://www.ibba.org/articles/the-state-line-trap/) | Yes |
| CAPTARGET ~$1–3K/mo (avg $2.5K), 4–8 owner meetings/mo | CAPTARGET's own page says **$2,000/mo** with no success fee. It **does not guarantee meetings**, and I found no source for "4–8 meetings". It is now part of SourceCo. | [CAPTARGET](https://www.captarget.com/insights/deal-origination-cost-comparison); [CAPTARGET origination](https://www.captarget.com/deal-origination) | Partly |
| SourceCo $4–8K/mo + 1–2% at close | $4–8K/mo month-to-month plus a success fee, per SourceCo's own page. The 1–2% figure is unconfirmed. | [SourceCo](https://www.sourcecodeals.com/deal-sourcing-alternative) | Mostly |
| Hypergen Lite $6,500/mo, 6-month minimum | Confirmed. | [Hypergen](https://www.hypergen.io/pricing) | Yes |
| Axia $350/meeting | Confirmed: "from $350 per qualified appointment", with a money-back guarantee. | [Axia](https://axiagrowth.com/); [GlobeNewswire](https://www.globenewswire.com/news-release/2025/09/16/3151009/0/en/Axia-Growth-Launches-Innovative-Deal-Sourcing-System-to-Redefine-Lower-Middle-Market-M-A.html) | Yes |
| Owner reply rates 1–3% | Generic cold-email average is about 3.4%. One 2026 study puts **owners/founders at 0.57%**. | [Instantly 2026](https://instantly.ai/cold-email-benchmark-report-2026); [Cleanlist](https://www.cleanlist.ai/blog/2026-02-18-cold-email-response-rate-statistics) | Worse than stated |
| Gmail/Yahoo complaint thresholds | Confirmed: 0.3% maximum (0.1% target), SPF/DKIM/DMARC and one-click unsubscribe required. Gmail began rejecting non-compliant mail in Nov 2025. | [Red Sift](https://redsift.com/resources/blog/gmails-enforcement-ramps-up-what-bulk-senders-need-to-know) | Yes |

### Newly found competitors
- **Q2Q** (YC W26): "tell us the companies you want to buy and we'll get qualified meetings booked", plus an AI phone agent. Its YC page now marks it **Inactive**, which I checked myself. A funded team with the identical pitch did not survive. ([launch](https://www.ycombinator.com/launches/POh-q2q-ai-native-deal-sourcing-for-private-equity); [status](https://www.ycombinator.com/companies/q2q))
- **Danish Lead Co**: from $3,500/mo with a 3-month minimum ([source](https://danishleadco.io/blog/best-b2b-lead-generation-agencies-private-equity-ma)).
- **Axial**: about $100 per deal unlocked, plus a success fee.
- **OffDeal** (YC), on the sell side.
- **SourceCo**, which now includes CAPTARGET.

### Most likely failure
The brothers' $3–6K/mo or $400–600/meeting offer is priced *above* CAPTARGET ($2K) and Axia ($350, money-back), with no differentiator buyers can see. HVAC and trades owners are saturated and increasingly hostile, so meetings come in below promise and clients churn after the 3-month minimum.

### Changes that would make it viable
1. **Don't sell it alone.** Bundle it as the outreach layer of Idea 3 for the long-tail buyers (independent sponsors, search funders) whom CAPTARGET and SourceCo underserve.
2. Price **at or below $350/held meeting with a money-back guarantee**, which is the market anchor.
3. Choose verticals where owners are *not* yet saturated (e.g. niche B2B services, not HVAC).
4. Keep the legal structure: send in the buyer's name, take no part in valuation or negotiation, never touch funds, charge only fees unrelated to closing, and get one securities-counsel review.

---

## Idea 5: Practice-acquisition screener (healthcare). **WEAKENED: 3.0/10 (medium confidence)**

### Claims checked

| Original claim | Finding | Source | Holds? |
|---|---|---|---|
| The Doctors & Clinicians file has graduation year (owner-age proxy) and group size | Confirmed from the live CSV header (file modified 2026-09-10): `Grd_yr`, `org_pac_id`, `num_org_mem`. For optometry, `Grd_yr` is filled in about 99.9% of rows. `Med_sch` is "OTHER" in 23% of rows. There are no ownership, revenue or email fields. | [CMS metastore mj5m-pzi6](https://data.cms.gov/provider-data/api/1/metastore/schemas/dataset/items/mj5m-pzi6) | Yes |
| Part B by-provider data gives a multi-year revenue proxy and growth trend | **Partly.** The latest year is **CY2024, published 2026-05-21**, so it is 21–33 months stale. It covers Medicare **fee-for-service only**, while Medicare Advantage now has about 54% of beneficiaries. Lines with ≤10 beneficiaries are suppressed, which drops the small solo targets. When a provider bills under both individual and group NPIs, CMS says the true total cannot be determined. | [CMS PUF methodology](https://www.cms.gov/Research-Statistics-Data-and-Systems/Statistics-Trends-and-Reports/Medicare-Provider-Charge-Data/Downloads/Medicare-Physician-and-Other-Supplier-PUF-Methodology.pdf); [data.cms.gov catalog](https://data.cms.gov/data.json); [KFF](https://x.com/KFF/status/1950278935893234106) | Partly |
| Medicare revenue is a usable size proxy for optometry and PT | **No for optometry.** Government programs are about 16% of owner-optometrist billings, and about 61% of independent optometry revenue is eyewear and contacts. PT is commercial-heavy and dermatology is partly cash-pay. It works only for **podiatry and ophthalmology**. | [AOA income survey](https://www.ferris.edu/optometry/pdfs-docs/2022_AOA_Income.pdf); [Optometry Business key metrics](https://files.optometrybusiness.com/Key%20Metrics%20of%20Established%20Practices.pdf) | **No** for the two launch specialties |
| The "Open Payments ownership file" shows physician ownership | **Wrong.** It covers physician ownership of drug and device manufacturers and GPOs, not of practices. | [Open Payments FAQ](https://www.cms.gov/openpayments/downloads/open-payments-general-faq.pdf) | **No** |
| CMS ownership files flag PE ownership | **Wrong for practices.** "All Owners" files exist only for hospitals, SNFs, HHAs, hospice, RHCs and FQHCs. Nothing covers physician or therapy practices, so the "independence flag" cannot come from CMS. | [data.cms.gov catalog](https://data.cms.gov/data.json) | **No** |
| "CPT not needed if we show only dollar totals" | Unverified and risky. The AMA requires a licence for any commercial use of CPT. Using only the **by-Provider** file, which has no HCPCS codes, sidesteps the question. | [AMA CPT licensing FAQ](https://www.ama-assn.org/practice-management/cpt/cpt-licensing-frequently-asked-questions-faqs) | Partly |
| PESP counted 1,029 PE healthcare deals in 2025 (664 add-ons, 420 platforms) | Exact match, but the figures cover **all of healthcare**, including health IT (151) and dental (149). Outpatient was 148 deals. The relevant specialty platforms number about **80–100** (eye care ~22, dermatology 18–35, PT ~18, podiatry ~5–8). | [PESP](https://pestakeholder.org/reports/pe-healthcare-deals-2025-in-review/); [CT Acq PT tracker](https://ctacquisitions.com/guides/physical-therapy-pe-rollup-tracker-2026/); [CT Acq ophth.](https://ctacquisitions.com/guides/ophthalmology-pe-rollup-tracker-2026/); [DealSeam derm](https://dealseam.com/dermatology-pe-rollup-tracker-2026); [HVG podiatry](https://healthvaluegroup.com/private-equity-podiatry-a-brief-overview/) | Partly (SAM overstated) |
| Willingness to pay $750–1,500/mo per specialty × region | **No direct evidence.** Provyx sells PE firms NPI-verified practice lists with ownership classification (solo, independent, PE-backed, MSO) at **$750 per 1,000 records, one-time**. That undercuts a monthly subscription for a list the buyer works through once. | [Provyx pricing](https://getprovyx.com/pricing/); [Provyx firmographics](https://getprovyx.com/services/practice-firmographics/) | Unverified, leaning no |
| State PE-healthcare laws affect buyers, not us | True, but they shrink demand: CA AB 1415 (90-day pre-closing notice from 2026-01-01, with expanded draft regulations 2026-09-11), CA SB 351, OR SB 951, MA H 5159, plus 9 more laws enacted in 2026. | [Kirkland](https://www.kirkland.com/publications/kirkland-alert/2026/09/california-expands-pre-closing-filing-and-disclosure-requirements-for-health-care-transactions); [HIT Consultant](https://hitconsultant.net/2026/09/22/states-expand-private-equity-scrutiny-healthcare-pesp-2026-policy-review/); [Cooley](https://www.cooley.com/news/insight/2025/2025-12-16-californias-new-laws-what-private-equity-needs-to-know-about-healthcare-investment-restrictions) | Yes; headwind |

### Newly found competitors
- **Alpha Sophia**: explicitly sells PE roll-up sourcing from all-payer claims, covering about 80% of US claims (Medicare, Medicaid and commercial), with territory maps and a CRM. Its data is strictly better than Medicare fee-for-service. ([source](https://www.alphasophia.com/solutions/investment-sourcing-due-diligence))
- **Provyx**: practice lists with ownership classification ([source](https://getprovyx.com/services/practice-firmographics/)).
- **Definitive Healthcare**: median contract about $50.5k/yr ([Vendr](https://www.vendr.com/marketplace/definitive-healthcare)).
- **Grata**.
- **DealSeam and CT Acquisitions**: free trackers plus buyer-paid deal flow.

### Most likely failure
Buyers see a Medicare-only, ownership-blind subset of Alpha Sophia or Provyx. The list includes practices that have already sold and misranks optometry and PT. Buyers pull it once and cancel.

### Changes that would make it viable
1. **One specialty where Medicare fee-for-service tracks revenue:** podiatry or ophthalmology/retina.
2. **Build the missing "already PE-owned" exclusion layer** by fuzzy-matching platform location pages and press releases. That, not graduation year, is the moat.
3. Use the **by-Provider file only**, which has no CPT codes.
4. Sell to **sell-side practice brokers** (sellers are the scarce side) or price per qualified introduction, not as a monthly subscription. Flag targets in notice-law states.

---

## Final cross-idea ranking (this batch)

| Rank | Idea | Revised score | Why it ranks here |
|---|---|---|---|
| 1 | **#3 Vertical Roll-up Target Intelligence**, re-scoped to CA/FL, the long-tail buyers and website-staleness as the signal | 3.5 | Real but overstated data. The one input competitors lack is the brothers' own crawler. Cheap to back-test. |
| 2 | **#1 Tariff Exposure Brief**, re-scoped as a broker white-label alert engine | 3.5 (≈2.5 as originally specified) | Strong trigger supply, but dollar figures from BOL data are not credible. Viable only through brokers, who hold the exact data. |
| 3 | **#5 Healthcare practice screener**, re-scoped to podiatry/ophthalmology with a PE-owned exclusion layer | 3.0 | Free, verified CMS data, but two key data claims were false, Alpha Sophia and Provyx exist, and there are only ~80–100 buyers. |
| 4 | **#4 Flat-fee add-on origination** | 3.0 | Legally workable as flat or per-meeting with conduct limits. Commercially priced above CAPTARGET and Axia, and a YC company with the same pitch is already inactive. |
| 5 | **#2a Duty-recovery lead engine** (flat retainer only) | 3.0 | Only a flat, transaction-independent retainer survives §111.36 / H276784. I found no evidence that drawback firms buy leads. |
| 6 | **#2b Drawback discovery with broker contingency split** | 1.5 | **Killed:** a contingency split from a licensed broker to an unlicensed party is what 19 CFR 111.36(b) and H276784 prohibit. |

**Bottom line for this batch:**
- **No idea is good enough to launch as written.**
- **The best next step** is a 3–4 week, under-$1K **back-test of Idea #3 in California**: CSLB issue dates plus the brothers' website-staleness crawl, scored against the HVAC, plumbing and electrical shops acquired since 2022. If the score shows clear lift over tenure alone, sell it to independent sponsors and search funders, with #4's outreach as a flat-fee add-on.
- **Everything in the trade lane should wait for one of two things:**
  - a CBP binding ruling on a flat-fee structure;
  - the export-manifest rule being finalised.
