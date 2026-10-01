# Verify-3: Adversarial verification of batch 3

*Date: 2026-10-01. Research only: no emails, signups, outreach or purchases.*

**Method.**
- The originals were read from `research/07-govcon` (ideas A, B, C), `research/11-wildcards` (#1, #2) and `research/05-property` (ideas 1, 2, 4).
- Each idea was re-checked by an independent verifier using fresh web searches (~180 total), WebFetch on primary documents, and live downloads where possible:
  - FAC API calls;
  - FAC web search counts;
  - DBPR condo, elevator and CAM CSVs downloaded and parsed with curl;
  - Census of Governments tables.
- Claims that could not be verified are listed as such.

## Executive summary

| # | Idea | Original score | Verdict | Revised score | Confidence |
|---|---|---|---|---|---|
| 1 | Single-audit Finding Fixer (07-A) | 7.1 | **WEAKENED** (near-KILLED as written) | **3/10** | Medium |
| 2 | Water Pipeline Radar + agenda-to-pipeline (07-B + 11-#1) | 6.9 / 6.7 | **WEAKENED** (near-KILLED as written) | **3/10** | Medium-high |
| 3 | Town Grant Desk, flat retainer (07-C) | 6.6 | **WEAKENED** | **4/10** | Medium |
| 4 | Florida Association Data Spine (05-1, 2, 4) | 7.0 / 6.3 / 5.8 | **WEAKENED**. Elevator product **KILLED** | **4/10** overall (1: 4.5, 2: 3, 4: 2) | Medium-high |
| 5 | Property-tax appeal evidence engine (11-#2) | 5.9 | **WEAKENED**. Path (a) near-KILLED | **3/10** | Medium-high |

**Nothing in this batch is CONFIRMED.** Four patterns repeat across the ideas:

1. **The moat claims were wrong.** Every write-up said something like "no direct competitor found." In every case one existed:
   - Single Audit Intelligence and GovtIntel (FAC findings);
   - EPIC and Bluefield (normalized SRF lists);
   - Civic IQ at $299/mo, including done-for-you pipeline (agendas);
   - Syncurrent at $49/mo and free state AI tools (grants);
   - HOA Contact Lists and Convex (condos and elevators);
   - AppealDesk at $49 and TaxNetUSA QuickAppeal (tax appeals).
2. **The "free public data" edge cuts both ways.** Buyers or free nonprofits can download the same files. Several products were essentially a cleaner copy of a CSV the buyer could fetch in one click.
3. **Timing kills the trigger.**
   - A single-audit corrective action plan is already written and filed by the time the finding becomes public.
   - An SRF priority-list project usually already has its engineer, because a Preliminary Engineering Report is required to get listed.
   - The Florida SIRS filing wave is past its deadline.
4. **Funding and regulatory tailwinds were overstated.**
   - BIL water money ended in FY26, and the FY27 request cuts the SRFs to $305M.
   - The PFAS 2031 extension is only proposed, not final.
   - Florida passed no new condo law in 2026.

---

## 1. Single-audit Finding Fixer (07-govcon, idea A)

**Verdict: WEAKENED, near-KILLED as a stand-alone business. Score 3/10 (was 7.1). Confidence: medium.**

The FAC data pipeline is real: the fields exist and emails are populated in a live call. The commercial premise fails on three counts:
- **The CAP already exists.** Under 2 CFR 200.511(c), the auditee prepares the corrective action plan *at the completion of the audit*, and it is filed in the FAC package. Every finding the outreach would cite already has a published plan.
- **The universe is about 5x smaller than "audits."** Only 17.5% of audits have any finding.
- **The deliverables are free or cheap elsewhere.** Templates are free (federal, state, LISC) or sell for $72–$100. SAM exclusion checks are free. The auditor itself may give best-practice advice.

### Claims checked

| Original claim | Finding | Source | Holds? |
|---|---|---|---|
| FAC API has `general`, `findings`, `findings_text`, `corrective_action_plans` | Confirmed; the dictionary lists 11 endpoints | https://www.fac.gov/api/dictionary/ | Yes |
| API "includes `auditee_email`, `auditee_phone`, contact title, auditor firm and auditor email" | Confirmed and populated in a live `curl https://api.fac.gov/general?limit=1` call (a real school-district email was returned). The blank rate could not be measured because the API was rate-limited. | https://api.fac.gov/general?limit=1 ; https://apify.com/scrapesage/single-audit-leads-scraper | Yes |
| Data works for all segments, including tribes | Tribes may opt out under 2 CFR 200.512(b)(2). Their finding text and CAPs are then hidden (`is_public=false`), and access needs a Tribal API Access Agreement. | https://www.fac.gov/api/tribal/ ; https://www.fac.gov/tribal/ | Partly |
| DEMO_KEY is "about 10 requests/hour, so get a real key" | DEMO_KEY: 30/hour and 50/day per IP; the live header showed limit 10, then a 429 with an ~11-hour retry. A registered key gets 1,000/hour. The FAC terms page has no explicit commercial or solicitation ban. | https://api.data.gov/docs/developer-manual/ ; https://www.fac.gov/api/terms/ | Yes |
| "46,650 audits" for AY2024 | Exactly 46,650 (FAC search). AY2023 had 47,927; AY2025 has 40,001 so far, still filling. | https://app.fac.gov/dissemination/search/ | Yes |
| "77,653 finding rows; 26,728 repeat-finding rows (~34%)"; "assume 25–35% have at least one finding → ~12k–16k entities" | **Wrong unit.** Only **8,187 of 46,650 audits (17.5%)** have any finding; 3,122 have a repeat finding; 3,125 a material weakness; 1,675 questioned costs. Row counts inflate the market about 9.5x per affected audit. The row totals themselves were not re-verified (rate limit). | https://app.fac.gov/dissemination/search/ ; https://www.fac.gov/search-resources/filters/ | **No**: the universe is ~8.2k, not 12–16k |
| GAO: ~40k single audits per year | GAO gives "about 40,000" and "approximately 35,000 to 40,000" | https://www.gao.gov/assets/gao-24-106173.pdf | Yes |
| $1M threshold "shrink[s] the universe by ~15%" | The threshold rise is confirmed (fiscal years beginning on or after 2024-10-01). The final rule contains no 15% estimate. | https://www.govinfo.gov/content/pkg/FR-2024-04-22/pdf/2024-07496.pdf | Unverified |
| "Auditors cannot remediate for their own attest clients … so they need someone to refer to" | Half true. GAGAS 3.43d flags an auditor preparing management's CAP as a threat, and 3.81 makes setting policies a management responsibility. But GAGAS 3.70–3.71 and AICPA ET 1.295.105 allow routine advice, research materials and best practices. **Any other CPA firm can remediate freely**, so the referral naturally goes to a peer CPA firm. | https://www.gao.gov/assets/gao-18-568g.pdf | Weak |
| Implied: the prospect needs a CAP drafted | 2 CFR 200.511(c): "At the completion of the audit, the auditee must prepare a corrective action plan." The CAP is already in the FAC package. | https://www.govinfo.gov/content/pkg/FR-2024-04-22/pdf/2024-07496.pdf | **No** |
| "Nobody turns FAC findings into a pre-built fix today"; "no direct findings-to-fix productized service" | **Wrong.** Single Audit Intelligence searches and monitors FAC findings and CAPs. GovtIntel (DWU Consulting) is an AI grant-compliance back office built on FAC finding patterns. JS Grants & Compliance sells 2 CFR 200 procurement templates plus a dashboard subscription. CLA and other CPA firms sell remediation. The Apify actor is explicitly pitched to CPA firms for "findings that need remediation help". | https://www.singleauditintel.com/ ; https://govtintel.com/articles/common-single-audit-findings ; https://jsgrantconsulting.com/ ; https://www.claconnect.com/en/resources/tools/resources-to-ease-the-burden-of-grant-compliance | **No** |
| Single audits cost $22k–$26k for a $10M nonprofit | Plausible (vendor guides: $10k–$50k, with single audits adding 25–50%). No primary source found. | https://www.bpm.com/insights/single-audit-threshold-2025-nonprofits/ | Roughly |
| 1,500 emails → 2% reply → 0.5% purchase (~7 packs) | Benchmarks: ~3.4% average reply rate. The 12–16% "nonprofit" figures are vendor claims. 7 sales on 1,500 emails is about $19k–$45k one-time. Citing someone's audit finding in a cold email to a public body creates a public record that reads as shaming. | https://belkins.io/blog/cold-email-response-rates ; https://instantly.ai/blog/email-sequence-benchmarks-2026-whats-a-good-open-rate-reply-rate-and-cost-per-meeting/ | Optimistic |
| "3–5% capture → $1.5M–$3.4M ARR" | Nonprofit, local and tribal audits with findings: 3,750 + 3,286 + 246 = **7,282**. 3–5% of that is 220–365 accounts, or $0.66M–$2.6M ARR, *if every account also subscribes*. Hitting $3.4M needs about 9% capture. The $1M–$20M expenditure filter shrinks it further. | Derived from FAC search counts | **No** |
| SAM exclusion checks as subscription value | SAM exclusion search is free and public | https://sam.gov/content/exclusions | Weak value |
| Policy templates "cheap" (kill risk 2) | Confirmed and worse than stated. BizManualz is $99.99, the Thompson desk guide $71.99, and LISC, DOE and Head Start templates are free. Washington SAO gives free procurement and internal-control help. | https://www.bizmanualz.com/non-profit/not-for-profit/nonprofit-policies-procedures-manual ; https://www.thompsongrants.com/desktop-guides ; https://www.energy.gov/management/articles/corrective-action-plan-template-single-profit-audits ; https://sao.wa.gov/improving-government/center-government-innovation | Yes, as a risk |
| Legal: "avoid the words 'audit' or 'CPA'" | Confirmed. UAA §14 bars titles implying "special competence as an accountant or auditor". CAN-SPAM has no B2B exemption. | https://nasba.org/app/uploads/2018/02/Uniform-Accountancy-Act-%E2%80%93-Eighth-Edition-%E2%80%93-January-2018.pdf ; https://www.ftc.gov/business-guidance/resources/can-spam-act-compliance-guide-business | Yes |

**AY2024 market mix (FAC search).**

| Segment | Audits | With findings |
|---|---|---|
| Nonprofits | 22,860 | 3,750 |
| Local governments | 20,275 | 3,286 |
| Tribes | 665 | 246 |
| Higher education | 1,755 | — |
| States | 875 | — |

### New competitors and risks
- **Competitors:**
  - Single Audit Intelligence (pricing not retrieved; 403)
  - GovtIntel / DWU Consulting
  - JS Grants & Compliance
  - Copedia Uniform Guidance Edition (200+ templates)
  - Euna Grants / AmpliFund (from about $15k/yr; https://www.capterra.com/p/122370/AmpliFund/)
  - CPA firms (CLA, CBIZ, Plante Moran, BDO, Wipfli)
  - Apify FAC actors at $3.86 per 1,000 records
- **Timing risk:** findings reach the FAC up to 9 months after fiscal year end, so outreach lands near the next audit.
- **Liability:** an AI-drafted federal-compliance policy without CPA or attorney review.

### What would make it viable
1. **Sell CAP implementation, not CAP drafting.** Target the 3,122 audits with *repeat* findings: "your auditor retests finding 2024-00X in N months."
2. **Flip the buyer to CPA firms and consultants.** Offer white-label remediation kits plus FAC-driven prospect lists. CPA firms are the ones who need referral partners and leads.
3. **Narrow to one finding type and price like a template.** Pick procurement or subrecipient monitoring, priced at $300–$900, with bespoke work routed to a CPA partner.
4. **Drop the SAM-check desk.** Use no "audit" branding, and exclude tribes with `is_public=false`.

**Most likely failure mode:** finance directors will not pay $2.5k–$6k to fix something they have already written a plan for. The free and $99 alternatives are abundant, and the cold email reads as "we read your audit findings."

---

## 2. Water Pipeline Radar + trade-specific agenda-to-pipeline (07-govcon B, merged with 11-wildcards #1)

**Verdict: WEAKENED, near-KILLED as written. Score 3/10 (was 6.9 / 6.7). Confidence: medium-high.**

Both moat claims fail:
- **The SRF lists are already normalized.** EPIC does it for free with open-source code; Bluefield sells it.
- **The agenda-to-pipeline space is crowded.** Several funded firms are in it, including one with a $299/mo self-serve tier and a done-for-you SDR service.

The funding story also reverses: FY26 was the last BIL year, and earmarks consumed most of the regular SRF base. Engineers, the core buyer, are usually already retained before a project appears on a priority list.

### Claims checked

| Original claim | Finding | Source | Holds? |
|---|---|---|---|
| "I found no product that normalizes all states' lists" | **Wrong.** EPIC's DWSRF Funding Tracker standardizes IUP and priority-list data. Its pipeline spans 50 states, is free, and the code is on GitHub. | https://www.policyinnovation.org/insights/understanding-state-by-state-differences-in-iups-and-project-lists-findings-from-epics-dwsrf-funding-tracker ; https://github.com/Environmental-Policy-Innovation-Center/dw-dashboard | **No** |
| Same, on the commercial side | Bluefield Research sells an SRF dashboard covering funded projects plus "IUP Project Requests" (applicant and requested $ by state), and CIP data for 725+ utilities | https://www.bluefieldresearch.com/data/state-revolving-fund-data/ ; https://www.bluefieldresearch.com/data/utility-capital-improvement-plan-2/ | **No** |
| Implied: no national project-level SRF data | EPA's SRF Public Portal publishes downloadable project-level data (post-award, since 2021) | https://www.asdwa.org/2023/11/09/epa-unveils-two-new-public-tools-to-provide-easy-access-to-srf-data/ | Partly (the pre-award gap remains) |
| "Dodge/ConstructConnect … not water-specialized or SRF-normalized; fairly blue" | Dodge tracks from pre-planning (~$5k–$20k+/yr). ConstructConnect is $129–$199/mo. The water niche also has Bluefield, GWI Project Tracker (~$2,280/yr for 10 users) and EPIC. | https://constructionbids.ai/blog/dodge-construction-network-alternative ; https://www.globalwaterintel.com/memberships | Partly. Not blue. |
| "FY2026 SRF is $7.2B" | Confirmed (base + IIJA allotments) | https://www.epa.gov/system/files/documents/2026-04/fy-2026-joint-srf-allotments-memorandum.pdf | Yes |
| Implied healthy base funding | Earmarks took most of the base. CWSRF: $1.639B minus $892.8M in earmarks leaves $746M. DWSRF: $715.4M of $1.126B (64%) was earmarks. Earmarks bypass IUPs. | https://www.everycrsreport.com/reports/IF13177.html ; https://www.policyinnovation.org/insights/srf-earmarks-reduce-set-aside-funds-for-all-states-fy2023-fy2026 | **No** |
| "Final year of BIL supplemental money" | True. IIJA water authorizations expired 2026-09-30. | https://www.smartcitiesdive.com/news/cities-push-congress-avert-water-infrastructure-funding-cliff-nlc/821608/ | Yes, and it hurts the idea |
| FY27 outlook (not in the original) | The President's FY27 request cuts the SRFs from about $2.7B to **$305M**. The House FY27 bill cuts them by about $662M (~24%). | https://www.waterworld.com/water-utility-management/news/55368873/white-house-proposes-significant-cuts-to-epa-srfs-in-fy-27-budget-proposal ; https://www.environmentalprotectionnetwork.org/20260521_house-fy27-epa-funding-bill_release/ | Funding shrinking |
| "PFOA/PFOS compliance moved to 2031" | **Premature.** It is a *proposal* (comments closed 2026-07-20). The 2024 rule remains in effect: monitoring by 2027-04-26 and MCLs by 2029-04-26. The D.C. Circuit denied EPA's motions to vacate and sever. | https://pfas.pillsburylaw.com/epa-cercla-drinking-water-regulatory-fight/ ; https://www.asdwa.org/2026/01/22/dc-court-denies-epas-motion-to-vacate-hazard-index-pfas-from-drinking-water-rule/ | **No** |
| LCRI compliance date 2027-11-01 | Confirmed. The AWWA challenge is pending, with no delay so far. | https://www.federalregister.gov/documents/2024/10/30/2024-23549/national-primary-drinking-water-regulations-for-lead-and-copper-improvements-lcri | Yes (litigation risk) |
| IUPs give engineers a 6–30 month head start; "many IUPs list the consulting engineer of record" | Mostly too late for engineers. Iowa, Indiana and Vermont require a Preliminary Engineering Report or facility plan *before* a project is listed, so the engineer is already hired. Only planning and design loan lines are early signals. | https://opportunityiowa.gov/media/6795/download?inline= ; https://www.in.gov/ifa/srf/files/dwsrf-per-guidance-updated-gpr.pdf ; https://dec.vermont.gov/water-investment/water-financing/srf/step-1-state-revolving-fund-planning-and-preliminary-0 | **No** for engineers; Yes for equipment reps and contractors |
| PDF extraction is manageable | EPIC found many states publish only static PDFs, with inconsistent naming, "fundable" vs "comprehensive" lists, and 1–2 years of archives | (EPIC link above) | Partly |
| Agenda competitors: "Curate (… small SMB footprint), Starbridge and Pursuit (enterprise), Hamlet" | Understated. Curate covers 12k+ entities from **$295/user/mo**. Starbridge has raised $53.8M and covers 320k+ entities. Pursuit raised $22M in April 2026. Hamlet covers 3,000+ governments with a free tier. | https://www.capterra.com/p/253803/Curate/ ; https://techcrunch.com/2026/04/29/bill-gurley-jack-altman-back-startup-pursuit-which-helps-companies-sell-to-government/ ; https://www.publicceo.com/2026/02/hamlet-launches-nationwide-public-meeting-coverage-over-3000-local-governments-videos-now-discoverable/ | **No** |
| "Nobody packages it per trade with done-for-you outreach for small vendors" | **Wrong.** Civic IQ: $299 / $899/mo, plus "Pipeline-as-a-Service" from $2k/mo with human SDRs. Also NationGraph ($18M raised), BidSparq ($199–249/mo), CitizenPortal.ai ($15/mo Pro), and Apify Legistar agenda-radar actors. | https://bidsparq.com/alternatives/starbridge ; https://www.pursuit.us/blog/pursuit-us-the-best-civiciq-alternative ; https://www.govtech.com/biz/ai-procurement-intel-platform-nationgraph-raises-18m ; https://apify.com/opalescent_game/legistar-agenda-radar | **No** (only the per-trade cut remains open) |
| Implied: GovSpend is a bid/PO tool only | GovSpend has a Meeting Intelligence module (transcript search plus alerts), median ~$11.6k/yr | https://govspend.com/webinars/get-to-know-meeting-intelligence-customer-training-webinar/ ; https://www.vendr.com/marketplace/gov-spend | **No** |
| School boards as a gap | Quorum Local scans about 3,000 school-board agendas. The open-source civic-scraper already handles CivicPlus, Legistar, Granicus, PrimeGov and CivicClerk. | https://www.quorum.us/products/school-board/ ; https://civic-scraper.readthedocs.io/en/latest/usage.html | **No** |
| CAC $150–400 | Average cold-email reply rate is 3.43%; construction is about 0.6% in one dataset. At about 1% reply and 10% reply-to-paid, CAC is well above $400. | https://instantly.ai/cold-email-benchmark-report-2026 ; https://growthengineer.ai/blog/cold-email-reply-rate-benchmarks-2026 | Unproven, likely low |
| Legistar is freely crawlable | The Web API is public, but "some clients require use of API tokens." Granicus scraping ToS not found. | https://webapi.legistar.com/Home/Examples | Partly |
| ~6k–8k accounts | Unverified. WEF and AWWA don't publish firm counts, and the Census CBP API needs a key. The pool is probably smaller once engineers are discounted. | https://wwema.org/membership/ | Unverified, probably high |

### New competitors and risks
- **Competitors:**
  - EPIC (free)
  - Bluefield SRF and CIP dashboards
  - GWI Project Tracker (~$2,280/yr)
  - Civic IQ ($299–$899/mo, plus $2k/mo outbound)
  - NationGraph
  - GovSpend Meetings
  - Quorum Local
  - CitizenPortal.ai
  - BidSparq
  - CivicSearch (free)
- **Risks:**
  - The FY27 funding cliff.
  - Earmarks route about $1.6B outside IUPs.
  - The PFAS and LCRI deadlines are legally unsettled.
  - Some Legistar tenants require tokens.

### What would make it viable
1. **Drop engineers as the core buyer.** Sell to water-equipment manufacturer reps and utility contractors, whose buying window comes *after* listing.
2. **Don't sell normalized SRF lists as the product.** EPIC and EPA give them away. Join what they lack into one project record: CWSRF coverage, USDA-RD, WIFIA, earmark line items, utility CIPs, board-agenda engineer awards and bid dates.
3. **Make it rep-territory-shaped** ("every pump and valve opportunity in your 3-state territory, with engineer of record"). Price it at $150–$400/mo, near GWI and ConstructConnect.
4. **For agendas, pick one trade the generalists serve badly** (e.g. playground and park equipment). Test against Civic IQ's $299 tier before building.
5. **Treat PFAS and LCRI as content, not as deadlines.**

**Most likely failure mode:** a near-commodity feed sold into a shrinking funding pool. The data is free (EPIC, EPA) or bundled into tools buyers already pay for. Engineers see IUP projects after they are hired. Cold conversion sits near 1%, and churn follows the first IUP cycle.

---

## 3. Town Grant Desk, flat retainer (07-govcon, idea C)

**Verdict: WEAKENED. Score 4/10 (was 6.6). Confidence: medium.**

What holds up:
- Towns do pay flat grant retainers in this price range.

What breaks:
- **Substitutes are everywhere and cheap or free:**
  - Syncurrent at $49/mo, partnered with municipal leagues;
  - Massachusetts' free GrantWell AI;
  - vendor-sponsored free help for public safety;
  - regional planning commissions that write grants at no charge.
- **The incumbents' per-grant pricing undercuts the Starter tier.**
- **Contingency and success-linked models do exist in the municipal market**, contrary to the original framing.
- **Cold email to clerks is the hardest part.** It has to lead to RFPs and council votes against firms with municipal references.

### Claims checked

| Original claim | Finding | Source | Holds? |
|---|---|---|---|
| "Grass Valley, CA: $3,800/mo fixed retainer (California Consulting)" | Confirmed (action sheet, 2026-01-13). Cut **from $4,400 to $3,800** with narrower scope. Year 1 cost about $53k and secured more than $300k. **Extended only 6 months "while further evaluating the effectiveness and return on investment."** That is a churn signal. | https://mccmeetingspublic.blob.core.usgovcloudapi.net/grassvalca-meet-0374476e648e4a8abb905c2df2cb2612/ITEM-Attachment-001-9fa92cf88d1e49419babdd3b574d9763.pdf | Yes, with an ROI caveat |
| "Selma, CA: $5,500/mo on-call retainer (Townsend Public Affairs)" | Figure confirmed (2026-09-01), but via an AI-summary site, not the minutes. Townsend is a **lobbying firm** bundling state and federal advocacy. Peers Hemet and Paso Robles pay $7,500/mo for advocacy plus grants. | https://citizenportal.ai/articles/9778890/California/Fresno-County/Selma-City/Selma-council-awards-primary-on-call-grant-writing-contract-to-Townsend-Public-Affairs ; https://www.townsendpa.com/services/ ; https://pub-pasorobles.escribemeetings.com/filestream.ashx?DocumentId=1176 | Partly. The scope is not comparable to grant writing alone. |
| "Ozawkie, KS: $2,100/mo retainer" | Confirmed (2025-01-13). An individual writer's past hourly billing was converted to a retainer. AI-summary source. | https://citizenportal.ai/articles/8635049/kansas/jefferson-county/ozawkie/council-approves-2100-monthly-retainer-to-keep-grant-writer-on-contract | Yes |
| "Needles, CA: $125/hr" | Confirmed (2026-05-26). Month-to-month and terminable on 30 days' notice, so towns can also buy hourly with no retainer. | https://mccmeetingspublic.blob.core.usgovcloudapi.net/needlesca-meet-3184a9dce7be4d81a75b0ab7ff4d27e6/ITEM-Attachment-001-0ff94f5fe2a944009f0e28dc6972dc20.pdf | Yes |
| (New anchor) Starter at $1,500/mo for 1 application per quarter | California Consulting's per-grant schedule to Sebastopol: **$1,500 (up to $10k grant), $4,000 ($10k–50k), $5,500 ($50k–100k), $7,500 ($100k–250k), $9k–12k (>$250k)**. Starter works out to about **$4,500 per application**, which is not cheaper for small grants. | https://www.cityofsebastopol.gov/wp-content/uploads/2023/01/Agenda-Item-Number-3-Award-of-Contract-Comprehensive-Grant-Writing-Services-CA-Consulting.pdf | Weakens the pricing claim |
| "GPA Code of Ethics item 19 bans [contingency]" | Confirmed via secondary quotes: "shall not accept or pay a finder's fee, commission, or percentage compensation based on grants." The GPA site returned 403. This is an ethics code, not law. | https://www.carpenternonprofitconsulting.com/blog/ethical-compensation-for-grant-writers ; https://grantprofessionals.org/page/ethics | Yes (not law) |
| "Many funders bar paying writers from the grant" (2 CFR) | 200.459 disallows consultant fees "contingent upon recovery of the costs from the Federal Government". 200.460 treats proposal costs as indirect, current-period costs. (200.415, cited in the brief, is "Required certifications" and is irrelevant.) | https://www.law.cornell.edu/cfr/text/2/200.459 ; https://www.law.cornell.edu/cfr/text/2/200.460 | Mostly |
| Implied: no contingency competitors exist | **False in practice.** ERI Grants advertises contingency fees to municipalities. GrantWorks (TX CDBG) writes the application and is paid via administration fees from the award (e.g., a $53,400 admin fee on a $750k Navasota request). | https://www.erigrants.com/our-fees ; https://citizenportal.ai/articles/9322821/Texas/Grimes-County/Navasota/Council-approves-GrantWorks-contract-to-support-CDBG-street-improvement-application | **No** |
| "~8k–12k" small active entities (towns of population 2.5k–25k) | 2022 Census of Governments Table 6: municipalities **5,264** (2,012 + 1,659 + 1,593) plus townships 3,677 = **~8,941**, before special districts | https://www2.census.gov/programs-surveys/gus/tables/2022/cog2022_cg2200org06.zip | Low end only (~5.3k excluding townships) |
| "Decision is by council vote" | City-manager signing limits are typically $25k–60k, so Starter ($18k/yr) can avoid a council vote but Pro ($36k/yr) usually can't. Grass Valley and Sebastopol ran **formal RFPs** with interview panels. | https://citizenportal.ai/articles/7181113/California/Napa-County/Saint-Helena/Council-raises-city-manager-signing-authority-to-60000-debates-safeguards | Partly |
| Kill risk: federal grant volatility | Mixed, not collapsing:<br>• BRIC was cancelled, then court-ordered restored (NOFO ordered March 2026).<br>• FY26 CDBG is $3.3B; FY26 earmarks are $3.62B.<br>• IIJA authorizations are extended to 2026-12-11.<br>• An OMB rule broadening grant terminations takes effect 2026-10-01 (NLC: deters small applicants). | https://www.floods.org/news-views/fema-news/fema-ordered-to-restart-bric-program/ ; https://ncrc.org/fy-2026-budget-deal-final-funding-for-hud-cdfi-sba-and-whats-next-for-dhs/ ; https://www.nlc.org/article/2026/06/17/new-omb-rules-for-grantees-could-override-local-authority/ | Confirmed as volatile |
| Free substitutes: "regional councils of governments, plus the state's own TA" | EPA's Thriving Communities TA Centers were terminated in 2025, and FY26 defunded the USDA Rural Partners Network. But regional planning commissions still write grants, some **at no charge** (Mid-Missouri RPC, Pioneer Valley PC). | https://greatlakestctac.umn.edu/great-lakes-thriving-communities-technical-assistance-center-suspends-services-following-epa ; https://ruralhome.org/usda-housing-funding-fy26/ ; https://www.midmorpc.org/services ; https://pvpc.org/program/ecd/municipal-grant-writing-and-management/ | Partly |
| Competitors: "AI tools (Grantable $50–$150/mo, Granted $19.99/mo), Euna Grants" | Missed: Syncurrent (**free / $49/mo per department**, AI grant discovery for small governments, partnered with the Michigan and Oregon municipal leagues); Massachusetts GrantWell (free state AI narrative drafting); Avila (local-government AI); and Lexipol's free GovGrantsHelp, FireGrantsHelp and PoliceGrantsHelp. Granted is now $29–$89. | https://www.syncurrent.com/pricing ; https://www.orcities.org/programs-services/services/syncurrent ; https://www.govtech.com/artificial-intelligence/massachusetts-uses-ai-to-help-cities-access-grant-funding ; https://www.getavila.ai/best-grant-management-software ; https://www.policegrantshelp.com/about/ ; https://grantedai.com/faq | **No**: undercounted |
| Cold email to managers and clerks | General B2B reply rate is about 3.4–4.5%; "government administration" about 3.8% (vendor data). Comptrollers warn towns about vendor-impostor emails, which raises suspicion of unknown vendors. | https://litemail.ai/blog/cold-email-reply-rate-by-industry-2026 ; https://www.macomptroller.org/announcement/vendor-imposter-scam-targeting-municipalities-vendors/ | Weak channel |
| "Lobbying registration may apply" | California's state PRA does not cover local lobbying, though some cities do (e.g. Oceanside). Texas registration applies to influencing state officials. Pure application writing is low risk; the Townsend-style advocacy bundle triggers registration. | https://www.fppc.ca.gov/learn/lobbying-rules/ ; https://www.ci.oceanside.ca.us/government/city-clerk/lobbyist-program | Low risk if no advocacy |

### Competitor prices found

| Competitor | Price | Source |
|---|---|---|
| Grant Writing USA, 2-day training | $525 | https://www.grantwritingusa.com/faq/ |
| California Consulting | $110–150/hr, $1.5k–12k per grant, or $3.8k–4.4k/mo | Sebastopol schedule above |
| Townsend | $5k–7.5k/mo, bundled with advocacy | Selma, Hemet, Paso Robles above |
| Euna Grants / eCivis | ~$30k–102k/yr | https://www.erpresearch.com/erp-add-ons/nonprofit/euna-grants |
| GrantStation | $199/yr | https://grantsights.com/blog/grantstation-review-alternative-2026 |
| Part-time writer (20 hr/week at $18–42/hr) | ~$36k/yr | https://www.indeed.com/career/grant-writer/salaries |

### What would make it viable
1. **Change the channel.** Use state municipal leagues, regional planning commissions and councils of governments as white-label partners instead of cold email (the Syncurrent playbook).
2. **Use hybrid pricing.**
   - A $300–500/mo monitoring retainer.
   - Per-application fees on California Consulting's scale.
   - Optionally, post-award *administration* paid from eligible admin budgets (the GrantWorks model), never a percentage for writing.
3. **Specialize in one program family and one state** (e.g. TxCDBG, SRF water, SS4A, AFG fire). Win rate and references are everything.
4. **Be RFP-ready** with a statement of qualifications, and send a quarterly ROI report so the 6-month review doesn't end the contract.

**Most likely failure mode:** sales and retention, not the writing. The free Funding Map is available elsewhere at $0–$49/mo. Interested towns still have to run an RFP or a council vote to buy from an unknown firm with no municipal references, and they review ROI within 6–12 months. One lost cycle or a federal freeze makes the retainer look like pure cost.

---

## 4. Florida Association Data Spine (05-property, ideas 1, 2 and 4)

**Verdict: spine overall WEAKENED, 4/10 (was 7.0). Confidence: medium-high.**
- (1) Capital-Event Feed: **WEAKENED, 4.5/10**
- (2) CAM switch-signal: **WEAKENED, near-KILLED, 3/10**
- (4) Elevator Conveyance Intel: **KILLED, 2/10** at the stated price and scale

The data is real, free and downloadable, and that is the problem: buyers can fetch it too. Three findings come from parsing the downloaded files:
- The condo CSV's "managing entity" is the **association**, not the CAM firm.
- The SIRS wave is past its deadline, and 2026 brought no new condo law.
- The buyer pools are tiny, and the vendor choice is controlled by someone else: engineers run the restoration bids, boards run CAM RFPs, and four OEMs hold about 65% of elevator service.

### Live data checks (curl, 2026-10-01)
**Condo CSVs.** Five regional files, 27,972 projects in total.
- In `Condo_MD.csv`, 5,818 of 5,821 "Managing Entity Number" values are `MA…` association numbers.
- A CAM firm appears only as a "C/O" mailing line, in 50.2% of rows statewide. Some of these are law firms, and some may be stale.

**`elevator.csv`.** 69,423 rows, modified 2026-09-27.
- It does contain the SERV/NSRV flag, the maintenance company name and license, the install year, the last passed inspection date and the building type.
- There is **no contract expiry date or contract value**.
- Otis, KONE, TKE and Schindler maintain 65.5% of elevators with a named maintenance company, and 48.8% of the 15,707 condo elevators.
- Only **80 independents maintain 50 or more units, and 22 maintain 200 or more**.
- `company.csv` lists 569 registered elevator companies (405 current).

**`lic38cam.csv`.** 2,040 CAM firms and 24,169 individual CAMs.

**SIRS database.** Two Qlik Sense dashboards rendered over JavaScript/websockets. No export link was found.

### Claims checked

| Original claim | Finding | Source | Holds? |
|---|---|---|---|
| DBPR "condo associations by county (name, address, units, managing entity) as free CSVs" | Five *regional* CSVs (not county files). The "Managing Entity" field is the association itself; the CAM firm appears only as a C/O line in 50.2% of rows. | https://www2.myfloridalicense.com/condos-timeshares-mobile-homes/public-records/ ; https://www2.myfloridalicense.com/sto/file_download/extracts/Condo_MD.csv | Partly. Misleading for product 2. |
| SIRS DB is a public web view updated within one business day; bulk export unverified | Confirmed: Qlik dashboards, "displayed exactly as submitted". No export. The reporting form captures who performed the SIRS and its cost, which is useful competitive intelligence. | https://www2.myfloridalicense.com/condos-timeshares-mobile-homes/condominiums-and-cooperatives-sirs-reporting/ ; https://www2.myfloridalicense.com/lsc/documents/E-Structural%20Integrity%20Reserve%20Study.pdf | Holds. Export still unverified. |
| Elevator registry "names each elevator's current maintenance contractor" | Confirmed in the downloaded header, but with no contract term or expiry field | https://www2.myfloridalicense.com/sto/file_download/extracts/elevator.csv | Holds, but free to everyone |
| Sunbiz bulk files are free via SFTP and include officers | Free (public credentials). Up to 6 officers plus the registered agent. | https://dos.fl.gov/sunbiz/other-services/data-downloads/ ; https://dos.sunbiz.org/data-definitions/cor.html | Holds |
| "2,001 licensed CAM firms" | 2,040 CAB records in the DBPR file, mostly micro-firms | https://www2.myfloridalicense.com/sto/file_download/extracts/lic38cam.csv | Holds (+2%) |
| ~27,750 associations; 11,270 with 3+ stories | 27,972 projects in the CSVs. The 11,270 figure is self-reported (February 2025). | https://citizenportal.ai/articles/6325346/Florida/2025-Legislature-FL/DBPR-says-SIRS-database-is-live-but-incomplete-agency-lacks-strong-enforcement-power | Holds, with caveats |
| ~7,836 SIRS submissions by 2025-11-30 | Not found in a primary source. The latest primary figure is 4,096 (2025-02-10). | same | Unverified |
| DBPR online-portal data (since July 2025): "whether this is public is unverified" | The HB 913 account collects the CAM firm, stories, units, special assessments, banks and board members. No public view was found. A ch. 119 request might obtain it (untested). | https://www.flsenate.gov/Session/Bill/2025/913/Analyses/h0913z1.HAT.PDF ; https://condos.myfloridalicense.com/faqs/ | Holds. This is the one possible proprietary edge. |
| Implied: regulation keeps creating events; "the legislature changes the rules again" | 2026 session: **no** new condo or HOA law. HB 657 died; HB 465 (mandatory CAM firm) died in committee. | https://advocacy.caionline.org/2026fleos/ | Weakened |
| "No direct B2B competitor found. Moderately blue ocean." | **Wrong.** HOA Contact Lists sells 200k+ verified FL board contacts across 49k associations. HOA-USA reaches 44k board and manager subscribers and sells mailing lists. PropFusion runs a free reserve-study proposal marketplace. CAMbrands runs a two-sided board/CAM RFP marketplace. | https://hoacontactlists.com/hoa-database/florida/ ; https://hoa-usa.com/advertise/ ; https://www.propfusion.com/law-guide/florida-sirs-requirements ; https://cambrands.com/ | **No** |
| CAM switch-signal: "No signal-based product found" | No signal product found. But boards switch managers through RFPs to 2–5 firms, and directories capture that inbound demand. | https://hoa-usa.com/florida-hoa-management-companies/ ; https://empirehoa.com/2026/02/09/hoa-management-company-transition-florida/ | Partly |
| Elevators: "no direct product found beyond raw-data tools" | **Wrong.** Convex sells sales intelligence for elevator independents, including estimated contract-renewal windows. | https://www.convex.com/solutions-elevator-industry | **No** |
| "No direct evidence yet that FL engineering firms buy lead feeds" | Still none. Engineers write the restoration bid packages, so contractors depend on them. FirstService FL makes vendors pay $90/yr for credentialing to get bid access, so CAMs gatekeep vendors. | https://www.teamues.com/concrete-restoration-design-and-inspections/ ; https://www.bcscoi.com/fsresidential/fl/ | Holds, and it hurts the idea |
| Market: "60–150 subscribers × $500–$1,500/mo = $0.4M–$2.7M ARR" | Recount: about 80 viable elevator independents (22 sizeable), 2,040 mostly-micro CAM firms, and about 5,600 engineering businesses statewide with an unknown condo share. Realistic: **$0.1M–$0.4M ARR**. | DBPR files above ; https://fbpe.org/licensure/licensure-process/engineering-firms/ | **No** |
| Florida email law §668.606 "allows private suits" | Confirmed, and active. $500 per email in liquidated damages; subject-line class actions arrived in Florida in April 2026. No B2B exemption. | https://www.ballardspahr.com/insights/alerts-and-articles/2026/04/trouble-in-paradise-subject-line-class-actions-come-to-florida | Risk confirmed |
| FTSA: "don't text or autodial" | Since 2023 it covers calls and texts that use automated "selection and dialing", with no B2B carve-out | https://www.mcguirewoods.com/client-resources/alerts/2023/5/pro-business-amendments-to-floridas-mini-tcpa-now-in-effect/ | Holds |
| Data-broker registration (not addressed) | Florida has none. CA, VT, TX, OR and CT register brokers, but those laws cover consumer data on their residents. | https://privacylawmap.com/blog/data-broker-registration-requirements-2026 | No registration needed |
| Durability: "urgency is a one-time spike" | Confirmed. The study phase is over; a repair-phase tail runs through about 2026–2028. Condo supply is at 13.2 months and prices are down 6.1% YoY. 5.1% of 25,225 South Florida listings disclose unresolved assessment or SIRS work. | https://longyield.substack.com/p/florida-housing-in-2026-bubble-normalization ; https://www.pbprealestate.com/condo-assessment-stress-index/ | Holds |

### What would make it viable
1. **Kill elevators as a standalone product.** At most, offer a $99–199/mo change alert (SERV/NSRV changes, delinquent certificates).
2. **Reposition product 1 as competitive intelligence for engineering and reserve-study firms.** The SIRS DB shows who performed each study and at what cost, so sell provider share and pricing by county, "3+ story with no SIRS on file," and "SIRS done → repair-phase candidates." Sell restoration contractors the map of **which engineer controls which building**, since the engineer is the real gatekeeper.
3. **File a ch. 119 request for the HB 913 online-account dataset.** If granted, it supplies the CAM-firm field and makes product 2 real. If refused, product 2 is not viable.
4. **Re-plan for $0.1M–$0.4M ARR in Florida**, or expand to other post-Surfside states (NJ reserve studies, CA SB 721).
5. **Write compliant subject lines** (FEMCA class-action risk) and phrase outputs as "not found in DBPR DB as of <date>" (defamation risk).

**Most likely failure mode:** buyers already have the same free files, and the decisions the leads target are made by engineers, boards and OEM contracts. Leads rarely convert, so subscribers churn within 2–3 months as the SIRS wave fades.

---

## 5. Property-tax appeal evidence engine (11-wildcards, #2)

**Verdict: WEAKENED. Path (a), SaaS packets, is near-KILLED. Score 3/10 (was 5.9). Confidence: medium-high.**

- **The packet is a $49 commodity.** AppealDesk sells it in 50 states, Ownwell has a nationwide AI "National Appeals Packet," and Texas consultants already use TaxNetUSA QuickAppeal and Property Tax Pilot.
- **The partner model collides with licensing.** Texas requires registration of anyone who "assists" a consultant and earns more than 50% of their income from it. Attorney-only venues (Cook County, NJ entities over $25k in taxes, NY Article 7) bar fee splits.
- **Expected revenue is roughly a third of plan.**

### Claims checked

| Original claim | Finding | Source | Holds? |
|---|---|---|---|
| "Ownwell raised a $50M Series B in Feb 2026" | 2026-02-19: $30M equity (Alpha Edison, Mercato) plus $20M debt (Western Alliance) | https://www.prnewswire.com/news-releases/ownwell-raises-50m-launches-national-service-to-streamline-property-tax-appeals-and-make-home-ownership-more-affordable-302692103.html | Partly (only $30M is equity) |
| "$74M raised" (05-property) | The release says $74M to date, including the debt | same | Yes, with caveat |
| "88% success rate"; "1MM appeals since 2021" | The release says **86%**; 88% appears only on third-party sites. More than 1M appeals and $400M+ saved, $774 average. | same ; https://www.howtomoney.com/ownwell-review/ | Roughly |
| "expanding into commercial in 7 states" vs "9 states" | 7 primary markets (TX, IL, FL, GA, CA, WA, NY), 9 in the FAQ. **Ownwell Commercial is already live** (10k+ businesses), and a National Appeals Packet launched nationwide. | https://www.ownwell.com/faqs ; https://www.ownwell.com/commercial | "Expanding" understates it |
| "Ownwell 25%" | 25–35% by state; about 33% for commercial on a secondary source; commercial is quote-based | https://www.ownwell.com/faqs ; https://www.moneycrashers.com/ownwell-review/ | Partly |
| "O'Connor 50% on commercial" | Confirmed: 50% (25% for owners 65+) | https://www.poconnor.com/wp-content/uploads/2023/06/Our-Terms.pdf | Yes |
| "Texas regionals 40%" | Range of 30–50% | https://www.ownwell.com/competitors/texas | Yes |
| "Texas requires a TDLR-registered consultant. Partner with an existing Texas registrant instead." | Occ. Code 1152 requires registration for consulting "for compensation". A person who *assists* a registrant and earns more than 50% of their income from it must also register. A revenue-shared evidence engine likely triggers this. | https://texas.public.law/statutes/tex._occ._code_section_1152.001 ; https://www.tdlr.texas.gov/ptc/ptcfaq.htm | Yes, and it reaches the brothers |
| Revenue share with a Texas registrant | No explicit referral-fee ban found. 16 TAC 66.100 bars evasion schemes, lending a registration, payment for services not performed, misleading solicitation, and advertising results without prior analysis (m). This rests on a 2014 compilation; the current text is not verified. | https://allstarce.com/wp-content/uploads/2015/06/TX.-Admin-Code-Prop-Tax.pdf | High risk |
| Cook BOR Rule 1: entities need counsel | Confirmed | https://www.cookcountyboardofreview.com/about/frequently-asked-questions | Yes |
| "Connecticut bars attorney contingency fees on commercial appeals over $500k" | **Wrong threshold.** The bar applies to §12-117a appeals for commercial property **assessed at $1.5M or more** (2016). | https://codes.findlaw.com/ct/title-12-taxation/ct-gen-st-sect-12-117a/ ; https://www.cga.ct.gov/2016/TOB/h/2016HB-05183-R00-HB.htm | **No** |
| "Other states cap or prohibit contingency fees for consultants" | Not verified in general. **Indiana** requires disclosure of contingent fees and DLGF certification, but **no ban**. Florida allows any agent with an owner signature or POA. Michigan small claims allows non-attorney agents. | https://regulations.justia.com/states/indiana/title-50/article-15/rule-5/section-7 ; https://www.myfloridalegal.com/print/pdf/node/2223 ; https://www.michigan.gov/taxtrib/faq/small-claims-hearings-faq | Unverified |
| Attorney venues can't share fees (ABA Rule 5.4), "so use flat-fee SaaS" | Correct. Model Rule 7.2(b) also bars paying for referrals. Exceptions exist only in Arizona (alternative business structures) and Utah's regulatory sandbox. New Jersey entities with $25k+ in taxes need an attorney. NY SCAR excludes commercial property. | https://law.stanford.edu/2025/06/02/regulatory-innovation-at-the-crossroads-five-years-of-data-on-entity-regulation-reform-in-arizona-and-utah/ ; https://bergencountynj.gov/faq/tax-appeals/ ; https://www.nycourts.gov/small-claims-assessment-review-scar | Yes |
| "~3–5k property-tax consultants and attorneys nationally" | Texas alone has **2,216** registered consultants (FY2024). No national count found. | https://www.tdlr.texas.gov/media/pdf/PTC%20at%20a%20Glance.pdf | Unverified; the pool is small and concentrated |
| Comps from "recent comparable sales" | Texas is a **non-disclosure state**, so sale prices are not public. Firms use MLS and *equity* comps, which TaxNetUSA already automates. Cook County is fully open (sales, values, commercial valuation workbooks), so evidence there is a commodity. | https://www.dallasnews.com/news/watchdog/2020/06/04/why-fighting-your-property-tax-protest-is-so-hard-texas-hides-sales-numbers-from-public-view/ ; https://datacatalog.cookcountyil.gov/Property-Taxation/Assessor-Commercial-Valuation-Data/csik-bsws | Hurts the Texas comp engine |
| Postal mail "1% conversion → ~$100 CAC" | Prospect-list direct mail gets about 2–4.4% *response*. Signed agreements are a fraction of that, and incumbents already mail every Texas commercial owner each year. | https://directmail.io/direct-mail-response-rate | Plausible, unproven |
| "$600 per win … win rate ~60% → ~$360 per signed client" | Texas ARB commercial success is about **49%**. A realistic small-commercial saving is $1k–3k. At $2k × 33% fee × 40% share ≈ $264 per win, expected revenue is **≈$130 per signed client**. | https://www.ballardpropertytaxprotest.com/post/property-tax-protest-success-rates-texas | **No** (2–3x too high) |
| "First dollar may be 6–12 months away" | Confirmed. Texas hearings run May–August, bills go out around October, and fees are invoiced after that, so cash arrives about 6–9 months after the mail spend. | https://dallascad.org/Forms/Protest_Process.pdf | Yes |
| ~5.9M commercial buildings → 200k actionable → $180M pool | 5.9M matches CBECS. The rest is the original's own arithmetic and was not verified. | https://www.eia.gov/consumption/commercial/ | Unverified |

### New competitors and risks
- **Owner packets:**
  - AppealDesk ($49, 50 states, refund if fairly assessed; https://www.appealdesk.com/)
  - appealmytax.dev ($49)
  - hometaxappeal.us
  - Ownwell National Appeals Packet
- **Consultant SaaS:**
  - TaxNetUSA QuickAppeal (white-label TX/FL comp reports; TaxNetPRO $12.49/mo per county; https://www.taxnetusa.com/quickappeal/)
  - Property Tax Pilot (https://www.propertytaxpilot.com/)
  - Tax Appeal Plus (launched October 2025)
  - CSC AppealTrack
  - AppealPal
- **Incumbents:** Ryan, which absorbed Marvin F. Poer in 2022 (https://ryan.com/about-ryan/press-room/marvin-f-poer-and-company-acquisition/), and TaxProper (25%, California).
- **Reputation risk:** 42% of 70 Trustpilot reviews of Ownwell are 1-star, including complaints about fees on claimed savings (https://www.appealdesk.com/blog/ownwell-pricing-review).
- **Advertising rule:** Texas 66.100(m) constrains "you're over-assessed by $X" mailers.

### What would make it viable
1. **Become the licensed firm.** One brother registers with TDLR and keeps the full 30–40% fee. Compete on $300k–$3M small commercial at about 30% with no minimum, against O'Connor's 50%. This is a different business (a tax consultancy) but it avoids every fee-split problem.
2. **Use equity (unequal-appraisal) evidence in Texas**, where sales are non-disclosed.
3. **Drop path (a)**, and avoid Cook County, New Jersey and New York commercial. Look at Florida VAB (any agent with POA) and Michigan small claims next.
4. **Model a 9-month cash lag and a 49% win rate.** Use auto-renewing multi-year agreements to capture lifetime value.

**Most likely failure mode:** Texas consultants already get comps cheaply, and attorney venues can't share fees. Cold mail from an unregistered middleman converts below 1% against incumbents who mail every owner. At about $130 expected revenue per signed client, paid 6–9 months later, the mail spend is never recovered.

---

## Cross-idea ranking (batch 3)

| Rank | Idea | Revised score | Why it ranks here |
|---|---|---|---|
| 1 | **Town Grant Desk** (07-C) | 4/10 | The only idea with *proven, recurring, council-approved* willingness to pay at this price ($2.1k–$7.5k/mo retainers verified in minutes). Its failures are in channel and pricing, which can be fixed (league or COG partnerships, hybrid per-application pricing, one-program specialization). It is the least automatable, though. |
| 2 | **FL Association Data Spine**, product 1 only, repositioned as SIRS-provider and engineer-gatekeeper intelligence (05-1) | 4/10 (4.5 for product 1) | The data is verified and downloadable. It is a small-dollar business ($0.1M–$0.4M ARR) unless the ch. 119 HB 913 dataset comes through. Cheap to test: the CSVs are already parsed. |
| 3 | **Property-tax appeals** (11-#2), only as a self-registered Texas consultant | 3/10 | Real money and proven contingency WTP, but as specified (partner-based or SaaS) it fails. Viable only as a licensed consultancy with seasonal cash, which is a different business model from the brothers'. |
| 4 | **Finding Fixer** (07-A), pivoted to CPA firms as the buyer | 3/10 | Clean data and emails, but the CAP is already written, the universe is ~8.2k (not 46k), templates are free or under $100, and products using FAC data exist. The best salvage is B2B lead and white-label kits for CPA firms. |
| 5 | **Water Pipeline Radar + agenda-to-pipeline** (07-B / 11-#1) | 3/10 | The worst competitive position: free (EPIC, EPA) and funded (Bluefield, Civic IQ, Starbridge, Pursuit, NationGraph, GovSpend) players already cover both halves. The funding base is shrinking after BIL, and the core engineer buyer is too late in the cycle. Only a narrow per-trade, rep-territory niche remains. |

**Bottom line for the brothers.**
- None of these five should be built as specified.
- If one is tested, run the Town Grant Desk through a single state municipal league or COG partnership, with per-application pricing, in one program family (e.g. TxCDBG or SS4A). That tests the one claim with hard willingness-to-pay evidence.
- The Florida spine is the cheapest secondary test: one ch. 119 request plus a provider-share report sent to ~50 engineering firms.

### Verification limits
- The FAC API was rate-limited after one DEMO_KEY call, so the row-level finding counts (77,653 / 26,728) and the email blank rate were not re-run.
- Export from the SIRS Qlik dashboards was not tested.
- Pricing could not be found for Single Audit Intelligence, Bluefield, Starbridge, Pursuit, Convex, HOA-USA or HOA Contact Lists.
- The FY27 Senate SRF figures and whether FY27 appropriations have been enacted were not found.
- The GPA ethics page returned 403, so item 19 is confirmed via secondary sources only.
- The Selma, Ozawkie and Navasota contract figures come from AI-summary sites (citizenportal.ai), not the primary minutes.
- The current text of 16 TAC 66.100 was not fetched; a 2014 compilation was used.
