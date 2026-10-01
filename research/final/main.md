# Executive summary

**The question you asked.** You already run an agent business: find local businesses with bad websites, build them a new site, send personalized outreach, handle replies. Where else can that same machine work? You wanted markets where Claude agents interpret data that used to take many people, with a big enough market, buyers who already pay, a clear go-to-market and recurring revenue. Every idea was to be independently verified, nothing was to be pitched just because you'd like it, and nothing was off the table.

**What we did (all on 1 October 2026)**
- **Round 1:** 11 parallel research sessions, one per market lane, including both of your seed ideas.
- **Round 2:** 4 more lanes, designed to avoid the failure patterns that round 1 exposed.
- **Verification:** 7 separate verifier sessions whose only job was to break the shortlisted ideas, plus about 20 sub-agents doing self-checks.
- **Volume:** **333 ideas** considered, **110 shortlisted**, and about **45 independently attacked**. Each session had its own search budget, about 3,000 web searches and page fetches in total. Every claim in the underlying reports carries a source URL. The reports sit on `research/*` branches of the `towers-playtest` repo.

**The honest headline: we did not find a blue-ocean, 7-out-of-10 business.**
- No verifier confirmed any new-market idea as originally specified.
- Lanes first scored their best ideas 6–7.4. After verification the same ideas landed at **1.5–5.5**.
- The reasons repeated so consistently that they are a finding in their own right (Section 6):
  - A $25–$300/mo vendor almost always already sells the "insight".
  - Free public data is free for your buyers too.
  - Public triggers usually appear after the decision has already been made.
  - Licensing and fee-splitting rules quietly kill most contingency-fee models.
- The pitch below is calibrated to that. We'd rather hand you three modest, defensible bets with cheap kill tests than ten exciting ones that fall apart in month two.

## What we're pitching

| # | Bet | Final score | Status | Why it survives |
|---|---|---|---|---|
| **1** | **Local Presence Plan.** Upsell your existing and new website customers to care/hosting plus reviews, Google Business Profile, citations and a monthly "AI and Maps visibility" report, priced around $129/mo. | **5.0** | **CONFIRMED** by two independent verifiers (verify-5, verify-6) | Acquisition cost is near zero, the work is real done-for-you work, and multi-product customers churn about 40% less. Build it into the sale rather than adding it later. |
| **2** | **California Industrial Stormwater Pre-Notice Audit and Watch.** A fixed-fee self-audit ($500–1,500) plus a $50–100/mo watch for small industrial sites (auto wreckers, scrap yards) exposed to Clean Water Act citizen suits. Sold direct and white-labelled through stormwater consultants. | **5.5** | **Upgraded** by the last verifier (verify-7) after live data queries | The open state dataset lists 20,429 active facilities, and **99.7% of them publish a contact email**. The incumbent charges $11–27k per site per year, which leaves the small owner-operator tier open. The average settlement is about $79k per facility, so a $1,000 audit is easy to justify. |
| **3** | **Co-op-funded marketing retainer for brand dealers** (HVAC, outdoor power equipment, marine). Manufacturers' co-op funds pay up to 50% of a $500–900/mo website/SEO retainer. | **4.0** (5.0 inside the segment) | WEAKENED but alive (verify-6) | High revenue per customer for the slice of your base that carries national brands. A standalone co-op *claim-filing* desk was killed. |

**Cheap options worth a test only after the bets above** (each 3.5–4.5 with a defined kill test, detailed later):
- a Florida condo capital-event feed
- a flat-fee town grant desk
- contractor insurance-expiration ("X-date") meetings for commercial insurance agents in WA/OR
- a flat-fee unclaimed-property sweep for CPA firms
- a back-test-first version of your M&A idea

**What we recommend you do not do, with high confidence**
- White-label your outbound engine as "AI outbound for vertical X" (2.5): commoditizing prices, 6–8%/mo churn, and the sender carries the legal exposure.
- Pro-se trademark lead feeds (3.5): the USPTO now lists exactly this outreach as a scam pattern.
- Licensed brokerages (2.0–3.5).
- Your two seed ideas as originally specified (Section 3).

**The single biggest strategic finding.** Every upsell scenario is dominated by **N, the number of website customers you have**.
- At 500 customers, the full upsell bundle adds roughly **$110–230K ARR**.
- At 2,000 customers it adds **$0.4–0.9M ARR**.
- Your outbound/build-before-you-pitch engine is your most valuable asset, and it is worth most when pointed at *your own* customer acquisition plus a vertical bundle, not resold or redeployed into a market where a $39/mo tool already does the "insight".
- The one large counter-example, Owner.com (about $81M ARR, $1B valuation), won by owning SMB customers in one vertical with website plus marketing. It did not win by selling data or outbound.

# 1. How we did it

| Phase | Sessions | What happened |
|---|---|---|
| Round 1: discovery | 11 lanes | M&A origination (seed a), trade/shipping intel (seed b), public-records signals, regulatory compliance, real estate/construction, healthcare data, government contracting, legal/IP, local-SMB adjacencies, B2B intent signals, wildcards/obscure data. Each produced 5–10 scored ideas plus rejects. |
| Round 1: verification | 5 verifiers | Each took 5–6 ideas it had **not** written and tried to break them. The checks covered data access (live API queries), hidden competitors, bottom-up buyer counts, licensing, cold-email economics and timing. Result: **0 confirmed, 28 weakened, 5 killed.** |
| Round 2: discovery | 4 lanes | Designed around round 1's failure patterns: done-for-you back-office work, contingency "found money" recovery, proprietary data (records requests at scale, data co-ops, agent-collected data) and agent-run brokerages. Each lane ran its own 2-agent adversarial self-check. |
| Final verification | 2 verifiers | verify-6 stress-tested the "upsell your base" thesis and the white-label outbound alternative. verify-7 attacked the round-2 standalone ideas and re-opened the best round-1 survivors. |

**Scoring.** Each idea was scored 1–10 on market size, willingness to pay, data access, automation, competition (10 = blue ocean), recurring revenue and time to first dollar, plus an overall judgment score and a confidence level. A 7+ required strong evidence on **both** willingness to pay and competition. No idea met that bar after verification.

**Limits.**
- Reddit and some vendor pages were blocked for several sessions, so evidence of buyer pain leans on pricing pages, filings and job data more than on forum posts.
- Some partner-program terms (commission splits, for example) sit behind logins.
- Market sizes marked "(est.)" in the source reports are the sessions' own arithmetic.

# 2. Ranked list of every idea that went through independent verification

| Rank | Idea | Lane | First score | Final score | Final verdict |
|---|---|---|---|---|---|
| 1 | CA industrial stormwater pre-notice audit and watch | 04 | 6.4 | **5.5** | Upgraded (verify-7) |
| 2 | Local Presence Plan: reviews/GBP/AI-visibility upsell to own customers | 09 | 7.0 | **5.0** | CONFIRMED (verify-5, verify-6) |
| 3 | FL condo capital-event feed (engineers and restoration firms) | 05 | 7.0 | **4.5** | WEAKENED (verify-3) |
| 4 | Co-op-funded marketing retainer for brand dealers | 13 | 4.5 | **4.0** (5.0 in segment) | WEAKENED (verify-6) |
| 5 | Town Grant Desk (flat retainer) | 07 | 6.6 | **4.0** | WEAKENED (verify-3) |
| 6 | Contractor coverage X-date engine (WA/OR/CA/FL) | 03 | 7.0 | **4.0** | WEAKENED (verify-2) |
| 7 | B2B unclaimed-property sweep via CPA firms (flat fee) | 08 | 6.2 | **4.0** | WEAKENED (verify-4) |
| 8 | Aircraft-owner outreach for avionics/MRO shops | 11 | 6.4 | **4.0** | WEAKENED (verify-5) |
| 9 | Seed (b): competitor sourcing-shift reports (as a free hook only) | 02 | 5.0 | **4.0** | WEAKENED (verify-5) |
| 10 | Seed (a): trades M&A origination, per meeting, with succession score | 01 | 6.0–6.4 | **3.5** | WEAKENED (verify-1, -5, -7) |
| 11 | Tariff exposure brief (re-scoped as a broker white-label alert) | 02 | 7.0 | **3.5** | WEAKENED (verify-1) |
| 12 | Vertical roll-up target intelligence | 01 | 6.4 | **3.5** | WEAKENED (verify-1) |
| 13 | Restaurant inspection → pest/hood vendor router | 03/04 | 6.7–6.8 | **3.5** | WEAKENED (verify-2) |
| 14 | Medicare enrollment guard / rate-gap report | 06 | 6.3–6.4 | **3.5** | WEAKENED (verify-4) |
| 15 | Trucking insurance renewal/lapse radar | 04/09/10 | 4.0–6.4 | **3.5** | WEAKENED (verify-5) |
| 16 | SMB technology-advisor residual book (telecom/merchant) | 15 | 5.0 | **3.5** | WEAKENED; energy KILLED (verify-6) |
| 17 | Pro-se trademark office-action feed / workbench | 08 | 6.6 | **3.5** | WORSE (verify-4, -7) |
| 18 | Single-audit finding fixer | 07 | 7.1 | **3.0** | WEAKENED (verify-3) |
| 19 | Water pipeline radar + agenda-to-pipeline | 07/11 | 6.7–6.9 | **3.0** | WEAKENED (verify-3) |
| 20 | Property-tax appeal evidence engine | 11 | 5.9 | **3.0** | WEAKENED (verify-3) |
| 21 | Flat-fee add-on origination for PE | 01 | 6.0 | **3.0** | WEAKENED (verify-1) |
| 22 | Healthcare practice-acquisition screener | 06 | 6.2 | **3.0** | WEAKENED (verify-1) |
| 23 | New Practice Radar | 10 | 6.5 | **3.0** | WEAKENED (verify-4) |
| 24 | Duty-recovery lead engine (flat retainer) | 02 | 6.4 | **3.0** | WEAKENED (verify-1) |
| 25 | Contractor back-office bundle (upsell) | 12 | 4.5 | **3.0** | WEAKENED (verify-6) |
| 26 | Prequal Desk (ISN/Avetta/Veriforce) | 12 | 4.0 | **3.0** | WEAKENED (verify-7) |
| 27 | Overdue Feed (fire inspection records) | 14 | 4.0 | **3.0** | WEAKENED (verify-7) |
| 28 | Vendor-side sales-tax overcharge recovery | 13 | 4.0 | **3.0** | WEAKENED (verify-7) |
| 29 | Prop 65 "Next Defendant" alerts | 04 | 7.4 | **3.0** | KILLED as specified (verify-2) |
| 30 | White-label "AI outbound for vertical X" | — | — | **2.5** | KILLED as a pivot (verify-6) |
| 31 | OSHA site-specific targeting predictor | 04 | 6.5 | **2.5** | KILLED (verify-2) |
| 32 | Quota liquor-license brokerage (FL/PA/MI) | 15 | 3.5 | **2.5** | Near KILLED (verify-7) |
| 33 | Restaurant commission-leak site + ordering | 09 | 6.0 | **2.5** | KILLED (verify-5) |
| 34 | RateLift: RV/heavy-truck warranty uplift | 13 | 4.0 | **2.0** | KILLED for RV (verify-7) |
| 35 | FL elevator conveyance intel | 05 | 5.8 | **2.0** | KILLED (verify-3) |
| 36 | Drawback discovery with broker contingency split | 11/02 | 5.3 | **1.5** | KILLED: 19 CFR 111.36 (verify-1) |

The full idea-by-idea record, including the 223 ideas the lanes rejected outright, is in Appendix A.

# 3. Your two seed ideas, judged honestly

## Seed (a): sell-side deal origination for investment banks and PE

**Verdict: real money moves, but the generic service is commoditized and consolidating. Final score 3.5.**

- **Willingness to pay is proven.**
  - Pay-per-appointment sourcing runs **$300–600 per meeting**.
  - Managed programs run **$4–25k/mo**.
  - Independent sponsors are a growing buyer base: about 1,400–1,500 active, twice the 2019 level, and 27% of Axial's closed deals.
- **The field is crowded and consolidating.**
  - SourceCo has merged with CAPTARGET, and Datasite owns both Grata and SourceScrub.
  - Axia, DealSource, CT Acquisitions (home services, 2,000+ operator relationships) and Collar AI (YC F26) all sell the same thing.
  - DealSource already markets a "succession score".
  - A YC company with essentially your pitch (Q2Q) is inactive.
- **The legal path exists but constrains the model.**
  - Flat per-meeting fees with no involvement in negotiation probably keep you a lead-gen vendor, not a broker (unverified).
  - Success fees run into broker-dealer and state business-broker rules. California and Florida treat business sales as real estate, and only about 23 states have M&A broker exemptions.
- **Your one potentially unique input is website staleness from your own crawler.** There is **no evidence yet** that it predicts a sale. Texas licence data lacks issue dates; California's licence board (CSLB) has them.
- **What would change our mind.**
  - Run a 3–4 week, under-$1K **back-test**: score California HVAC, plumbing and electrical licences on tenure plus website staleness, and check them against shops that later cancelled or transferred licences or were acquired.
  - If the score shows clear lift over tenure alone (around 1.5× or better), sell it as a data add-on to existing originators and independent sponsors. Do not run another meeting-setting shop.

## Seed (b): competitor reports from shipping data

**Verdict: "your competitor switched suppliers" loses to ImportYeti, which is free. Final score 4.0 as a free hook, 3.5 as a tariff-alert product.**
- Bill-of-lading data is widely resold. ImportYeti gives it away, and up to about 35% of shipments are masked by manifest-confidentiality filings.
- Dollar estimates of tariff exposure built from bill-of-lading data alone are not credible, because the records carry no values or HTS codes.
- **The surviving variant:** a white-label alert engine sold to customs brokers. They hold the exact entry data and the client relationship.
- **The killed variant:** sharing a broker's contingency fee on duty drawback or refunds. 19 CFR 111.36 prohibits it.
- **Recommendation:** shelve it unless CBP issues a binding ruling allowing a flat-fee lead structure, or the pending export-manifest rule lands.

# 4. Bet #1: the Local Presence Plan (CONFIRMED, 5.0)

**Pitch.** Every website you build ships with a monthly plan:
- care and hosting;
- review generation and response;
- Google Business Profile management;
- citation clean-up;
- a monthly "how visible are you on Google Maps and in AI answers" report.

It is offered at about **$129/mo**, or tiered at $79 for care only and $149 with reviews.

**Why it survives when the standalone version doesn't.**
- As a cold-outbound product it scores 3.5. BrightLocal already includes AI-visibility tracking from **$31/mo**, Local Falcon from $24.99, and Merchynt wholesales at about $20 per profile.
- Sold to customers who already trust you, the acquisition cost is near zero, and the work is real done-for-you work that business owners won't do themselves.
- Vendasta's study of about 100K small-business accounts shows two-year retention of **30% with one product, 48% with two, and 78% with four**. That is roughly 4.9%/mo churn falling to about 3.0%.

**Be honest with customers about the AI report.**
- Studies of thousands of repeat queries show that AI recommendation lists almost never repeat; fewer than 1 in 100 runs gives the same list.
- API results overlap only about 15–24% with what the consumer interface shows.
- Report **mention frequency over many samples**, never a "rank". Treat AI visibility as the hook and reviews/GBP as the product.

**Economics (verify-6 model, steady state about 12 months after launch).**

| | 100 customers | 500 customers | 2,000 customers |
|---|---|---|---|
| Added MRR, base case (15% attach to the plan + co-op retainers for dealers + telecom referrals) | ~$3.9K | ~$19.4K | ~$77.7K |
| Added ARR, base case | ~$47K | ~$233K | ~$932K |
| Added ARR, downside (8% attach) | ~$21K | ~$109K | ~$436K |
| Human load | ~15 hr/mo | ~75 hr/mo | ~2 FTE |

**Agent pipeline.**
1. **Find:** existing customers plus every new site deal.
2. **Build the deliverable:** a stacked defect audit covering AI-search absence, the review gap against the Maps 3-pack, incomplete GBP, dead booking links or expired SSL, and mismatched hours.
3. **Outreach:** a personalized audit email.
4. **Handle replies:** your existing reply agent.
5. **Deliver and renew:** agents draft review requests and responses, GBP posts and citation fixes, with human approval for anything published. Then a monthly report.

**Legal.**
- The Google Business Profile API prohibits using its data for lead generation, so prospect with your own crawler, not the API.
- Review gating and incentivised reviews violate FTC rules.

**Test and kill criteria.** Offer the plan to every new site customer for 90 days, and to 100 existing customers. **Kill or reshape it if attach is under 8% after 90 days**, or if plan churn exceeds 6%/mo.

# 5. Bet #2: California Industrial Stormwater Pre-Notice Audit and Watch (5.5)

**The problem.** California's Industrial General Permit (in place since 2014 and still administratively continued) requires about 20,000 industrial facilities to sample stormwater, file annual reports and stay under action levels. Private plaintiff groups send 60-day notices of intent to sue under the Clean Water Act citizen-suit provision. They build these notices from the same public monitoring data, looking back five years. The average California consent decree since 2015 is about **$79k per facility**, more than half of it attorney fees; outliers reach $300–625k.

**Why it's a data-and-agents business, not another dashboard.**
- **The data is open and unusually complete.** The state's CKAN SQL API publishes facility records, monitoring results (about 2.3M rows) and violations (about 90,600 rows).
- **Live query on 1 Oct 2026:** **20,429 active facilities, and 20,359 of them (99.7%) publish a contact email.** That removes the enrichment cost and the deliverability risk.
- **The owner-operator bottom of the market is visible.** 3,436 active facilities use Gmail/Yahoo-type email addresses, including **500 of 676 auto wreckers** and **278 of 791 scrap yards**. These owners look a lot like your existing customers, and many will also need a website.
- **Agents can do the plaintiffs' analysis first.** That means matching sampling gaps against NOAA rain days, late annual reports and action-level exceedances across the 5-year lookback window, which is exactly what plaintiffs use.

**Competition.**
- Mapistry has a "Litigation Intelligence Group", but it is bundled into an enterprise platform at about **$11–27k per location per year**.
- californiastormwater.com aggregates about 19,700 registrations for consultants and lawyers, with **no risk scoring**.
- The single-site, owner-operator tier is open.

**Offer.**
- A fixed-fee **pre-notice self-audit at $500–1,500** that shows exactly what a plaintiff would see.
- A **$50–100/mo watch** that alerts the owner before each sampling window and each filing deadline.
- Sold direct to owner-operators **and white-labelled through Qualified Industrial Stormwater Practitioners (QISPs)**, the consultants who already serve these sites. QISP training costs $505, so the field is fragmented.

**Agent pipeline.**
1. **Find:** pull facilities with risk patterns, prioritising SIC 5015/5093 owner-operators.
2. **Build the deliverable:** a personalized "what a plaintiff sees" brief.
3. **Outreach:** compliant cold email to the published facility contact.
4. **Handle replies:** your reply agent books the audit.
5. **Deliver and renew:** the audit report, a QISP referral for fixes, and the watch subscription.

About 80% of this is automatable. The human touchpoints are audit QA and QISP partnerships.

**Risks.**
- Demand may be reactive: owners may ignore anything until a notice actually arrives.
- "You look like a lawsuit target" from a stranger can read like a shakedown. Tone, framing and the QISP channel matter.
- Current notice volume is unverified, because the state stopped tracking notices in 2010.

**Test and kill criteria.**
1. **Back-test:** pull consent decrees and notices from PACER and check whether the risk score would have flagged those facilities beforehand.
2. **200-site letter/email test** to owner-operators, plus 10 QISP conversations.
3. **Kill if** the back-test shows no lift, fewer than 5 paid audits come from 200 sites, or no QISP agrees to pilot white-label.

# 6. What the failures teach: a checklist for every future idea

The failure patterns repeated across 15 lanes and 7 verifiers. Run these checks before spending a dollar on any agent business:

1. **Search for the $39/mo version first.** "No competitor found" was wrong in almost every case. Examples: Actable's "Practice Radar" at $39/mo, BrightLocal AI tracking at $31, Civic IQ at $299, Prop65Radar at about $29, AppealDesk at $49, Single Audit Intelligence, DealSource. Search "[deliverable] software / service / AI", G2, Capterra, Product Hunt and recent YC batches.
2. **If buyers can download the CSV, a cleaner copy isn't a business.** Free public data is free for your buyers too. Near-zero usage of cheap data resellers is a demand signal. One Apify pro-se trademark lead feed has 2 monthly active users.
3. **Check timing.** Many public triggers appear after the decision is made: the engineer is hired before a water project reaches the state priority list, a corrective plan is filed before an audit finding is published, a filing deadline has already passed.
4. **Licensing and fee-splitting kill contingency models.** Examples:
   - customs brokers (19 CFR 111.36);
   - unclaimed-property finder fee caps (FL, TX, CA);
   - insurance producer rules;
   - attorney solicitation rules and unauthorized practice of law;
   - AICPA contingency rules;
   - real-estate licensing for business brokerage in CA and FL;
   - energy broker licensing by state.
5. **Search "[industry] scam warning".** When a regulator has publicly described your outreach as a scam template, the cold-email model breaks regardless of data quality. The USPTO now lists post-office-action solicitation letters, and fire departments warn about fake inspection notices.
6. **Find the scarce side.** Agents are best at the part that isn't scarce, such as finding sellers or overdue buildings. If the bottleneck is buyers (liquor licences) or technician capacity (fire inspections), automation doesn't help.
7. **Model cold email at today's rates.** The average cold-email reply rate fell to **3.43%** (Instantly 2026 benchmark). Gmail moved to permanent rejections in November 2025, and Microsoft has rejected non-compliant senders of 5K+ emails a day since May 2025. Guarded professionals (physicians, attorneys) convert worst. California's anti-spam law gives a private right of action at $1,000 per email.
8. **Prefer data that includes the buyer's contact.** Open datasets that publish a working contact email (like the stormwater data) are rare and valuable.

# 7. Suggested 12-month test sequence

| When | Action | Cost | Go / kill gate |
|---|---|---|---|
| Month 0–1 | Launch the **Local Presence Plan** on every new site deal; offer it to 100 existing customers | ~$0 + tools at ~$25–35 per customer | Go if attach ≥ 8% and plan churn ≤ 6%/mo at day 90 |
| Month 0–1 | **Stormwater back-test** (PACER consent decrees vs. risk score) | <$500 | Go if flagged facilities are clearly over-represented |
| Month 1–2 | **Co-op audit**: check 20 brand-dealer customers' manufacturer programs | ~$0 | Go if ≥ 5 have at least $2k a year of unspent accrual |
| Month 2–4 | **Stormwater 200-site test** + 10 QISP conversations | ~$1–2k | Go if ≥ 5 paid audits or ≥ 1 QISP pilot |
| Month 3–4 | **M&A succession-score back-test** (CA licence tenure + website staleness) | <$1k | Go only if lift ≥ ~1.5× over tenure alone |
| Month 4–6 | One option test at a time, ranked: (1) WA/OR contractor X-date meetings for commercial agents; (2) flat-fee town grant desk; (3) FL condo capital-event feed; (4) CPA unclaimed-property sweep | $0.5–2k each | Each has its own kill line (Appendix B) |
| Month 6–12 | Put winners into the core offer; **reinvest most effort in growing N** (website customers), because every upsell scales with it | — | Revisit the killed list only if a cited blocker changes (CBP ruling, new state law, a competitor exits) |

# 8. Bottom line

You asked us not to be agreeable, so here it is plainly.
- **Most of the "AI interprets public data" opportunity is already priced in.** Cheap vendors have productized almost every obvious data-to-insight play, and the rest are blocked by timing or licensing.
- **Your edge is execution:** building the thing before you pitch it, and an outbound and reply machine that converts.
- **Point that edge at:**
  - growing and deepening your own website customer base (Bet #1), and
  - one genuinely under-served, data-rich niche with a reachable buyer (Bet #2).
- Keep a short list of cheap options and kill them fast.

None of these is a 7/10 business today. A 5.0–5.5 with a near-zero acquisition cost and a $500 kill test is a better use of next month than a 7.0 that exists only on paper.
