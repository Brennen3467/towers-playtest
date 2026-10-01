# Verify-5: Adversarial verification of SMB-adjacent, trucking, aviation and restaurant ideas, plus a second opinion on the two seed ideas

*Verification date: 2026-10-01. Research only: no outreach, signups or purchases. Original write-ups were read from `origin/research/09-smb-adjacent`, `10-intent-signals`, `04-compliance`, `11-wildcards`, `01-ma-origination` and `02-trade-intel`. Every finding has a URL. Primary-source checks I ran myself (FMCSA Socrata API queries) are reproducible from the URLs given. **(est.)** marks my own arithmetic or judgement.*

**Method and limits**
- About 150 web searches and fetches in total, split across this session and four parallel verifier sub-agents.
- FMCSA data was queried live through the Socrata SODA API on data.transportation.gov.
- Some FAA pages (the releasable-registry download page and `ardata.pdf`) returned HTTP 403, so the registry field list comes from mirrors and resellers.
- Many SaaS prices come from third-party pricing blogs. Prices confirmed on the vendor's own page are marked "(official)".
- Reddit was not used.

---

## Verdict summary

| # | Idea | Original score(s) | Verdict | Revised score | Confidence |
|---|---|---|---|---|---|
| 1 | AI + Maps Visibility Plan (L09 #1 and #2) | 7.0 / 6.6 | **WEAKENED** | **5.0** as an upsell to existing site customers; **3.5** as a cold-outbound product | Medium-high |
| 2 | Trucking insurance renewal / lapse intelligence (L09 6.4, L10 4.0, L04 5.3) | 4.0–6.4 | **WEAKENED** (close to killed as a SaaS) | **3.5** | Medium-high |
| 3 | Aircraft-owner outreach for avionics/MRO shops (L11 #3) | 6.4 | **WEAKENED** | **4.0** | Medium |
| 4 | Restaurant commission-leak site + ordering (L09 #3) | 6.0 | **KILLED** as specified | **2.5** | High |
| 5a | Seed: M&A sell-side origination (L01) | 6.4 (#1) / 6.0 (#2) | **WEAKENED** | **4.0** (#1 data product) / **4.5** (#2 flat-fee origination) | Medium |
| 5b | Seed: Competitor Sourcing-Shift Monthly (L02 #5) | 5.0 | **WEAKENED** (L02 was right) | **4.0** | Medium-high |

**Cross-cutting lesson.** All four batch ideas assumed public data plus a Claude-written brief would be differentiated. In every case, a vendor already ships that same brief at $25–$250/mo: BrightLocal, Local Falcon, Merchynt, Carrier IQ, PollyAI, DoorDash Starter, and the Apify registry scrapers. The brothers' surviving edge is **done-for-you execution sold to people who already trust them**, not data.

---

## Idea 1: "AI + Maps Visibility Plan" (L09 Ideas 1+2)

**Verdict: WEAKENED. Revised 5.0/10 as an upsell to the brothers' existing website customers, 3.5/10 as a cold-outbound lead offer. Confidence: medium-high.**

### Claims checked

| Original claim | Finding | Source | Holds? |
|---|---|---|---|
| "SMB willingness to pay specifically for AI visibility is unproven" | Still unproven at ~$149 for *monitoring*. Agencies sell GEO as a $900+/mo add-on, and productized dental GEO is quoted at $1,400–5,500/mo. These are price lists, not retention evidence. Self-serve SMB AI-visibility tools sit at $25–$99. | [Young Co.](https://youngcompany.com/knowledge-base/how-much-do-marketing-agencies-charge-for-aio-geo-and-seo-in-2026/), [Citevio](https://citevio.com/geo-for-dental-clinics-cost) | Yes (the caution stands) |
| "BrightLocal and Yext are only now adding local AI tracking … window lasts 12–18 months" | **The window has already closed.** BrightLocal's Local AI Visibility Tracker (Google AI Overviews, AI Mode, ChatGPT; 20 prompts/location) "comes as standard in our Track, Manage, and Grow plans", from **$31/mo** (official). Local Falcon includes AI-engine geo-grids on every plan from $24.99. | [BrightLocal (official)](https://www.brightlocal.com/local-seo-tools/local-ai-visibility/), [Local Falcon](https://www.localfalcon.com/) | **No** |
| Competitors: Paige $99, Semrush AI $99, Otterly $29–489, Peec ~€85+ | Confirmed. Merchynt Paige is $99/location with white-label wholesale ~$20/profile and now markets GEO for ChatGPT, Gemini and AI Mode. Profound has a $99 Starter (ChatGPT only) and $399 Growth. Peec €85/€205/€425. Localo $39–49 with an AI agent. | [Merchynt (official)](https://www.merchynt.com/pricing), [leadoracle](https://www.leadoracle.ai/blog/merchynt-pricing-guide), [get-ryze Profound](https://www.get-ryze.ai/blog/profound-pricing-2026), [trakkr Otterly](https://trakkr.ai/reviews/otterly-review/pricing), [workduo Peec](https://www.workduo.ai/blog/peec-ai-pricing), [get-ryze Semrush](https://www.get-ryze.ai/blog/semrush-ai-visibility-pricing-2026), [Localo](https://localo.com/pricing) | Yes |
| Birdeye / Podium / Yext | Birdeye "Search AI" offers Share-of-Answer by location (quote-only, annual). Yext Scout is an enterprise add-on, and Yext is building "Corvo AI" for SMB owners after buying GoShine. I found no Podium AI-visibility product. | [Birdeye](https://birdeye.com/blog/best-ai-search-visibility-tools/), [Yext Q2 FY27 PR](https://investors.yext.com/news-events/press-releases/detail/391/yext-announces-second-quarter-fiscal-2027-results), [Yext Scout](https://www.yext.com/platform/scout) | Yes |
| GHL snapshot sellers | No native HighLevel AI-visibility feature found. White-label AI-visibility report vendors for agencies already exist (Lighthouse Local, GEO Catalyst, SEOforGPT). Vendasta's marketplace lists 250+ white-label SMB products. | [Lighthouse Local](https://www.lighthouselocal.ai/blog/white-label-ai-visibility-tracking-for-agencies), [GEO Catalyst](https://www.geocatalyst.ai/white-label-ai-visibility-reporting), [Vendasta](https://www.vendasta.com/partners/) | Partly |
| Snapshot via "LLM APIs with web search … Must use the API" proves "whether ChatGPT recommends you" | **This is the core flaw.** Surfer's August 2026 study (1,000 prompts, 13,779 answers, 5 products) found raw brand overlap between API and scraped consumer UI of only **15.5%–23.8%** (21–32% after canonicalizing). ChatGPT's UI cited 12.1 sources versus 3.1 via the API. The legal method (API) does not show what consumers see. The faithful method (scraping the UI) violates OpenAI's terms. | [Surfer](https://surferseo.com/blog/llm-scraped-ai-answers-vs-api-results), [OpenAI terms](https://openai.com/policies/row-terms-of-use/) | **No** |
| Measurement is repeatable (implied by the "proof-first" pitch) | SparkToro/Gumshoe (2,961 runs): fewer than 1 in 100 runs return the same brand list and fewer than 1 in 1,000 the same order. Google AI Mode has 9.2% URL overlap across repeat sessions. Only *mention frequency over many samples* is meaningful; "rank" is noise. L09 itself flagged this as kill risk 2, and the evidence confirms it. | [Search Engine Land](https://searchengineland.com/ai-recommendation-lists-rarely-repeat-study-468076), [MediaPost](https://www.mediapost.com/publications/article/412364/ai-brand-recommendations-chaotic-inconsistent.html), [SEJ](https://www.searchenginejournal.com/study-google-ai-mode-returns-largely-different-results-across-sessions/550249/) | **No** |
| "LLM sampling ~$0.20–$0.50 per prospect (est., not verified)" | Cost is not the problem. OpenAI web search is $10/1K calls (reasoning models) or $25/1K. Gemini grounding is $14/1K after 5K free per month. The 30-call snapshot costs about $0.30–0.75. | [OpenAI pricing](https://developers.openai.com/api/docs/pricing), [Gemini pricing](https://ai.google.dev/gemini-api/docs/pricing) | Yes |
| Churn 5%/mo | Reasonable. SMB SaaS runs 3–7%/mo, and SEO agency clients ~3.2%/mo (~32-month life). Yext customers under $50K ARR had **69% dollar gross retention** a year (official, July 2026), down from 75%. | [Kalungi](https://www.kalungi.com/blog/saas-churn-rate-benchmarks), [Focus Digital](https://focus-digital.co/average-marketing-agency-churn/), [Yext PR](https://investors.yext.com/news-events/press-releases/detail/391/yext-announces-second-quarter-fiscal-2027-results) | Yes |
| GBP API: lead-gen prohibited, consent for automated edits, 30-day cache | Confirmed. Using GoogleLocations data for lead generation leads to revocation. Agencies need their own Cloud project and a verified GBP active 60+ days. | [GBP policies](https://developers.google.com/my-business/content/policies), [prereqs](https://developers.google.com/my-business/content/prereqs) | Yes |
| Close rate 0.5–1% of prospects, CAC $60–120 | Optimistic. The 2026 Instantly benchmark puts average cold-email reply rate at 3.43% (top quartile 5.5%). Converting ~15–30% of replies to a sale at $149 is aggressive for a commodity offer that BrightLocal-equipped agencies already bundle. Model it at 0.2–0.5% (est.), giving a CAC of ~$150–300 before founder time. | [Instantly 2026](https://instantly.ai/cold-email-benchmark-report-2026) | Partly |
| Consumer demand: 45% used AI for local recommendations; 97% cross-check reviews | Confirmed. ChatGPT named only ~1.2% of 350K local locations, versus 35.9% for Google's 3-pack. Most clients will therefore see "0% visibility" month after month. | [BrightLocal LCRS](https://www.brightlocal.com/research/lcrs-ai-trust/), [MarketingCode/SOCi](https://www.marketingcode.com/chatgpt-recommends-1-percent-local-businesses-contractors/) | Yes, but it cuts both ways |

### New competitors and risks

- **New competitors:**
  - Local Falcon (AI geo-grid on all plans, $24.99–$199.99)
  - SOCi
  - Lighthouse Local
  - LLMrefs ($79)
  - Rankscale (€20)
  - Ahrefs Brand Radar
  - ChatFeatured ($2M pre-seed, July 2026)
  - Gumroad "AI optimization" subscriptions at $5.99–$90/mo ([Lighthouse Local list](https://www.lighthouselocal.ai/blog/ai-search-visibility-tools-for-small-businesses), [SaaSRise](https://www.saasrise.com/deals/chatfeatured-secures-2-million-usd-to-optimize-your-companys-chatbot-reach-0f464c42-0612-488d-9145-fe72655bfb01))
- **Legal: FTC substantiation.** A "ChatGPT doesn't recommend you" email built from API answers that overlap only ~20% with what users see is a claim you cannot substantiate. The accessiBe order ([FTC](https://www.ftc.gov/news-events/news/press-releases/2025/01/ftc-order-requires-online-marketer-pay-1-million-deceptive-claims-its-ai-product-could-make-websites)) shows the FTC acts on unsubstantiated AI claims. Word the snapshot as "in N of M sampled API answers…".
- **Legal: other.** CAN-SPAM applies to every send. State anti-spam laws add little for B2B email beyond CAN-SPAM, which pre-empts most of them except for falsity or deception. Texting SMB owners' cell phones falls under the TCPA, so email only. No licensing issues.
- **Automation.** Snapshot generation and reports are ~90% automatable. Human time goes to GBP suspensions and reinstatements, review-feed onboarding, and disputes like "my phone shows something different". The 80% claim is fair.

### Single most likely way this fails

The client checks ChatGPT on their own phone, sees a different answer from the report, and cancels. Meanwhile, the agency down the road gives the same report away inside a $31 BrightLocal seat.

### Changes that would make it viable

1. **Sell it only to existing website customers first** (CAC ≈ 0), as a done-for-you **"Reviews + GBP + Citations" plan at $79–$129**. Put AI visibility in the monthly report as the hook, not the product.
2. **Build on wholesale tools instead of a custom sampler:** BrightLocal $31, Merchynt white-label ~$20/profile, Local Falcon. Report *mention rate across ≥10 samples per prompt*, with the method disclosed.
3. **For cold outbound, lead with the review gap**, which is deterministic and verifiable from the Places API, not with the AI snapshot.
4. **Kill gate:** fewer than 10% of existing site customers take the upsell within 60 days.

---

## Idea 2: Trucking insurance renewal / lapse intelligence from FMCSA data

**Verdict: WEAKENED, close to KILLED as a standalone SaaS. Revised score 3.5/10 (confidence: medium-high).**

**How the three lanes' scores compare.** Lane 10 (4.0) and lane 04 (5.3, "crowded") were closer to the truth than lane 09 (6.4).

Lane 09 made two mistakes:
- It treated "renewal-window plus risk-scored data" as differentiated, but at least five vendors already sell exactly that for $79–$249/mo.
- It priced Option B at "$299–$999/mo". That is 2–10× the observed market.

I also found something none of the three lanes caught. Since FMCSA moved to Motus on 14 May 2026, the free public bulk data **no longer exposes pending (future-dated) cancellations**. That removes the most valuable signal, the "30-day lapse warning".

### Primary-source spot checks (Socrata API, data.transportation.gov, queried 2026-10-01)

| Check | Result |
|---|---|
| Lane 09's dataset `ActPendInsur – All With History` ([y77m-3nfx](https://data.transportation.gov/Trucking-and-Motorcoaches/ActPendInsur-All-With-History/y77m-3nfx)) | Metadata `rowsUpdatedAt` = **6 Dec 2023**. It is a stale copy. Lane 09's `chgs-tx6x` link returns no metadata. |
| Legacy live copy `ActPendInsur – All With History` ([qh9u-swkp](https://data.transportation.gov/resource/qh9u-swkp.json)) | 467,983 rows. Fields: docket, DOT, form code, insurer name, policy no, trans_date, effective_date, cancl_effective_date, limits. **Max `trans_date` = May 2026**, so it froze at the Motus cutover. 384,507 distinct DOT numbers hold a BMC-91/91X liability filing. |
| Pending cancellations in the legacy file | 22,119 rows have a cancel-effective date. They cluster in May–June 2026 (19.8K), then drop to 120 (Aug), 28 (Sep) and 16 (Oct). This is consistent with the feed freezing. |
| Motus-native `Motus Insur – All With History` ([c5y8-a4uz](https://data.transportation.gov/resource/c5y8-a4uz.json)) | 129,713 rows, 111,738 distinct DOTs, ~10–15K new filings a month (27,563 since 1 Aug 2026). **It has no cancellation-date column.** Fields: insurer, effective date, policy no, form, limits, trans_date. |
| `Motus InsHist – All With History` ([3uet-3z4i](https://data.transportation.gov/resource/3uet-3z4i.json)) | 48,781 rows. `FILING_STATUS_REASON` takes the values CANCEL / TERM/REPL / NAMECHG. BMC-91 CANCEL rows by cancel-effective month: Jun 3,401, Jul 5,353, Aug 3,378, Sep 930; **only 12 rows are dated after 1 Oct 2026.** Cancellations therefore appear around or after the effective date, not 30 days ahead. The "lapse radar" becomes a "just lapsed" list. |
| Is the renewal date in the data? | **No.** BMC-91X filings are continuous, and a policy "stays in force continuously unless one party cancels" ([49 CFR 387.7/387.313](https://www.law.cornell.edu/cfr/text/49/387.313)). For the largest insurers, active filings' effective dates are spread over many years (e.g. Great West: 2026 3,730; 2025 8,480; 2024 6,837; 2023 4,684; 2022 3,117). So the effective date is the *original filing date*, not the current term start. The anniversary month is a guess and has not been validated. |
| Data-quality issues | Legacy rows include impossible effective dates (2027–2032; e.g. a Progressive filing with trans_date 2023 and effective 08/10/2032). [Fleetfax](https://www.fleetfax.com/research/motus-cutover) found that Motus public exports **silently omit carriers**: of 9,849 carriers that read as lapsed, 541 (5.5%) actually had active insurance. Cancellations recorded only in Motus may never reach the exports. |
| Census universe | Company Census File ([az4n-8mr2](https://data.transportation.gov/resource/az4n-8mr2.json)): 2,245,127 active DOT records, 660,450 active interstate with ≥1 power unit. Among active records with an active MC docket (665,632): 443K have 1 PU, 152K 2–5, 31K 6–10, 18K 11–20, 21K 21+. **599,589 have an email address.** Email availability is not a moat; every vendor has it. |

### Claims checked

| Original claim | Finding | Source | Holds? |
|---|---|---|---|
| L09: "FMCSA ActPendInsur: free daily-difference file … effective, posted and cancel-effective dates" | True only before 14 May 2026. The legacy feeds are frozen. The Motus replacement has no cancel-date column in Insur, and InsHist posts cancels at or after the effective date. | Socrata queries above; [FMCSA Motus notice](https://www.fmcsa.dot.gov/sites/fmcsa.dot.gov/files/2026-05/USDOT%20Mail%20-%20Transition%20to%20Motus%20Begins%20May%2014.pdf); [Fleetfax](https://www.fleetfax.com/research/motus-cutover) | **No** (for the lapse signal) |
| L09: "pending cancellations show up in near-real time" (30-day BMC-35) | The 30-day notice rule is real ([387.313](https://www.law.cornell.edu/cfr/text/49/387.313)), but the future-dated cancel is not in the public bulk data now. It may be visible per carrier on the Motus or L&I web lookup. That means per-carrier polling, and the terms are unverified. | as above | **No** |
| L10: "legacy InsHist stopped updating May 14 2026" | Confirmed, and it applies to ActPendInsur and Insur as well. | Socrata `trans_date` max | **Yes** |
| L09: renewal date "*inferred* from the anniversary" | Correctly flagged as an inference. The data shows effective dates are original filing dates spread over years. Accuracy is unknown; needs ground truth from an agency's book. | Socrata distribution | Partly |
| L09: Option B SaaS at "$299–$999/mo" | The market anchor is far lower. Carrier IQ: $149/mo for 1 state, $199 for 5, $249 for 10 (annual $119–$199), including "Policy Renewals" and "Mid-Term Cancellations" plus a CRM. PollyAI: $39 + $40/state, with "insurance expiration on every carrier". | [Carrier IQ pricing](https://carrieriq.io/pricing), [PollyAI](https://getpollyai.com/blog/best-trucking-insurance-leads) | **No** |
| L09: competition "Moderate … renewal-window + risk-scored … less common" | Wrong. Already selling renewal X-dates and/or cancellations to agents: Carrier Software DOT Leads ("X dates, form letters and email marketing", listed on the Travelers innovation network), Carrier IQ, PollyAI, CarrierOk ("explicitly supports the 30–60 day renewal window"), Carrier Network (HOT/WARM/COLD coverage events), MyTruckingLeads ("renewal prospects"), TruckingSignal (auto-emails in the agent's name, territory-exclusive), TruckerDB $49, Carrier Leads Direct $297. | [Carrier Software](https://www.carriersoftware.com/products/dot-leads/), [Travelers](https://innovationnetwork.travelers.com/solution/hub/42), [CarrierOk](https://getpollyai.com/blog/carrierok-alternative), [Carrier Network PR](https://www.issuewire.com/growing-usa-trucking-insurance-lead-platform-helping-agents-quote-faster-1858705820310451), [MyTruckingLeads](https://www.mytruckingleads.com/), [TruckingSignal](https://www.truckingsignal.com/) | **No** |
| L04: "crowded" | Confirmed, and more crowded than L04 listed. | as above | **Yes** |
| L09: "~$1,500/yr average commission per small carrier" | Plausible. A single-truck dry-van package averages ~$11.8K/yr (range $8–16K), so 10–15% commission is $1.2–1.8K. ATRI puts insurance at $0.11/mile in 2025, up 6.4% in Q1 2026. | [Truck Writers](https://truckwriters.com/blog/average-cost-of-commercial-truck-insurance/), [FleetOwner/ATRI](https://www.fleetowner.com/operations/article/55392569/atri-report-breaks-down-class-8-truck-operating-costs-by-region-and-expense-category) | Yes |
| L09: "active interstate carriers several hundred thousand, majority <10 trucks" | Confirmed: 384.5K DOTs with active BIPD filings (legacy, May 2026). About 92% of MC-docket carriers have ≤5 PUs. | Socrata | Yes |
| L10: agent market "low thousands of agencies, $1–2M ARR ceiling" | No primary count exists. For scale, Sentry alone has 65 specialist trucking agencies ([search](https://www.sentry.com/who-we-serve/trucking-insurance)). At ~$150/mo the SaaS ceiling is even lower than L10 said: 3,000 agencies × $150 × 12 ≈ $5.4M *total* across all vendors (est.). | — | Yes (if anything, generous) |
| Carrier411 / Highway / RMIS / FreightValidate / CarrierSource as competitors | These are **broker-side** carrier-vetting and insurance-monitoring tools: Carrier411 ~$35/user to $99/mo; RMIS (Truckstop) ~$200–350/mo; Highway is enterprise identity. They are not agent-prospecting tools, but they show FMCSA insurance monitoring is a commodity feature. I found no agent product called "CarrierSource". | [Carrier411](https://www.carrier411.com/), [RMIS/Truckstop](https://www.prnewswire.com/news-releases/truckstopcom-acquires-registry-monitoring-insurance-services-rmis-301252521.html), [Highway](https://highway.com/), [FreightValidate](https://freightvalidate.com/), [Carrier411 alternatives](https://www.cipherandrow.com/blog/carrier411-alternatives-2026) | n/a: adjacent |

### Legal and regulatory

- **Option A (become the agency).** Needs a P&C producer license in each state where you sell, plus carrier appointments. Trucking markets rarely appoint brand-new small agencies, so in practice the route is a wholesaler or aggregator (L09 kill risk 3, unrebutted).
- **Option B (SaaS or lead sale).** Needs no license if the fee is flat and not contingent on a sale. Contingent referral fees are capped in some states, e.g. NC $50 ([NCDOI](https://www.ncdoi.gov/documents/agent-services/referral-fees-faqs/open)).
- **TCPA.** Most carriers are 1-truck sole proprietors whose phones are personal cell phones. Autodialed or AI-voice calls and texts need prior express consent ([FCC 2024 AI-voice ruling](https://docs.fcc.gov/public/attachments/DOC-400393A1.pdf)).
- **CAN-SPAM** applies to every email.
- **Trust damage.** FMCSA-data scam and impersonation spam ("DOT compliance" scams) has poisoned this channel ([TruckersReport forum](https://www.thetruckersreport.com/truckingindustryforum/threads/dot-compliance-group-scam-and-spam.2350203/)).
- **Data-broker registration.** Selling compiled data on sole-proprietor carriers (natural persons) to third parties can trigger data-broker registration in CA, VT, TX and OR (est., not verified per state). This is a risk for Option B, not Option A.

### Automation

- Data ETL and scoring: ~95% automatable.
- Agent-side outreach: TruckingSignal already automates it in the agent's name.
- The quote and bind step is licensed human work: loss runs, MVRs, ELD data, underwriting submissions.

### Unit economics (revised)

- Price anchor: **$79–$249/mo**, not $499.
- At ~$150/mo and agency churn of ~4–6%/mo (est., SMB SaaS), LTV is about $2.5–3.75K. That only pays for a CAC under ~$1K.
- Agents are reachable: there are few of them and they are on LinkedIn. But they are already pitched by 8+ vendors.
- Cold-email reply rates to insurance agents should be modeled at the generic 1–3% (est.).

### Single most likely way this fails

You arrive as the 9th vendor with a weaker data feed: no future-dated cancellations since Motus, and the same renewal-date guesses as everyone else. You sell at Carrier IQ's price into a market of a few thousand agencies.

### What would make it viable

1. **Don't sell data; be the agency's outbound department.** Run done-for-you renewal-timed **email** campaigns in the agency's name, with personalised briefs. Charge $1–2K/mo flat to 10–20 trucking agencies. This mirrors the brothers' existing skill. TruckingSignal does this only for *new authorities*, so the renewal and mid-term segment is the gap.
2. **Ground-truth the renewal inference first.** Get one agency's book (policy term dates for ~200 carriers) and measure how often filing-anniversary month equals actual renewal month. Kill the idea if accuracy is below ~60%.
3. **Get pending-cancel data legally per carrier.** Check whether the Motus or QCMobile API exposes future-dated BMC-35s and whether its terms allow commercial polling. Without that, drop the "lapse" pitch.
4. Optionally, **partner with a licensed wholesaler** and take an agreed share via the licensed entity. Get counsel on rebating and referral rules first.

---

## Idea 3: Aircraft-owner outreach for avionics/MRO shops (L11 #3)

**Verdict: WEAKENED. Revised 4.0/10 (confidence: medium).**

### Claims checked

| Original claim | Finding | Source | Holds? |
|---|---|---|---|
| FAA Releasable Aircraft Database has owner, address, make/model/year; "~269k–301k records"; free daily download | Fields confirmed: name, street, city, state, zip, make/model, year. **No phone or email.** Record counts: ~312.7K registered on a third-party explorer; Datamasters sells 246,180 owners after deduplication. The FAA download page returned 403 to us, so fields were verified via mirrors. | [FAA ardata.pdf](https://registry.faa.gov/database/ardata.pdf), [simonw mirror](https://github.com/simonw/scrape-faa-releasable-aircraft), [Datamasters](https://www.datamasters.org/mailing-lists/aircraft-mailing-list-data-samples/), [faa-app explorer](https://faa-app-bc1.pages.dev/) | Yes |
| "Since 2025, owners can withhold their address" | Confirmed: FAA Reauthorization §803 (49 USC 44114), effective 28 Mar 2025. Opt-outs reportedly number only ~200, but the FAA has **sought comment on making withholding the default** for private owners. If adopted, most of the data source disappears. | [FAA](https://www.faa.gov/newsroom/faa-moves-protect-aircraft-owners-private-information), [Cozen](https://www.cozen.com/news-resources/publications/2025/faa-proposes-to-increase-privacy-for-private-aircraft-owners-and-operators), [Flying](https://www.flyingmag.com/faa-database/) | Partly (risk understated) |
| 5,038 Part 145 stations | That figure comes from a third-party directory and includes foreign stations. I could not reconcile it to an FAA primary count. ARSA counts 1,507 US stations with EASA approval. Most 145s are component, airline or engine shops, not piston-GA avionics installers. | [faa145stations](https://faa145stations.com/), [ARSA](https://arsa.org/easa-us-certificates/) | Unverified; overstates buyers |
| ~1,300 AEA member companies | "Nearly 1,300 member companies in more than 40 countries", including manufacturers and distributors. US GA installing shops are probably a few hundred (est.). | [WAI/AEA](https://www.wai.org/corporate-members/aircraft-electronics-association) | Yes, but the buyer count is smaller |
| "~6k shops × 20% × $500 ≈ $7M ARR ceiling" | Too high. Realistically ~300–800 relevant US shops × 20% × $600 ≈ **$0.4–1.2M ARR** (est.). | — | **No** (overstated) |
| Shops pay agencies for leads | Confirmed. Shops spend $2–5K/mo on ads for 20–30 leads (OutboundClick); Off The Ground Marketing starts at $1,500/mo. A $400–800/mo price is plausible. | [OutboundClick](https://outboundclick.com/industries/aviation), [OTG](https://www.offthegroundmarketing.com/aviation-marketing-us) | Yes |
| Registry + AD join is a differentiated deliverable | The data is a commodity: Apify registry scrapers cost $3–10 per 1K rows, Datamasters sells postal at $0.14/name, a NextMark list of 39K owner emails costs $175/M, and GlobalAir AvBlast sells GA email blasts. **ADs are a weak trigger.** Annual and 100-hour inspections must verify AD compliance, so the owner's existing IA handles them. Upgrade pitches (e.g. the Garmin AXIS STC for hundreds of piston models, $8K–$23.4K) are stronger. | [Apify](https://apify.com/scrapemint/aircraft-owner-leads), [NextMark](https://lists.nextmark.com/market?page=order%2Fonline%2Fdatacard&id=201898), [AvBlast](https://www.globalair.com/myaircraft/avblast), [FAA AD responsibilities](https://www.faa.gov/aircraft/air_cert/continued_operation/ad/gen_resp), [AeroTime](https://www.aerotime.aero/articles/garmin-axis-integrated-flight-displays/amp) | **No** |
| Demand exists | Demand is real but **capacity-constrained**. Retrofit sales were up 26.8% YoY in the latest AEA report I found, and installers are "booked out months". A backlogged shop doesn't need a lead service, so churn would be quick. | [AEA market report](https://aea.net/marketreport/), [AVweb](https://avweb.com/aviation-news/ads-b-installs-delay-backlog-will-be-worse-next-year/), [e3](https://e3aviationassociation.com/aviation-articles/general-aviation-market-2026/) | Cuts against the idea |
| "Postal mail is safest" | Agreed. Matching emails to individual owners (47% of aircraft are owned by individuals, 19% by LLCs) makes the brothers a **data broker** under California's Delete Act, and DROP deletion processing has been mandatory since 1 Aug 2026. | [GAO-20-164](https://www.gao.gov/products/gao-20-164), [CPPA](https://cppa.ca.gov/data_brokers) | Yes |

### Newly discovered competitors and risks

- **Competitors:**
  - Datamasters, AIRPAC (since 1981), Amerilist, DMDatabases, NextMark lists
  - OutboundClick (exclusive avionics leads, no lock-in)
  - AvBlast/GlobalAir
  - Savvy for Shops (2025), which owns the owner relationships
- **Regulatory risk:** the FAA may make owner withholding the default.

### Automation

Building the lists is ~95% automatable, but postal outreach adds per-piece cost and lag. Reply handling is mostly phone calls to shops.

### Single most likely way this fails

The good shops are booked months out and the struggling ones can't pay. The data is $0.14 a name from list brokers, so there is nothing defensible.

### Changes that would make it viable

1. Make it **campaign-priced, postal-only "STC upgrade campaigns"**: "your 1978 PA-28 qualifies for X", sent to owners within 150 nm.
2. Sell to shops that just earned a new install certification or have open bays.
3. Better still, sell to **avionics OEMs' dealer-marketing programs**, where one buyer has hundreds of shops. Whether Garmin or Avidyne run co-op programs is unconfirmed.
4. Treat it as a cross-sell of the core website product to aviation shops, not as a separate business.

---

## Idea 4: Restaurant "commission-leak" site + direct ordering (L09 Idea 3)

**Verdict: KILLED as specified. Revised 2.5/10 (confidence: high).**

**The fatal finding that L09 missed:** DoorDash's Commerce Platform **Starter tier is free**. It includes "a free branded website and commission-free online ordering", "built and maintained by DoorDash using the menu, branding and images already used on its platform". Paid tiers are Boost $54 and Pro $249 ([PYMNTS](https://www.pymnts.com/restaurant-technology/2025/doordash-adds-tiered-membership-packages-to-commerce-platform-for-restaurants/), [DoorDash branded websites](https://merchants.doordash.com/en-us/products/branded-websites)). Uber has an equivalent in Webshop ([Uber](https://merchants.ubereats.com/us/en/services/online-ordering/)). Every prospect the pipeline would target, a restaurant whose Order button already points to DoorDash, can get the brothers' deliverable free from its existing vendor.

### Claims checked

| Original claim | Finding | Source | Holds? |
|---|---|---|---|
| Owner.com raised $240M at a $2.3B valuation, $100M+ ARR, expanding to "every local business" | Confirmed: Goldman Sachs Alternatives led the round, and expansion covers salons, spas and grocers. | [PRNewswire](https://www.prnewswire.com/news-releases/owner-raises-240m-led-by-goldman-sachs-alternatives-to-build-the-ai-native-platform-for-every-local-business-302862420.html), [GS](https://am.gs.com/en-us/advisors/news/press-release/2026/owner-raises-240m-gs-alts) | Yes |
| Owner pricing $249 + 5% or $499 flat | Confirmed. Guests also pay a 5% order-support fee. | [Owner pricing](https://www.owner.com/pricing) | Yes |
| Owner is "outbound-led" (~79% of new ARR from outbound) | Sacra estimates 60–70% inbound now. | [Sacra](https://sacra.com/c/owner/) | Partly (dated) |
| Toast ~164K locations, online ordering ~$75 add-on | 164K was the end-2025 figure. **~180K at Q2 2026** (+22% YoY, record 9,500 net adds). The $75 figure is third-party only; Toast bundles online ordering and Websites. | [Toast 8-K Q2'26](https://www.sec.gov/Archives/edgar/data/1650164/000165016426000162/tost-20260630xexhibit991.htm), [Toast Websites](https://pos.toasttab.com/products/websites) | Outdated |
| ChowNow $249–449; Popmenu $179–499 | Confirmed. ChowNow adds a $119–499 setup fee; Popmenu ordering is ~$50 plus $1/order. BentoBox: website from $119, ordering +$49 plus $0.99/order, pushed to Clover merchants. | [Sauce](https://www.getsauce.com/post/chownow-pricing-and-fees), [orderitto Popmenu](https://orderitto.com/compare/popmenu-pricing), [orderitto BentoBox](https://orderitto.com/compare/bentobox-pricing) | Yes |
| "Use Square Online ($0/mo, 3.3%+30¢) or Menufy" and "free tiers (Square Online, Menufy, GloriaFood)" | **Menufy now charges new customers $149–179/mo plus $1.75/order. GloriaFood stopped taking signups and shuts down on 30 Apr 2027** (~123K restaurants). Square is still $0/mo, at 3.3%+30¢ since Jan 2026. | [orderitto Menufy](https://orderitto.com/compare/menufy-pricing), [Menuro](https://menuro.io/blog/gloriafood-shutting-down-2027/), [agms](https://agms.com/square-price-increase-2026-alternatives/) | **No** (2 of 3 "free" backends gone) |
| DoorDash 15/25/30% tiers | Still current, but **pickup is 6%**. Most of the "leak" is delivery, and a direct-ordering site still needs a courier (Uber Direct from $7.99). | [DoorDash pricing](https://merchants.doordash.com/en-us/pricing), [Uber Direct](https://merchants.ubereats.com/us/en/services/uber-direct/) | Partly (the leak is overstated) |
| ~300K independents not on Toast | NRN counts **412,498 independents at end-2025, down 2.3%** (more than 9,500 net closures). | [NRN](https://www.nrn.com/independent-restaurants/the-independent-restaurant-sector-shrunk-by-2-3-in-2025) | Roughly, and shrinking |
| Churn 4–6%/mo | Supported. ~17% of restaurants close in year 1 and ~49% within 5 years. | [restolabs](https://www.restolabs.com/blog/restaurant-failure-rate) | Yes |

### Single most likely way this fails

The owner's DoorDash rep offers the identical free site the same week. Owner.com outspends the brothers on everyone else.

### Changes that would make it viable

1. **The GloriaFood shutdown is a hard deadline** (30 Apr 2027): a ~123K-restaurant migration window. Sell paid migration plus site rebuilds, ideally as a referral partner of Owner, ChowNow or Toast for a bounty.
2. Otherwise, fold "DoorDash-routed Order button" into the core website pitch as a proof line, and point owners to the free DoorDash/Toast/Square ordering. Don't sell ordering.

---

## 5. Second opinion on the brothers' seed ideas

### 5a. M&A sell-side origination for PE and investment banks (L01)

**My view: L01's "red ocean" verdict is right, but its escape route (Idea #1 "SuccessionMap") is weaker than it scored. Revised: Idea #1 4.0/10 (L01: 6.4); Idea #2, flat-fee origination, 4.5/10 (L01: 6.0). Confidence: medium.**

| L01 claim | Finding | Source | Holds? |
|---|---|---|---|
| SourceCo bought CAPTARGET (Apr 2026) | Confirmed (28 Apr 2026). SourceCo calls it "the first of several" acquisitions, so consolidation will continue. | [SourceCo](https://www.sourcecodeals.com/blog/sourceco-acquired-captarget-what-that-means-for-deal-sourcing), [CAPTARGET](https://www.captarget.com/insights/captarget-joins-sourceco-to-build-the-next-generation-of-buy-side-deal-origination) | Yes |
| Datasite bought Grata + Sourcescrub | Confirmed: Grata (Jun 2025), Blueflame AI agents (Jul), Sourcescrub (8 Aug 2025), backed by $500M from CapVest. | [BusinessWire](https://www.businesswire.com/news/home/20250808557102/en/Datasite-to-Acquire-Sourcescrub-Expanding-Private-Market-Intelligence-Solutions) | Yes |
| Succession-likelihood scoring for licensed trades is a gap ("Horizontal databases do not join these sources") | **Already productized.** DealSource Systems (Danish Lead Co.) downloads "the state contractor database, filter by HVAC or refrigeration licence type", prioritizes by founder age and tenure, and reaches owners "for a flat $4,000 a month". DealPotential markets predictive signals including aging founders. Inven ($12.75M Series A), OffDeal (YC, $17M) and Q2Q (YC) are also active. | [DealSource Systems](https://dealsourcesystems.com/blog/hvac-company-acquisitions-sourcing/), [DealPotential](https://dealpotential.com/), [Inven](https://www.inven.ai/articles/announcing-series-a-funding-deal-sourcing-private-market-research), [OffDeal/YC](https://www.ycombinator.com/companies/offdeal) | **No** |
| TX TDLR open data gives "State trade-license first-issue date … Owner tenure" | **False.** I pulled the column metadata for dataset `7358-krk7`. The fields are license type and number, county, business name, address and phone, `license_expiration_date_mmddccyy`, owner name, address and phone, subtype, and CE flag. **There is no issue or original-license date.** The core feature of the flagship build state is missing. It would need FOIA or license-number-sequence inference (untested). | [TDLR metadata](https://data.texas.gov/api/views/7358-krk7.json) | **No** |
| Tenure/age predicts a sale | No validating study found. The Minneapolis Fed says boomer owners are staying on rather than selling; Watermark says sell-side volume has fallen ~15%/yr since 2021. Only 20–30% of businesses taken to market actually sell. L01's own BizBuySell figure (9,586 closed deals in 2025) agrees. | [Minneapolis Fed](https://www.minneapolisfed.org/article/2023/why-are-boomer-business-owners-hanging-on-to-their-businesses-long-past-retirement-age), [Watermark](https://watermarkadvisors.com/wire/questioning-a-silver-tsunami/), [Project Equity](https://project-equity.org/impact/silver-tsunami/) | Unproven |
| Flat fee is the conservative structure | Agreed. It is not a safe harbor: about 17 states require a real-estate license for business brokerage, unlicensed brokerage is a felony in Florida, and Illinois requires registration. Stay buyer-paid, outreach-only, and do no negotiating or valuation. | [IBBA](https://www.ibba.org/articles/the-state-line-trap/), [bizbrokerplus](https://www.bizbrokerplus.com/blog/2025/04/02/states-that-require-real-estate-license-to-sell-business/), [Venable](https://www.venable.com/-/media/files/publications/2023/06/finders-and-unregistered-brokerdealers.pdf?rev=922155ed555f4819aea0b5d72e2d3681) | Yes |
| Buyers pay $2–25K/mo for origination | Confirmed, but they pay for **meetings**, not scores. Grata and Inven already sell lists. | [Axia](https://axiagrowth.com/blog/in-house-bdr-vs-outsourced-deal-sourcing) | Yes |
| Deliverability: Gmail/Yahoo 0.3% complaint limit | Confirmed, and Microsoft Outlook bulk-sender enforcement started in 2026. Many trades owners use Gmail or Outlook addresses. | [warmforge](https://www.warmforge.ai/blog/microsoft-bulk-sender-guidelines) | Yes |

**Most likely failure.** The brothers become the 200th AI-SDR shop emailing HVAC owners who already get weekly PE letters. The "succession score" can't be shown to beat a random list.

**What would make it viable:**
1. **The brothers' real edge is the website crawl, not the license data.** Score website staleness and owner disengagement for trades businesses in states whose license data *does* carry issue dates (verify per state).
2. **Backtest** against roughly 800 trades add-ons announced since 2022 before selling anything.
3. Then sell **per-meeting** (~$400–600, with a minimum) to the ~50 most acquisitive trades platforms.
4. Or white-label the agent stack to SourceCo or DealSource rather than competing with them.

### 5b. Competitor Sourcing-Shift Monthly (L02 Idea 5)

**My view: L02 got this one right and was if anything generous. Revised 4.0/10 (L02: 5.0). Confidence: medium-high.**

| L02 claim | Finding | Source | Holds? |
|---|---|---|---|
| ImportYeti free / Pro ~$50; ImportGenius $229/$449 | Confirmed. ImportYeti Enterprise starts at $1,000/mo. Both vendors have shipment **alerts** on tracked companies, as does Panjiva. Alerts are a commodity feature. | [Capterra](https://www.capterra.com/p/10006176/ImportYeti/), [ImportGenius](https://www.importgenius.com/pricing), [S&P Panjiva](https://www.spglobal.com/market-intelligence/en/solutions/products/panjiva-supply-chain-intelligence) | Yes |
| Assume subscription seats ban redistribution | Confirmed. ImportYeti's terms allow "personal, internal, non-commercial" use only. | [ImportYeti ToS](https://www.importyeti.com/policies/terms) | Yes |
| CBP AMS feed: "low thousands of dollars a month (est.)" | **Unsourced.** 19 CFR 103.31 says only "production cost". A 2023 FOIA request for bulk BOL data was refused, and no public price exists. A phone quote is the first gating step. | [19 CFR 103.31](https://www.law.cornell.edu/cfr/text/19/103.31), [Data Liberation Project](https://www.data-liberation-project.org/requests/cbp-bills-of-lading/) | Unverified |
| Consignee IDs missing on 12–17% | **Understated.** The same Fed paper shows missing consignee IDs ranged from 8.0% to 35.1% across 2007–2021. CBP's new online confidentiality tool cuts approval from 60–90 days to ~24 hours, which makes masking easier. The best-run competitors are the most likely to be masked. | [Fed FEDS 2021-066](https://www.federalreserve.gov/econres/feds/files/2021066pap.pdf), [FreightWaves](https://www.freightwaves.com/news/cbp-will-introduce-vessel-manifest-data-confidentiality-tool) | Partly |
| 2026 tariff churn makes sourcing news | Confirmed: IEEPA struck down (20 Feb), §122 surcharge (expired 24 Jul), then §301 forced-labor tariffs on 60 economies. Interest is real, but there is no evidence of *paid recurring* demand. | [Ropes & Gray](https://www.ropesgray.com/en/insights/alerts/2026/02/supreme-court-strikes-down-ieepa-tariffs-key-takeaways-and-implications-for-importers), [PwC](https://www.pwc.com/us/en/services/tax/library/pwc-ustr-imposes-sec-301-tariffs-following-forced-labor-investigations.html) | Yes |

**Most likely failure.** "Nothing changed this month" for most niches, plus the competitor that matters is masked. Customers churn by month 3.

**What would make it viable.** Use it only as the free hook for L02's Tariff Exposure Brief, as L02 recommends, or as a lead magnet for a sourcing or tariff consultancy. **Get the CBP feed price by phone before writing any code.**

---

## 6. Cross-idea ranking for this batch

| Rank | Idea | Revised score | Verdict | One-line reason |
|---|---|---|---|---|
| 1 | AI + Maps Visibility Plan, **as an upsell to existing site customers** (reviews + GBP + citations, AI as the reporting hook) | **5.0** | WEAKENED | Near-zero CAC and real done-for-you work. As a standalone AI-report product it is a 3.5, because BrightLocal includes it at $31. |
| 2 | Seed (a) M&A origination: per-meeting, website-staleness-scored trades sourcing | **4.5** (Idea #2) / 4.0 (data product) | WEAKENED | Willingness to pay is proven, but DealSource already sells the "succession score" and TX has no issue dates. |
| 3 | Seed (b) Competitor Sourcing-Shift Monthly | **4.0** | WEAKENED | Alerts are commoditized, masking runs up to 35%, and the feed price is unknown. Useful only as a hook. |
| 4 | Aircraft-owner outreach for avionics shops | **4.0** | WEAKENED | Data costs $0.14 a name, ADs are a weak trigger, shops are backlogged, and the market is ≤$1M ARR. |
| 5 | Trucking insurance renewal/lapse radar | **3.5** | WEAKENED / near KILLED | 9+ vendors at $79–249/mo, and the Motus cutover removed the future-dated cancellation signal from the public bulk data. |
| 6 | Restaurant commission-leak site + ordering | **2.5** | KILLED | DoorDash gives the same site and ordering away free; Menufy and GloriaFood are no longer free. |

**Bottom line for the brothers:**
- **Nothing in this batch is a new business.** The best item is a **retention and ARPU upsell to their own website customers**.
- Where a data play survives (trucking, M&A, trade), it survives only as **done-for-you outreach in the client's name, priced per outcome or as a flat retainer to a small, identifiable buyer list**. That is the brothers' actual competency.
- The data products themselves are already sold for under $250/mo by multiple vendors.
- **Run the cheap ground-truth tests before building anything:**
  - the existing-customer upsell take-rate
  - one trucking agency's book to test the renewal-month inference
  - the TX-alternative license data and the backtest for M&A
  - a CBP phone quote
