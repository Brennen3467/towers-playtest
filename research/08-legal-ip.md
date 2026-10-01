# Lane 08: Legal, Litigation and IP Data

*Research date: 2026-10-01. Research only: no outreach, signups or purchases were made. Every material claim cites a URL. Anything marked **(est.)** is my own estimate and is not a sourced figure.*

---

## TL;DR

- This lane has more data than any other, but the obvious plays are already taken. Docket monitoring, trademark watching, brand protection, mass-tort intelligence, DMCA takedowns and securities-settlement filing all have funded incumbents. Some of them already sell "AI" versions of exactly what a Claude pipeline would build.
- The gaps that remain are **ticket sizes too small for manual work** and **segments the incumbents' sales motion can't reach profitably**:
  - pro-se trademark applicants
  - mid-market and SMB recoveries of unclaimed property and court funds
  - trade creditors in small Chapter 11 cases
  - local businesses swept into antitrust settlement classes
- Two things decide most outcomes here: the **regulatory wrapper** (unauthorized practice of law, attorney-advertising rules, state finder statutes, court orders on third-party claim filers) and the long history of **USPTO scam solicitations**. Get the wrapper wrong and the whole idea dies.
- Best ideas, in order:
  1. **Pro-se trademark office-action opportunity feed sold to trademark attorneys** (overall 6.6)
  2. **B2B "found money" sweep (state unclaimed property plus bankruptcy-court unclaimed funds), sold through CPA firms** (6.2)
  3. **ADA website-lawsuit signals feeding the brothers' existing site-rebuild engine** (6.0)
- Nothing in this lane scores 8 or higher. My honest view: this is a **good adjacent lane, not a blue ocean**.

---

## 1. Lane overview

### 1.1 The data landscape (access, cost, limits)

| Source | What's in it | Access | Cost | Key limits |
|---|---|---|---|---|
| USPTO trademark bulk XML and TSDR/ODP APIs | Every prosecution event, published daily. July 2026 alone had 1,108,850 case-file transactions in 31 files ([patent.dev](https://patent.dev/uspto-odp-go-client-office-action-and-trademark-apis/)). Office-action text API, 2018 onward, with a 180-day lag (same source). | Bulk download plus API key ([USPTO bulk data](https://www.uspto.gov/trademarks/trademark-updates-and-announcements/trademark-bulk-data-us-patent-and-trademark-office); [TSDR API key guide](https://www.uspto.gov/sites/default/files/documents/tm-enterprise-api-user-guide-v2.pdf)) | Free | 60 status requests per minute per key, 4 PDF requests per minute ([patent.dev](https://patent.dev/uspto-odp-go-client-office-action-and-trademark-apis/)). Owner email is **masked when the owner has counsel, but still visible for unrepresented owners** ([USPTO](https://www.uspto.gov/subscription-center/2020/owner-email-address-field-now-masked-teas-and-teasi-documents-tsdr)). |
| TTAB / Official Gazette | Oppositions, extensions of time to oppose, cancellations. Published weekly. | TTABVUE, bulk | Free | FY2025: 7,650 oppositions, 19,130 extensions, 2,897 cancellations ([trademarkraft](https://trademarkraft.com/blogs/news/ttab-caseloads-vs-uspto-filings-trademark-opposition-cancellation-trends-2021-2025-why-95-settle-before-trial)) |
| PACER | Federal dockets, including bankruptcy schedules, claims registers and adversary complaints | Account | $0.10/page, capped at $3 per document. Fees are waived if under $30 per quarter ([PACER](https://pacer.uscourts.gov/policy-procedures); [LegalClarity](https://legalclarity.org/is-pacer-free-federal-court-fees-and-waivers/)) | The per-document cap does not apply to search reports |
| CourtListener / RECAP | Crowd-sourced PACER archive, API, webhooks, alerts | API | Free tier up to Tier 4 at $100/mo ([softwarefinder](https://softwarefinder.com/legal/courtlistener); [RECAP API docs](https://www.courtlistener.com/help/api/rest/recap/)) | Coverage gaps. Commercial use is quoted separately. |
| State court aggregators | State dockets | SaaS/API | Docket Alarm $99/mo; UniCourt $59–$399/mo plus enterprise API; Trellis from $99.95/mo ([search summary of vendor pages](https://www.docketalarm.com/); [UniCourt pricing](https://unicourt.com/pricing)) | API pricing is by quote |
| Bankruptcy claims-agent sites (Kroll, Epiq, Stretto, etc.) | Schedules, claims registers, bar dates | Web | Free to view | **Kroll's terms bar commercial use, copying and mirroring** ([Kroll ToS](https://media.ra.kroll.com/sitecontent/TermsOfUse/TermOfUse.html)). Pull the same filings from PACER instead. |
| Bankruptcy-court unclaimed funds | $200M+ held for creditors | Unclaimed Funds Locator; 66 of 87 courts participate ([uscourts govdelivery](https://content.govdelivery.com/accounts/USFEDCOURTS/bulletins/2492607); [arddun](https://www.arddun.com/bankruptcy-courts-holding-large-sums-for-creditors-yet-to-claim-funds/)) | Free | A locator needs a power of attorney. Checks are payable to the claimant only, never solely to the locator ([uscourts](https://www.uscourts.gov/court-programs/bankruptcy/unclaimed-funds-bankruptcy); [TNMB rules](https://www.tnmb.uscourts.gov/unclaimed-funds-rules-and-guidance)) |
| State unclaimed property | More than $70B held nationally ([NAUPA via search](https://www.bringyourfinancestolife.com/2024/09/unclaimed-property-reaches-70-billion-know-family-impacted/)). $4.49B returned in FY2024 ([NAUPA FY24](https://unclaimed.org/wp-content/uploads/NAUPA-FY-24-Report.pdf)). CA holds more than $15B; NY more than $18B ([search summary of SCO/OSC](https://www.sco.ca.gov/search_upd.html)). | CA: weekly CSV download ([SCO](https://sco.ca.gov/upd_download_property_records.html)). NY: quarterly SFTP for location providers. TX: by request with a PI license number ([data.texas.gov](https://data.texas.gov/Government-and-Taxes/Texas-Unclaimed-Property-Listing/3un9-h9it)). **IL: no bulk access, statutorily exempt** ([IL Treasurer](https://illinoistreasurer.gov/home/individuals/unclaimed-property/unclaimed-property-finder-applications/faq-unclaimed-property-finder-application/)). | Free | Finder fee caps, waiting periods and licensing apply (see Idea 2) |
| Class-action settlement notices | Class definitions, deadlines | Administrator sites, PR Newswire, SEC filings | Free | Courts police third-party filers (see Idea 6) |
| Copyright Office | About 22M registration records, 1978 to June 2025, as a bulk CSV ([USCO bulletin](https://content.govdelivery.com/accounts/USLOCCOPYRIGHT/bulletins/40374ba)) | Bulk | Free | |
| UCC filings | Lien filings | State SOS feeds, resellers | $0.005–$0.75 per lead ([search summary of list vendors](https://www.merchantfinancingleads.com/merchant-cash-advance-ucc-leads-lists)) | Commoditized |
| Business registries | Entity names, formation dates, officers | FL Sunbiz: free quarterly SFTP ([FL DOS](https://dos.fl.gov/sunbiz/other-services/data-downloads/quarterly-data/)). OpenCorporates API from £2,250/yr ([findmymoat](https://www.findmymoat.com/tools/opencorporates)). | Free to low | OpenCorporates' open-data license restricts commercial use unless you pay |

### 1.2 Incumbents by segment

- **Docket and litigation analytics:** Westlaw, Lexis, Bloomberg Law, Docket Alarm, UniCourt, Trellis.
  - Mass-tort intelligence is already full of AI-native startups: Darrow, TortIntel, LexGenius, TortSignal and Velocity Justice ([search results](https://tortintel.ai/); [LexGenius](https://feed.lexgenius.ai/); [Velocity](https://www.velocityjustice.com/)).
- **Trademark:**
  - Watch services: Corsearch and CompuMark/Clarivate, quote-based ([Corsearch](https://corsearch.com/trademark-solutions/trademark-watching)).
  - Docketing: Alt Legal at **$60/mo for 50 matters up to $295/mo for 400** ([Alt Legal pricing](https://www.altlegal.com/pricing/)).
  - Raw new-filing lead scrapers: Apify actors at about $6 per 1,000 records, with only 10 users ([Apify](https://apify.com/foxlabs/uspto-trademark-leads)).
- **Brand protection:**
  - Red Points: entry at about $15k/yr, average about $35k/yr ([knockoff.co summary](https://knockoff.co/guides/red-points-review); [Red Points pricing](https://www.redpoints.com/pricing/)).
  - MarqVision: $25k–$100k/yr.
  - Brand Protector: $199/mo ([brandprotector.io](https://brandprotector.io/blog/red-points-alternatives)).
- **DMCA for creators:** Rulta $109–$324/mo; BranditScan $69–$149/mo ([search summary](https://www.rulta.com/); [BranditScan pricing](https://branditscan.com/pricing)).
- **Copyright enforcement:** Pixsy takes about 50% of recoveries; Copytrack about 45% ([picdefense](https://picdefense.io/demand-letters/enforcement/pixsy/); [picdefense](https://picdefense.io/demand-letters/enforcement/copytrack/)).
- **Bankruptcy:**
  - Epiq AACER for filer matching ([Epiq](https://www.epiqglobal.com/en-us/services/bankruptcy-and-trustee-services/bankruptcy-services/filer-match-notify)).
  - Octus/Reorg and Debtwire for large-case intelligence.
  - Xclaim marketplace: $19M raised, 1% buyer fee, crypto-heavy ([Yahoo/Xclaim](https://finance.yahoo.com/news/bankruptcy-marketplace-xclaim-raises-7-130000596.html); [search summary](https://www.x-claim.com/faqs)).
  - Claims buyers and brokers: Cherokee, Pioneer Funding, TRC and others ([Pioneer](https://www.pioneerfundingllc.com/); [TRC](https://www.trcmllc.com/)).
- **Settlement claim filing for businesses:**
  - Chicago Clearing Corp: more than 2,900 institutional clients ([SIFMA](https://sources.sifma.org/listing/chicago-clearing-corporation)).
  - Others: Spectrum Settlement Recovery, Class Action Refund, MCAG, Claims Compensation Bureau, FRS ([Spectrum](https://spectrumsettlement.com/active-cases/); [Class Action Refund](https://classactionrefund.com/antitrust-class-actions/); [MCAG](https://www.mcaginc.com/post/food-industry-settlements); [FRS PVC summary](https://www.frsco.com/summaries/PVC%20Pipe%20Summary.pdf)).
- **Corporate unclaimed property recovery:**
  - KPMG: contingency fee, "fuzzy match" analytics ([KPMG PDF](https://kpmg.com/kpmg-us/content/dam/kpmg/pdf/2024/up-asset-recovery-2024.pdf)).
  - apexanalytix ([apex](https://www.apexanalytix.com/solutions/audit-recovery/unclaimed-property-asset-recovery/)).
  - Small firms such as US Recovery Services at a flat 10% ([USRS](https://www.usrecoveryservices.org/)).
- **ADA web accessibility:**
  - AudioEye: $40.3M revenue, about $40.0M ARR, about 131k customers in 2025 ([PR Newswire](https://www.prnewswire.com/news-releases/audioeye-reports-record-fourth-quarter-and-full-year-2025-results-302705842.html)).
  - accessiBe, which the FTC fined $1M in 2025 ([FTC](https://www.ftc.gov/legal-library/browse/cases-proceedings/2223156-accessibe-inc)).
  - Dozens of AI scanners.

### 1.3 Where the gaps are

1. **Recoveries too small for manual work.**
   - KPMG and apexanalytix serve large holders. Contingency filers chase the big settlements.
   - A business with $3k across four states, or a restaurant owed a few hundred dollars from a protein price-fixing settlement, gets no service.
   - The work involves entity resolution, filling forms, gathering documents and following up. That is exactly what Claude agents are good at.
2. **Pro-se segments.**
   - About 30% of trademark applications are filed pro se. Only about 46% of those succeed, against about 60% for attorney filings ([Trademark Engine/USPTO summary](https://www.trademarkengine.com/blog/us-trademark-filings-latest-uspto-data-before-you-file/)).
   - Attorneys can't afford to prospect these applicants manually.
3. **Creditor-side intelligence in small Chapter 11 cases.**
   - Commercial Chapter 11 filings were 7,940 in 2025, of which 2,446 were Subchapter V ([Epiq](https://www.epiqglobal.com/en-us/resource-center/news/total-bankruptcy-filings-increase-11-in-calendar-year-2025)).
   - Octus and Debtwire cover the big cases. Trade-claim buyers still pay sourcing analysts to do "heavy telephone work" ([Fusion Staffing](https://fusionstaffingpartners.com/?page_id=329)).
4. **Cross-source matching.**
   - Nobody I found combines, for one SMB: state unclaimed property across all states, bankruptcy-court unclaimed funds, and open settlement classes keyed to the business's industry and operating years.

---

## 2. Candidate ideas

> Scores and the ranked shortlist are in Section 4. The ideas below are listed in **ranked order**.

---

### Idea 1: Pro-Se Office-Action Opportunity Feed for trademark attorneys ("OA Radar")

**One-line pitch:** Every morning, each subscribing trademark attorney gets a list of fresh office actions issued to *unrepresented* applicants. Claude decodes each one (refusal type, difficulty, deadline, a suggested fee band), and the attorney gets a bar-compliant, attorney-branded outreach draft to send from their own domain.

**Data sources**
- **USPTO trademark daily XML and the TSDR/ODP API.** Free, API key required ([USPTO bulk](https://www.uspto.gov/trademarks/trademark-updates-and-announcements/trademark-bulk-data-us-patent-and-trademark-office)).
  - Fields used: office-action events, attorney-of-record field (to flag pro se), correspondent address, and email for unrepresented owners. The USPTO masks owner email only where counsel is listed ([USPTO](https://www.uspto.gov/subscription-center/2020/owner-email-address-field-now-masked-teas-and-teasi-documents-tsdr)).
  - Limits: rate limits of 60/min for status and 4/min for documents ([patent.dev](https://patent.dev/uspto-odp-go-client-office-action-and-trademark-apis/)). USPTO data is public domain. There's no licensing fee, but you must respect API-key terms.
- **Office-action text.** Fetch the OA document from TSDR per serial number, within rate limits. The ODP Office Action API has a 180-day lag, so it is useless for freshness. Use TSDR document retrieval instead.
- **Optional enrichment:**
  - The applicant's website, to judge business size.
  - Prior TTAB activity.
  - Similar registered marks cited in a 2(d) refusal (the likelihood-of-confusion ground).

**The data combination that creates new value**
- Joins: OA issuance event × pro-se flag × parsed refusal type (2(d), descriptiveness, specimen, identification) × days left on the **3-month response clock** ([USPTO](https://www.uspto.gov/subscription-center/2022/new-three-month-deadline-responding-pre-registration-office-actions)) × applicant size signals.
- The output is a **ranked, pre-qualified matter** rather than a raw lead. Raw new-filing leads already sell for about $6 per 1,000 on Apify ([Apify](https://apify.com/foxlabs/uspto-trademark-leads)), so the value is in the qualification.

**Buyer persona**
- Solo and small-firm trademark attorneys, typically 1–10 lawyers, who already run flat-fee office-action response packages.
- Also small firms that want volume, and the trademark practices of mid-size firms that run flat-fee "trademark mills."

**Evidence of willingness to pay**
- Attorneys charge **$500–$2,000+ per office-action response**. Traditional firms charge $1,500–$3,500 ([trademarkraft](https://trademarkraft.com/blogs/news/what-is-the-cost-for-an-office-action-response-by-a-us-attorney); [Branding Iron](https://brandingironlegal.com/trademark-resources/trademark-office-action-response-cost/); [Michael Meyer](https://www.michaelmeyerlaw.com/blog/trademark-office-action-response/)).
- Lawyers routinely pay per lead. ABA Model Rule 7.2 commentary expressly permits pay-per-lead ([leadgen-economy summary of ABA comment](https://www.leadgen-economy.com/blog/legal-lead-ethics-bar-association-guidelines/); [Ohio Bar Rule 7.2 text](https://www.ohiobar.org/link/4e925b63386f467b8be4495c64c2497c.aspx)).
- The manual alternative is a trademark paralegal or docketing specialist, at roughly **$58k–$92k**, or $90k–$110k in New York ([Glassdoor](https://www.glassdoor.com/Salaries/ip-docketing-specialist-salary-SRCH_KO0,23.htm); [salary summary](https://www.indeed.com/q-trademark-docketing-specialist-jobs.html)).
- Comparable software: Alt Legal's docketing proves small firms pay $60–$295/mo for trademark tooling ([Alt Legal](https://www.altlegal.com/pricing/)).

**Market size**
- 824,192 application **classes** were filed in FY2025 ([Trademark Engine citing the USPTO FY25 AFR](https://www.trademarkengine.com/blog/us-trademark-filings-latest-uspto-data-before-you-file/)).
- About 30% are pro se, which is about 247k pro-se classes (same source). **(est.)** That is roughly 150–180k pro-se applications.
- Most applications receive at least one office action ([Branding Iron](https://brandingironlegal.com/trademark-resources/trademark-office-action-response-cost/)). **(est.)** That gives 90–130k pro-se office actions a year.
- At $500–$1,500 per response, the attorney fee pool is about **$45M–$195M a year (est.)**.
- **Bottom-up buyer count (est.):** the USPTO does not keep a roster of trademark attorneys ([USPTO](https://www.uspto.gov/learning-and-resources/patent-and-trademark-practitioners/finding-trademark-practitioner)). Counting distinct attorneys of record in the bulk XML would answer this.
  - My working estimate: 3,000–6,000 small firms are active in trademark filing.
  - At a $6k/yr ACV, the serviceable market is about **$18M–$36M/yr (est.)**. That is small but real for a two-person, agent-run shop.

**Deliverable and pricing**
- A daily dashboard and email digest, with an exclusive or semi-exclusive lead cap per firm.
- Pricing options **(est.)**:
  - $299/mo for up to 40 qualified OAs per month, in shared mode.
  - $799/mo with category exclusivity (for example, "2(d) refusals, class 25, CA applicants").
  - Or $15–$40 per lead.
- **Recurring:** yes, as a subscription.
- **Add-ons:**
  - Section 8/9 renewal-window feed for unrepresented registrants, offered *only* as attorney-branded outreach. Over 400,000 registrations issued in FY2020 ([USPTO](https://www.uspto.gov/about-us/news-updates/uspto-year-review-new-search-tool-shorter-examination-times-and-unexpected)), so 2026 is a big year-5/6 cohort.
  - Abandonment-revival feed. Petitions to revive are due within 2 months of the notice of abandonment.

**Automation pipeline**

| Stage | How it works |
|---|---|
| Find prospects (the attorneys) | Parse 12 months of bulk XML. Rank attorneys of record by filing volume and pro-se-friendly class mix. Pull firm websites and emails. |
| Build deliverable | Nightly XML ingest → filter OA events with no attorney → TSDR document fetch → Claude classifies refusal grounds and drafts a 3-line plain-English summary → difficulty and fee band → dedupe → route to subscriber by filters. |
| Personalized outreach (to attorneys) | Email each attorney a free sample of 5 real matters in their own classes or states (the "built-it-already" hook copied from the website business). |
| Handle replies | Claude answers FAQs (exclusivity, compliance) and books a demo. A human closes the first 20 deals. |
| Deliver and renew | Self-serve Stripe billing. Monthly win report: OAs sent vs. retained, based on the attorney filing an appearance, which is visible in TSDR. **We can measure ROI from public data**, which drives renewals. |

**Automation:** about 85%. Human touchpoints remain at:
- the first sales calls
- a compliance review of templates for each new state bar
- QA on the refusal classifier at launch

**GTM, first 90 days**
- **Days 1–20:** build the ingest and classifier, and backtest on six months of OAs. Do the attorneys who eventually appeared on those matters correlate with our scoring?
- **Days 21–45:** pick 300 attorneys with more than 30 filings a year. Send each a personalized sample, and offer free 30-day pilots to 25.
- **Days 46–90:** convert 8–12 to paid at $299–$799. Publish a "retained-matter rate" case study. Add the renewal feed.

**Unit economics (est.)**
- CAC: $300–$800, from outbound email plus a short call.
- Price: about $500/mo blended ARPA.
- Data cost: about $0 (USPTO is free).
- Compute: about $0.05–$0.15 per OA classified, with Claude Haiku/Sonnet class models on 5–15 page documents.
- Gross margin: more than 90%.
- Payback: under 2 months.
- Churn risk: high if leads don't convert.

**Competitors and crowding**
- Apify scrapers sell raw new filings ([Apify](https://apify.com/foxlabs/uspto-trademark-leads)).
- High-volume filers like Trademarkia/LegalForce and LegalZoom market directly to applicants.
- Docketing tools (Alt Legal) serve *existing* clients, not prospecting.
- I found **no product that sells decoded pro-se OAs to attorneys**. Crowding is moderate: 5/10.

**Legal and regulatory: how to stay clean (UPL plus the USPTO scam history)**

- **UPL, and who may practice before the USPTO.**
  - Only attorneys may prepare, sign or file trademark documents for others, or "otherwise represent" an applicant ([37 CFR 11.14](https://www.ecfr.gov/current/title-37/chapter-I/subchapter-A/part-11/subpart-B/subject-group-ECFRa9deb1f9b3dd8c7/section-11.14); [TMEP 600 summary](https://www.cohnlg.com/TMEP/tmep-0600.html)).
  - Our company **never** contacts applicants on its own behalf, never advises them, and never drafts responses for them. We are a data and advertising vendor to licensed attorneys.
- **Scam history.**
  - The USPTO warns that private parties use public filing data for misleading solicitations ([USPTO non-USPTO solicitations](https://www.uspto.gov/patents/basics/using-legal-services/scam-prevention/non-uspto-solicitations); [USPTO scam-prevention PDF](https://www.uspto.gov/sites/default/files/documents/tm-trademarks-scamprevention_20230427.pdf)).
  - The FTC re-issued an impersonation alert in September 2025 ([FTC](https://consumer.ftc.gov/consumer-alerts/2025/09/scammers-are-impersonating-united-states-patent-and-trademark-office)).
  - A Latvian national got **more than 4 years in prison and $4.5M restitution** for "Patent and Trademark Office LLC" and "Patent and Trademark Bureau" renewal mailers that hit more than 2,900 registrants ([USPTO](https://www.uspto.gov/trademarks/protect/criminal-conviction-trademark-renewal-solicitation-scam)).
- **Hard rules to bake into the templates** (attorneys send them, but we supply them):
  1. The sender is the named law firm, from its own domain.
  2. Mark it "Advertising Material," or the state equivalent.
  3. Prominently state: "This is not a communication from the USPTO. You may respond yourself at no attorney cost."
  4. No USPTO-like names, seals, invoice layouts or "payment due" language.
  5. Show the flat fee upfront.
  6. Say "responses are due by [date]." Never use countdown fear copy.
  7. Never contact represented applicants. That respects Rule 4.2, and their emails are masked anyway.
- **Attorney advertising.** Model Rule 7.3 allows targeted written solicitation but restricts live contact ([attorneyatwork](https://www.attorneyatwork.com/lawyer-advertising-rules/)). Some states require filing or labeling direct mail. Ship a per-state ruleset.
- **Paying for leads.** Pay-per-lead is OK under the ABA 7.2 comment if we don't "recommend" the lawyer and don't share fees ([leadgen-economy](https://www.leadgen-economy.com/blog/legal-lead-ethics-bar-association-guidelines/)). **Never price as a percentage of legal fees.** That would be fee-splitting with a non-lawyer (Rule 5.4).
- **Email law.** CAN-SPAM applies to our own B2B emails to attorneys (opt-out, physical address, accurate headers). GDPR is irrelevant unless we sell to EU firms. TCPA is not triggered with no calls or texts.

**Kill risks**
1. The USPTO masks unrepresented-applicant emails too, or rate-limits documents harder. That leaves postal mail only, and conversion collapses.
2. Lead conversion is too low. Pro-se applicants are price-sensitive, and 46% fail anyway. Attorneys then churn after 2–3 months.
3. A bar complaint or a USPTO "misleading solicitation" warning names a subscriber, and the reputational blowback lands on the vendor.

---

### Idea 2: B2B "Found Money" sweep: multi-state unclaimed property plus bankruptcy-court unclaimed funds, sold through CPA firms

**One-line pitch:** A CPA firm uploads its business client list. Agents search every state program and the bankruptcy courts' unclaimed-funds registers, resolve name variants and DBAs, and pre-assemble claim packets. The CPA delivers "we found you $X" to the client and keeps the relationship. We share the fee, or charge the firm SaaS.

**Data sources**
- **State unclaimed property, varying by state:**
  - CA: weekly downloadable CSV of the public database ([SCO](https://sco.ca.gov/upd_download_property_records.html)).
  - NY: quarterly SFTP list for location service providers.
  - TX: dataset by email request, which asks for a PI license number ([data.texas.gov](https://data.texas.gov/Government-and-Taxes/Texas-Unclaimed-Property-Listing/3un9-h9it)).
  - IL: **no bulk access** ([IL Treasurer](https://illinoistreasurer.gov/home/individuals/unclaimed-property/unclaimed-property-finder-applications/faq-unclaimed-property-finder-application/)).
  - Elsewhere: per-name searches on state sites or MissingMoney ([NAUPA](https://unclaimed.org/search/)). Read each state's site terms before automating searches. Rate-limit, and don't scrape where it's prohibited.
- **Bankruptcy-court unclaimed funds:** more than $200M held, searchable via the locator in 66 of 87 courts ([uscourts bulletin](https://content.govdelivery.com/accounts/USFEDCOURTS/bulletins/2492607); [arddun](https://www.arddun.com/bankruptcy-courts-holding-large-sums-for-creditors-yet-to-claim-funds/)).
- **Entity resolution:**
  - Secretary of State registries. FL bulk is free ([FL DOS](https://dos.fl.gov/sunbiz/other-services/data-downloads/quarterly-data/)). OpenCorporates paid API from £2,250/yr ([findmymoat](https://www.findmymoat.com/tools/opencorporates)).
  - The client's own legal names, former names, addresses and acquired entities, supplied by the CPA with consent.

**The data combination**
- The CPA's verified client roster (legal names, EINs, prior addresses, acquisitions) × state property lists × federal court registries × fuzzy matching.
- KPMG itself says the edge is "fuzzy match" queries because holder data has misspellings and bad addresses ([KPMG](https://kpmg.com/kpmg-us/content/dam/kpmg/pdf/2024/up-asset-recovery-2024.pdf)).
- The roster is semi-private data that a CPA can share with client consent. That fixes the identity-verification and document problem that kills cold finder outreach.

**Buyer persona**
- **Primary:** the managing partner or "client advisory services" lead at a CPA firm with 2–50 staff and 100–2,000 business clients. They want a value-add that costs nothing to deliver.
- **Secondary:** the controller or CFO at a $10M–$500M company. KPMG/apex are too expensive for them, and they have multi-state footprints.

**Evidence of willingness to pay**
- The contingency model is proven:
  - KPMG runs a contingency-fee asset recovery practice ([KPMG](https://kpmg.com/kpmg-us/content/dam/kpmg/pdf/2024/up-asset-recovery-2024.pdf)).
  - US Recovery Services charges a flat 10% and claims more than $25M identified ([USRS](https://www.usrecoveryservices.org/)).
  - Other B2B recovery firms charge 10–20% ([search summary](https://www.valeugroup.com/uncalimed-property-recovery)).
- Salaries for the people who do this manually: unclaimed property analysts earn $70k–$140k; claims analysts $45k–$77k ([ZipRecruiter](https://www.ziprecruiter.com/Jobs/Unclaimed-Property-Analyst); [SC state posting](https://www.governmentjobs.com/careers/sc/jobs/5296194/unclaimed-property-claims-analyst)).
- Pool size: WV paid $40.6M across 20,908 claims in FY2025 (about $1,940 per claim, individuals and businesses mixed) ([WV Treasury](https://wvtreasury.gov/About/Press-Releases/details/treasurer-pack-announces-another-record-breaking-year-for-unclaimed-property-returns)). PA returned a record $334M in 2025 ([PA Treasury](https://www.patreasury.gov/newsroom/archive/2026/02-18-Record.html)).

**Market size**
- **Pool:** more than $70B held; $4.49B returned per year ([NAUPA FY24](https://unclaimed.org/wp-content/uploads/NAUPA-FY-24-Report.pdf)). The business-owned share isn't published.
  - **(est.)** 15–25% of the dollars are business-owned (vendor checks, refunds, deposits, insurance), so about $10B–$18B is business-owned.
  - Caveat: about 15 states have B2B exemptions that reduce business-owned escheat ([Baker Tilly](https://www.bakertilly.com/insights/unclaimed-property-unraveling-the-business-to-business-exemption); [UPPO](https://www.uppo.org/blogpost/925381/237086/Inside-the-B2B-exemption)).
- **Buyers:** about 50,885 CPA firms; 86% have under 10 employees ([VerticalIQ/CPA stats summary](https://verticaliq.com/product/cpa-practices/)). **(est.)** 15,000 firms with business clients are serviceable.
- **(est.) Per-firm economics:**
  - A 400-client firm with a 25% hit rate and about $2,500 average recovers about $250k.
  - At a 10% fee that's $25k, split with the CPA.
  - Plus re-sweeps every year as holders report.

**Deliverable and pricing**
- A per-client "found money" report, pre-filled claim packets, e-signature and remote-notary hand-off, and status tracking.
- Pricing **(est.)**, two options:
  - (a) A contingency of 10%, or the state cap if lower, split 50/50 with the CPA, where the CPA acts as claimant representative in states that require a licensee.
  - (b) SaaS for the CPA firm at $199–$499/mo, where the CPA bills its own client.
- **Recurring:** partly. New property is reported every year, so annual re-sweeps are a real reason to keep paying, but revenue is lumpy.

**Automation pipeline**

| Stage | How it works |
|---|---|
| Find prospects | Build a CPA firm list from state CPA board rosters and websites. Pre-search each firm's *own name* and a few *public clients* (from case studies) to make a teaser: "We found $4,120 for 3 of your listed clients." |
| Build deliverable | Ingest the roster → name normalization and alias generation from SOS data → per-state search and download match → Claude reviews matches (holder, address history, property type) → confidence score → draft the claim form per state's spec → document checklist (officer authorization, notarization, proof of address or EIN). |
| Personalized outreach | An email to the CPA with the teaser. Never contact the CPA's clients directly; the CPA owns that relationship. |
| Handle replies | Claude answers questions about state rules and fee caps, and sends the engagement letter and data-processing agreement. |
| Deliver and renew | Track claim status by state portal or email. Invoice on payment (payment always goes to the owner). Run an annual automated re-sweep and send a "new property found" alert. |

**Automation:** about 70%. Human touchpoints:
- notarized officer signatures (remote notarization helps)
- states demanding paper or wet ink
- disputed ownership after mergers
- licensed-representative sign-off in FL and TX
- partner-level sales to CPA firms

**GTM, first 90 days**
- Start in CA and NY: the largest holdings ($15B+ and $18B+) and bulk lists are available.
- Recruit 10 CPA firms in IL and FL first. In IL, CPA firms serving non-individual clients are **exempt from finder licensing** ([IL Treasurer](https://illinoistreasurer.gov/home/individuals/unclaimed-property/unclaimed-property-finder-applications/faq-unclaimed-property-finder-application/)). In FL, CPAs can register as claimant's representatives ([Fla. Stat. 717.1400](https://www.flsenate.gov/laws/statutes/2023/717.1400)). The CPA channel *is* the licensing workaround.
- Target: 10 pilot firms, 1,000 client sweeps, and the first claims paid by about day 75–120. State processing takes months ([KPMG](https://kpmg.com/kpmg-us/content/dam/kpmg/pdf/2024/up-asset-recovery-2024.pdf)).

**Unit economics (est.)**
- CAC per CPA firm: $500–$1,500.
- Revenue per firm per year: $5k–$15k.
- Data cost: near zero, plus OpenCorporates at about $2.7k/yr.
- Compute: about $0.50–$2 per client sweep.
- Gross margin: about 75% after the CPA split and notary or postage costs.
- Cash conversion is slow (3–9 months to state payout).

**Competitors and crowding**
- KPMG and apexanalytix serve the enterprise.
- Heir finders are consumer-focused.
- A few B2B 10% firms exist (USRS, Valeu, Duality).
- No CPA-channel, multi-source product found. Crowding: 6/10.

**Legal and regulatory**
- **Finder statutes.**
  - Most states cap fees at 10%: CA under [CCP 1582](https://sco.ca.gov/upd_investigator_about.html); TX at 10% plus registration and bond ([TX summary](https://themissingmint.com/guides/texas-unclaimed-property-search-and-claim)). A few states go to 20–30% ([fee-cap table](https://themissingmint.com/guides/unclaimed-money-finder-fee-cap-by-state)).
  - Many states bar finder agreements for 24 months after reporting; Delaware for 36 months (same source).
  - RUUPA requires the agreement to state that the owner can recover free and to give the administrator's contact info ([RUUPA text](https://compacts.csg.org/wp-content/uploads/2024/03/Uniform-Unclaimed-Property-Act.pdf)).
- **Licensing.**
  - TX requires a PI license, registration and bond ([search summary](https://www.claimittexas.gov/app/faq-ucp)).
  - FL limits claimant's reps to registered attorneys, CPAs and PIs ([717.1400](https://www.flsenate.gov/laws/statutes/2023/717.1400)).
  - IL requires a license ($500 plus a bond) unless you are an exempt CPA or attorney ([IL FAQ](https://illinoistreasurer.gov/home/individuals/unclaimed-property/unclaimed-property-finder-applications/faq-unclaimed-property-finder-application/)).
- **Bankruptcy courts:** power of attorney required; checks payable to the claimant only; a hearing may be set ([TNMB](https://www.tnmb.uscourts.gov/unclaimed-funds-rules-and-guidance)).
- **CAN-SPAM** applies to emails to CPAs. No TCPA exposure if there are no calls or texts.
- **Data privacy:** client rosters are confidential client information for the CPA. Sign a data-processing agreement and follow AICPA confidentiality rules (ET 1.700). The CPA must get consent where required.

**Kill risks**
1. States keep expanding **automatic "money match" returns** and free outreach. PA and others are already pushing returns ([PA Treasury](https://www.patreasury.gov/newsroom/archive/2026/02-18-Record.html)). That shrinks the addressable pool and makes the "you can claim free" disclosure bite harder.
2. Average business hits turn out small (a few hundred dollars), so a 10% fee can't cover per-claim notary and document friction.
3. The patchwork of state licensing and data access (IL has no bulk data; TX wants a PI license) caps coverage at about 15 states without heavy legal overhead.

---

### Idea 3: ADA website-lawsuit signals feeding the brothers' site-rebuild engine

**One-line pitch:** Watch federal and NY/CA state ADA website complaints daily. Auto-audit every sued site and its "lookalike" peers on the same platform and vertical. Offer a rebuilt accessible site plus monitoring, at a price far below the cost of the next demand letter.

**Data sources**
- **Federal complaints:** PACER/RECAP via CourtListener alerts and API (free to $100/mo) ([CourtListener](https://www.courtlistener.com/help/api/rest/recap/)). Filter on ADA nature-of-suit codes and serial-plaintiff firms.
- **State suits:** NY and CA, through UniCourt or Trellis ($59–$399/mo; enterprise API by quote) ([UniCourt](https://unicourt.com/pricing)).
- **Site audits:** your own crawls with an open-source accessibility engine (axe-core style) plus Claude triage. No licensing issue for public pages; respect robots.txt.
- **Benchmark:** UsableNet's annual and monthly trackers ([UsableNet 2025 YE](https://info.usablenet.com/hubfs/Remediated%20-%202025_Year-End_Digital_Accessibility_Lawsuit_Report_FINAL.pdf)).

**The data combination**
- New complaint × defendant's site platform and theme fingerprint × plaintiff firm's historical targeting pattern (vertical, state, platform) × a live WCAG scan of the defendant **and of its 50 nearest look-alike sites**.
- That produces two segments: a "you were sued" list, and a "you look exactly like who they sue" list.

**Buyer persona**
- Owners and e-commerce managers of $1M–$50M online retailers and restaurants. 70% of suits target e-commerce and 21% food service.
- 1,427 of the 5,114 suits in 2025 hit already-sued companies, so repeat targets matter ([UsableNet blog](https://blog.usablenet.com/ada-web-lawsuit-trends-2026); [beaccessible](https://beaccessible.com/post/web-accessibility-statistics/)).

**Evidence of willingness to pay**
- Small-business settlements run $5k–$25k. Defense costs reach $10k–$50k+ ([search summary](https://www.adawebpro.com/blog/ada-website-lawsuit-statistics/); [dev.to](https://dev.to/agentkit/how-much-does-an-ada-lawsuit-actually-cost-2025-real-data-4ha0)).
- Remediation runs $500–$5k (same).
- AudioEye has about $40M ARR from about 131k customers ([PR Newswire](https://www.prnewswire.com/news-releases/audioeye-reports-record-fourth-quarter-and-full-year-2025-results-302705842.html)). **ARPU is only about $305/yr**, so subscription pricing is low.

**Market size**
- 5,114 suits in 2025: 3,195 federal and 1,919 in NY/CA state courts ([UsableNet](https://info.usablenet.com/hubfs/Remediated%20-%202025_Year-End_Digital_Accessibility_Lawsuit_Report_FINAL.pdf)).
- Demand letters, which are never filed, are a multiple of that **(est. 3–10×)**.
- **(est.)** The look-alike prospect pool is 200k–500k small e-commerce and restaurant sites.
- **Bottom-up (est.):** 5,000 sued businesses a year × 10% close × $3k rebuild = $1.5M, plus monitoring at $50/mo. Look-alikes are the upside.

**Deliverable and pricing**
- An audit report (free, as the hook).
- A rebuild at $1.5k–$5k, or a fix-in-place.
- Monitoring and re-audit at $49–$149/mo **(est.)**, recurring.

**Automation pipeline**

| Stage | How it works |
|---|---|
| Find | Daily docket alerts → parse the complaint (Claude extracts the URL, plaintiff firm, alleged barriers) → find look-alikes by platform fingerprint |
| Build | Crawl and audit → Claude writes a plain-English barrier list → generate a demo of the rebuilt page (the brothers' existing pipeline) |
| Outreach | Email the business, not its lawyer: "Here's an independent audit of the barriers listed in public complaints like yours, and a fixed version." |
| Replies | Claude handles questions and scoping. It never comments on the lawsuit itself and refers that to counsel. |
| Deliver and renew | Deploy, monitor monthly, send a re-audit report |

**Automation:** about 75%. Human touchpoints: complex sites, sales calls with anxious owners, and defense-counsel coordination.

**GTM, first 90 days**
- Days 1–30: build the complaint parser on CourtListener and audit 300 sued sites.
- Days 31–60: outreach to sued businesses only, which is the highest-intent segment.
- Days 61–90: launch the look-alike program in one vertical (for example, Shopify apparel).

**Unit economics (est.)**
- CAC: $150–$400.
- First-year value: $3k rebuild + $600 monitoring.
- Gross margin: about 70%.
- Data: about $1.2k–$5k/yr.

**Competitors and crowding**
- AudioEye, accessiBe, UserWay and Level Access, plus a long tail of AI scanners publishing lawsuit content ([dev.to](https://dev.to/agentkit/ada-website-lawsuits-what-small-business-owners-need-to-know-in-2026-3dma); [testparty](https://testparty.ai/blog/ada-lawsuit-cost-statistics-settlement-defense-data)).
- Defense firms solicit defendants too.
- **Crowded: 3/10.** The edge is "we actually rebuild the site," which overlay vendors don't.

**Legal and regulatory**
- **FTC v. accessiBe:** a $1M fine for claiming "full compliance" and lawsuit protection ([FTC](https://www.ftc.gov/legal-library/browse/cases-proceedings/2223156-accessibe-inc)). Never promise compliance or immunity from lawsuits.
- **UPL:** don't advise on the suit, settlement or response. Refer to counsel.
- **CAN-SPAM** for outreach.
- Don't misrepresent affiliation with the court or the plaintiff.
- Tone must not be predatory; reputational risk is high.

**Kill risks**
1. Low ARPU and fierce competition. The overlay vendors' $25–$100/mo anchors pricing.
2. Sued businesses have already been sold by their defense lawyer's preferred vendor before our email lands.
3. Policy shifts. A DOJ rule, a circuit split or a state law change (for example in NY or CA) could cut filings.

---

### Idea 4: Trade-claim sourcing engine for bankruptcy claim buyers (white-label "claims desk")

**One-line pitch:** For each new Chapter 11, parse the debtor's schedules and claims register. Score every trade creditor by claim size, priority (including 503(b)(9) administrative priority for goods delivered within 20 days of filing) and expected recovery. Then run white-label outreach to the creditors *on behalf of* a subscribing claims-buying fund.

**Data sources**
- **PACER:** petitions, Schedules E/F (unsecured creditors with amounts), bar-date orders, disclosure statements. $0.10/page, capped at $3 per document ([PACER](https://pacer.uscourts.gov/policy-procedures)).
- **RECAP** copies where they exist.
- **Claims-agent sites:** view for orientation only. Kroll's terms bar commercial reuse ([Kroll ToS](https://media.ra.kroll.com/sitecontent/TermsOfUse/TermOfUse.html)).
- **Contact enrichment:** company websites.
- **Filing stream:** Epiq-reported volumes; 7,940 commercial Chapter 11s in 2025 ([Epiq](https://www.epiqglobal.com/en-us/resource-center/news/total-bankruptcy-filings-increase-11-in-calendar-year-2025)).

**The data combination**
- Schedule F creditor × amount × 503(b)(9) eligibility window ([NACM](https://www.nacmcommercialservices.org/chapter-11-vendor-game-changer-section-503b9-claims/)) × recovery estimate parsed from the disclosure statement × creditor contact.
- That produces a **priced, ranked sourcing list** the day documents post. Sourcing analysts build these by hand today.

**Buyer persona**
- The head of trade-claim acquisitions at distressed funds and claims buyers: Cherokee, Pioneer Funding, TRC and similar ([search summary](https://www.crunchbase.com/organization/cherokee-acquisition); [Pioneer](https://www.pioneerfundingllc.com/); [TRC](https://www.trcmllc.com/)).

**Evidence of willingness to pay**
- Funds hire "Trade Claims Sourcing Analysts" for "heavy telephone work" at $40k plus bonus ([Fusion Staffing](https://fusionstaffingpartners.com/?page_id=329)). Trade facilitation analysts earn $110k–$125k ([ZipRecruiter](https://www.ziprecruiter.com/Jobs/Distressed-Debt-Hedge-Fund)).
- Trade claims trade at about 20–50¢ on the dollar ([search summary](https://ibinterviewquestions.com/guides/restructuring-investment-banking/claims-trading-how-distressed-funds-buy-in)), so the spread margin is large.
- Brokers earn 0.5–1% ([search summary](https://www.fa-mag.com/news/wall-street-pros-offer-crypto-holders-a-backdoor-bankruptcy-exit-69154.html)).
- Xclaim raised about $19M for a marketplace ([Yahoo](https://finance.yahoo.com/news/bankruptcy-marketplace-xclaim-raises-7-130000596.html)).

**Market size**
- Claims trading is "hundreds of billions" by some estimates; more than $25B in non-Lehman US cases in 2018 ([ABI](https://www.abi.org/feed-item/five-things-to-consider-when-approached-by-a-bankruptcy-claims-trader); [DailyDAC](https://www.dailydac.com/introduction-bankruptcy-claims-trading/)).
- **Buyers (est.):** 30–60 active trade-claim buyers. At $3k–$10k/mo each, the serviceable market is about $1M–$7M/yr. It is a small number of buyers, but they pay well.

**Deliverable and pricing**
- Per-case dossiers and a daily feed: **$2.5k–$7.5k/mo (est.)**.
- Optional white-label outreach: **$150–$500 per qualified seller conversation**, or a success fee of 0.5–1% of face value. That matches broker norms.
- **Recurring:** yes.

**Automation pipeline**

| Stage | How it works |
|---|---|
| Find (buyers) | Rule 3001(e) transfer notices on PACER name every active buyer and their case appetite. That is a perfect prospect list. |
| Build | New-case trigger → pull petition and schedules → Claude extracts creditor tables from PDFs (OCR as needed) → join against bar dates and 503(b)(9) → price bands |
| Outreach (to buyers) | Send each buyer a free dossier on a case they just bought into, as shown by their own transfer notices |
| Replies | Claude handles the demo and scoping |
| Deliver and renew | Daily feed; creditor outreach under the buyer's brand; monthly "claims sourced → closed" report |

**Automation:** about 80%. Human touchpoints: buyer relationships, edge-case claim analysis, compliance review of outreach scripts.

**GTM, first 90 days**
- Mine 12 months of transfer notices to rank buyers.
- Ship free dossiers on 10 live cases.
- Sign 2–3 design partners at a discounted $1.5k/mo.

**Unit economics (est.)**
- CAC: $2k–$5k.
- ACV: $40k–$90k.
- PACER cost: $100–$500/mo.
- Gross margin: more than 85%.

**Competitors and crowding**
- Octus and Debtwire cover large cases.
- Xclaim is a two-sided marketplace.
- Buyers run in-house sourcing desks.
- I found no "sourcing-as-a-service" vendor. Crowding: 6/10.

**Legal and regulatory**
- Rule 3001(e) transfer mechanics ([Rule 3001](https://www.federalrulesofbankruptcyprocedure.org/part-iii/rule-3001/)).
- Claims trading is "virtually unregulated," but sellers face refund and objection risk. Outreach must not misstate recovery ([ABI](https://www.abi.org/feed-item/five-things-to-consider-when-approached-by-a-bankruptcy-claims-trader)).
- Ordinary trade claims are generally treated as non-securities. **Get counsel's opinion before taking success fees**, and never broker bond or loan claims without broker-dealer registration ([SEC BD guide](https://www.sec.gov/about/divisions-offices/division-trading-markets/division-trading-markets-compliance-guides/guide-broker-dealer-registration)).
- TCPA if any calls or texts go to mobile numbers.
- Respect the Kroll terms; use PACER copies.

**Kill risks**
1. The buyer universe is tiny and relationship-driven. Funds may see sourcing as their own edge and won't outsource it.
2. Creditors already get swamped with offers. Buyers "mail checks" unsolicited ([ABI](https://www.abi.org/feed-item/five-things-to-consider-when-approached-by-a-bankruptcy-claims-trader)), so outreach-on-behalf adds little.
3. Securities-law characterization of success fees, or a bad-actor claims buyer client, creates liability.

---

### Idea 5: Creditor-side bankruptcy action alerts for mid-market suppliers (bar dates, 503(b)(9) and preference exposure)

**One-line pitch:** A credit department uploads its customer list. When a customer files, Claude produces a one-page action brief:
- your scheduled amount vs. your ledger amount
- the bar date
- the 503(b)(9) amount (goods received in the last 20 days)
- estimated preference exposure (payments in the last 90 days)
- current claims-buyer interest, from Idea 4's feed

**Data sources:** PACER/RECAP (as above) and the customer's AR ledger (private, with consent).

**The data combination:** AR ledger × schedules × bar-date orders × payment history. That makes it a **pre-calculated recovery and defense brief**, where today the credit manager reads 200-page filings.

**Buyer persona:** credit managers and VP Credit at $50M–$2B manufacturers and distributors (NACM-type members).

**Evidence of willingness to pay**
- Epiq AACER sells filer-match and notice parsing to lenders ([Epiq](https://bankruptcy.epiqglobal.com/aacer-platform-overview-handout)).
- NACM runs paid bankruptcy services ([NACM](https://www.nacmcommercialservices.org/chapter-11-vendor-game-changer-section-503b9-claims/)).
- 503(b)(9) is "underappreciated" and converts near-worthless claims into priority claims ([Crowell](https://www.crowell.com/en/insights/client-alerts/section-503b9-an-underappreciated-avenue-for-improved-recovery)).
- Large cases produce "hundreds" of preference suits per debtor ([Bloomberg Law overview](https://www.bloomberglaw.com/external/document/X42I4GLC000000/bankruptcy-overview-managing-preference-action-litigation)).

**Market size (est.):** 15k–30k US companies with formal credit departments × $3k–$12k/yr gives roughly **$50M–$300M**.

**Deliverable and pricing:** SaaS at $250–$1,000/mo by customer-count tier **(est.)**. Recurring.

**Automation pipeline**
- Find: credit managers via NACM chapter rosters and LinkedIn titles.
- Build: daily filing match → document pull → Claude brief.
- Outreach: "Your customer X filed yesterday; here's your brief."
- Replies: Claude.
- Renew: monthly value report.

**Automation:** about 85%. Human touchpoints: onboarding ledger integrations (ERP exports) and preference-defense referrals to counsel.

**GTM, first 90 days:** trigger-based outreach. When a mid-size retailer or restaurant chain files, email its top scheduled suppliers (from Schedule F) a free brief, then offer monitoring for all their customers.

**Unit economics (est.)**
- CAC: $800–$2k.
- ACV: $6k.
- Gross margin: about 85%.
- PACER cost: about $200/mo.

**Competitors:** Epiq AACER, Creditsafe/Cortera, CreditRiskMonitor, NACM services, bankruptcy law firms' free alerts. Crowding: 4/10.

**Legal and regulatory**
- Briefs must be informational. Do not advise whether to file or how to defend a preference (UPL). Refer to counsel.
- Proofs of claim *can* be signed by a creditor's authorized agent on Official Form 410 (**verify with counsel before offering filing**).
- Ledger data is confidential. Use SOC 2-lite controls.

**Kill risks**
1. Alert fatigue. Most customers never file, and the value is episodic.
2. Incumbent credit-data vendors bundle "good-enough" bankruptcy alerts for free.
3. ERP integration friction slows onboarding enough to kill self-serve.

---

### Idea 6: Business settlement-eligibility radar and claims filing (CIIPP, end-user and procurement classes)

**One-line pitch:** Match a business's industry, location, operating years and (ideally) AP vendor data against every open antitrust class whose class members are businesses. File the claims, or hand the business a pre-filled packet.

**Data sources**
- Settlement notices and administrator FAQs. Examples:
  - Pork commercial/institutional indirect purchasers ([porkcommercialcase](https://www.porkcommercialcase.com/Home/FAQ))
  - Beef direct purchasers: $82.5M, deadline Nov 30, 2026 ([MCAG](https://www.mcaginc.com/post/food-industry-settlements))
  - Turkey direct purchasers: $93.6M, deadline Oct 30, 2026 ([openclassactions](https://openclassactions.com/settlements/turkey-price-fixing-class-action-settlement.php))
  - PVC pipe end users: $50M from Atkore, no claim form yet ([openclassactions](https://openclassactions.com/news/atkore-pvc-pipe-antitrust-end-user-settlement-announced.php); [Atkore 8-K](https://www.sec.gov/Archives/edgar/data/0001666138/000166613826000014/atkr-20260604.htm))
  - Broiler chicken CIIPP: more than $145M total ([Brooks Institute](https://thebrooksinstitute.org/animal-law-digest/us/issue-284/federal-court-grants-preliminary-approval-4125-million-chicken))
- Business registries for formation dates (FL bulk, OpenCorporates).
- Business type: licensing data, plus the website-business lists the brothers already have.

**The data combination:** local business list (restaurants, contractors, clinics) × formation date (to prove operation in the class period) × class definitions and deadlines. This is a near-perfect fit with the brothers' existing local-business prospect database.

**Buyer persona:** independent restaurant owners (412,498 independent locations ([NRN](https://www.nrn.com/independent-restaurants/the-independent-restaurant-sector-shrunk-by-2-3-in-2025))), caterers, plumbing and irrigation contractors, nursing homes, plus CPA/bookkeeping firms acting as a channel.

**Evidence of willingness to pay**
- Third-party filers charge **10–40%** ([CampusGuard/Gravity summary](https://gravitypayments.com/blog/what-you-should-know-about-the-payment-card-interchange-fee-settlement/)).
- Several firms run contingency businesses on this: Spectrum, CCC, Class Action Refund, MCAG, FRS.
- Claim rates are low. The FTC's median consumer claims rate is 9% ([FTC](https://www.ftc.gov/system/files/documents/reports/consumers-class-actions-retrospective-analysis-settlement-campaigns/class_action_fairness_report_0.pdf)), which leaves money on the table.

**Market size**
- Visa/Mastercard is the giant, with 18.6M eligible merchants ([Payments Dive](https://www.paymentsdive.com/news/visa-mastercard-card-settlement-merchant-claims-form-deadline/715225/)), but **its deadline passed Feb 4, 2025**. Distributions are ongoing: $418.9M to about 599k merchants ([Payments Dive](https://www.paymentsdive.com/news/visa-mastercard-swipe-fee-fund-has-paid-414m/821869/)).
- The BCBS provider settlement ($2.8B) also closed, on July 29, 2025 ([CMA](https://www.cmadocs.org/newsroom/news/view/ArticleId/50913/Reminder-Deadline-to-file-your-claim-in-the-BCBS-provider-antitrust-settlement-is-July-29)).
- **The pipeline that's still open is smaller:** **(est.)** $300M–$1B a year in business-claimant funds, after attorney fees of up to 35% ([chicken CIIPP notice](https://chickencommercialsettlement.com/assets/Docs/CIIPP%20Long%20Form%20Notice_Final.pdf)).
- **Per-restaurant payouts are likely hundreds of dollars (est.)**. At 20% that means $50–$200 per claim.

**Deliverable and pricing**
- Contingency of 15–20%.
- Or a CPA-channel subscription at $99–$299/mo for "settlement radar" across the CPA's client book **(est.)**.
- Weakly recurring: new settlements appear every few months.

**Automation pipeline**
- Find: existing local-business lists.
- Build: eligibility match plus a pre-filled claim.
- Outreach: email with the court-required disclosures.
- Replies: Claude handles questions and e-signature.
- Deliver: file online with the administrator, track, invoice on payout.

**Automation:** about 80%.

**GTM, first 90 days:** pilot with restaurants for the beef and turkey deadlines (Oct–Nov 2026) via CPA partners. Get the PVC end-user class ready for when its claim form opens.

**Unit economics (est.)**
- CAC: $10–$40 by email.
- Revenue: $50–$300 per claimant.
- Margin: about 85%.
- Cash lag: 6–24 months from claim to distribution.

**Competitors:** Spectrum, Class Action Refund, CCC, MCAG, FRS, Claims Compensation Bureau. Crowding: 4/10.

**Legal and regulatory**
- The interchange court found some third-party filers' solicitations misleading. In Sept 2018 (Dkt. 7260) it ordered mandatory disclosures in **every** solicitation, under threat of being permanently barred from the settlement ([search summary of EDNY order](https://www.paymentcardsettlement.com/Content/Documents/9549%20-%20Sua%20Sponte%20Report%20and%20Recommendation%20re%20Merchant%20Stronghold%20and%20Cardsettlementorg.pdf)).
- Imposter sites drew cease-and-desists ([Payments Dive](https://www.paymentsdive.com/news/visa-mastercard-card-settlement-merchant-claims-form-deadline/715225/)).
- Claim forms require disclosure of any third-party assignee ([search summary of BCBS form](https://documents.cap.org/documents/BCBS_Settlement_Agreement_FAQs.pdf)).
- Class counsel and administrators help for free. Some forms are **pre-populated** from class counsel's data ([chicken notice](https://chickencommercialsettlement.com/assets/Docs/CIIPP%20Long%20Form%20Notice_Final.pdf)), which erodes the value of a filer.
- Not UPL, since filing is ministerial, but deceptive-practices law (the FTC Act and state UDAP statutes) applies.

**Kill risks**
1. Per-claimant dollars for SMBs are too small, and the payout lag is 1–2 years.
2. Judicial hostility to third-party filers, plus free administrator help and pre-filled forms.
3. Lumpy deal flow. The big business classes (interchange, BCBS) are closed.

---

### Idea 7: Name-conflict watch for unregistered local businesses

**One-line pitch:** Each week, match newly *published-for-opposition* federal trademark applications against Secretary of State and local-business names in the same goods or services. Alert the senior local user before the 30-day opposition window closes.

**Data sources**
- The USPTO Official Gazette, published weekly, which opens a 30-day opposition window that is extendable ([UpCounsel](https://www.upcounsel.com/us-trademark-opposition-period); [TTAB](https://www.uspto.gov/trademarks/ttab/initiating-new-proceeding)).
- SOS registries (FL bulk, OpenCorporates) and local business listings.

**The data combination:** a federal filing by a junior user × an older local entity with the same or a similar name in the same trade. Common-law senior users keep local priority ([Mandour](https://www.mandourlaw.com/common-law-trademark-rights/)), but they lose expansion rights once a federal registration issues.

**Buyer persona:** owner-operators of 5+ year-old local businesses (restaurants, salons, contractors) with no federal registration. The secondary buyer is a trademark attorney paying per lead.

**Evidence of willingness to pay**
- Weak for SMBs.
- Existing watch services sell only to registered-mark owners (Corsearch, CompuMark, quote-based).
- TTAB volume shows the conflict is real: 19,130 extensions and 7,650 oppositions in FY2025 ([trademarkraft](https://trademarkraft.com/blogs/news/ttab-caseloads-vs-uspto-filings-trademark-opposition-cancellation-trends-2021-2025-why-95-settle-before-trial)).

**Market size (est.):** about 6–10k marks published per week. **(est.)** 1–3% fuzzy-match a qualifying local business, giving about 5k–15k alerts a year. At $49 one-time, or $15/mo, plus a $50 attorney lead fee, that's about $1M–$3M/yr.

**Deliverable and pricing:** a free first alert, then an annual "name watch" subscription; attorney referral leads on a pay-per-lead basis.

**Automation:** about 90%. Humans are only needed for attorney partner management.

**GTM:** piggyback on the website business. Every local business they already contact gets a free name scan.

**Unit economics (est.):** CAC near zero inside the existing funnel; low ARPU.

**Competitors:** none aimed at unregistered SMBs that I could find. Crowding: 8/10, blue water.

**Legal and regulatory**
- **This is the riskiest framing in the lane:** "someone filed your name, act now" reads exactly like the USPTO scam mailers.
- Must state: not from the USPTO, no legal advice, consult an attorney.
- Attorney referrals must comply with ABA Rule 7.2: no "recommendation," and pay per lead, never a percentage of the fee.

**Kill risks**
1. SMBs won't pay to watch a risk they don't understand.
2. Scam-like optics hurt the brothers' core brand.
3. High false-positive matching. Same name in different trades generates noise and complaints.

---

## 3. Ideas considered and rejected

| Idea | Why it was rejected (evidence) |
|---|---|
| **Visa/MC interchange claims filing** | Deadline passed Feb 4, 2025. The court polices filers with mandatory disclosures and injunction threats ([Payments Dive](https://www.paymentsdive.com/news/visa-mastercard-swipe-fee-fund-has-paid-414m/821869/); [EDNY order summary](https://www.paymentcardsettlement.com/Content/Documents/9549%20-%20Sua%20Sponte%20Report%20and%20Recommendation%20re%20Merchant%20Stronghold%20and%20Cardsettlementorg.pdf)). No new money to claim. |
| **Securities class-action claims filing** | Owned by CCC (more than 2,900 institutional clients), Broadridge, ISS SCAS and FRT. Custodians like Schwab bundle it ([SIFMA](https://sources.sifma.org/listing/chicago-clearing-corporation); [Schwab](https://advisorservices.schwab.com/provider-solutions/Class-Action-Claim-Recovery)). Retail is low-value. |
| **Mass-tort signal intelligence for plaintiff firms** | Crowded by AI-native players: Darrow, TortIntel, LexGenius, TortSignal, Velocity Justice ([TortIntel](https://tortintel.ai/); [LexGenius](https://feed.lexgenius.ai/)). The real ad money (about $4B in legal ads; about $1B mass tort ([search summary](https://everything-pr.com/mass-tort-plaintiff-pr))) flows to media buyers and lead vendors, where TCPA risk is high. |
| **White-label trademark docketing and renewal monitoring for law firms** | Alt Legal sells docketing plus watch from $60/mo ([Alt Legal](https://www.altlegal.com/pricing/)), and Corsearch/CompuMark own watch services. Commoditized, so there's nothing to white-label profitably. |
| **Direct-to-owner Section 8/9 renewal services** | Non-attorneys can't file for others ([37 CFR 11.14](https://www.ecfr.gov/current/title-37/chapter-I/subchapter-A/part-11/subpart-B/subject-group-ECFRa9deb1f9b3dd8c7/section-11.14)). This is the exact pattern of the convicted renewal scam ([USPTO](https://www.uspto.gov/trademarks/protect/criminal-conviction-trademark-renewal-solicitation-scam)). Kept only as an attorney-branded add-on inside Idea 1. |
| **Brand protection and counterfeit monitoring subscription** | Red Points ($15k–$70k/yr), MarqVision, BrandShield and Corsearch at the top; Brand Protector ($199/mo) and others at the bottom. Amazon Brand Registry is free ([brandprotector.io](https://brandprotector.io/blog/red-points-alternatives)). No data edge. |
| **DMCA takedown for creators** | Many incumbents: Rulta, BranditScan and 18+ others ([Fanlock list](https://fanlock.com/best-dmca-takedown-services)). Adult-creator concentration adds platform and reputational risk. |
| **Copyright-infringement recovery (Pixsy-style)** | Pixsy and Copytrack take 45–50% ([picdefense](https://picdefense.io/demand-letters/enforcement/pixsy/)). It generates "troll" backlash, and the CCB small-claims route mostly dismisses: only 35 of 1,222 claims reached final determination ([CCB stats summary](http://www.ccb.gov/CCB-Statistics-and-FAQs-October-2025.pdf)). It also conflicts with the brothers' SMB-friendly brand. |
| **UCC-filing lead lists (MCA lending)** | Commoditized at $0.005–$0.75 per lead ([search summary](https://www.merchantfinancingleads.com/merchant-cash-advance-ucc-leads-lists)). MCA is heavily scrutinized. |
| **Bankruptcy claims brokering as broker of record** | 0.5–1% commissions ([search summary](https://www.fa-mag.com/news/wall-street-pros-offer-crypto-holders-a-backdoor-bankruptcy-exit-69154.html)). Relationship-driven, with securities-law ambiguity. Folded into Idea 4 as a data and sourcing service instead. |
| **Preference-suit defendant lead feed for defense attorneys** (standalone) | It works, but it's narrow and episodic. Real 547 waves arrive about 2 years after the petition, from a few dozen big liquidating trusts ([Bloomberg Law](https://www.bloomberglaw.com/external/document/X42I4GLC000000/bankruptcy-overview-managing-preference-action-litigation)). Folded into Idea 5. |
| **Construction lien-deadline tool** | Proven willingness to pay (Procore bought Levelset for $500M ([Procore](https://www.procore.com/press/procore-completes-acquisition-of-levelset-to-simplify-lien-management-workflows-for-construction))), but now owned by an incumbent platform. |
| **Judgment-recovery origination from state courts** | State-court data is fragmented and costly (UniCourt and Trellis APIs by quote). Collection-law and FDCPA exposure. |
| **Litigation "you've been sued" alerts to SMB defendants** (generic) | Defense firms already monitor. Selling legal outcomes to defendants without being a law firm edges toward UPL. Only the ADA vertical (Idea 3) has a non-legal product to sell. |

---

## 4. Ranked shortlist

The scale is 1 to 10, where 10 is best. For competition, 10 means blue ocean. The **overall** score is a judgment weighting: willingness to pay, legal risk and data access count more than a straight average. The straight average is shown for transparency.

| Rank | Idea | Market | WTP | Data access | Automation | Competition | Recurring | Time to $ | Avg | **Overall** | Confidence |
|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | **Pro-se OA feed for trademark attorneys** | 5 | 6 | 9 | 8 | 5 | 8 | 7 | 6.9 | **6.6** | Medium. Data and willingness to pay are solid; attorney conversion is unproven. |
| 2 | **B2B Found-Money sweep via CPA firms** | 6 | 6 | 6 | 7 | 6 | 5 | 6 | 6.0 | **6.2** | Medium-low. The business share of the pool and average hit size are unknown. |
| 3 | **ADA lawsuit signals → site rebuild** | 7 | 6 | 7 | 7 | 3 | 6 | 7 | 6.1 | **6.0** | Medium. Synergy with the brothers' existing engine; crowded. |
| 4 | **Trade-claim sourcing engine for claims buyers** | 4 | 7 | 7 | 7 | 6 | 7 | 5 | 6.1 | **5.8** | Low-medium. Tiny buyer universe; outsourcing appetite unknown. |
| 5 | **Creditor-side bankruptcy action briefs** | 5 | 5 | 6 | 8 | 4 | 8 | 5 | 5.9 | **5.5** | Medium-low. |
| 6 | **Settlement-eligibility radar and filing for SMBs** | 6 | 5 | 7 | 7 | 4 | 4 | 6 | 5.6 | **5.2** | Medium. Evidence is good, but the economics look thin. |
| 7 | **Name-conflict watch for local businesses** | 5 | 3 | 7 | 8 | 8 | 6 | 5 | 6.0 | **4.8** | Low. Blue ocean mostly because nobody pays. |

### Honest read

- **Nothing here is a slam dunk.** The legal-data lane has been mined for 20 years by Westlaw, Lexis, Corsearch, Epiq and the claims filers. The newer AI wave (Darrow, TortIntel, AI accessibility scanners) has already taken the "Claude reads the dockets" angle in mass torts and ADA.
- The **defensible edge** comes from two things:
  - (a) **qualifying public events into ranked, pre-decoded opportunities for a licensed professional** who carries the regulatory burden (attorneys in Idea 1, CPAs in Idea 2)
  - (b) **reusing the brothers' existing local-business funnel** (Ideas 3, 6 and 7)
- **Recommended first move:** build Idea 1. All its data is free, it's 2–3 weeks of engineering, the ROI is measurable from public data, and it's clean if attorneys send the outreach.
- In parallel, run a 10-firm CPA pilot of Idea 2. Its biggest unknown, the average business hit size, can be answered cheaply in weeks with CA and NY bulk lists.
- Treat Idea 3 as a **feature of the core website business**, not a new company.

### Open questions to resolve before committing (cheap to test)

1. **Idea 1:**
   - Pull 30 days of bulk XML and count pro-se office actions. Measure what share have a visible email.
   - Backtest how many later get an attorney appearance. That is the baseline conversion.
2. **Idea 2:**
   - Run 500 known SMB names (from the website-business prospect list) through the CA weekly CSV and NY lists.
   - Measure hit rate and median amount. If the median is under about $500, kill the contingency version.
3. **Idea 4:**
   - Count distinct transferees in Rule 3001(e) notices across 20 recent mid-size cases. That measures the real buyer universe.
4. **Legal:**
   - A one-hour consult with (a) a trademark ethics attorney on per-state solicitation template rules, and (b) an unclaimed-property attorney on whether a CPA-fronted model needs separate finder registration in CA and NY.
