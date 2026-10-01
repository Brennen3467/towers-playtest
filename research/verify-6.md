# Verify-6: Stress-testing the "upsell to existing website customers / SMB growth platform" thesis

*Verification date: 2026-10-01. Research only: no outreach, signups or purchases. I read the source write-ups from `origin/research/09-smb-adjacent`, `verify-5`, `13-found-money`, `15-agent-brokerage` and `12-dfy-backoffice`.*

*Every material claim has a URL. **(est.)** marks my own arithmetic or judgement.*

**Method and limits**
- **Search budget:** about 176 web searches and fetches. Four parallel verifier sub-agents ran about 165 of them and I ran the rest.
- **Hidden partner terms:** many TSD terms sit behind partner logins. These include exact advisor splits, payment lag and minimums. Telarus promos are now "available after sign-in to Telarus Hub" ([promos.telarus.com](https://promos.telarus.com/)), so those figures rely on secondary sources and are marked.
- **Blocked sources:** Channel Futures pages returned 403, and I did not use Reddit.
- **Unverified firms:** Advocado turned out to be an ad-occurrence and measurement company, not a co-op claim service ([BusinessWire](https://www.businesswire.com/news/home/20230905457924/en/Irwin-Gotlieb-Steven-Saslow-Join-Advocados-Board-of-Directors-to-Accelerate-Advocados-Vision)). I found no public evidence of firms named "Co-op Assist" or "CoopCommerce".
- **"Vendor Managed Co-op" is not a co-op firm.** The search surfaced VMC Group, which files class-action settlement claims ([vmcclaim.com](https://www.vmcclaim.com/)).

---

## Verdict summary

| # | Item | Prior score | Verdict | Revised score | Confidence |
|---|---|---|---|---|---|
| 1 | Upsell economics: "existing customers will buy more, and it's the best lever" | (implicit 4.5–5) | **CONFIRMED in direction, WEAKENED in size.** Attach is real (about 20–35% buy *some* second product over 12 months), but no single add-on reaches more than about 15% attach. Retention improves too, but as a secondary effect. It scales linearly with N, so below about 300 customers it is a feature, not a business. | **5.0** as the operating strategy; **3.0** as a stand-alone "platform" pivot | Medium-high |
| 2 | TSD technology-advisor residual book (L15) | 5.0 | **WEAKENED** | **3.5** for telecom + merchant referral. **Energy: KILLED (1.5)** unless they get licensed per state. | Medium-high |
| 3 | Co-op claim desk + co-op-funded marketing (L13) | 4.5 / 5.0 | **WEAKENED.** A standalone claim desk is effectively **KILLED (2.5)**. As a co-op-*eligible* retainer for brand dealers it holds within that segment. | **4.0** overall (5.0 *only* where 10%+ of the base are national-brand dealers) | Medium |
| 4 | Reviews / GBP / AI-visibility retainer (L09, verify-5) | 5.0 | **CONFIRMED** (verify-5's conclusion holds) | **5.0**, the best single upsell | Medium-high |
| 5 | Contractor back-office bundle (L12 Idea 5) | 4.0–4.5 | **WEAKENED** for the typical residential-trades website customer | **3.0** (4.0 for a commercial-sub segment only) | Medium |
| 6a | Strategic: best bundle | — | Reviews/GBP plan + care plan as the core; co-op retainer for dealers only; tech-advisor as an opportunistic referral line, not a product | see §6 | Medium |
| 6b | White-label "AI outbound for vertical X" | (new) | **KILLED as a primary pivot; WEAKENED as a side pilot** | **2.5** (pivot) / **3.5** (narrow pay-per-result pilot) | Medium-high |

**The thesis, restated after verification.** "Turn the website business into an agent-run SMB back office / growth platform" overstates what the evidence supports. The supported version is narrower: **a retention bundle**, i.e. website + care + reviews/GBP, plus one segment-specific add-on.

For the customers who take it, that bundle roughly doubles revenue per customer and cuts their churn by about a third (Vendasta: about 4.9% → about 3.0%/mo). That is valuable, but across the whole base it adds only about $20–40/mo per customer (N × $18–39 in the §6 math). The well-funded "platform" incumbents are not winning big at this:
- Thryv: 95K SaaS clients, 29% on 2+ products, seasoned NRR down to 90%.
- Vendasta: 250+ white-label products.
- GoDaddy Airo.

The brothers should not plan to beat them on breadth. The constraint on the business is still **N** (new website customers), so the outbound engine stays the most valuable asset, used for their own acquisition.

---

## 1. Upsell economics for website/agency SMB customers

**Verdict: CONFIRMED in direction, WEAKENED in magnitude. 5.0 as strategy.**

### Evidence: attach and ARPU expansion at scaled web-presence vendors

| Company | What the data shows | Source |
|---|---|---|
| **GoDaddy** | ARPU $250 TTM (+8.7%) with customers flat at 20.5M. Applications & Commerce +11% vs Core +3.9%; A&C is about 40% of revenue at 46.8% EBITDA margin. Retention about 84% overall, about 87% on its own platform, about 90% at 3+ years' tenure. Over 89% of revenue comes from prior-year customers. Only about 9% of customers spend more than $500/yr. | [Q2'26 8-K](https://www.sec.gov/Archives/edgar/data/0001609711/000160971126000087/gddyex991-20260630xq2earni.htm), [FY24 10-K](https://www.sec.gov/Archives/edgar/data/1609711/000160971125000023/gddy-20241231.htm), [webhosting.today](https://webhosting.today/2026/07/31/godaddy-q2-2026-more-revenue-from-the-same-customers/) |
| GoDaddy Airo | $50M annualised bookings; "over 70% of Airo users have 2+ products". This group is self-selected, so it is not an attach rate. | [GuruFocus call notes](https://www.gurufocus.com/news/8993570/godaddy-inc-gddy-q2-2026-earnings-call-highlights-airo-surges-5x-to-50m-arr-driving-record-margins-and-free-cash-flow) |
| **Wix** | Partners revenue (agencies, B2B) $213.8M, +17%, about 38% of revenue. Collections per subscription +14% while premium subs fell about 74K. NRR about 105% in 2025. | [Q2'26 release](https://www.sec.gov/Archives/edgar/data/1576789/000162828026052108/secondquarter2026results.htm), [MVC](https://mvcinvesting.substack.com/p/wix-wix-q4-2025-earnings-review) |
| **Squarespace** | Last public ARPUS $225–227 (+3–7%) from "commerce attach". Went private in Oct 2024; Acuity/email attach was never disclosed. | [8-K Aug 2024](https://www.sec.gov/Archives/edgar/data/1496963/000149696324000070/sqsp-08022024x8kexhibit991.htm) |
| **Thryv** | 95K SaaS clients, ARPU $394/mo, **seasoned NRR 90% (down from 93%)**, **29% on 2+ SaaS products (28% a year earlier)**. Seeds-to-SaaS: 83% of 2024 converts and 75% of 2025 converts were still active at year end. | [Thryv Q2'26](https://investor.thryv.com/news/news-details/2026/Thryv-Reports-Second-Quarter-2026-Results-and-Launches-Thryv-Growth-Platform/default.aspx), [MarketBeat](https://www.marketbeat.com/instant-alerts/thryv-q2-earnings-call-highlights-2026-08-04/), [10-K](https://www.sec.gov/Archives/edgar/data/1556739/000155673926000013/thry-20251231.htm) |
| **LocaliQ (USA TODAY Co.)** | About 12,200 customers (**−12% YoY**) at a record $2,908/mo ARPU. Budget retention about 95–96%, which I read as about 4%/mo budget churn. | [Q2'26 transcript](https://www.fool.com/earnings/call-transcripts/2026/08/13/usa-today-tday-q2-2026-earnings-call-transcript/), [Investing.com](https://www.investing.com/news/company-news/gannett-q3-2025-slides-digital-revenue-nears-50-milestone-amid-overall-decline-93CH-4320533) |
| **Yelp** | Paying ad locations −3% in 2025 while revenue per location hit a record. It never discloses absolute churn. | [Yelp 10-K](https://www.sec.gov/Archives/edgar/data/1345016/000134501626000019/yelp-20251231.htm) |
| **Newfold / Web.com** | S&P estimates more than 1M subscribers lost (about 17%) since 2023. Web.com was folded into Network Solutions. | [webhosting.today](https://webhosting.today/2026/01/30/sp-global-believes-that-newfold-lost-over-1-million-subscribers-roughly-17-since-2023/) |
| **Weave / Yext** | Weave GRR 89% / NRR 92% (about 0.95%/mo gross churn). Yext direct NRR 92%; customers under $50K ARR are at 69% dollar retention (verify-5). | [Weave](https://uk.finance.yahoo.com/news/weave-communications-inc-weav-q2-050728310.html), [Yext 10-K](https://www.sec.gov/Archives/edgar/data/1614178/000161417825000030/yext-20250131.htm) |
| Hibu, Podium, Birdeye | No usable public attach or churn data (private). | — |

**The pattern across the table.** The winners grow ARPU on a flat or shrinking customer count: GoDaddy, Wix, LocaliQ and Yelp. Upsell *does* expand ARPU. But even companies with sales teams of thousands get **about 29% multi-product penetration** (Thryv), and NRR is *below* 100% at Thryv, Weave and Yext. On average, upsell slows decline rather than compounding.

### Evidence: churn by service at agencies

**Vendasta churn study** (about 100K SMB accounts) — the best multi-product data ([MarTech](https://martech.org/report-key-to-smb-advertiser-retention-is-onboarding-engagement-and-early-upselling/), [Vendasta](https://www.vendasta.com/blog/vendasta-client-churn-study/)):

| Products held | 2-year retention | Implied monthly churn (est.) |
|---|---|---|
| 1 | 30% | about 4.9% |
| 2 | 48% | about 3.0% |
| 3 | 50% | about 2.8% |
| 4 | 78% | about 1.0% |

- 62% of clients not upsold within 3 months churned within 2 years.

**Focus Digital 2026** (no stated n, so indicative) — monthly churn by service and by contract model ([Focus Digital](https://focus-digital.co/average-marketing-agency-churn/)):

| By service | Monthly churn | By contract model | Monthly churn |
|---|---|---|---|
| Full-service | 2.1% | Retainer | 1.6% |
| Content | 2.9% | Hybrid | 2.5% |
| SEO | 3.2% | Performance | 3.1% |
| Email | 3.4% | Project | 4.2% |
| Social | 3.8% | | |
| PPC | 4.1% | | |

- Agencies with 1–10 staff: about 32% annual churn.

**Other agency data**
- **Admin Bar 2026** (622 WordPress agencies, median team size 1): 58.3% of agencies with 0% recurring revenue are rarely or never profitable, versus under 10% for agencies with 25%+ recurring ([Admin Bar](https://theadminbar.com/2026-survey/)).
- **Unsourced claim:** "85% vs 52% care-plan retention", widely quoted as ManageWP 2024, could not be traced to a primary source. **Do not use it.**
- **LSA 2016:** SMB marketing agencies churn 40–50% a year ([Localogy](https://www.localogy.com/2019/09/churn-busting-best-practices-for-small-business-advertiser-retention/)).

### What retains best (ranked, est.)
1. **Hosting/website care:** about 1–1.5%/mo. It is infrastructure, and switching is painful.
2. **Reviews/listings software-plus-service:** about 2–3%/mo.
3. **SEO:** about 3%/mo.
4. **Social:** about 3.5–4%/mo.
5. **PPC and performance lead-gen:** about 4–5%/mo. Results-tied products churn the fastest.

### Planning numbers for the brothers (est.)
- 12-month attach to **any** recurring second product: **20–35%**. 50% is top-quartile, not plan.
- Attach to any **single** add-on in an in-product/email offer: **8–15%** in year 1. This matches verify-5's 10% kill gate and L12's 5–15% assumption.
- **Retention is a real but secondary benefit.** Moving a customer from 1 product to 2 cuts monthly churn from about 4.9% to about 3.0% (Vendasta). Expected life goes from about 20 to about 33 months, so a $75/mo core line earns about $975 more per upgraded customer. That is useful, but smaller than the add-on's own revenue (about $4K over the same life at $129/mo).
- **Timing:** the upsell must land **within 90 days of site launch**. Build it into onboarding, not a later campaign.

**What would kill item 1:** the brothers' customers mostly pay a one-time site fee with no monthly hosting/care relationship. Then there is no "existing customer channel" to sell into, and every upsell is a cold re-sell. *Check this first: what % of the current base pays monthly?*

---

## 2. Technology-advisor (TSD) residual book

**Verdict: WEAKENED, 5.0 → 3.5. Energy brokerage: KILLED without per-state licensing (1.5).**

### How residuals actually work

**Advisor split**
- Entry-level agents historically get 60–70% of the supplier commission and top tiers 75–80%; competitors offer up to 85% ([LinkedIn, Telarus exec](https://www.linkedin.com/pulse/telarus-secret-sauce-revealed-5-ways-we-double-our-agents-edwards)).
- An MSP reports keeping 80% of a 25% supplier commission at Sandler. A Chicago IT firm found the master-agent route better until it reached "$100k+ in new deals per year" ([Lawrence Systems forum](https://forums.lawrencesystems.com/t/anyone-have-any-experience-with-sandler-partners/2107)).
- Avant, Intelisys, AppDirect and Bridgepointe do not publish splits. The norm is 70–85% (est.).

**Supplier commission**
- Usually 15–20% of MRC (8–25% across programs). It is paid on MRC net of taxes, USF, E911, surcharges and install fees.
- Durations vary from 12–36 months with sunsets to evergreen ([rev.io](https://www.rev.io/blog/telecom-agent-commissions), [voip-int](https://voip-int.com/blog/voip-international-blog-posts-4/telecom-agent-programs-how-commissions-actually-work-and-where-the-catch-hides-276)).

**Spiffs are not for small deals** ([April 2025 spiff sheet](https://dcnxfkgt2gjxz.cloudfront.net/April-2025-SPIFF-Sheet-1.pdf)):
- Breezeline coax pays 1× MRC only at **$250+/mo on a 24-month term**.
- Consolidated spiffs start at **$1,000+ net-new MRR**.
- Dynalink pays "after the 2nd invoice".
- Rich spiffs (3–10× MRC) are concentrated in UCaaS (IPFone, Coeo, Dialpad).
- Comcast and Spectrum pay one-time bounties, not residuals (L15).

**Chargebacks and timing**
- Clawback windows run up to about 12 months ([rev.io](https://www.rev.io/blog/telecom-agent-commissions), [WDG](https://www.wirelessdealergroup.com/post/residuals-chargebacks-spiffs-how-telecom-commissions-work)).
- The first residual arrives about **60–120 days after install** (est.: supplier invoice → TSD → advisor).

**Commission trend: down**
- RingCentral cut 1 point and Dialpad cut 2 points on new sales ([Channel Playbook](https://channelplaybook.com/telecom/who-is-cutting-commissions/)).
- Comcast unified its channel commission tiers after integrating Nitel in 2025 ([Comcast](https://business.comcast.com/about-us/press-releases/2025/cb-and-nitel-announce-channel-sales-integration)).

### Small-SMB math (est.)

| Product | Customer MRC | Advisor residual | Spiff |
|---|---|---|---|
| Cable/coax internet | $100 | about $8–16/mo | usually none |
| 10-seat UCaaS | about $300 | about $40–55/mo | 1–5× possible |
| Merchant processing, $15–30K/mo volume, 50% split | — | about $15–40/mo | about $450 average upfront (vendor) |
| Realistic bundled customer | — | **about $30–100/mo** | — |

- Merchant figures come from [CCSalesPro](https://www.ccsalespro.com/blog/much-residual-can-make-selling-merchant-services-merchant-services-sales-commission) and [residualsforsale](https://www.residualsforsale.com/guides/how-merchant-residuals-work/).
- The bundled-customer residual loses 10–25% of accounts a year to merchant attrition.
- Worked example: $1,000 MRR × 20% × 80% = **$160/mo**. Most of the brothers' customers will be at a tenth of that.

### Who succeeds and saturation
- **Market:** $16.6B of TSD billings in 2024. The top 6 hold 72.3% (Telarus $2.9B, Intelisys $2.7B, Avant $2.1B, AppDirect $2.0B, Sandler $1.4B, Bridgepointe $755M). 86% of partners are tech advisors; only 4% are MSPs ([Omdia](https://omdia.tech.informa.com/blogs/2026/jan/key-insights-from-the-16point6bn-dollars-technology-services-distribution-tsd-market)).
- **Ownership:** the industry is PE-consolidated: Avant/Pamlico + Court Square, Bridgepointe/Charlesbank + Carlyle, ScanSource→Intelisys + Resourcive, AppDirect→TBI ([Channel Dive](https://www.channeldive.com/news/bridgepointe-recapitalization-investment-the-carlyle-group-charlesbank/817010/), [ScanSource](https://www.scansource.com/about/press-releases/2024/scansource-acquires-resourcive), [AppDirect](https://www.appdirect.com/blog/appdirect-acquires-tbi)).
- **Who wins:** long-tenured advisors with mid-market books, and MSPs that pair with advisors on managed services ([MSP Summit](https://themspsummit.com/article/agents-ponder-the-future-of-the-technology-adviser-model/), [Channel Futures](https://www.channelfutures.com/channel-sales-marketing/how-tech-advisors-are-driving-sales-for-these-13-msps)).
- **SMB tickets:** small deal size is named as the channel's weakness (Omdia).
- **Saturation:** the channel isn't saturated for *mid-market*. For the brothers' micro-SMB base, the economics, not the competition, are the problem.

### Legal: energy brokerage
| State | Requirement | Source |
|---|---|---|
| **TX** | PUCT broker registration under PURA §39.3555 for anyone paid for brokerage. $0 fee, renew every 3 years. OPUC is pushing audits and disclosure of all compensation (Docket 57999). | [PUCT form](https://ftp.puc.texas.gov/public/puct-info/industry/electric/forms/brk/brk_form.pdf), [Energy Choice Matters](http://www.energychoicematters.com/stories/20250711a.html) |
| **IL** | ICC ABC certificate (220 ILCS 5/16-115C; electricity). 90–180 days, cannot be expedited. $5,000 bond. **Signed pre-contract disclosure of total price including broker fees.** | [ICC FAQ](https://www.icc.illinois.gov/downloads/public/abc/ABC%20Certification%20FAQ.pdf), [ILCS](https://ilga.gov/legislation/ilcs/fulltext.asp?DocName=022000050K16-115C) |
| **PA** | PUC broker/marketer license. $350 fee + $10,000 bond/LOC, per-utility approval. | [PA PUC](https://www.puc.pa.gov/electric/pdf/EGS_Licen_app.pdf) |
| **OH** | PUCO power broker/aggregator certificate (2-year term), plus utility registration (AEP $356). | [PUCO](https://dis.puc.state.oh.us/ViewImage.aspx?CMID=A1001001A22G07B20036H00372), [AEP Ohio](https://www.aepohio.com/company/about/choice/cres/power-broker) |
| NY | $500/yr + **$100K irrevocable LOC** (brokers) | [NY DPS](https://dps.ny.gov/energy-broker-and-energy-consultant-registration) |

- **Sub-agent loophole:** the claim that sub-agents can "ride" a licensed broker's licence comes from a broker selling an agent program ([Diversegy](https://diversegy.com/energy-brokers/energy-broker-license/)).
- The TX and IL statutes cover anyone *compensated* for brokerage. Assume your own registration is needed unless counsel says otherwise (est.).
- **Do not include energy in an automated upsell.**

### Revised view
Run the telecom/merchant referral as an opportunistic line: the agent flags a bill on request, then hands it to a TSD-backed partner. Conversion is about 3–10% of the base per year (est., no public data) at about $40/mo. That gives about **$150–400/mo of new residual per 100 customers per year**, with a 2–4 month lag and clawbacks. It is a nice-to-have, not a pillar.

**Score 3.5.** It loses 1.5 points because the spiff and minimum structure excludes micro-SMB deals, the lag is long, and commissions are being cut.

---

## 3. Manufacturer co-op claim management

**Verdict: WEAKENED. Standalone claim desk ≈ KILLED (2.5); co-op-eligible retainer for brand dealers holds at 4.0–5.0 within that segment.**

### Who already does it, and at what price
| Player | Model / price | Source |
|---|---|---|
| Contingency claim agencies (generic) | **15–25% of reimbursement**. Dealer's own labour estimated at $800–2,400 per claim; minimum viable claim $2–5K. | [Dealer1](https://www.dealer1solutions.com/blog/the-oem-co-op-claim-money-your-dealership-might-be-leaving-on-the-table-and-why-) |
| COOPABLE (auto) | **$1,000 / $1,250 / $1,500 per month** retainer (reports → claim submission → pre-approvals) | [coopable](https://coopable.com/co-op-packages/) |
| CoopReclaim (HVAC, 5–30 staff) | **$99/mo** planned, free in early access. Prepares the packet; the contractor files it. | [coopreclaim](https://coopreclaim.com/) |
| Motivated Marketing (auto) | Unpublished; claims "$50M+ managed" | [motivatedmarketing](https://motivatedmarketing.com/services/co-op-management/) |
| Co-op Connect | About 8,000-plan database + "Concierge" (balances, pre-approvals, invoices). Sold mainly to media companies and agencies; price not public. | [coopconnect](https://coopconnect.com/co-op-services/co-op-database/) |
| Ansira (absorbed Brandmuscle, SproutLoud) | **Brand-side** co-op/MDF administration, paid by the manufacturer. Brand-side processing costs about $16 per claim. | [Brandmuscle](https://www.brandmuscle.com/), [SproutLoud](https://sproutloud.com/blogs/the-7-failure-points-of-co-op) |
| PowerChord, Dealer Spike / LeadVenture, ARI, Surefire Local, MTA360 | OEM-sanctioned platforms and **approved vendors** with co-op built in | [PowerChord](https://www.powerchord.com/powersports-dealer-marketing), [LeadVenture](https://www.leadventure.com/resource/maximizing-oem-co-op-funds/), [Bryant](https://adkit.bryant.com/en/us/guidelines/co-op-guidelines) |
| HVAC agencies (RevLocal, MPW, etc.) | Bundle claims free with paid marketing (L13) | L13 |

### How much co-op goes unspent
- **Headline figures are recycled and old.** LSA 2016 gives $14–35B unclaimed of a $36–70B pool ([Inside Radio](http://www.insideradio.com/free/there-s-b-in-unused-co-op-dollars-and-a/article_914e44d6-df89-11e5-ba6e-3b3112f14e2d.html)). Borrell 2015 says only 15% of local advertisers use co-op ([MarTech](https://martech.org/report-billions-in-co-op-advertising-funds-left-unspent-each-year/)). Vendor sources say about 50–60% of available funds are claimed. **No primary study has been published since 2016.**
- **Counter-evidence.** Franchised auto dealers: 99% participate and use "almost 100%" of new-car co-op ([DemandLocal](https://www.demandlocal.com/blog/co-op-fund-utilization-statistics/)). The unspent pool sits with *small, multi-brand, non-auto* dealers. That is also where accruals are smallest.
- **Per-dealer amounts.** Anecdotes include $13K, $18K and $27K ([Powersports Business](https://powersportsbusiness.com/news/dealers/2025/08/28/making-the-most-of-your-oem-co-op-program/), [MPN](https://www.motorcyclepowersportsnews.com/breakdown-oem-co-op-changes-2026/)). A typical small HVAC or powersports dealer accrues about **$5–30K a year** (est.).
- **Use-it-or-lose-it.** Pre-approval is standard and windows are short:
  - Carrier: 1.5–2% accrual, requests within 60 days, Dec 15 cutoff ([Carrier 2026](https://resource.carrierenterprise.com/is/content/Watscocom/ce_ca_carrier-program-benefits_pdf_20260304_2026_Co-Op_AdvertisingPolicy_Carrier-Janpdf)).
  - Rheem: 1% of purchases, portal closes Dec 8 ([Rheem](https://rcn-emails.s3.amazonaws.com/template/2025/03/16/2025-co-op-program-guide-rh.pdf)).
  - CFMOTO: funds expire May 7.
  - **Retroactive "found money" is mostly unavailable**, as L13 itself found.

### Is the website itself co-op-eligible?
- **Carrier/Bryant (US):** site build, **hosting, SEO and annual support are eligible**. Conditions: pre-approval, an SEO plan submitted in advance, a prominent brand logo, and that brand's products only ([Bryant](https://adkit.bryant.com/en/us/guidelines/co-op-guidelines)).
- **Carrier Canada 2026:** *"URL, hosting and maintenance fees are not eligible"*. Funds are clawed back if the site stops being Carrier-exclusive within 12 months.
- **Trane:** prorated by the share of the site devoted to HVAC. **Rheem:** a website is a precondition, not a claimable item.
- **Agency fees:** eligible on media at Carrier/Bryant, capped at 17% of media and shown as a separate line.
- **Claim-preparation fees:** not listed as eligible anywhere I read.

### Approved-vendor lock-in (the structural killer)
- **Yamaha:** pays 70% vs 40% only through **3 approved agencies**.
- **Honda:** in-house Google Ads cannot be claimed (approved SEM vendors only).
- **Kawasaki:** one approved AI-website vendor.
- **Polaris:** Certified Web Program (Dealer Spike, PSXDigital).
- **Lennox:** preferred supplier network.
- Sources: [MPN](https://www.motorcyclepowersportsnews.com/breakdown-oem-co-op-changes-2026/), [LennoxPros](https://www.lennoxpros.com/partner-resources/preferred-suppliers), [PSX](https://psxdigital.com/polaris-partnership/).
- **Powersports is largely closed to a non-certified agency. HVAC (Carrier/Bryant/Trane) is the open door.**

### Revised view
- **Claim-fee economics:** about $1–7K per dealer per year at 15–25% of a $5–30K accrual. Competitors run from $99/mo to $1,000+/mo, and many agencies do it free with services.
- **Where it works:** a **co-op-eligible website + SEO retainer for HVAC dealers**. "Up to 50% of this is Carrier-funded" lowers net price, lifts close rate and raises switching cost.
- **Score: 4.0** across a mixed base, **5.0** if 10%+ of the brothers' customers are brand-carrying HVAC/OPE/appliance dealers.
- **First check:** what share of the existing base carries a national brand with a co-op program?

---

## 4. Reviews / GBP / AI-visibility retainer (re-check of verify-5)

**Verdict: CONFIRMED. 5.0, the strongest single upsell.**

**Price anchors (2026)**
- **Review software:** NiceJob $75/mo, GatherUp $99/mo (single location), BrightLocal Grow $59/mo, Birdeye about $299/mo, Podium about $399–599/mo ([Valley Marketing](https://thevalleymarketinggroup.com/blog/podium-vs-birdeye-vs-nicejob-review-management-2026/), [reviewdrop](https://www.reviewdrop.co/blog/best-review-management-software-small-businesses-2026)).
- **Managed GBP retainers:** $125–400/mo per location; full Map Pack management $800–1,200 ([Merchynt](https://www.merchynt.com/post/google-my-business-management-pricing)).
- **What this means:** verify-5's done-for-you **$79–129** "Reviews + GBP + Citations" plan sits between DIY software and agency retainers. That is the right gap for an agent-run service.

**Retention**
- Reviews/listings software churns about 2–3%/mo (est. from §1).
- It is a *second* product, which on Vendasta data moves the customer from about 4.9% to about 3.0% monthly churn.

**New risk since verify-5**
- **The FTC Consumer Review Rule (16 CFR 465)** has been in force since Oct 2024. Warning letters went to 10 companies in Dec 2025, and penalties run up to $53,088 per violation ([Arnold & Porter](https://www.arnoldporter.com/en/perspectives/blogs/consumer-products-and-retail-navigator/2026/01/ftc-warning-letters-over-consumer-review-rule), [Benesch](https://www.beneschlaw.com/insight/five-stars-zero-tolerance-ftc-turns-up-enforcement-under-consumer-review-rule/)).
- Combined with Google's ban on selectively soliciting positive reviews, the agent must **ask every customer the same way**: no "happy? → Google, unhappy? → private form" gating, and no incentives tied to the review.
- Review texts to consumers also need 10DLC registration.
- This is a design constraint, not a kill.

**Verify-5's AI-visibility caveat stands.** API answers overlap only about 15–24% with what users see in the consumer UI, and ChatGPT names only about 1.2% of local businesses. Keep AI visibility as a disclosed *mention-rate* line in the report, not as the product.

---

## 5. Construction back-office bundle (L12 Idea 5)

**Verdict: WEAKENED, about 4.0 → 3.0 for a typical trades website base (4.0 only for a commercial-sub segment).**

**Who actually needs it.** The paperwork in the bundle belongs to *commercial* work: COIs, prelims/lien notices, certified payroll and prevailing wage, ISN/Avetta prequal.
- Over 85% of GCs and owners require COIs before work starts, but formal COI/endorsement regimes are a commercial-project feature ([getbusinesscoverage](https://www.getbusinesscoverage.com/learn/contractor-insurance), [Progressive Commercial](https://www.progressivecommercial.com/business-insurance/certificate-of-insurance-for-contractors/)).
- A business that buys a website from a "your website is bad" cold pitch skews to residential, consumer-facing micro-trades (est.). That is exactly the L12 kill risk.

**The pieces residential trades do need are already free or bundled**
- **COIs** are traditionally issued free by the broker/insurer. Charging for them is illegal in Florida. NEXT Insurance gives unlimited self-serve COIs in its app ([GetBCS](https://www.getbcs.com/blog/how-to-get-a-certificate-of-insurance), [NEXT](https://www.nextinsurance.com/certificate-of-insurance/)).
- **Field-service suites:**
  - Jobber offers an **AI Receptionist at $29–99/mo** and a Marketing Suite at $79 ([serviceharness](https://www.serviceharness.com/software/jobber)).
  - Housecall Pro includes an "AI team" on every plan ([serviceharness](https://www.serviceharness.com/software/housecall-pro)).
  - FSM adoption is about 71% among HVAC, plumbing and electrical contractors ([marketgrowthreports](https://www.marketgrowthreports.com/market-reports/home-services-management-software-market-118780)).
- **Licence and insurance renewal reminders:** worth about $20/mo (L12's own estimate).

**What survives.** A $199/mo "paperwork desk" for the subset of customers doing commercial/GC sub work (electrical, HVAC, roofing, concrete). Identify them from their site copy and job photos. Keep L12's kill gate: attach under 3% of trade customers, or more than 2 hours of human time per client per month.

**Do not lead the platform with it.**

---

## 6. Strategic question: ranking and the bundle

### Ranking of upsells (for a typical local-SMB website base)

| Rank | Upsell | Score | Why |
|---|---|---|---|
| 1 | **Website care/hosting plan** (if not already monthly) | — (prerequisite) | The stickiest line (about 1–1.5%/mo churn), and it creates the monthly relationship every other upsell needs |
| 2 | **Reviews + GBP + citations plan, AI-visibility reporting as the hook** ($99–149/mo) | **5.0** | Applies to almost every customer; deterministic value; tools wholesale at about $20–60; low legal risk if rule-compliant |
| 3 | **Co-op-eligible website/SEO retainer** for brand dealers ($500–900/mo, up to 50% OEM-funded) | **4.0** (5.0 in segment) | High ARPU but narrow; HVAC open, powersports largely closed |
| 4 | **Tech-advisor referral** (telecom/UCaaS/merchant, no energy) | **3.5** | Low effort as a referral; small residuals; 2–4 month lag |
| 5 | **Contractor paperwork desk** | **3.0** | Only the commercial-sub subset needs it |
| — | White-label AI outbound | **2.5** pivot / 3.5 pilot | See below |

### Proposed bundle

- **Core: "Local Presence Plan"** = care/hosting + reviews/GBP/citations + monthly visibility report, at **$129/mo**, or tiered at $79 care-only and $149 with reviews.
- **Segment add-on A, brand dealers:** co-op-funded marketing retainer.
- **Segment add-on B, everyone:** a bill-review referral offered once a year in the report.

### Math at N = 100, 500, 2,000 (est., steady state about 12 months after launch)

| Assumption | Base case | Downside |
|---|---|---|
| Reviews/GBP plan: attach, price, gross margin | 15% × $129 × 75% (tools about $25–35 + compute) | 8% |
| Brand dealers in base × attach to co-op retainer | 10% × 25% = 2.5% of N, at $700/mo × 60% GM | 5% × 20% = 1% of N |
| Tech-advisor conversions (cumulative yr 1) × residual | 5% of N × $40/mo × 90% GM | 2% |
| Retention uplift on core | Customers on 2+ products churn about 3.0% vs about 4.9%/mo (Vendasta) | — |

| | N = 100 | N = 500 | N = 2,000 |
|---|---|---|---|
| Reviews/GBP subs (base) | 15 → **$1,935/mo** | 75 → **$9,675/mo** | 300 → **$38,700/mo** |
| Co-op retainers (base) | 2.5 → **$1,750/mo** | 12.5 → **$8,750/mo** | 50 → **$35,000/mo** |
| Tech-advisor residual (base) | 5 → **$200/mo** | 25 → **$1,000/mo** | 100 → **$4,000/mo** |
| **Added MRR (base)** | **≈ $3.9K (≈ $47K ARR)** | **≈ $19.4K (≈ $233K ARR)** | **≈ $77.7K (≈ $932K ARR)** |
| Added gross profit/mo (base) | ≈ $2.7K | ≈ $13.4K | ≈ $53.6K |
| **Added MRR (downside)** | ≈ $1.8K (≈ $21K ARR) | ≈ $9.1K (≈ $109K ARR) | ≈ $36.3K (≈ $436K ARR) |
| Human load (about 0.5 hr/mo per review sub; about 3 hr/mo per co-op retainer) | about 15 hr/mo | about 75 hr/mo | about 0.3 FTE + 150 hr/mo co-op ≈ 2 FTE |

**Retention dividend (base case, est.).** Suppose about 20% of the base moves from 1 to 2+ products, and the core site/care line is worth about $75/mo. Cutting churn on that cohort from about 4.9% to about 3.0%/mo saves about 0.4% of N per month (0.2 × 1.9%).
- **N = 500:** about 2 customers a month, so about $140/mo of core MRR saved per month, or about $1.5–1.7K/mo after a year.
- **N = 2,000:** about $6–7K/mo after a year.
- This is a real but secondary effect. The add-on revenue in the table is the main prize. The retention gain mainly makes that revenue last longer, and it makes add-on buyers the best-retained cohort.

**Reading the math**
- **N = 100:** a side project (under $50K ARR). Do it because it protects the core, not as a business.
- **N = 500:** a real second line (about $110–230K ARR) that one founder can run with agents.
- **N = 2,000:** about $0.4–0.9M ARR plus a meaningful retention dividend.
- **Implication:** every scenario is dominated by N. The engine that wins *new website customers* is worth more than any upsell. The bundle should be built *into the acquisition offer* (site + Local Presence Plan from day one, the 90-day rule) rather than sold later.

### Should they instead white-label the outbound engine ("AI outbound for vertical X")?

**Verdict: KILLED as the primary pivot (2.5); a narrow pay-per-result pilot rates 3.5.**

**Pricing is collapsing toward commodity**
- **AI SDR tools:** AiSDR about $900/mo, Salesforge $599–900, Amplemarket about $1,500/user, 11x about $40–60K/yr, Artisan about $1.5K/mo+ ([marketbetter](https://marketbetter.ai/blog/best-ai-sdr-tools/), [whitespace](https://www.whitespacesolutions.ai/content/ai-sdr-pricing-guide-2026)).
- **Sending infrastructure:** Instantly from $37 and Smartlead from $39, with Smartlead white-label at $29 per client per month ([Instantly](https://instantly.ai/blog/ai-reply-agent-pricing-for-agencies/), [miniloop](https://www.miniloop.ai/blog/smartlead-pricing)).
- **Done-for-you agencies:** $2.5–5K/mo retainers or $150–600 per meeting ([SalesHive](https://saleshive.com/blog/lead-generation-services-what-should-they-cost), [intentsignal](https://intentsignal.ai/content/cold-email-agency-pricing)).
- **White-label AI setters for agencies:** about $29–2,000/mo (CloseBot $397, Ringlyn $2,497) ([Ringlyn](https://www.ringlyn.com/blog/white-label-ai-services-2026/)).
- **The brothers' specific angle (demo site built before outreach) is already a cheap tool category:**
  - Apify demo-site generator: **$105 per 1,000 demo sites**.
  - MyLeadBots: $9–99/mo.
  - ClaimSite: $49–199/mo.
  - SiteSwan: "live demo sites in minutes" for resellers.
  - Sources: [Apify](https://apify.com/sebastian_elustondo/local-business-demo-site-generator), [MyLeadBots](https://myleadbots.com/), [Indie Hackers](https://www.indiehackers.com/post/i-built-a-tool-that-generates-a-live-website-for-a-local-business-before-you-contact-them-qoZTIOY6f8DC83FRfxmP), [SiteSwan](https://www.siteswan.com/reseller-opportunity).

**Churn is the category's defining problem**
- **11x:** most early customers used 3-month break clauses but were counted in ARR ([TechCrunch](https://techcrunch.com/2025/03/24/a16z-and-benchmark-backed-11x-has-been-claiming-customers-it-doesnt-have/)).
- **Artisan:** admits "relatively high churn" for first-gen AI SDRs ([TechCrunch](https://techcrunch.com/2025/04/09/artisan-the-stop-hiring-humans-ai-agent-startup-raises-25m-and-is-still-hiring-humans)).
- **Performance-based agencies:** 3.1%/mo churn vs 1.6% for retainers ([Focus Digital](https://focus-digital.co/average-marketing-agency-churn/)).

**The channel itself is degrading**
- **Reply rates:** cold-email reply rates fell to **3.43%** on average in 2025 data ([Instantly 2026](https://instantly.ai/cold-email-benchmark-report-2026)). Belkins measured 6.8% in 2023 and 5.8% in 2024 ([Belkins](https://belkins.io/resources/b2b-cold-outreach-benchmarks)).
- **Gmail:** enforcement moved to permanent rejections in Nov 2025 ([Red Sift](https://redsift.com/blog/gmails-enforcement-ramps-up-what-bulk-senders-need-to-know)).
- **Microsoft:** rejects non-compliant senders of 5K+ a day since May 5, 2025 ([Microsoft](https://techcommunity.microsoft.com/blog/microsoftdefenderforoffice365blog/strengthening-email-ecosystem-outlook%E2%80%99s-new-requirements-for-high%E2%80%90volume-senders/4399730)).
- **Saturation:** the more AI SDRs, the worse the channel. About 44% of B2B teams now use them ([LinkedOtter](https://www.linkedotter.com/articles/ai-sdr-44-percent-b2b-sales-adoption-june-2026)).

**Legal exposure gets multiplied**
- **CAN-SPAM:** both the sender and the promoted business can be liable, at up to $53,088 per email ([FTC](https://www.ftc.gov/business-guidance/resources/can-spam-act-compliance-guide-business)).
- **California B&P §17529.5:** a private right of action at $1,000 per email, with an active class-action wave ([Crowell](https://www.crowell.com/en/insights/client-alerts/report-as-spam-a-new-wave-of-california-anti-spam-class-actions-raises-significant-risks-for-email-marketers)).
- **Canada (CASL) and UK sole traders:** consent is required ([salespeople.co.uk](https://www.salespeople.co.uk/explained/cold-email-pecr-regulation-22)).
- **White-label effect:** sending for dozens of clients puts the brothers' domains and liability behind every client's claims.

**Unit math (est.)**
- **Target:** $20K MRR at $1,000 per agency client means 20 clients.
- **Churn:** at 6–8%/mo, about 1.2–1.6 replacements a month just to stand still.
- **Acquisition:** clients are bought through the same degrading cold-email channel, from buyers (agencies) who are themselves outbound-savvy and price-sensitive.
- **Comparison:** compare this with an existing website customer who already trusts them, buys at about $0 CAC and churns at 1–3%/mo.

**The one counter-example points the other way.** Owner.com (about $81M ARR, $1B valuation, 10K+ restaurants) won by **owning SMB customers in one vertical** with website + marketing. It did not sell outbound as a service ([Restaurant Business](https://www.restaurantbusinessonline.com/technology/tech-supplier-ownercom-raises-120m-giving-it-1b-valuation)).
- **What follows:** go vertical with their own customers, not horizontal as a vendor to other agencies.

**If they test it anyway**
- **Shape:** one vertical, pay-per-qualified-meeting or per-site-sold, 2–3 pilot agencies, a 60-day cap.
- **Kill if:** client churn exceeds 10%/mo, or any pilot's spam-complaint rate exceeds 0.1%.

---

## 7. Bottom line for the project

1. **The "upsell to existing customers" finding survives**, but it is a **retention-and-ARPU multiplier on N**, not a new business. At N = 100 it is worth under $50K ARR; at N = 500, about $110–230K; at N = 2,000, about $0.4–0.9M.
2. **Reframe from "SMB back-office platform" to "Local Presence Plan, sold at site launch".** The breadth platform is Thryv's and Vendasta's game, and their own numbers (29% multi-product, NRR around 90%) show how hard it is.
3. **Downgrades**
   - Tech-advisor 5.0 → 3.5 (energy killed).
   - Co-op 4.5 → 4.0 (HVAC dealers only).
   - Back-office 4.0 → 3.0.
   - White-label outbound 2.5.
4. **Kept:** reviews/GBP at 5.0.
5. **Three checks before building anything**
   1. What % of the current base pays monthly? If under about 50%, fix that first.
   2. What % carry a national brand with co-op?
   3. What % do commercial/GC sub work?

   These three numbers decide which add-on, if any, goes beyond the core plan.
6. **Kill gates**
   - Reviews/GBP: under 10% attach within 60 days of offer (verify-5).
   - Co-op: fewer than 5 of the first 20 dealer customers have $2K+ of unspent current-period accrual (L13).
   - Paperwork desk: under 3% attach (L12).
   - Tech-advisor: no residual received within 150 days of the first signed order.
