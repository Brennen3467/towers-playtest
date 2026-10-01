# Lane 06: Healthcare Data — Market Research

*Research date: 2026-10-01. Research only: no outreach, signups or purchases were made.*

**Conventions**
- **[EST]** marks my own estimates or arithmetic.
- **[ANALYSIS]** marks numbers I computed myself from public CMS files downloaded during this research. The source file URL is given each time.
- **[VENDOR]** marks a claim made by a company that sells into the market. Treat these with skepticism.
- **[3P]** marks third-party aggregator figures (Vendr, CostBench, Latka, Tracxn, IBISWorld). Their reliability is low to medium.

---

## 0. TL;DR

- **The best opportunity is not a data platform.** It is a "website-model" clone: a pre-built, personalized deliverable for small independent practices, made entirely from public data and used as the hook in cold outreach. That is what the brothers already do with websites.
- **Two data combinations create value nobody sells to small practices today:**
  1. **Payer rate gap.** TiC payer price files, with ghost rates filtered out using each provider's Medicare Part B utilization. This yields a practice's *own* commercial rates against local peers, for the codes they actually bill.
  2. **Medicare enrollment health check.** The CMS Revalidation Due Date List, PECOS reassignment, NPPES and Doctors & Clinicians addresses, and Part B revenue combine into a "your Medicare billing is at risk on date X, here is $Y/month at stake" alert.
- Both can be built and sent with almost no human labor.
- **Honest headline: this lane has real money but a hard data layer and a cautious buyer.**
  - Only **18% of medical groups use TiC data in negotiations** ([MGMA Stat, Dec 2025](https://www.mgma.com/mgma-stat/using-tic-negotiated-rate-data-to-negotiate-payer-contrac)).
  - About **95% of TiC provider–code pairs are "ghost rates"** ([Health Affairs Scholar](https://academic.oup.com/healthaffairsscholar/article/3/11/qxaf212/8321476)).
  - CPT codes are AMA-licensed ([CMS AMA license](https://www.cms.gov/license/ama?file=/files/zip/medicare-ncci-2026-q4-hospital-ptp-edits-ccioph-v323r0-f1.zip)).
  - Credentialing and exclusion screening are commoditized: $30–40/month for exclusion screening ([ExclusionScreening pricing](https://exclusionscreening.com/pricing/)).
- **None of the ideas scores above 6.5/10.** Confidence is medium-low across the board until a first outreach test is run.

---

## 1. Lane overview

### 1.1 Landscape

US healthcare publishes more free, provider-level administrative data than almost any other industry. None of the public files below contain PHI; they are provider-level or aggregate. Volumes marked [ANALYSIS] were measured by API calls made during this research.

| Data | What it gives you | Access / cost / refresh | Key limits |
|---|---|---|---|
| **NPPES/NPI** | 9.46M NPI records (secondary count, [NPIScan](https://npiscan.com/)). Type 2 (organization) records include the **authorized official's name, title and phone**. | Monthly full file (1.1 GB zip) and weekly diffs, free ([CMS NPI files](https://download.cms.gov/nppes/NPI_Files.html)). | **No email field.** The only electronic contact is Direct/FHIR endpoints. **[ANALYSIS]** The 21–27 Sep 2026 weekly diff had about 13.5k newly enumerated NPIs, about 2.5k of them organizations ([weekly file](https://download.cms.gov/nppes/NPPES_Data_Dissemination_092126_092726_Weekly_V2.zip)). |
| **Medicare Part B / Part D / DMEPOS utilization** | Per-NPI × per-HCPCS volume and allowed amounts. CY2024 is the latest year; Part B has 9.78M rows. | data.cms.gov API, free ([dataset](https://data.cms.gov/provider-summary-by-type-of-service/medicare-physician-other-practitioners/medicare-physician-other-practitioners-by-provider-and-service)). | About 18 months of lag. Cells with 10 or fewer beneficiaries are suppressed ([methodology](https://data.cms.gov/sites/default/files/2024-06/MUP_PHY_RY24_20240530_Methodology_508_0.pdf)). |
| **Doctors & Clinicians National Downloadable File** | 3.39M rows: NPI, **graduation year**, med school, specialty, group PAC ID, **number of group members**, address, phone. | Free, monthly ([PDC dataset mj5m-pzi6](https://data.cms.gov/provider-data/dataset/mj5m-pzi6)). | Medicare-enrolled clinicians only. |
| **PECOS public files** | Enrollment (2.98M rows, quarterly); reassignment (who bills under which group); **Revalidation Due Date List** (2.94M rows, monthly); Opt-Out Affidavits (57.8k); Order & Referring (2.0M, weekly). | Free ([PPEF](https://data.cms.gov/provider-characteristics/medicare-provider-supplier-enrollment/medicare-fee-for-service-public-provider-enrollment), [Revalidation](https://data.cms.gov/provider-characteristics/medicare-provider-supplier-enrollment/revalidation-due-date-list)). | Revalidation dates are posted only about 6–7 months ahead; everyone else shows "TBD". |
| **Open Payments** | Program Year 2025: 17.07M records, $14.67B in industry payments, including ownership interests ([PALTmed summary](https://paltmed.org/news-media/cms-publishes-program-year-2025-open-payments-data)). | Free, annual (June) plus a January refresh. | Records can change after publication. |
| **Transparency in Coverage (TiC) payer MRFs** | Negotiated rates for every in-network provider, by NPI and TIN × billing code. | Free, but about **1 PB/month** across the industry, with individual files up to 1 TB ([TiC proposed rule, 90 FR 60432](https://www.govinfo.gov/content/pkg/FR-2025-12-23/pdf/2025-23693.pdf)). | 70–96% of rates are implausible ghost rates (same source). Contains CPT codes, which are AMA-licensed. A proposed rule would move to quarterly files plus utilization and taxonomy files, but it was **not final** as of 2026-10-01 ([comment extension](https://www.federalregister.gov/documents/2026/02/25/2026-03798/private-health-insurance-transparency-in-coverage-extension-of-comment-period)). |
| **Hospital MRFs (45 CFR 180)** | Hospital standard charges and negotiated rates. The 2026 rules add median and 10th/90th percentile allowed amounts. | Free; crawl each hospital's site and its `cms-hpt.txt` file ([CMS fact sheet](https://www.cms.gov/newsroom/fact-sheets/cy-2026-opps-ambulatory-surgical-center-final-rule-hospital-price-transparency-policy-changes)). | Enforcement is weak: 28 civil money penalties (CMPs) since 2022 ([Forvis Mazars](https://www.forvismazars.us/forsights/2026/06/price-transparency-enforcement-hhs-cms-reaffirm-focus)). |
| **No Surprises Act IDR public use files (PUF)** | Line-item disputes: initiating party, service code, offers as a % of the qualifying payment amount (QPA), prevailing party, arbitrator (IDR entity), practice size, region. Covers 2023 Q1 to 2025 Q4. | Free, released semiannually ([PUF general info](https://www.cms.gov/files/document/federal-idr-puf-general-information.pdf)). | Codes with fewer than 10 instances per region are suppressed. |
| **Nursing home Care Compare** | Health deficiencies (tag, scope/severity, dates), penalties, ownership, inspection dates; Payroll-Based Journal (PBJ) daily staffing (1.30M rows per quarter). | Free, monthly / quarterly ([NH data dictionary](https://data.cms.gov/provider-data/sites/default/files/data_dictionaries/nursing_home/NH_Data_Dictionary.pdf), [PBJ](https://data.cms.gov/quality-of-care/payroll-based-journal-daily-nurse-staffing/api-docs)). | Lags the actual survey by weeks to months. |
| **OIG exclusion list (LEIE)** | 84,001 excluded individuals and entities. **Only 10.6% have an NPI.** | Free monthly CSV ([OIG](https://oig.hhs.gov/exclusions/exclusions_list.asp)). | Matching requires name, date of birth and address. |
| **SAM.gov exclusions** | Federal debarment list. | Free API key, but **10 requests/day** without a role ([GSA](https://open.gsa.gov/api/exclusions-api/)). | Use the Extract API for bulk. |
| **State Medicaid exclusion lists** | About 45 lists. | Excel, PDF or HTML, with no aggregator ([Streamline Verify](https://streamlineverify.com/state-medicaid-list/)). | This normalization work is the incumbents' moat. |
| **340B OPAIS** | Covered entities and contract pharmacies. | Free daily JSON/Excel ([OPAIS](https://340bopais.hrsa.gov/Help/Reports/DailyReports.htm)). | **Ceiling prices are confidential.** |
| **State Medicaid fee schedules** | Fee-for-service (FFS) rates. | All states must publish them publicly by 2026-07-01 ([42 CFR 447.203](https://www.ecfr.gov/current/title-42/chapter-IV/subchapter-C/part-447/subpart-B/section-447.203)). | Formats are not standard. T-MSIS claims data is PHI and costs about $25k per seat ([ResDAC](https://www.resdac.org/cms-fee-information-research-identifiable-data)). |
| **HCPCS Level II / Physician Fee Schedule RVUs / NCCI edits** | Quarterly code changes; fee schedule; bundling edits. | Free ([HCPCS quarterly](https://www.cms.gov/medicare/coding-billing/healthcare-common-procedure-system/quarterly-update)). | HCPCS II is public domain. RVU and NCCI files contain CPT and fall under AMA terms. |
| **Form 5500 (DOL)** | Self-insured plans with 100+ participants, plan sponsor, Schedules A and C (insurers, brokers, service providers). | Free, monthly refresh, 2025 is the latest year ([DOL datasets](https://www.dol.gov/agencies/ebsa/about-ebsa/our-activities/public-disclosure/foia/form-5500-datasets)). | Small unfunded plans are exempt from filing. |

### 1.2 Incumbents

Incumbents sell enterprise contracts. Small buyers are mostly served by people, not products.

**Price transparency and rate benchmarking**
- **Turquoise Health:** $40M Series C in March 2026, about $95M raised in total, 300+ customers. It serves "10 of the top 25 health systems" and "4 of 5 national payers." Pricing is custom; the only free tier is a search tool for researchers and journalists ([BusinessWire](https://www.businesswire.com/news/home/20260317136906/en/Turquoise-Health-Announces-$40-Million-Series-C-to-Become-the-Operating-System-for-Healthcare-Contracts-and-Payments), [plans](https://turquoise.health/plans/providers)).
- **Serif Health:** "starting at $1,000/month" per region in 2022 ([Serif blog](https://www.serifhealth.com/blog/announcing-our-payer-price-transparency-analytics-portal-api)). It launched **Network Benchmarking for brokers and self-funded employers on 2026-07-16** ([PR Newswire](https://www.prnewswire.com/news-releases/serif-health-launches-network-benchmarking-for-brokers-consultants-and-self-funded-employers-302826963.html)).
- **Payerset:** historically $95k–$350k+ per year for hospitals. This is from a search-indexed version of the page; the live page now shows no prices ([pricing](https://payerset.com/pricing/)).
- **Others:** Trilliant (quote-only, [rate benchmarking](https://www.trillianthealth.com/analytics/rate-benchmarking)); Clarify Rates IQ; PayerPrice; Gigasheet ($1.8k–$21.7k range shown, [pricing](https://www.gigasheet.com/pricing)).

**Provider data**
- **Definitive Healthcare:**
  - FY2025 revenue was $241.5M, down 4%.
  - Customers fell from about 2,500 to 2,330, and the 10-K says smaller customers churn disproportionately ([10-K](https://www.sec.gov/Archives/edgar/data/1861795/000119312526076782/dh-20251231.htm)).
  - The median contract is about $50.5k per year [3P] ([Vendr](https://www.vendr.com/marketplace/definitive-healthcare)).
  - **Signal:** even the category leader cannot keep small customers at enterprise prices.
- **IQVIA OneKey:** $50k–$200k+ per year [3P] ([healthcaredatabase.org](https://healthcaredatabase.org/d/iqvia-onekey/)).

**Contract and underpayment tools for small practices**
- **Rivet:** $6,000/year ([Capterra](https://www.capterra.com/p/205843/Rivet/)).
- **MDClarity:** custom pricing ([pricing](https://www.mdclarity.com/pricing)).
- **Contracting Providers:** $5,000 for up to 4 contracts, plus $500 per percentage point of rate increase ([pricing](https://contractingproviders.com/services/payer-contract-negotiations)).
- **Tribunus Health:** targets independent practices; no price published ([Tribunus](https://www.tribunushealth.com/solutions/price-transparency/)).

**Credentialing**
- **Platforms:** Medallion ($43M raise, [MobiHealthNews](https://www.mobihealthnews.com/news/medallion-raises-43m-launches-credentialing-clearinghouse)), CertifyOS (payer-focused), Verifiable (about $299/user/month [3P], [G2](https://www.g2.com/products/verifiable/pricing)), HealthStream ($304M revenue, [10-K](https://www.sec.gov/Archives/edgar/data/1095565/000143774926005916/hstm20251231_10k.htm)).
- **Small-practice services:** $100–300 per payer application and $600–2,400 per provider per year for maintenance [VENDOR] ([Medwave](https://medwave.io/2026/03/how-much-does-medical-credentialing-cost/)).
- **Exclusion screening:** ExclusionScreening.com at $30–40/month ([pricing](https://exclusionscreening.com/pricing/)); ProviderTrust, Verisys, Streamline (quote-only).

**IDR (No Surprises Act arbitration)**
- **HaloMD:** filed 17–22% of all disputes in 2025 ([Georgetown CHIR](https://chir.georgetown.edu/the-no-surprises-act-idr-process-an-early-look-at-2025-data/)). Its contract with Nutex sets a **20% contingency** ([SEC Ex. 10.17](https://www.sec.gov/Archives/edgar/data/1479681/000162828026015168/ex1017-paymentdisputeresol.htm)).
- **Others:** TeamHealth and Radiology Partners file in-house. Callagy, BillWell and IDR Claims sell to providers.

**PE deal sourcing**
- Grata from about $15k/year ([Capterra](https://www.capterra.com/p/193002/Product-Search/pricing/)); SourceScrub (both now owned by Datasite, [BusinessWire](https://www.businesswire.com/news/home/20250808557102/en/Datasite-to-Acquire-Sourcescrub-Expanding-Private-Market-Intelligence-Solutions)).
- PitchBook: median about $30k [3P] ([CostBench](https://costbench.com/software/financial-data-terminals/pitchbook/)).

### 1.3 Where the gaps are

1. **Done-for-you benchmarking for small independent practices.** 82% of groups don't use TiC data, citing "lack of awareness, unclear value, and insufficient tools, time, or skills" ([MGMA](https://www.mgma.com/mgma-stat/using-tic-negotiated-rate-data-to-negotiate-payer-contrac)). The barrier is labor and skill, not data. That is exactly the gap Claude agents fill.
2. **Ghost-rate filtering is the real data moat.** Every vendor struggles with it. Joining TiC to Medicare utilization (codes an NPI *actually bills*) is a cheap, public filter. The government's own proposed rule would add a "utilization file" for the same reason ([CMS fact sheet](https://www.cms.gov/newsroom/fact-sheets/transparency-coverage-proposed-rule-cms-9882-p)).
3. **Medicare enrollment lapses cause real, documented losses.** Revalidation failures create **permanent unbillable gaps** ([AAPM&R/CMS](https://www.aapmr.org/docs/default-source/quality-practice/cms-provider-enrollment-revalidation-information.pdf?sfvrsn=a497527c_0)). There were about 10 Administrative Law Judge (ALJ) decisions in 2026 alone upholding gaps of up to about 7 months, e.g. Lake Shore OB GYN ([CR6850](https://www.hhs.gov/about/agencies/dab/decisions/alj-decisions/2026/alj-cr6850/index.html)). Yet nobody sells a cheap, proactive alert to practices.
4. **Lower-middle-market practice acquisition screening.** Grata and PitchBook are generic and cost $15k+. Medicare files give specialty-specific practice size, revenue proxies and owner-age proxies for free.
5. **Regulatory shocks in 2026** reset the IDR, 340B and hospice/home-health markets (details per idea below). Shocks create short windows when incumbents are slow.

---

## 2. Candidate ideas

### Idea 1: "Rate Gap Report": payer-rate benchmarking for independent practices, PT clinics and ASCs

**Pitch:** "Here are *your* actual negotiated rates with Blue Cross, UHC, Aetna and Cigna for the 25 codes you bill most, versus what those payers pay your local peers. You are \$X/year under the median." The report is built before we ever contact the practice.

**Data sources**

| Source | Access | Cost | ToS / licensing |
|---|---|---|---|
| TiC in-network MRFs (per payer, via table-of-contents files) | HTTP download / stream | Free data. Compute and egress are the cost: **[EST]** \$2–8k/month to stream-parse one state × 4–6 payers × a target code list. Alternative: license Serif (from \$1k/month in 2022) or Serif via [Dewey](https://www.deweydata.io/blog/healthcare-price-transparency-data-for-research-serif-health-is-now-on-dewey). | Public by regulation. **CPT codes inside require an AMA distribution license** for commercial display: about \$18.50/user/year plus a \$1,050 royalty fee (2026 schedule as summarized; [AMA notice](https://compliance.ama-assn.org/hc/en-us/articles/15166274293399-Notice-Standard-CPT-Distribution-Pricing-Schedule-2026)). |
| Medicare Part B by Provider & Service | data.cms.gov API | Free | Public; CPT terms apply. |
| Physician Fee Schedule RVU / locality files | cms.gov | Free | CPT inside (AMA). |
| NPPES + Doctors & Clinicians file (TIN/group mapping, phone) | Bulk files | Free | Public. |
| Hospital MRFs (ASC and outpatient comparisons) | Crawl | Free | Public. |

**The data combination**
- TiC alone is about 95% noise.
- **TiC × Part B utilization:** keep only the provider–code pairs where that NPI or its group *actually bills* the code to Medicare. This removes most ghost rates and gives realistic peer distributions.
- **× PFS:** express each rate as a % of Medicare. Commercial professional rates averaged **148% of Medicare in 2025** ([Milliman](https://www.milliman.com/en/insight/commercial-reimbursement-benchmarking-medicare-ffs-rates-2025)), which is a sanity anchor.
- **× Part B volumes as weights:** estimates dollar impact, e.g. "gap × your volume ≈ \$38k/year" [EST methodology].
- Nobody sells this at small-practice prices.

**Buyer persona:** the owner-physician or practice administrator of a 1–15 clinician independent group in a commercially insured metro. Best-fit specialties are those with concentrated code sets: PT, orthopedics, dermatology, GI, ophthalmology/optometry, podiatry, and single-specialty ASCs. The secondary buyer is a **medical billing company**, whose fee is 4–10% of collections, so a rate uplift raises its own revenue ([Neolytix](https://neolytix.com/articles/what-is-the-going-rate-for-medical-billing-services/)).

**Evidence of willingness to pay**
- A negotiation consultant publishes **\$5,000 for 4 contracts plus \$500 per point of increase** ([Contracting Providers](https://contractingproviders.com/services/payer-contract-negotiations)).
- Healthcare attorneys bill \$150–350/hour ([getpracticehelp](https://www.getpracticehelp.com/medical-billing-rcm/payer-contract-negotiation/)).
- Rivet sells at \$6k/year.
- Underpayment recovery runs at 20–35% contingency ([MDClarity comparison](https://www.mdclarity.com/comparison/best-healthcare-underpayment-recovery-services)).
- MGMA membership is about \$399/year ([Physicians Thrive](https://physiciansthrive.com/mgma-salary-data/)).
- **Counter-evidence:** 82% of groups don't use TiC data ([MGMA](https://www.mgma.com/mgma-stat/using-tic-negotiated-rate-data-to-negotiate-payer-contrac)).

**Market size (bottom-up)**
- **[ANALYSIS]** From the Doctors & Clinicians file (Aug 2026, [download](https://data.cms.gov/provider-data/dataset/mj5m-pzi6)): **83,420 Medicare-enrolled group practices** (organization IDs). Small groups (1–10 members) where the dominant specialty is:

  | Specialty | Small groups |
  |---|---|
  | PT in private practice | 6,654 |
  | Optometry | 5,823 |
  | Ophthalmology | 1,819 |
  | Podiatry | 1,722 |
  | Dermatology | 1,123 |
  | Orthopedics | 581 |
  | GI | 383 |
  | Allergy | 292 |
  | Urology | 212 |

  These nine specialties alone give about **18.6k small groups**. Solo practitioners not billing under a group are excluded.
- **Other counts:** 6,436 ASCs ([MedPAC](https://www.medpac.gov/wp-content/uploads/2026/03/Mar26_Ch11_MedPAC_Report_To_Congress_SEC.pdf)); 42.2% of physicians are in private practice ([AMA](https://www.ama-assn.org/system/files/2024-prp-pp-characteristics.pdf)).
- **[EST] Serviceable market:** about 40k small groups plus ASCs × \$1,000/year ≈ \$40M/year. A realistic 3-year capture of 1–2% is about \$0.4–0.8M ARR. This is a niche business, not a venture-scale one, unless the billing-company channel works.

**Deliverable and pricing**
- **Free teaser in outreach:** 3 codes × 1 payer.
- **Full report:** \$490 for one payer, or \$990 for the top 4 payers, as a PDF plus an editable negotiation letter.
- **Recurring tier:** \$99–149/month for monthly re-checks, payer-renewal reminders and new-rate alerts.
- **Optional:** a success-fee negotiation add-on through a partner consultant (referral fee).
- **White-label for billing companies:** \$300–1,000/month per billing company covering all its clients [EST].
- **Recurring?** Partly. Contracts renew every 1–3 years, so expect high churn after the negotiation.

**Automation pipeline**
1. **Find prospects:** filter the Doctors & Clinicians file by specialty, group size and metro. Join to Part B volume. Get the authorized official and phone from NPPES Type 2. Email requires enrichment from the practice website or a paid vendor such as Apollo or ZoomInfo (\$, ToS).
2. **Build the deliverable:** a Claude agent pulls the group's TIN/NPI rows from parsed TiC, filters them with Part B, computes peer percentiles, writes a narrative and renders a PDF. Fully automatable once the pipeline exists.
3. **Personalized outreach:** "Dr. X, Aetna pays your group \$94 for 97110; the median for Austin PT groups is \$112." Specific dollar figures make the cold email credible.
4. **Handle replies:** the agent answers questions about methodology, payers and pricing, and books calls. Escalate to a human on contract-legal questions.
5. **Deliver and renew:** Stripe checkout, automated report delivery, monthly re-pulls and an annual renewal reminder synced to contract anniversaries.

**% automatable:** about 85% [EST].
- Human touchpoints: QA of the first ~50 reports (ghost-rate edge cases); occasional sales calls; partner negotiation hand-off.

**GTM, first 90 days**
- **Days 1–30:**
  - Choose one state where BCBS dominates (e.g., TX or NC). Parse 4 payers.
  - Pick PT plus one physician specialty.
  - Hand-validate 30 reports against public anecdotes.
  - Sign the AMA CPT distribution license, or show only HCPCS code numbers without descriptors while waiting for legal advice.
- **Days 31–60:** send 2,000 personalized emails. Target 2% paid conversion at \$490–990.
- **Days 61–90:**
  - Pitch 30 regional billing companies (IBISWorld counts 1,364 billing firms [3P], [IBISWorld](https://www.ibisworld.com/united-states/industry/medical-billing-services/6341/)).
  - Test the white-label offer.
  - Add a second state if the paid rate is above 1%.

**Unit economics sketch [EST]**

| Item | Estimate |
|---|---|
| Data | \$3–8k/month per state (compute), or \$1–3k/month licensed |
| AMA license | About \$1–5k/year |
| CAC (cold email: sending infrastructure, enrichment at \$0.05–0.20/contact, 1–2% conversion) | \$50–250 per paying customer |
| Average first-year revenue | About \$900 (report plus a few months of subscription) |
| Gross margin at 300+ customers/state | 70–85% |
| Break-even per state | About 60–100 customers/year |

**Competitors / crowding**
- **Enterprise is crowded:** Turquoise, Serif, Payerset, Trilliant, Clarify, PayerPrice.
- **Small-practice self-serve is thin:** Rivet, MDClarity, Tribunus, consultants.
- Serif is the most likely to move down-market. Serif already targets ASCs and physician groups ([Serif](https://www.serifhealth.com/solutions/health-systems-and-providers)).
- **Crowding:** medium.

**Legal / regulatory**
- **CPT/AMA copyright:** a real cost and real litigation risk. PatientRightsAdvocate is suing AMA to free CPT; the case is pending ([PRA](https://www.patientrightsadvocate.org/blog/patientrightsadvocateorg-sues-american-medical-association-to-make-medical-billing-codes-freely-available-to-the-public)).
- **CAN-SPAM** (B2B cold email allowed with a physical address, honest subject lines and opt-out; [FTC guide](https://www.ftc.gov/business-guidance/resources/can-spam-act-compliance-guide-business)).
- **TCPA:** no autodialed or prerecorded calls or texts to cell numbers without consent ([47 CFR 64.1200](https://www.ecfr.gov/current/title-47/chapter-I/subchapter-B/part-64/subpart-L/section-64.1200)).
- **Antitrust:** sharing *current* rate data among competing providers can raise concerns. Use aggregated, government-published data. The FTC/DOJ withdrew the old safe harbors in 2023, so get counsel.
- **HIPAA:** none for the public-data report. **If we ingest the practice's 835/837 remits for underpayment detection, we become a business associate and need a BAA** ([HHS](https://www.hhs.gov/hipaa/for-professionals/privacy/guidance/business-associates/index.html)).
- **Payer ToS:** MRFs must be public by rule, so low risk.

**Kill risks**
1. **No leverage, so no payment.** A 3-doctor group knowing it is below median rarely moves BCBS, and the report is "interesting, not actionable."
2. **Data engineering cost and quality.** Petabyte-scale files, TIN/NPI mapping errors, and stale rates make wrong numbers in a cold email fatal to credibility.
3. **Serif or Turquoise launch a \$99/month practice tier,** or the TiC rule change (quarterly files, utilization files) makes clean data a commodity.

---

### Idea 2: "Medicare Enrollment Guard": revalidation, reassignment and address-mismatch alerts

**Pitch:** "Your group's Medicare revalidation is due 30 Nov 2026. CMS will send the notice to an address that doesn't match your NPPES record. You billed \$412k to Medicare in 2024, about \$34k a month at risk. We'll file it for \$249." This is a pre-built, dated, dollar-quantified alert. It is the closest analog to the brothers' website model.

**Data sources (all free, public, monthly; no PHI)**
- Revalidation Due Date List plus 2 reassignment lists ([data.cms.gov](https://data.cms.gov/provider-characteristics/medicare-provider-supplier-enrollment/revalidation-due-date-list)).
- PECOS public enrollment (PPEF) and reassignment.
- NPPES practice and mailing addresses.
- Doctors & Clinicians addresses and phone numbers.
- Part B by provider (Medicare dollars at risk).
- Opt-Out Affidavits.
- Order & Referring file: DME, lab and imaging claims are denied if the ordering NPI is absent.
- None of these carry ToS limits beyond the CPT terms in Part B (only dollar totals are needed).

**The data combination**
- Due date × group revenue gives *dollars at risk*.
- PECOS address vs NPPES / Doctors & Clinicians address gives a *notice mis-delivery risk*. This is the documented failure mode: revalidation notices sent to a former employer ([VitalLaw](https://www.vitallaw.com/news/conditions-of-participation-dab-decisions-surgeon-blamed-for-medicare-revalidation-request-going-to-his-former-employer/hld012eb807f47d86100090aa005056885db608)).
- Reassignment chains flag *which clinicians are tied to which group's revalidation*.
- **[ANALYSIS]** Of the September 2026 file's 2.94M rows (2.45M unique NPIs), **218,382 enrollments carry a dated due date**. That is about **6–8k per month** going forward. Dated rows from 2023–2025 are also still listed, which may indicate overdue or unprocessed enrollments; this needs validation before it is used as a sales claim.
- **[ANALYSIS]** Specialties with due dates from Sep 2026 to Mar 2027 ([file](https://data.cms.gov/sites/default/files/2026-08/987d15c1-e213-488b-a817-b9d746b7b01d/revalidation_base.csv)):

  | Enrollment type | Enrollments due |
  |---|---|
  | Clinic/Group Practice | 21,498 |
  | Pharmacy | 6,489 |
  | Ambulance | 1,631 |
  | Independent lab | 1,217 |
  | Medical supply | 1,041 |
  | Hospital | 928 |
  | PT groups | 812 |

**Buyer persona**
- **Primary:** practice manager or owner of a 1–20 clinician group, plus small DME suppliers, labs and ambulance companies. These carry higher revalidation frequency (DMEPOS every 3 years) and higher dollars per enrollment.
- **Secondary (channel):** billing companies and MSOs monitoring dozens of client NPIs.

**Evidence of willingness to pay**
- Revalidation filing services charge **\$99–300 per enrollment** [VENDOR] ([Medwave](https://medwave.io/2026/03/how-much-does-medical-credentialing-cost/), [Medsole](https://medsolercm.com/blog/medicare-provider-enrollment-2026-guide)).
- Credentialing maintenance costs \$600–2,400 per provider per year.
- Credentialing specialists earn **\$25.32/hour** on average ([Indeed](https://www.indeed.com/career/credentialing-specialist/salaries)).
- **Pain:** a deactivation leads to permanent non-payment for the gap period, with no extensions ([CMS revalidations](https://www.cms.gov/medicare/enrollment-renewal/providers-suppliers/revalidations)). There are about 10 ALJ decisions in 2026 upholding gaps, including SpineMD, Ohio Heart Group and Chabot Urology ([DAB CR6947](https://www.hhs.gov/about/agencies/dab/decisions/alj-decisions/2026/alj-cr6947/index.html)).

**Market size [EST]**
- About 3k group or organizational enrollments come due per month, plus DME, lab and ambulance suppliers, so about **40–50k per year**.
- At \$249 per filing and 3% conversion: about \$300–370k/year in filing revenue.
- A monitoring subscription for billing companies (about 1,364 to roughly 5,000+ firms) at \$1–2 per provider per month could add similar revenue.
- **Ceiling:** about \$1–2M/year. This is a **wedge, not a big business.**

**Deliverable and pricing**
- **Alert:** free, with dollars at risk.
- **Done-for-you filing:** \$199–299 per enrollment (PECOS submission by a human or agent with the practice's PECOS credentials).
- **Monitoring:** \$15 per group per month, covering revalidation, reassignment drift, opt-out and Order & Referring status, plus address-mismatch checks.
- **Billing-company white-label API:** \$1–2 per NPI per month.
- **Recurring?** The monitoring is, but its value is low between 5-year cycles, so churn risk is high.

**Automation pipeline**
1. **Find prospects:** a monthly diff of the revalidation list yields new dated enrollments. Join to Part B dollars and NPPES contact (authorized official and phone). Enrich email.
2. **Build the deliverable:** an agent generates a one-page "enrollment health" PDF: due date, linked clinicians, address mismatches, dollars at risk.
3. **Outreach:** email, plus physical mail (which converts well to small medical offices [EST]), at T-150 and T-90 days.
4. **Handle replies:** an agent answers; payment through checkout; an intake form collects PECOS identity info.
5. **Deliver and renew:** a human or agent completes the PECOS 2.0 submission (credentialed login; agents operating someone's government account is a ToS and identity question, so keep a human in the loop). Track MAC approval, then auto-enroll in monitoring.

**% automatable:** about 75%.
- Human touchpoints: PECOS submission and MAC follow-ups; edge cases (CHOWs, reassignment disputes).

**GTM, first 90 days**
- **Weeks 1–3:** build the join and validate 100 records by hand against PECOS lookups.
- **Weeks 4–8:** send 3,000 emails and 500 letters to groups due within 90–150 days.
- **Weeks 9–12:** pitch 20 billing companies on the white-label monitor.
- **First dollar is likely within 30–45 days**, the fastest in this lane.

**Unit economics [EST]**

| Item | Estimate |
|---|---|
| Data | \$0 (only compute) |
| CAC | About \$40–120 (email plus a \$1.20 letter) |
| Filing price | \$249 |
| Labor | 30–60 minutes per filing (\$15–40) |
| Gross margin | About 75–85% |

**Competitors / crowding**
- Credentialing firms and billing companies already bundle this. Free lookup sites exist ([npiprofile](https://npiprofile.com/resources/medicare-revalidation)).
- The raw list is already being resold as "leads" on Apify ([Apify](https://apify.com/jserle/medicare-revalidation-due-leads)). Others see the same opportunity, so speed matters.
- CMS itself mails notices 3–4 months ahead.
- **Crowding:** medium-low for proactive, dollar-quantified alerts.

**Legal / regulatory**
- **Social Security Act §1140** prohibits using "Medicare" or "CMS" names and symbols in a way that implies government endorsement. Outreach must clearly be from a private company ([SSA §1140](https://www.ssa.gov/OP_Home/ssact/title11/1140.htm)).
- FTC Act deception rules apply.
- CAN-SPAM and TCPA as above.
- No PHI.
- Acting inside PECOS on a provider's behalf requires a proper surrogate or I&A authorization.

**Kill risks**
1. **Low price ceiling and episodic need.** Revalidation happens every 5 years, so recurring revenue is thin.
2. **Perception risk.** Outreach about Medicare deadlines can look like a scam or government impersonation, which hurts trust and deliverability.
3. **Disintermediation.** CMS improves its notices, or the practice's billing company already handles revalidation, so the buyer says "covered."

---

### Idea 3: Practice-acquisition target screener for lower-middle-market healthcare roll-ups (links to the M&A lane)

**Pitch:** "A monthly ranked list of the 200 most acquirable independent optometry, PT, derm or podiatry practices in your target states. Each comes with Medicare revenue, clinician count, owner-age proxy, growth trend and independence flags, plus optional AI-written owner outreach."

**Data sources (all free and public)**
- Doctors & Clinicians file: graduation year as an owner-age proxy, group size, phone.
- Part B by provider and service, multi-year: revenue proxy and growth.
- PECOS reassignment: who belongs to which group.
- NPPES: enumeration date, organization authorized official.
- Open Payments ownership file: physician ownership or investment interests.
- CMS ownership files: SNF, hospice and HHA, with PE/REIT flags ([CMS](https://www.cms.gov/newsroom/press-releases/first-time-hhs-making-ownership-data-all-medicare-certified-hospice-home-health-agencies-publicly)).
- State Secretary of State filings: scraping varies by state ToS.
- **Vet:** no Medicare data. The only free ownership map is a volunteer list ([privateequityvet.org](https://privateequityvet.org/vet-list/)).
- **Dental:** dentists are thin in Medicare, so this is weak for dental and vet roll-ups.

**The data combination**
Owner age (graduation year) × practice size × Medicare revenue trend × "not already part of a big org" (reassignment to a large org PAC, PE-flagged entities) gives an **acquirability score**. Generic tools like Grata scrape websites; they do not have clinician-level billing and age signals.

**Buyer persona:** a corp-dev or associate-level sourcer at a PE-backed platform doing add-ons, plus independent sponsors and search funds. Also sell-side practice brokers looking for listings.

**Evidence of willingness to pay**
- Grata from \$15k/year; SourceScrub \$20–60k [3P]; Definitive median \$50.5k [3P]; PitchBook median about \$30k [3P].
- PE associates earn \$200–375k ([Glassdoor](https://www.glassdoor.com/Salaries/private-equity-associate-salary-SRCH_KO0,24.htm)), and much of the junior role is manual sourcing.
- Practice brokers take **6–12% success fees** in dental and vet ([Dental Transitions](https://dentaltransitions.com/articles/best-dental-practice-broker/), [CT Acquisitions](https://ctacquisitions.com/ma-advisor-for-veterinary-practice/)).

**Market size (bottom-up)**
- **Deal volume:** PESP counted **1,029 PE healthcare deals in 2025** (664 add-ons) across **420 platforms** ([PESP](https://pestakeholder.org/reports/pe-healthcare-deals-2025-in-review/)). PitchBook counts about 747 healthcare-services deals ([PitchBook Q4 2025](https://pitchbook.brightspotcdn.com/2d/0a/acb3601c4e19925c22d3f3877637/q4-2025-healthcare-services-report.pdf)).
- **[EST]** About 420 platforms plus about 300 search funds and independent sponsors plus about 200 brokers ≈ 900 buyers. At \$6–15k/year that is a \$5–13M SAM.
- **[ANALYSIS] Target universe**, as small groups (1–10 members) with at least one clinician who graduated in or before 1996 (about age 55+):

  | Specialty | Targets |
  |---|---|
  | Optometry | 3,077 |
  | PT | 2,865 |
  | Ophthalmology | 1,432 |
  | Podiatry | 928 |
  | Dermatology | 641 |
  | Orthopedics | 387 |

**Deliverable and pricing**
- \$750–1,500/month per specialty × region (an annual contract is preferred), delivered as a CRM-ready CSV plus a dashboard.
- Add-on: owner-outreach-as-a-service at \$2–5k/month, or a success fee by agreement.
- **Recurring?** Yes, with monthly refresh.

**Automation pipeline**
1. **Find prospects (buyers):** PESP/press deal announcements and platform websites; add-on announcements reveal each platform's specialty and geography.
2. **Build the deliverable:** an agent builds a sample list for *that platform's* specialty and geography (the pre-built deliverable).
3. **Outreach:** "Here are 10 of 214 independent PT practices in Ohio we score as likely sellers. Full list attached for a trial."
4. **Handle replies:** an agent handles them; a human takes demos for \$10k+ deals.
5. **Deliver and renew:** a monthly automated refresh plus "new signals" (an owner's group shrinks, a clinician leaves, revenue declines).

**% automatable:** about 80%. Human touchpoints: enterprise sales calls, custom scoring tweaks.

**GTM, first 90 days**
- Pick 2 specialties (PT, optometry). Build national scores.
- Cold-email 150 platforms and searchers with free sample lists.
- Target 5 paid pilots at \$750/month.
- Cross-sell to the M&A lane's broker list.

**Unit economics [EST]**

| Item | Estimate |
|---|---|
| Data | About \$0 (plus optional email enrichment, \$200–500/month) |
| CAC | About \$500–1,500 (longer cycle) |
| ARPA | About \$12k/year |
| Gross margin | 85–90% |

**Competitors / crowding**
- Grata/SourceScrub (Datasite), PitchBook (which now markets a "Healthcare PE AI Lead Gen" product, per an unverified page), Definitive, Provyx (dental per-record data, [Provyx](https://getprovyx.com/use-cases/dental-practice-data/)).
- **Crowding:** medium-high at the top, medium in the long tail.

**Legal / regulatory**
- CAN-SPAM for outreach to owners; TCPA for calls.
- No PHI.
- **CPT not needed** if we show only dollar totals.
- State corporate-practice-of-medicine laws and new PE-transaction notice laws (e.g., CA, OR) affect buyers, not us.
- Open Payments data can be used commercially.

**Kill risks**
1. **Medicare blind spots.** Commercial-heavy practices (derm cosmetics, PT cash-pay) and dental/vet are invisible or understated in the data.
2. **Small buyer pool that already owns tools.** Platforms with Grata or PitchBook seats may see this as "nice to have."
3. **A cyclical PE pullback** in 2026 ([Advisory Board](https://www.advisory.com/daily-briefing/2026/09/02/around-the-nation)) and physician-practice deals down 18% ([PitchBook](https://pitchbook.brightspotcdn.com/2d/0a/acb3601c4e19925c22d3f3877637/q4-2025-healthcare-services-report.pdf)).

---

### Idea 4: Nursing-home "survey window" and deficiency-risk lead feed for long-term care (LTC) vendors

**Pitch:** "Each month, every SNF in your territory that is likely to receive its standard inspection in the next 60–90 days, ranked by risk of infection-control, staffing and other citations, with the administrator's contact details."

**Data sources:** Care Compare health deficiencies, inspection dates, penalties, ownership, provider info; PBJ daily staffing; SNF cost reports. All are free, monthly or quarterly, with no ToS limits ([NH dictionary](https://data.cms.gov/provider-data/sites/default/files/data_dictionaries/nursing_home/NH_Data_Dictionary.pdf)).

**The data combination**
- Standard surveys must happen **within 15 months, with a statewide average of 12 months or less** ([42 CFR 488.308](https://www.law.cornell.edu/cfr/text/42/488.308)). The last survey date therefore gives a predictable **upcoming survey window**.
- Add deficiency-tag history (repeat tags), PBJ staffing drops, and ownership changes.
- The result is a timed buying trigger for mock-survey consultants, infection-prevention trainers, staffing agencies, pharmacy consultants and therapy contractors.
- Existing tools benchmark quality; they don't time sales triggers.

**Buyer persona:** the owner of a small LTC compliance consultancy (mock surveys, plan-of-correction writing); a regional staffing-agency sales lead; an LTC pharmacy business-development rep.

**Evidence of willingness to pay**
- Mock surveys cost **\$1,500–2,000 per consultant-day with a 3-day minimum** [VENDOR] ([Health Dimensions](https://healthdimensionsgroup.com/how-to-prepare-for-a-nursing-home-or-assisted-living-survey-mock-survey-faqs/)), or about \$10k per facility per year ([SMK](https://smkmedical.com/smk-medical-compliance-minute/the-137000-mistake-a-true-story-of-why-mock-surveys-matter-in-long-term-care)).
- StarPRO charges \$95–195 per user per month with a 5-user minimum, \$349 per facility per month for operators, and includes alerts ([StarPRO pricing](https://getstarpro.com/pricing/)).
- F880 (infection control) is the most-cited tag ([PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC9666375/)).

**Market size**
- **14,742 nursing facilities** ([KFF](https://www.kff.org/medicaid/a-look-at-nursing-facility-characteristics/)).
- **[EST]** Vendor buyers: about 1,000–2,000 LTC compliance consultancies and pharmacy/therapy/staffing sales teams (unsourced; buyer count is the biggest unknown). 500 subscribers × \$300/month ≈ \$1.8M ARR ceiling.
- Healthcare staffing agencies: 3,349 [3P] ([IBISWorld](https://www.ibisworld.com/united-states/number-of-businesses/healthcare-staff-recruitment-agencies/4956/)).

**Deliverable and pricing**
- \$199–499/month per state territory; CSV/CRM sync plus a weekly email.
- **Recurring?** Yes.

**Automation pipeline**
1. **Find prospects:** vendors from LTC association exhibitor lists, Google Maps and LinkedIn.
2. **Build the deliverable:** a sample feed for their state.
3. **Outreach:** "17 SNFs in Ohio enter their survey window in November; 9 had repeat F880."
4. **Handle replies and deliver/renew:** agent-handled replies, automated monthly delivery.

**% automatable:** about 90%.

**GTM, first 90 days**
- Validate the window model by back-testing: predict 2025 surveys from 2024 data and measure the hit rate.
- Sell to 50 consultants in 5 states.
- Aim for 10 subscribers.

**Unit economics [EST]:** data \$0; CAC \$200–600; ARPA \$3.6k/year; gross margin 90%.

**Competitors / crowding**
- AHCA LTC Trend Tracker is **free to members** and used by 8,000+ centers ([AHCA](https://www.ahcancal.org/Data-and-Research/LTC-Trend-Tracker/Pages/default.aspx)). It is operator-facing, though.
- StarPRO, Trella, Definitive.
- Raw citations are resold at \$2.50–3 per 1,000 records ([Apify](https://apify.com/jserle/nursing-home-deficiency-citations)).
- ProPublica Nursing Home Inspect is free.
- **Crowding:** medium.

**Legal / regulatory:** public data; CAN-SPAM. Avoid plaintiff-attorney lead generation; attorney solicitation rules and consumer-facing marketing change the risk profile. No PHI.

**Kill risks**
1. **Fragmented, small-budget buyers.** Consultants are often 1–5 person shops.
2. **Window prediction may be too fuzzy.** States vary, and complaint surveys are unpredictable.
3. **StarPRO or Trella add the feature,** or staffing demand drops: the federal minimum-staffing rule was repealed in December 2025 ([AHA](https://www.aha.org/news/headline/2025-12-02-cms-repeals-minimum-staffing-requirements-skilled-nursing-long-term-care-facilities)).

---

### Idea 5: IDR (No Surprises Act arbitration) prep for small out-of-network providers

**Pitch:** "We find your eligible out-of-network claims, recommend the offer most likely to win (from 4M+ public dispute outcomes), batch them under the new rules, and file. 12% contingency versus the 20% norm."

**Data sources**
- IDR public use files: initiating party, service code, offer as % of QPA, prevailing party, arbitrator (IDR entity), region ([CMS](https://www.cms.gov/files/document/federal-idr-puf-general-information.pdf)).
- TiC (to detect which payers a provider is *out* of network with).
- Part B (volume).
- NPPES.
- The provider's own EOBs and remits (**PHI, so a BAA is needed**).

**The data combination**
- **PUF offer/award distributions by code × region × arbitrator** give an offer-optimization model.
- **TiC network absence × NPPES specialty** (anesthesia, ER, radiology, neuromonitoring, ambulance) identifies **out-of-network providers who are not already filing** (cross-checked against PUF initiating-party names).

**Buyer persona:** the owner or revenue-cycle lead of an independent anesthesia, emergency, radiology, neuromonitoring, assistant-surgeon or ground/air ambulance group with \$1–20M in revenue.

**Evidence of willingness to pay**
- HaloMD's **20% contingency** (SEC exhibit, above).
- Nutex reported arbitration costs of about 25% of arbitration revenue ([Nutex 10-K](https://www.sec.gov/Archives/edgar/data/1479681/000162828026015168/nutx-20251231.htm)).
- Providers won about **85–88%** of 2025 disputes ([CMS supplemental](https://www.cms.gov/priorities/innovation/data-and-reports/2026/federal-idr-supplemental-background-2025-q3-2025-q4)).
- Median winning award was 445% of QPA ([CHIR](https://chir.georgetown.edu/the-no-surprises-act-idr-process-an-early-look-at-2025-data/)).

**Market size**
- About **2.56M disputes in 2025** (1.19M in H1, 1.37M in H2).
- First-half 2025 administrative fees alone were \$844M ([CHIR](https://chir.georgetown.edu/the-no-surprises-act-idr-process-an-early-look-at-2025-data/)).
- The top 10 initiators file about 66% of disputes, leaving about 870k a year to the long tail ([Healthcare Dive](https://www.healthcaredive.com/news/no-surprises-act-disputes-increase-arbiters-progress-speed-backlog-cms/826011/)).
- **[EST]** At \$300 in contingency per won dispute, 1% of the long tail is about \$2.6M/year.

**2026 shocks**
- The administrative fee drops **from \$115 to \$15 per party** for disputes initiated on or after 2026-06-11 ([FR 2026-11140](https://www.federalregister.gov/documents/2026/06/04/2026-11140/federal-independent-dispute-resolution-operations)).
- Batching expands.
- The Fifth Circuit en banc ruling in *TMA v. HHS* (Aug 2026) requires ghost rates to be excluded from QPAs, so QPAs are likely to rise ([Harris Beach Murtha](https://www.harrisbeachmurtha.com/insights/potential-impacts-of-fifth-circuit-en-banc-decision-in-texas-medical-association-v-hhs/)).

**Deliverable and pricing:** 10–15% contingency on recovered amounts above the initial payment, or SaaS at \$500–2,000/month for groups that file themselves. **Recurring?** Effectively yes, because claims flow continuously.

**Automation pipeline**
1. **Find prospects:** TiC network-absence plus specialty filter; exclude large known filers.
2. **Build the deliverable:** a free "IDR opportunity estimate" from public data (your specialty, payers you're out of network with, typical award %).
3. **Outreach:** personalized email.
4. **Handle replies:** agent-handled.
5. **Deliver:** sign a BAA; ingest 835s; an agent screens eligibility (state vs federal law, timing, open-negotiation notice) and drafts offers; **a human reviews every filing**; submit via the IDR portal; track determinations and payment collection (plans often pay late).

**% automatable:** about 55–65%. Eligibility review and payer payment collection stay human.

**GTM, first 90 days:** BAA and HIPAA security program first (SOC 2-lite); healthcare regulatory counsel; 3 design partners (anesthesia or neuromonitoring); file 200 disputes; measure the win rate and time to cash.

**Unit economics [EST]**

| Item | Estimate |
|---|---|
| Data | Free |
| Upfront arbitrator fees fronted per dispute | \$200–840 (or the client pays) ([FR 2023](https://www.federalregister.gov/documents/2023/12/21/2023-27931/federal-independent-dispute-resolution-idr-process-administrative-fee-and-certified-idr-entity-fee)) |
| Working capital | Heavy |
| CAC | \$2–5k per group |
| Gross margin | 50–60% after human review |

**Competitors / crowding:** HaloMD, TeamHealth and RadPartners in-house, Callagy, BillWell, IDR Claims, CollectionPro. **Crowding:** high at the top, medium in the long tail.

**Legal / regulatory**
- **Highest risk in this lane.** Payers have filed RICO suits against high-volume filers; Anthem alleges 55% of HaloMD's submissions were ineligible ([Healthcare Dive](https://www.healthcaredive.com/news/elevance-surprise-billing-suit-tossed-california-halomd/817405/)). HCSC sued Neuromonitoring Associates ([CFS Law Monitor](https://www.consumerfinancialserviceslawmonitor.com/2025/07/litigation-heats-up-over-air-ambulance-billing-practices-under-the-no-surprises-act/)).
- HIPAA business associate obligations apply.
- Some states restrict fee-splitting or contingency billing arrangements; needs counsel.

**Kill risks**
1. Litigation and payer retaliation against filers.
2. Working capital and human review make it a services business, not a software business.
3. Further rule changes, or Congress amending the IDR process.

---

### Idea 6: Self-funded employer network-rate benchmark sold through small benefits brokers

**Pitch:** "For your 300-life self-funded client on Aetna's network, here is what that network actually pays local hospitals and doctors as a % of Medicare, versus the alternative network. Fiduciary-grade documentation for the renewal meeting."

**Data sources**
- Form 5500 plus Schedules A and C: who is self-insured, size, broker, TPA. Free ([DOL](https://www.dol.gov/agencies/ebsa/about-ebsa/our-activities/public-disclosure/foia/form-5500-datasets)).
- TiC network rates.
- Hospital MRFs.
- Medicare fee schedules.

**The data combination:** Form 5500 identifies the employer and its broker. TiC plus hospital MRFs price the network. Medicare normalizes. ERISA litigation pressure supplies the "why now": about 70 proposed ERISA health-plan class actions in Q1 2026 ([actuary.info](https://actuary.info/insights/erisa-health-plan-fee-suits-fiduciary-liability-repricing-2026)), though the J&J case was dismissed twice ([NFP](https://www.nfp.com/insights/court-again-dismisses-erisa-fiduciary-breach-claims-against-jj/)).

**Buyer persona:** the producer at a regional benefits brokerage with self-funded clients of 100–1,000 lives; secondarily the HR/CFO of the employer.

**Evidence of willingness to pay**
- Serif launched exactly this for brokers in July 2026, and Payerset sells to employers ([Payerset](https://payerset.com/solutions/employers/)). Incumbents investing here signals demand.
- The large consultancies (WTW, Mercer) charge consulting fees (not public).

**Market size:** about **49,000 self-insured plans** filed Form 5500 for 2022 ([DOL report](https://www.dol.gov/sites/dolgov/files/EBSA/researchers/statistics/retirement-bulletins/annual-report-on-self-insured-group-health-plans-2025.pdf)). **[EST]** About 30k are in the 100–1,000-life band; at \$1,500 per report per year, that is a \$45M SAM.

**Deliverable and pricing:** \$1,000–2,500 per employer report, or a broker subscription at \$500–1,500/month. **Recurring?** Yes, with an annual renewal cycle.

**Automation pipeline:** Form 5500 gives employers and brokers. Build a sample report for one of the broker's real clients (public data). Outreach to the broker, agent-handled replies, an annual auto-refresh before renewal.

**% automatable:** about 75%.

**GTM, first 90 days:** one metro; 100 brokers; 10 paid reports. Partner with independent TPAs.

**Unit economics [EST]:** data cost as in Idea 1 (shared pipeline); CAC \$300–800; gross margin 75%.

**Competitors / crowding:** Serif, Payerset, Turquoise, Healthcare Bluebook, the big consultancies. **Crowding:** medium-high and rising.

**Legal / regulatory:** CPT licensing as in Idea 1; CAN-SPAM; no PHI from public data. If the deliverable is claims-based, a BAA is needed with the plan. This is an investment-advice-adjacent area, though not securities.

**Kill risks**
1. Serif and Turquoise got there first with funding.
2. Brokers are conflicted: commissions and the carriers' own networks.
3. Network rates can't be changed by a 300-life employer, which limits actionability.

---

### Idea 7: Exclusion and license monitoring for home care, home health/hospice and staffing agencies

**Pitch:** "Monthly OIG, SAM and all-state Medicaid exclusion checks plus license checks for every nurse and aide you employ, with an audit-ready certificate."

**Data and combination**
- LEIE (free monthly CSV, **only 10.6% NPI coverage**, so fuzzy matching is needed), SAM Extract API, about 45 state lists (messy; LLM parsing is a modest moat), Nursys e-Notify (paid; **its ToS bars scraping**, [Nursys](https://nursys.net/policy/)).
- Prospects come from OIG CMP enforcement press releases and HHA/hospice ownership files.

**Buyer persona:** the administrator or HR lead of a home health agency, hospice or healthcare staffing agency.

**Evidence of willingness to pay**
- The CMP for employing an excluded person is **\$25,595 per item or service**, plus treble damages ([91 FR 3665](https://www.govinfo.gov/content/pkg/FR-2026-01-28/html/2026-01688.htm)).
- Real settlements: \$292,594 (Center at Lowry, [OIG](https://oig.hhs.gov/fraud/enforcement/center-at-lowry-agreed-to-pay-292000-for-allegedly-violating-the-civil-monetary-penalties-law-by-employing-an-excluded-individual/)); \$1.57M across 19 SNFs ([OIG](https://oig.hhs.gov/fraud/enforcement/skilled-nursing-facilities-agreed-to-pay-15-million-for-allegedly-violating-the-civil-monetary-penalties-law-by-employing-excluded-individuals/)).
- Monthly screening is OIG-recommended ([2013 bulletin](https://www.federalregister.gov/documents/2013/05/09/2013-11055/updated-special-advisory-bulletin-on-the-effect-of-exclusion-from-participation-in-federal-health)) and required through state Medicaid agreements ([CMS CIB](https://www.medicaid.gov/federal-policy-guidance/downloads/cib-12-23-11.pdf)).
- **But the market price is \$30–40/month** ([ExclusionScreening](https://exclusionscreening.com/pricing/)).

**Market size**
- About 11,000 HHAs, 6,706 hospices ([MedPAC](https://www.medpac.gov/wp-content/uploads/2026/03/Mar26_Ch10_MedPAC_Report_To_Congress_SEC.pdf)), 14,742 SNFs, about 3,349 staffing agencies.
- **[EST]** About 35k buyers × \$50–100/month ≈ \$20–40M. Low price points make a bottom-up path to \$1M ARR require 1,000+ customers.

**Deliverable and pricing:** \$49–99/month by headcount tier. **Recurring:** yes (sticky).

**Automation:** about 95%. The human touchpoint is a fuzzy-match "possible hit" review (false positives).

**GTM:** cold email to HHAs and hospices in moratorium/fraud-focus states (CA, TX), using the CMS crackdown as the hook ([CMS](https://www.cms.gov/newsroom/press-releases/cms-announces-aggressive-nationwide-crackdown-fraud-six-month-hospice-home-health-agency-enrollment)).

**Unit economics [EST]:** CAC \$150–400; ARPA about \$900/year; gross margin 90%; payback 3–6 months.

**Competitors / crowding:** ProviderTrust, Verisys, Streamline Verify, ExclusionScreening, OIG Compliance Now, HR/background-check vendors (Checkr and similar). **Crowding:** high.

**Legal / regulatory:** low. A false negative (a missed hit) creates liability exposure, so carry E&O insurance and include contract disclaimers. If doing employment-related checks, consider whether FCRA applies (consumer-report rules) [needs counsel]. Not PHI.

**Kill risks:** (1) a commodity price; (2) bundled free in HR/credentialing suites; (3) differentiation is near-impossible beyond price.

---

### Idea 8: 340B rebate-pilot reconciliation for small covered entities

**Pitch:** "For FQHCs and critical-access hospitals: we match your claims to the 2027 rebate-pilot drugs, submit to Beacon within the 45-day window, and chase unpaid rebates."

**Data**
- OPAIS (free daily JSON).
- The revised rebate pilot covers about 25 Maximum Fair Price drugs, **effective 2027-01-01** ([FR 2026-15633](https://www.federalregister.gov/documents/2026/08/03/2026-15633/notice-regarding-340b-rebate-model-pilot-program)).
- The entity's claims and dispensing data are PHI, so a BAA is required.
- Ceiling prices are confidential ([HHS PIA](https://www.hhs.gov/sites/default/files/hrsa-opais-340b-pricing-system-20160519-remediated-sd.pdf)).

**Buyer:** the 340B coordinator or CFO at an FQHC or rural hospital.

**Evidence of willingness to pay:** mock audits cost \$50–150k ([AAFCPA](https://www.aafcpa.com/industries/healthcare/340b-pharmacy-program-audit-consulting/)); TPAs charge per prescription ([GAO-18-480](https://www.gao.gov/assets/gao-18-480.pdf)).

**Market:** 15,249 covered entities ([MN DOH FAQ](https://www.health.state.mn.us/data/340b/docs/340bfaq.pdf)).

**Pricing:** \$500–1,500/month.

**Automation:** about 50% (integration-heavy).

**Competitors:** Beacon/Second Sight (the chokepoint), Kalderos, Plenful, existing 340B TPAs.

**Legal:** HIPAA business associate; 340B program-integrity rules; the pilot has already been enjoined once ([Feldesman](https://www.feldesman.com/hrsa-pauses-340b-rebate-model-pilot-program-following-federal-court-order/)).

**Kill risks:** (1) policy reversal or litigation; (2) TPAs and Beacon own the data pipes; (3) needs EHR and pharmacy integrations, which is the opposite of the public-data model.

---

## 3. Ideas considered and rejected

| Idea | Why rejected |
|---|---|
| **New-NPI / "new practice" lead lists** | NPPES-derived leads already sell for **\$0.50–10 per 1,000 records** ([Apify](https://apify.com/scrapesignal_labs/npi-healthcare-provider-leads)) and \$0.21–0.30 per record for mail ([PostcardMania](https://www.postcardmania.com/products-services/mailing-list-of-doctors/)). Most new Type 1 NPIs are residents and non-billing staff. Commodity. |
| **Hospital price-transparency compliance monitoring** | CMS publishes a free validator ([GitHub](https://github.com/CMSgov/hospital-price-transparency)). Turquoise and PatientRightsAdvocate publish free compliance trackers. Only 28 CMPs in about 4 years. MRF-generation vendors bundle compliance. |
| **Standalone credentialing service** | Labor-heavy (PECOS, CAQH, payer portals). CAQH is free to providers. Hundreds of offshore-staffed services at \$99–300 per application. Medallion and Verifiable have raised \$100M+. Not data-driven. |
| **MA / Part D Star-ratings consulting** | Few buyers (small MA plans). Entrenched actuarial consultancies. Data advantage is nil. |
| **Open Payments KOL / pharma targeting** | Enterprise life-sciences buyers served by IQVIA, H1 and Komodo at \$50k–200k+. A public-data entrant has no edge. |
| **Nursing-home deficiency leads for plaintiff attorneys** | Attorneys already use free CMS and ProPublica data. The value lies in consumer lead generation (\$625 per lead, about \$4–5k per signed case, [rankings.io](https://rankings.io/blog/personal-injury-lead-costs/)), which is a different and regulated business (attorney solicitation and advertising rules). |
| **Medicaid fee-schedule aggregator** | New July 2026 rule makes all state FFS rates public ([42 CFR 447.203](https://www.ecfr.gov/current/title-42/chapter-IV/subchapter-C/part-447/subpart-B/section-447.203)), a genuine LLM-parsing opportunity. But states must also publish their *own* Medicare comparison analyses, and buyers (multi-state groups, consultants) are few with unclear willingness to pay. Revisit as a feature of Idea 1. |
| **HCPCS / code-change alerting** | Free from CMS quarterly; AAPC and EHR vendors push it to coders already. Willingness to pay is near zero. |
| **T-MSIS-based Medicaid analytics** | PHI, research-only data use agreement (DUA), about \$25k per seat. Commercial use is not permitted. |
| **Hospice/HHA license brokerage during the moratorium** | The moratorium also freezes majority changes of ownership ([Nixon Peabody](https://www.nixonpeabody.com/insights/alerts/2026/05/14/cms-hospice-and-home-health-agency-moratorium-impact-on-ma-and-ownership-changes)). Fraud-heavy segment (about 800 LA providers suspended, [CMS](https://www.cms.gov/newsroom/press-releases/cms-announces-aggressive-nationwide-crackdown-fraud-six-month-hospice-home-health-agency-enrollment)). Reputational and regulatory risk is too high. |
| **Plan-side (TPA) IDR exposure analytics** | Interesting (plans are the under-served side), but buyers are few large TPAs and carriers with in-house analytics, and sales cycles are long. Kept as a possible pivot for Idea 5. |
| **Revalidation lists sold as "leads" to billing companies** | Already on Apify ([link](https://apify.com/jserle/medicare-revalidation-due-leads)). Selling the list is a race to zero; selling the *outcome* (Idea 2) isn't. |

---

## 4. Ranked shortlist

Scores are 1–10; for competition, 10 = blue ocean. **Overall is a judgment-weighted score, not a simple average.** It weights willingness to pay, data accessibility and time to first dollar more heavily, because those match the brothers' model.

| Rank | Idea | Market size | WTP | Data access | Automation | Competition | Recurring | Time to first $ | **Overall** | Confidence |
|---|---|---|---|---|---|---|---|---|---|---|
| 1 | **Rate Gap Report** (TiC × Part B ghost-rate filter) for independent practices and PT/ASCs, plus billing-company white-label | 7 | 6 | 5 | 8 | 6 | 5 | 5 | **6.4** | Medium-low. The data pipeline and real buyer conversion are both untested. |
| 2 | **Medicare Enrollment Guard** (revalidation plus address-mismatch alerts with \$-at-risk) | 4 | 6 | 10 | 8 | 6 | 4 | 9 | **6.3** | Medium. Pain and data are verified; the price ceiling is low. |
| 3 | **Practice-acquisition screener** for LMM roll-ups (PT, optometry, derm, podiatry, ophthalmology) | 5 | 8 | 8 | 8 | 4 | 7 | 6 | **6.2** | Medium-low. Small buyer pool; Medicare blind spots. |
| 4 | **Nursing-home survey-window lead feed** | 4 | 4 | 9 | 9 | 6 | 7 | 6 | **5.6** | Low. Buyer count and budget unverified. |
| 5 | **IDR prep for small OON providers** | 8 | 8 | 6 | 5 | 4 | 7 | 3 | **5.4** | Medium on market, low on survivability (litigation, PHI, working capital). |
| 6 | **Employer network-rate benchmark via brokers** | 6 | 6 | 5 | 7 | 3 | 6 | 4 | **5.0** | Medium-low. Serif entered in July 2026. |
| 7 | **Exclusion/license monitoring** | 5 | 3 | 7 | 9 | 2 | 9 | 7 | **4.6** | High that it's a commodity. |
| 8 | **340B rebate reconciliation** | 4 | 6 | 3 | 4 | 5 | 7 | 2 | **3.6** | Low. Policy volatility. |

### Recommendation

**Build #2 and #1 as one brand aimed at the same buyer: the independent practice owner, or their billing company.**
- **#2 is the low-cost hook.** It needs only free data and has the fastest first dollar, about 30–45 days.
- **#1 is the higher-value upsell,** once the TiC pipeline is proven in one state.
- Both share NPPES and Doctors & Clinicians prospecting, the Part B join, the Claude report-writer and the outreach stack.

**#3 is a strong second line** if the M&A lane is also pursued: zero data cost and higher ARPA.

**Do not start with IDR** despite its large market: it is litigation-exposed, PHI-heavy and has a slow cash cycle.

**Gate before scaling:**
- #2 must reach at least 1% paid conversion on 3,000 contacts.
- #1 must have 30 hand-validated reports whose own-rates match what practices confirm.
- If neither gate is met within 90 days, kill this lane.

**Biggest unknowns, to resolve with cheap tests**
1. How CPT licensing applies to code-number-only reports. Get counsel for about \$1–2k.
2. Real TiC pipeline cost for one state. Prototype on one payer's table-of-contents file.
3. Whether the past-due rows still on the revalidation list represent truly deactivated enrollments. Spot-check them in PECOS.
4. Conversion of cold, dollar-quantified outreach to physicians. Their inboxes are heavily guarded by practice managers.
