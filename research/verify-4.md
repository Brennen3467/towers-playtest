# Verify-4: Adversarial verification of five candidate ideas

*Verification date: 2026-10-01. Research only: no emails, signups, outreach, purchases or claims were made.*

**Ideas checked**
- Medicare Enrollment Guard (from 06-healthcare #2)
- Rate Gap Report (from 06-healthcare #1)
- New Practice Radar (from 10-intent-signals #1)
- Pro-se trademark OA feed (from 08-legal-ip #1)
- B2B unclaimed-property sweep via CPAs (from 08-legal-ip #2)

**Method**
- I pulled each original write-up from its branch with `git show origin/research/<branch>:research/<file>.md`.
- I re-checked the claims independently: direct calls to the CMS data APIs, the full September 2026 Revalidation Due Date List (2,943,135 rows), the NPPES weekly file for 21–27 Sep 2026, a live sample of 200 TSDR records, and statute text (CCP 1582, NY ABP 1416, Tex. Prop. Code 74.507, Fla. Stat. 717.135/.1322/.1400, 37 CFR 11.702–703, 39 USC 3001, CA B&P 5061).
- I used roughly 175 web searches across the batch.
- Where a page blocked fetching (AMA, the CA SCO download page, MissingMoney), the claim is cited from search snippets and flagged as such.

---

## Summary

| Idea | Original score | Verdict | Revised score (confidence) | One-line reason |
|---|---|---|---|---|
| Pro-se TM office-action feed | 6.6 | **WEAKENED** | **4.5** (medium) | The data is real and pro-se emails are public. But the channel is poisoned by scams, the raw data costs about $3 per 1k, and the buyer base is tiny and concentrated. |
| B2B unclaimed property via CPAs | 6.2 | **WEAKENED** | **4.0** (medium) | The 50/50 contingency split is barred or restricted in FL, TX and CA, and for attest clients under AICPA rules. The median claim is $100. |
| Medicare Enrollment Guard | 6.3 | **WEAKENED** (address-mismatch feature **KILLED**) | **3.5** (medium-high) | The public files have no addresses, so the mismatch check cannot be computed. CMS already alerts by 2 letters and 2 emails. Shared PECOS logins are prohibited. |
| Rate Gap Report | 6.4 | **WEAKENED** | **3.5** (medium) | "Nobody sells this at small-practice prices" is false: MGMA Rates, PayerPrice, the Turquoise free tier and Rivet all do. CMS-9882 would commoditize the ghost-rate filter. |
| New Practice Radar | 6.5 | **WEAKENED** (near KILLED) | **3.0** (medium) | Actable already sells a "Practice Radar" for $39/mo. 72% of billing firms grow by referral. The pool is dominated by solo therapists. |

Nothing in this batch is killed outright. But no idea survives at its original score, and none reaches 5.

---

## 1. Medicare Enrollment Guard (06-healthcare #2)

**Verdict: WEAKENED. The address-mismatch differentiator is KILLED. Revised score: 3.5/10 (original 6.3), confidence medium-high.**

### Claims checked

| Original claim | Finding | Source | Holds? |
|---|---|---|---|
| "CMS will send the notice to an address that doesn't match your NPPES record" (address mismatch computed from public data) | **Cannot be computed.** The Revalidation Due Date List has 13 fields and **no address**. The PPEF API has 11 fields (NPI, PAC ID, enrollment ID, type, state, name) and no address. Doctors & Clinicians has only the practice location. Notices go to the PECOS correspondence and special-payments addresses and the correspondence email, none of which is published. | API pulls: [Revalidation](https://data.cms.gov/data-api/v1/dataset/3746498e-874d-45d8-9c69-68603cafea60/data?size=3), [PPEF](https://data.cms.gov/data-api/v1/dataset/2457ea29-fc82-48b0-86ec-3b0755de7515/data?size=3), [D&C](https://data.cms.gov/provider-data/api/1/datastore/query/mj5m-pzi6/0?limit=1); [Noridian revalidation](https://med.noridianmedicare.com/web/jfb/enrollment/revalidation) | **No (killed)** |
| "CMS itself mails notices 3–4 months ahead" | Understated. MACs send **two letters** (special-payments and correspondence addresses) and **two emails**, about 4 months and about 1.5 months out. CMS also publishes due dates 7 months ahead in a free lookup tool, and PECOS 2.0 adds in-portal notices. | [Noridian](https://med.noridianmedicare.com/web/jfb/enrollment/revalidation); [CMS revalidations](https://www.cms.gov/medicare/enrollment-renewal/providers-suppliers/revalidations); [CMS lookup tool](https://data.cms.gov/tools/medicare-revalidation-list) | Understated |
| "218,382 enrollments carry a dated due date" | **Reproduced exactly** (unique enrollment IDs). But 90.6% of the 2.94M rows are "TBD", and only 10,742 dated rows are individuals, so "linked clinicians" is mostly empty. | My analysis of [revalidation_base.csv](https://data.cms.gov/sites/default/files/2026-08/987d15c1-e213-488b-a817-b9d746b7b01d/revalidation_base.csv) | Yes |
| "About 6–8k per month going forward" | 5,616–6,167 unique forward-dated enrollments per month for Oct 2026–Feb 2027. Of the Oct–Mar rows: 18,075 Clinic/Group, 5,398 Pharmacy (chain-heavy, e.g. Walgreen Co), 2,428 mass immunizers, 653 PT. | Same file | Roughly |
| Past-dated 2023–25 rows "may indicate overdue" | 87% of dated rows (240,584) are before Oct 2026. Noridian says a due date "may continue to appear… until the application is fully processed." These are stale rows, not deactivated leads, so pitching them as at-risk would be a false claim. | [Noridian](https://med.noridianmedicare.com/web/jfb/enrollment/revalidation) | **No** |
| Done-for-you filing "with the practice's PECOS credentials" | **Prohibited.** I&A requires an individual account per user and bans shared logins. A surrogate can prepare an application but cannot sign it; the Authorized Official must sign. | [NPPES I&A FAQ](https://nppes.cms.hhs.gov/IAWebContent/FAQs.pdf); [PECOS surrogacy](https://healthcare.trainingleader.com/2021/05/pecos-login-surrogacy-designation) | **No** |
| Pain is real: ~10 2026 ALJ decisions upholding billing gaps | Confirmed: CR6947 (Anderson Township, 27 Jul 2026), CR6933 Chabot Urology, CR6906. But many deactivations come from **failing to answer development requests**, which a due-date alert does not fix. | [DAB CR6947](https://www.hhs.gov/about/agencies/dab/decisions/alj-decisions/2026/alj-cr6947/index.html) (via search snippet; page blocked) | Partly |
| "Crowding medium-low"; the Apify resale shows "others see the same opportunity" | Medallion tracks revalidation automatically. CredyApp sends 90/60/30-day alerts and Qualigenix sends 6/3-month alerts; Credential OS and Modio also track. The Apify actor has **2 users, 1 monthly active**, which is evidence of **no demand**, not of a race. | [Medallion](https://medallion.co/products/payer-enrollments); [CredyApp](https://credyapp.com); [Qualigenix](https://qualigenix.com/medicare-revalidation-2026); [Apify](https://apify.com/jserle/medicare-revalidation-due-leads) | **No** |
| Perception risk (kill risk #2) | Worse than stated. In Jan 2026 Noridian and CMS warned about **fraudulent mailed letters about Medicare enrollment** that use urgent language. | [CMA: fraudulent correspondence](https://www.cmadocs.org/newsroom/news/view/ArticleId/51100/Fraudulent-correspondence-targeting-Medicare-providers) | Understated |
| Legal list: SSA §1140, FTC, CAN-SPAM, TCPA | Missing **39 U.S.C. §3001(h)**, the Deceptive Mailings Prevention Act. A mailed solicitation that references a federal agency must carry "THIS IS NOT A GOVERNMENT DOCUMENT" plus the not-approved-by-the-federal-government notice, or it is nonmailable. Several states have government-lookalike solicitation analogues. | [39 USC 3001](https://codes.findlaw.com/us/title-39-postal-service/39-usc-sect-3001) | Incomplete |
| CAC $40–120; first dollar in 30–45 days | Healthcare cold-email reply rates are ≈0.56–0.6% (Belkins, 7.5M emails). 3,000 emails give about 18 replies, so perhaps 3–10 filings at $249. CAC works out to about $150–400 against a once-in-5-years sale. | [Belkins](https://belkins.io/blog/cold-email-response-rates) | **No** |

### New competitors and risks
- **Free CMS channels.** The lookup tool, the MAC letters and emails, and PECOS 2.0 already do the alerting.
- **Credentialing platforms.** Medallion, CredyApp, Qualigenix, Credential OS, Modio and Verifiable all track revalidations, and billing companies bundle enrollment work.
- **Signing rules.** The Authorized Official must sign, so the service can never be fully done-for-you.
- **Mailing law.** Compliance with 39 USC 3001(h) is required, plus the active MAC fraud warnings.
- **Prospect quality.** The pharmacy and immunizer rows are dominated by chains.

### What would make it viable
1. **Drop address mismatch entirely.** It cannot be computed.
2. **Sell to billing companies and MSOs, not practices.** Offer white-label NPI-roster monitoring at about $1–2 per NPI per month: due-date diffs, reassignment drift, Order & Referring status, opt-out and deactivation detection. These firms already hold surrogate access.
3. **Clean the prospect list.** Use only forward-dated rows (≤7 months) and exclude chains and hospital-owned groups.
4. **Reposition as prep plus development-request response, with the Authorized Official signing.** Charge more for complex DMEPOS/855S filings.

### Most likely failure
Recipients read the outreach as another "Medicare deadline" mailer in the same season that MACs are warning about fake enrollment letters, or they reply "our biller handles it." The free CMS letters and emails already did the alerting.

---

## 2. Rate Gap Report (06-healthcare #1)

**Verdict: WEAKENED. Revised score: 3.5/10 (original 6.4), confidence medium.**

### Claims checked

| Original claim | Finding | Source | Holds? |
|---|---|---|---|
| "Nobody sells this at small-practice prices." | **False.** Several tools already reach small practices free or cheaply: Turquoise's free "MRF Search" tier; PayerPrice's free explorer and free sample "your contracts vs. payer files" report, aimed at independent groups; **MGMA Rates (HexIQ)**, a member benefit with free 99202–99215 and 99232/3 negotiated rates; Strata PT's free PT payer benchmarks. | [Turquoise plans](https://turquoise.health/plans/providers); [PayerPrice](https://payerprice.com/blog/how-to-benchmark-reimbursement-rate); [HexIQ/MGMA](https://www.hexiq.com/mgma); [Strata PT](https://stratapt.com/benchmarks/payer-reimbursement-rates) | **No** |
| "Small-practice self-serve is thin: Rivet, MDClarity, Tribunus." | Rivet Benchmark targets derm, GI, ortho, ophthalmology, urology and billing consultants, from $6,000/yr. Trek Health raised an $11M Series A, has 130+ customers and launched Contract Intelligence in Sep 2025. | [Rivet Benchmark](https://www.rivethealth.com/rivet-benchmark); [Software Advice](https://www.softwareadvice.com/product/233932-rivet/); [Trek Health (BusinessWire)](https://www.businesswire.com/news/home/20250923635338/en/) | **No** |
| "TiC alone is about 95% noise." | Confirmed: 91.8% of rates and 95.4% of provider–code pairs are ghost rates. | [Health Affairs Scholar / PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC12631121/) | Yes |
| The TiC × Part B ghost-rate filter is the moat | Eroding. Proposed rule CMS-9882-P adds a Utilization File, removes unlikely provider–service rates and moves to quarterly files. It was not final as of 2026-10-01; once final, it applies ≥1 year later. Any filter built now gets commoditized around 2027–28. | [Federal Register 2025-23693](https://www.federalregister.gov/documents/2025/12/23/2025-23693) | Partly |
| Compute "$2–8k/month to stream-parse one state × 4–6 payers" | No primary support. Single files run 86 GB to 1 TB+ (UHC/UMR); one month of large-carrier files exceeds 100 TB compressed; single-object JSON defeats streaming parsers. Serif licensing at "from $1k/month" (2022) beats building. | [UMR MRF notice](https://www.umr.com/print/UMC0210.pdf); [Serif](https://www.serifhealth.com/blog/announcing-our-payer-price-transparency-analytics-portal-api) | Unverified / optimistic |
| "Here are *your* actual negotiated rates…" | Coverage is risky. UHC once dropped about 92% of in-network provider rates, including far fewer PT 97110 rates (the write-up's own example). A missing or wrong own-rate in a cold email is fatal to credibility. | [Serif on UHC walkback](https://www.serifhealth.com/blog/united-healthcares-massive-walkback-on-tic-data) | Risky |
| "82% of groups don't use TiC data" | Misstated. The MGMA poll (n=207) found 18% yes, **46% no, 36% unsure**. MGMA uses the stat to sell its own MGMA Rates product, which is a direct competitor. | [MGMA Stat](https://www.mgma.com/mgma-stat/using-tic-negotiated-rate-data-to-negotiate-payer-contrac) | Partly |
| AMA license ≈$18.50/user + $1,050 royalty; show "code numbers without descriptors" meanwhile | The fee figures match the AMA 2026 schedule per search snippet (the page is Cloudflare-blocked). **Code numbers alone are not a clean exemption.** CMS/AMA guidance still requires a copyright notice, and commercial distribution still falls under the AMA license. | [AMA 2026 schedule](https://compliance.ama-assn.org/hc/en-us/articles/15166274293399-Notice-Standard-CPT-Distribution-Pricing-Schedule-2026) (snippet); [CMS transmittal AB-01-18](https://www.cms.gov/regulations-and-guidance/guidance/transmittals/downloads/ab01182.pdf) | Fee yes; workaround no |
| PatientRightsAdvocate v. AMA is pending | Confirmed: filed 13 Aug 2026. No relief is plausible within a 90-day launch. | [Healthcare Dive](https://www.healthcaredive.com/news/patient-rights-advocate-sues-ama-cpt-billing-codes-copyright/827830/) | Yes |
| 2% paid conversion on 2,000 cold emails | **Not credible.** Belkins (7.5M emails) puts the average reply rate at 0.45% and healthcare at about 0.56–0.6%. Realistic paid conversion is about 0.05–0.3%, i.e. 1–6 sales per 2,000 emails. | [Belkins](https://belkins.io/blog/cold-email-response-rates); [Instantly](https://instantly.ai/blog/cold-email-reply-rate-benchmarks/) | **No** |
| CAC $50–250; break-even 60–100 customers per state | At 0.1–0.3% paid, CAC is about $100–600 before data. At $3–8k/month of pipeline cost per state, 5–16 report sales a month are needed just to cover data. | Derived from the rows above | **No** |

### New competitors and risks
- **MGMA Rates/HexIQ.** Sold through the association the buyer already pays, which makes it the most dangerous competitor.
- **Other direct competitors:** PayerPrice, the Turquoise free tier, Trek Health, Rivet Benchmark, Serif "Peer Rates", FAIR Health, and Strata PT/WebPT for PT.
- **Leverage risk is confirmed.** Successful renegotiations win 8–15% on 3–5 high-volume codes; across-the-board asks "almost universally fail" ([KevinMD 2026](https://kevinmd.com/2026/05/payer-contract-renegotiation-costs-independent-practices.html)).

### What would make it viable
1. **License the data, don't build it.** Use Serif, HexIQ or the PayerPrice API, or white-label one of them.
2. **Sell the negotiation outcome on a success fee** through a partner consultant, not a $490 PDF.
3. **Make billing companies the primary channel.** They are paid a % of collections, so they share the upside.
4. **Pick one high-leverage specialty** (ortho, GI or derm) and avoid PT.
5. **Never put an unvalidated own-rate in a cold email.**

### Most likely failure
Free alternatives plus 0.5%-level reply rates mean the report rarely sells. Meanwhile one wrong own-rate number burns the sender domain's credibility.

---

## 3. New Practice Radar (10-intent-signals #1)

**Verdict: WEAKENED, near KILLED. Revised score: 3.0/10 (original 6.5), confidence medium.**

### Own analysis of the NPPES weekly file
Source: `NPPES_Data_Dissemination_092126_092726_Weekly_V2.zip`, 6.5 MB, from [CMS NPI files](https://download.cms.gov/nppes/NPI_Files.html). "New" means a Provider Enumeration Date between 21 and 27 Sep 2026.

**File contents**
- **34,009 rows**, of which **13,537 (40%) are newly enumerated**. The rest are updates and deactivations going back to 2006.
- **New Type 1 / Type 2: 11,038 / 2,499.** This reproduces the original exactly.
- **No email field.** The file does include the authorized official's name, title and phone, up to 15 taxonomies, a subpart flag, and enumeration and update dates.

**New Type 2 NPIs by primary taxonomy**

| Taxonomy | New Type 2 NPIs |
|---|---|
| Behavioral | 443 |
| 261Q clinics | 346 |
| Physician | 314 |
| Home health / hospice | 203 |
| NP | 133 |
| Residential / SNF | 129 |
| Therapy / chiro | 117 |
| In-home care | 113 |
| DME | 112 |
| Dental | 107 |
| Transport | 106 |
| Pharmacy | 70 |

**"Practice-like" organizations: 1,530 that week.** Within them:
- **44% behavioral, mostly solo-therapist LLCs.**
- **75 are subparts and 58 have hospital-style names.** One Emory official filed 32 department NPIs.
- **230 officials filed more than one organization NPI that week.**
- **Vendor involvement, at least ~8%:**
  - 116 list a non-owner official such as "Credentialing Manager" or "Billing Manager".
  - 80 share a phone number with officials of other names; one Houston number appears on 27 generic LLCs.
- **Plausibly independent: about 1,100–1,300 a week.** Only about 250 a week are physician groups. CA, FL and TX together give about 600 a month, of which about 130 are physician or dental.

**Individual NPIs.** Behavioral 42%, nursing and aides 2,022, and only 704 students or residents. The sibling session's "mostly residents" claim was only partly right.

**NPPES API.** It cannot filter by enumeration date alone, so the weekly file is the only practical source.

### Claims checked

| Original claim | Finding | Source | Holds? |
|---|---|---|---|
| "11,038 new individual NPIs and 2,499 new organization NPIs" | Reproduced exactly. The same file also has 20,472 update or deactivation rows. | [CMS NPI files](https://download.cms.gov/nppes/NPI_Files.html), my parse | Yes |
| "10–25% genuinely independent, about 1–3k/month" | About 45–50% look independent (≈5k/month), but 44% of those are solo behavioral. Only about 1k/month are physician groups. | My parse | Count understated; value overstated |
| NPPES is public, no email, no licensing | Confirmed: FOIA-disclosable, providers cannot opt out, no commercial-use restriction found. | [CMS data dissemination](https://www.cms.gov/medicare/regulations-guidance/administrative-simplification/data-dissemination); [Fed. Reg. CMS-6060-N](https://www.federalregister.gov/documents/2007/05/30/07-2651/hipaa-administrative-simplification-national-plan-and-provider-enumeration-system-data-dissemination) | Yes |
| A new NPI means the practice "has not yet picked billing or IT vendors" | Partly false. Startup credentialing firms list obtaining the Type 1 and Type 2 NPI as a service they provide, and at least ~8% of the file shows vendor filers. Credentialing firms are often too late; billing and MSP firms not necessarily. | [credentialing.com](https://www.credentialing.com/practice-startup-services-telemedicine/); [Credex](https://credexhealthcare.com/npi-registration/); [ProEnrollment](https://proenrollment.com/blog/new-practice-startup-credentialing-cost) | Partly |
| "The mid-market interpreted-feed niche looks open, 6/10" | **Actable sells a product literally called "Practice Radar"** to billing firms: weekly, 48 states, with authorized official and phone, at $39/mo or $19 one-off. NPI Data Services sells "Provider Signals" (new practices and moves). CarePrecise flags new providers. | [Actable](https://actablesite.com/npi-leads-for-medical-billing-companies); [NPI Data Services](https://www.npidataservices.com/); [CarePrecise](https://www.careprecise.com/detail_access_complete.htm) | **No** |
| Billing worth "$1,500–5,000/mo per small practice" | For the most common new organization, a solo therapist, it is about $350–900/mo. | [EliteMed](https://elitemedfinancials.com/mental-health-billing-services-cost/) | No, for the largest segment |
| IBISWorld 1,364 billing establishments | 1,364, declining at a 3.4% CAGR. HBMA has only about 300 member companies. The original's "3–6k firms" is plausible but unverified. | [IBISWorld](https://www.ibisworld.com/industry-statistics/number-of-businesses/medical-billing-services-united-states/); [HBMA media kit](https://mk.multibriefs.com/MediaKit/Pricing/hbma) | Partly |
| Kill risk #3: billing firms may not run outbound | **Largely confirmed.** 72% name referrals as their top source of new business, and 39% require a minimum invoice that excludes tiny new practices. | [Tebra survey](https://www.tebra.com/theintake/healthcare-reports/billing-companies/getting-paid-how-to-get-medical-billing-clients) | Risk confirmed |
| CAC $300–800 | The B2B average reply rate is 3.43%. 600 firms give about 20 replies and 3–6 trials, against a $39 incumbent. | [Instantly benchmarks](https://instantly.ai/blog/email-sequence-benchmarks-2026-whats-a-good-open-rate-reply-rate-and-cost-per-meeting/) | Optimistic |
| Raw feeds commoditized at about $0.50/1k | Confirmed. More Apify actors exist ("NPI New Provider Weekly Monitor" at $19/1k; "Newly Registered Providers by Metro"), each with **about 2 users**: weak demand even at near-zero prices. | [Apify monitor](https://apify.com/lead.gen.labs/npi-new-provider-weekly-monitor); [Apify metro](https://apify.com/easikey/npi-new-providers-metro) | Yes |

### New competitors and risks
- **Data and list sellers.** Actable "Practice Radar", NPI Data Services, CarePrecise, and Provyx (NPI-verified contacts with emails, from $2,500 per project; [Provyx](https://getprovyx.com/compare/provyx-vs-definitive-healthcare/)).
- **Lead-gen agencies already selling to billing firms with richer "switch" signals.** Launch Leads ([link](https://www.launchleads.com/industries/medical-billing/)), CallingAgency ([link](https://callingagency.com/industries-we-serve/medical-billing-lead-generation/)) and Callbox ([link](https://www.callboxinc.com/appointment-setting-lead-generation/)).
- **Shell and fraud clusters.** Houston LLC batches in the file are a classifier hazard.

### What would make it viable
1. **Drop the feed.** It is a $39/mo commodity.
2. **Sell pay-per-booked-meeting with new physician, dental or multi-provider groups only.** Filters: not a subpart; official is the owner; no third-party filer phone; a Secretary of State match within 120 days. That leaves about 250–400 a week nationally.
3. **Target buyers whose window opens after the NPI** (billing, EHR, MSP, malpractice and payroll), not credentialing firms.
4. **Use the 60% of the file that is updates.** Moves and "leaving the group" signals are less crowded.
5. **Pre-sell 10 billing-firm owners before building anything.**

### Most likely failure
Billing firms grow by referral and ignore outbound. Those who try the feed find solo therapists, hospital departments and already-served practices, compare it with the $39 Actable product, and churn.

---

## 4. Pro-se trademark office-action feed (08-legal-ip #1)

**Verdict: WEAKENED. Revised score: 4.5/10 (original 6.6), confidence medium.**

### Claims checked

| Original claim | Finding | Source | Holds? |
|---|---|---|---|
| "Owner email is masked when the owner has counsel, but still visible for unrepresented owners" | Correct as of 2026-10-01. In a live sample of 200 serials, **all 42 pro-se records showed a correspondent email** on public TSDR. I found no later rule that masks them. A 2024 USPTO leak exposed emails of represented applicants and was retracted. | [USPTO 2020 notice](https://www.uspto.gov/subscription-center/2020/owner-email-address-field-now-masked-teas-and-teasi-documents-tsdr); [WTR 2024](https://www.worldtrademarkreview.com/article/uspto-inadvertently-makes-applicant-emails-public-responds-community-concern) | Yes |
| The daily XML provides OA events, an attorney field **and email** for pro-se owners | Partly wrong. The XML has event statements, `attorney-name` and a `correspondent` element, but that element holds **address lines only, with no email element**. Email needs one TSDR call per serial. | [USPTO XML resources](https://www.uspto.gov/learning-and-resources/xml-resources); [ustm.xsd mirror](https://github.com/zgreg179/TM/blob/main/us-tm/ustm.xsd) | Partly |
| Rate limits of 60/min for status and 4/min for documents | Correct, and not binding: off-peak limits are 120 and 12 per minute. That is far more than ~400–500 pro-se OAs a day. Keys "should not be shared". I found no clause banning commercial use or solicitation. | [TSDR API key guide](https://www.uspto.gov/sites/default/files/documents/tm-enterprise-api-user-guide-v2.pdf) | Yes |
| "824,192 application classes in FY2025" | The cited source says only "more than 824,000… up 7.4%". The exact number is not in it. | [Trademark Engine](https://www.trademarkengine.com/blog/us-trademark-filings-latest-uspto-data-before-you-file/) | Approximately |
| "About 30% are pro se (same source)" | **The cited source has no pro-se figure.** USPTO data puts US-domiciled pro-se filings at 28.5% (FY17). The Gerhardt & Lee study found 26%. My sample found 30% (42 of 140), including 3 China-domiciled "pro se" filings that should not exist under the 2019 US-counsel rule. | [2019 Fed. Reg. rule](https://www.govinfo.gov/content/pkg/FR-2019-07-02/html/2019-14087.htm); [Gerhardt & Lee, TMR 2022](https://www.inta.org/wp-content/uploads/public-files/resources/the-trademark-reporter/TMR-Vol-112-No-06_Gerhardt-Lee.pdf) | Number OK, citation wrong |
| Kill risk: "Pro-se applicants are price-sensitive, and 46% fail anyway" | **Wrong.** The study says "46% of pro se applicants succeed… 60% for those represented", so about 54% fail. | [Gerhardt & Lee p.897](https://www.inta.org/wp-content/uploads/public-files/resources/the-trademark-reporter/TMR-Vol-112-No-06_Gerhardt-Lee.pdf) | **No (misquoted)** |
| "Most applications receive at least one OA"; 90–130k pro-se OAs a year | Plausible. 69% of pro-se records in my sample had a non-final action, against 45% of represented ones. 15 of 42 pro-se files were already abandoned. | Live TSDR sample, e.g. [sn99400122](https://tsdr.uspto.gov/statusview/sn99400122) | Yes |
| The 3-month response clock is the urgency hook | Confirmed, but a 3-month extension is available for $125 electronically, so the real window is up to 6 months. Madrid §66(a) filings keep 6 months. | [USPTO 2022](https://www.uspto.gov/subscription-center/2022/new-three-month-deadline-responding-pre-registration-office-actions); [37 CFR 2.6](https://www.ecfr.gov/current/title-37/section-2.6) | Weaker hook |
| Rule 7.3 allows targeted written solicitation; some states require labelling or filing | Confirmed. **USPTO 37 CFR 11.703** bans only live person-to-person contact. 11.702(b)(1) allows paying for advertising, and 11.702(d) requires the responsible practitioner's name. **Texas:** "ADVERTISEMENT" first in the subject line, file with the Advertising Review Committee within 10 days. **Florida:** "Advertisement" in the subject line, filing ≥20 days before use, $150 per ad. | [eCFR 11.702](https://www.ecfr.gov/current/title-37/section-11.702); [11.703](https://www.ecfr.gov/current/title-37/section-11.703); [TX Rules VII](https://www.texasbar.com/Content/NavigationMenu/ForLawyers/MembershipInformation/AdvertisingReview2/TDRPC_VII.pdf); [FL filing](https://www.floridabar.org/ethics/etad/advertising-filing-requirements/) | Yes |
| Pay-per-lead is fine under ABA 7.2 | Yes, but **ABA Formal Op. 501 (2022)** makes the lawyer responsible (Rules 5.3 and 8.4(a)) for how a lead generator contacts people. Our templates therefore become the subscriber's ethics exposure. | [ABA Op. 501](https://images.law.com/contrib/content/uploads/documents/399/77701/aba-formal-opinion-501.pdf) | With caveat |
| "No product sells decoded pro-se OAs to attorneys; crowding 5/10" | No packaged SaaS exists, but there are **about 30 Apify USPTO actors**, including an office-actions scraper and a pro-se lead actor with emails, priced down to $2.79 per 1k. All have tiny usage. Trademarkia was emailing applicants about OA deadlines back in 2013. Effective crowding is about 7/10. | [Apify store search](https://api.apify.com/v2/store?search=office%20action); [everythingtrademarks 2013](https://everythingtrademarks.com/2013/11/20/trademarkia/) | Weakened |
| OA responses sell for $500–2,000+ | The floor is far lower: Law 4 Small Business from **$89**, Trademark Engine from $599. | [L4SB](https://www.l4sb.com/services/trademark-office-action-response/); [Trademark Engine](https://www.trademarkengine.com/office-action-response/) | Partly |
| 3,000–6,000 small firms are buyers | Unverifiable, and filing volume is extremely concentrated: the 5% of attorneys with 100+ filings handle **79%** of attorney-filed applications. The high-volume firms can run their own pipelines. | [Gerhardt & Lee p.899–900](https://www.inta.org/wp-content/uploads/public-files/resources/the-trademark-reporter/TMR-Vol-112-No-06_Gerhardt-Lee.pdf) | Weak |

### New competitors and risks
- **A scam-poisoned channel.** Fake-law-firm and USPTO-impersonation campaigns are ongoing, including the 2026 "Mandatory Verification Appointment" scam. Applicants are told that unsolicited trademark email is almost always a scam. Sources: [Dinsmore](https://www.dinsmore.com/publications/scam-targets-trademark-owners-with-false-law-firm-solicitations/), [Heitner 2026](https://heitnerlegal.com/2026/04/10/mandatory-verification-appointment-the-latest-trademark-scam-targeting-applicants/), [USPTO common scams](https://www.uspto.gov/trademarks/protect/recognizing-common-scams).
- **"Pro-se" records that are really filing mills.** Many correspondent emails belong to filing mills, not owners. The USPTO terminated 52,000+ filings tied to one mill ([USPTO](https://www.uspto.gov/about-us/news-updates/uspto-has-terminated-more-52000-fraudulently-filed-trademark-applications-and)).
- **The funnel is already owned.** LegalZoom, Trademark Engine and Trademarkia upsell OA responses to their own pro-se customers, and $89 shops anchor the price.

### What would make it viable
1. **Sell an attorney-side OA workbench, not leads.** It would decode the OA, draft a response skeleton, and produce a quote and engagement letter, with outreach as an option. It is also useful for the attorney's existing clients, which reduces churn.
2. **Lead with abandonment and revival windows and final actions.** Use **postal letters** that carry a verifiable bar number and a "check TSDR yourself" line.
3. **Make leads exclusive by geography or class.** Target 50–150 mid-volume solos, priced flat, never as a percentage of fees (Rule 5.4).
4. **Filter out mill correspondents and non-US "pro se" records.** Ship TX and FL compliance packs and an Op. 501 acknowledgment.
5. **Run a 60-day, 3-firm pilot.** Kill the idea if retained matters come in under about 1% of contacts. At a ~$600 fee, a lead is worth about $6–12 to the attorney, so $7.50 per lead is barely break-even for the buyer.

### Most likely failure
Pro-se applicants treat attorney emails as scams, so conversion falls below 1%. Subscribing attorneys see one or two matters a month at $89–600 each against a $299–799 fee, and churn within 2–3 months.

---

## 5. B2B unclaimed-property sweep via CPA firms (08-legal-ip #2)

**Verdict: WEAKENED. Revised score: 4.0/10 (original 6.2), confidence medium.**

### Claims checked

| Original claim | Finding | Source | Holds? |
|---|---|---|---|
| CA caps fees at 10% under CCP 1582 | Correct, but CA does not use a "24-month" bar. Agreements are invalid between the holder's report and delivery of the property to the Controller. After that, the agreement must be in writing, disclose the property and the free-claim route, be signed after disclosure, and charge ≤10%, with no upfront fees. | [CCP 1582](https://leginfo.legislature.ca.gov/faces/codes_displaySection.xhtml?lawCode=CCP&sectionNum=1582) | Partly |
| "Many states bar finder agreements for 24 months" | True in RUUPA states such as IL (void until 24 months after delivery to the administrator). Not true in the CA, TX or NY statute text. In RUUPA states this undercuts the "annual re-sweep of newly reported property" pitch. | [765 ILCS 1026 Title 15](https://law.justia.com/codes/illinois/chapter-765/act-765-ilcs-1026/title-15/) | Partly |
| NY: quarterly SFTP list for location providers | An SFTP file exists and anyone can request it. But "**Dollar values are not included in the list**", accounts under $20 are excluded, and no quarterly schedule is stated. A "$X found" teaser is impossible from NY data. | [OSC owner name file](https://www.osc.ny.gov/unclaimed-funds/resources/owner-name-file-request-form) | Weakened |
| NY finder rules (not stated in original) | The cap is **15%**. The agreement must be notarized, use OSC's form with a bold free-claim disclosure, and be mailed as originals. §1416 **exempts an accountant with a "pre-existing relationship"**, so the CPA is exempt but we are not. | [NY ABP §1416](https://www.nysenate.gov/legislation/laws/ABP/1416); [OSC APLSP procedures](https://www.osc.ny.gov/files/unclaimed-funds/claimants/pdf/aplsp-requirements-and-procedures.pdf) | Mixed |
| TX: "10% plus registration and bond"; data needs a PI license | §74.507 caps fees at 10% plus reasonable attorney fees; the statute text has **no registration or bond**. **§74.507(b):** a fee-taking locator "may not file or receive a form to claim on behalf of a claimant." A PI license is needed only for work beyond public-records review. The data request asks for a PI number only "if applicable." | [Tex. Prop. Code 74.507](https://texas.public.law/statutes/tex._prop._code_section_74.507); [TX DPS](https://www.dps.texas.gov/section/private-security/heir-finders-and-investigations-related-unclaimed-accounts); [data.texas.gov metadata](https://data.texas.gov/api/views/3un9-h9it.json) | Wrong in parts |
| FL: CPAs can register as claimant's representatives | True, but only **Florida-certified** CPAs. The fee cap is **30%** (§717.135(2)(j)). Only the department's form is valid. **§717.1322(1)(j)** makes it a violation for anyone except an attorney, FL CPA or PI to take compensation for assisting a claimant, which **bars our 50% split**. | [717.135](https://www.flsenate.gov/Laws/Statutes/2025/717.135); [717.1400](https://www.flsenate.gov/Laws/Statutes/2025/717.1400); [717.1322](https://www.flsenate.gov/Laws/Statutes/2025/717.1322) | Holds for the CPA; kills the split |
| IL: CPA firms serving non-individual clients are exempt | Narrower than stated. The firm must register with the Treasurer, be in good standing with IDFPR, and **provide professional services related to unclaimed property reporting**. The cap is 10%. There is no bulk data. Our own locating role may still need a finder license. | [IL Treasurer FAQ](https://illinoistreasurer.gov/home/individuals/unclaimed-property/unclaimed-property-finder-applications/faq-unclaimed-property-finder-application/); [ICPAS](https://www.icpas.org/advocacy/government-relations/leg-reg-alerts/revised-uniform-unclaimed-property-act--cpas-and-recovery-services) | Overstated |
| Split 50/50 with the CPA | **CA B&P 5061** bars a CPA from taking a fee for referring a client, and bars any commission from clients receiving audit, review, prospective-information or relied-upon compilation work. **AICPA ET 1.520 and 1.510** ban commissions and contingent fees for attest clients. Most small firms compile or review for many business clients. | [CA B&P 5061](https://leginfo.legislature.ca.gov/faces/codes_displaySection.xhtml?lawCode=BPC&sectionNum=5061); [NJCPA summary](https://www.njcpa.org/stayinformed/hubs/topics/commissions-and-contingent-fees) | **Wrong for many clients** |
| CA: weekly CSV download | Supported via search snippets: a weekly CSV by amount band, with owner name, holder and cash reported. Direct fetch was blocked (403). Several Apify scrapers already resell it. | [SCO download page](https://sco.ca.gov/upd_download_property_records.html) (snippet); [Apify CA scraper](https://apify.com/keeganlabs/ca-unclaimed-property-search) | Yes |
| ~$2,500 average; 25% hit rate gives ~$250k per 400-client firm | NAUPA FY20 shows an average claim of **$1,610 and a median of $100**. No state publishes a business-owned share, so "15–25%" remains a guess. | [NAUPA FY20](https://unclaimed.org/fy20-annual-report/) | Not supported |
| E-signature and remote notary; ~70% automated | CA investigator claims need a **wet signature**, notarization at ≥$1,000, and **yellow paper**. NY needs notarized originals. FL accepts only its own e-signature product. Bankruptcy Form 1340 has two notary blocks. | [CA investigator handbook](https://www.sco.ca.gov/files-upd/guide_investigator_handbook.pdf); [Form 1340](https://www.uscourts.gov/sites/default/files/form_1340_application_for_payment_of_unclaimed_funds.pdf) | Weakened |
| Bankruptcy courts: $200M+ held; locator in 66 of 87 courts | "66 of 87" comes from a **2019** bulletin that gives no dollar total. "$200M+" is a law-firm estimate. Claims also require notice to the US Attorney (28 USC 2042). | [USCourts 2019 bulletin](https://content.govdelivery.com/accounts/USFEDCOURTS/bulletins/2492607); [whhlaw](https://whhlaw.com/have-bankruptcy-unclaimed-funds/) | Stale / unverified |
| Kill risk: automatic money-match returns | This mostly affects individuals. PA auto-returns up to $500 to individuals. Iowa's 2026 program leaves businesses to the normal claim process. The risk to a B2B product is lower than the original said, which is good news. | [PA Money Match](https://patreasury.gov/newsroom/archive/2025/06-24-Money-Match.html); [Iowa 2026](https://westerniowatoday.com/2026/08/17/state-treasurer-roby-smith-launches-money-match-initiative-to-return-unclaimed-property-faster/) | Better than claimed |
| Per-name searches on MissingMoney and state sites | MissingMoney returned a Cloudflare block on every path, including its terms page and robots.txt. Multi-state automation beyond the CA, NY and TX files is fragile. | missingmoney.com, direct fetch 2026-10-01 | Weakened |

### New competitors and risks
- **Corporate recovery firms the original missed:** Financial Recovery Strategies (45,000+ corporate clients; [PRN](https://www.prnewswire.com/news-releases/financial-recovery-strategies-and-profittrust-partner-to-launch-duty-discovery-bringing-ai-powered-customs-duty-recovery-to-importers-nationwide-302878027.html)), DMA ([link](https://dmainc.com/practice-areas/unclaimed-property/asset-recovery/)), Abandoned Property Advisors ([link](https://www.ap-advisors.com/corporate-asset-recovery/)), PwC ([link](https://www.pwc.com/us/en/services/tax/state-local-tax/unclaimed-property.html)), Ryan ([link](https://ryan.com/practice-areas/abandoned-and-unclaimed-property/)), Crowe, Baker Tilly and Georgeson.
- **Commoditized search tooling:** multi-state Apify scrapers ([Apify](https://apify.com/crawlerbros/us-unclaimed-property-scraper)).
- **A funded holder-side player:** Eisen raised $18.5M in May 2026 ([Finovate](https://finovate.com/regtech-eisen-raises-18-5-million-to-streamline-escheatment/)).
- **Reputation.** States run scam alerts about finders ([CA SCO fraud alerts](https://www.sco.ca.gov/upd_consumer_fraud_alerts.html)).
- **Cold-email benchmark.** Emailing accounting partners gets about a 2–4% reply rate ([moderninbound](https://moderninbound.com/blog/cold-email-for-accounting-firms)). That is workable.

### What would make it viable
1. **Drop the contingency split.** Sell flat SaaS or per-sweep pricing to the CPA firm only, and never take a percentage. This avoids the FL §717.1322 and TX §74.507(b) problems.
2. **Have the client file the claim itself,** using pre-filled forms and a notary checklist.
3. **Automatically flag attest clients,** so the CPA never takes a contingency or commission from them.
4. **Lead with CA, which has amounts.** Use NY and TX only for name matching. Skip the bankruptcy leg until it is verified.
5. **Bundle with holder-side compliance** (CA VCP, due-diligence letters), where the recurring budget is.

### Most likely failure
CPA firms won't pay. The search is free on state sites, the median hit is about $100, and law and ethics block the revenue share that was meant to motivate them. What remains is a cheap, easy-to-copy SaaS with a 3–9-month cash cycle and manual notary steps.

---

## Cross-idea themes
1. **The raw data is commoditized everywhere.** The Apify actors for the revalidation list, new NPIs, USPTO and CA unclaimed property all exist and **all have about 2–57 users**. That says the raw-list market is not just cheap but nearly demand-less. Interpretation alone does not escape this unless it is tied to an outcome.
2. **Cold outreach is scam-adjacent in all four lanes.** Fake Medicare enrollment letters (MAC warning, Jan 2026), USPTO and law-firm impersonation, and unclaimed-property finder scams. This is the brothers' core channel, and it is structurally disadvantaged here in a way it is not for "your website is bad".
3. **Healthcare reply rates (≈0.5–0.6%) are far below the 2% paid-conversion assumptions** in the 06 write-up.
4. **The "website model" works because the defect is visible, the fix is fully deliverable by agents, and there is no free substitute.** None of these five ideas has all three:
   - Revalidation has a free substitute (CMS notices) and the fix needs the AO's signature.
   - Rate gaps have free substitutes (MGMA Rates, PayerPrice), and the fix is a negotiation that agents cannot deliver.
   - Office actions are visible, but the fix needs a licensed attorney.
   - Unclaimed property is visible, but the fix requires notarization and wet ink.
   - New NPIs have a $39 substitute.

## Final ranking of this batch

| Rank | Idea | Revised score | Confidence | Best surviving variant |
|---|---|---|---|---|
| 1 | Pro-se TM office-action feed | **4.5** | Medium | An attorney OA workbench with exclusive territories, postal letters with verifiable bar IDs, and a 3-firm pilot gate |
| 2 | B2B unclaimed property via CPAs | **4.0** | Medium | Flat-fee CA-first sweep SaaS for CPA firms, with the client filing, bundled with holder-side compliance; no contingency |
| 3 (tie) | Medicare Enrollment Guard | **3.5** | Medium-high | White-label NPI-roster monitoring for billing companies and MSOs at $1–2 per NPI per month |
| 3 (tie) | Rate Gap Report | **3.5** | Medium | Licensed data (Serif or HexIQ) sold through billing companies on a negotiation success fee |
| 5 | New Practice Radar | **3.0** | Medium | Pay-per-meeting for new physician and dental groups only, plus "provider moved / left group" update signals |

**Recommendation.** Do not commit to any of these as the brothers' next market. If the healthcare lane is kept at all, merge Enrollment Guard, Rate Gap and New Practice Radar into one billing-company channel product. Validate it with 10 pre-sale interviews before building anything. Do not cold-pitch physicians.
