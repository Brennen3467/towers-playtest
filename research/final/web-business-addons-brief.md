# Brief: add-ons for the automated website business

*For a Claude agent extending the existing pipeline. This brief was distilled on 2026-10-01 from a 15-lane research study with 7 independent verifiers. Every claim below was checked by at least one adversarial verifier. The full reports, each claim with a source URL, are on the `research/*` branches of `Brennen3467/towers-playtest`. The most relevant are `research/09-smb-adjacent`, `research/13-found-money`, `research/15-agent-brokerage`, `research/verify-5` and `research/verify-6`.*

## 0. Context and what you're building

**How the business works today**
1. Agents find local businesses with old, broken or missing websites.
2. They build each one a new site before contacting it.
3. They send a personalized outreach email.
4. They handle the replies.

**Your job:** add recurring add-on services that are sold to (a) every new website customer at the point of sale, and (b) existing customers.

**Why this, and not a new market.** Across 333 ideas researched, the only thesis two independent verifiers confirmed is **selling more to customers who already trust you**:
- Acquisition cost is near zero.
- Multi-product SMB customers churn far less. Vendasta's study of about 100K SMB accounts found 2-year retention of 30% with 1 product, 48% with 2 and 78% with 4, which works out to about 4.9%/mo churn falling to about 3.0%/mo.
- Standalone versions of these same services, sold by cold email, score badly. BrightLocal, Local Falcon, Merchynt and others sell the "insight" for $25–$99/mo.

**Design principle: build the bundle into the acquisition offer.** Bundle it with the site from day one rather than upselling months later. Every scenario below scales linearly with N, the number of website customers, so do not let the add-ons slow down new-customer acquisition.

## 1. Before building anything: answer these from our own data

The economics of each add-on depend on the customer mix. Query the existing customer and prospect database and report:

1. **N:** total active website customers. Are they on a monthly care/hosting plan or did they pay one-time?
2. **Vertical mix**, in particular:
   - the share who are **brand-carrying dealers or contractors**: HVAC (Carrier, Bryant, Trane, Rheem, Lennox), outdoor power equipment, appliance, marine, powersports;
   - the share who are **commercial or public-works trades**.
3. **Current monthly churn** of site/hosting customers.
4. Whether we already have Google Business Profile (GBP) access or manager rights for any customers.

**Gates**
- If N is under about 300, the add-ons are a retention feature, not a revenue line. Build only add-on A.
- If brand dealers are under 10% of the base, skip add-on B.

## 2. Add-ons, in priority order

### A. Local Presence Plan (BUILD FIRST): verified 5.0/10, confirmed by two verifiers

**What it is.** A monthly plan attached to every site:

| Tier | Price | Includes |
|---|---|---|
| Care | ~$79/mo | Hosting, SSL, uptime, small edits, monthly backup |
| Presence (default offer) | ~$129–149/mo | Care, plus review generation and response, GBP management, citation/NAP clean-up, and a monthly visibility report |

**The visibility report is the hook, not the product.** It covers Google Maps / local 3-pack position and "AI answer" mentions (ChatGPT, Gemini, Google AI Overviews). The real value is reviews and GBP work the owner won't do themselves.

**How to build it into the pipeline**
- **Prospecting / audit stage.** Extend the existing site audit into a **stacked defect audit** that lists several verifiable problems in one outreach. The research found stacking makes the email more credible than any single claim. Check for:
  - missing, outdated or broken website (current signal)
  - review count and rating gap against the businesses in the Maps 3-pack for their main search
  - an incomplete GBP: missing hours, categories, photos, description or services
  - hours mismatched between the site, GBP and other listings
  - dead booking or contact links, expired SSL
  - an "Order online" button that routes to DoorDash or another commission-taking marketplace (restaurants)
  - absence from AI answers across many sampled prompts (see the measurement rules below)
- **Offer stage.** Show the new site plus the Presence Plan as the default package, with Care-only as the downgrade.
- **Delivery agents.** These run monthly:
  - Draft review-request messages (SMS/email) sent from the customer's own account or platform.
  - Draft review responses, held for customer approval for the first 30 days, then auto-post if they opt in.
  - Draft GBP posts, photo uploads, and Q&A and category fixes.
  - Run citation consistency checks and file submissions.
  - Generate the monthly report.
- **Renewal.** The monthly report email is the retention touchpoint. Include one "next fix" in each report.

**Measurement rules (important; the research found this is where competitors overclaim)**
- AI recommendation lists are highly unstable. Fewer than 1 in 100 repeated runs return the same brand list (SparkToro/Gumshoe, 2,961 runs).
- API results overlap with what consumers see in the ChatGPT UI only about 15–24% of the time (Surfer, Aug 2026). Scraping the consumer UI violates OpenAI's terms.
- **Therefore, report mention frequency over many sampled prompts** (e.g. "mentioned in 6 of 30 local-intent queries this month"). **Never report a "rank".** Use the APIs, not scraping. This costs about $0.30–0.75 per 30-query snapshot.
- ChatGPT mentions only about 1.2% of local businesses, versus about 35.9% that appear in Google's 3-pack. Expect most customers to show zero AI visibility for months. Lead the report with reviews and Maps progress so it doesn't read as failure.

**Unit economics**
- Third-party tools cost about $20–60 per location wholesale (white-label BrightLocal, Local Falcon or Merchynt-type APIs), or build in-house.
- Gross margin is about 75%.
- Human time is about 0.5 hr per customer per month (approvals, edge cases).

**Guardrails**
- **The GBP API prohibits using its data for lead generation.** Prospect with our own crawler and public pages, never the GBP API. To manage a customer's profile, the customer grants manager access to our own verified Google Cloud project.
- **FTC rules on reviews:**
  - No review gating (asking only happy customers).
  - No incentives for reviews.
  - No fake or AI-written reviews.
  - Responses must not misrepresent anything.
- **Cold email:**
  - CAN-SPAM requires a physical address, an accurate From line and subject, and honoring opt-out within 10 business days.
  - California B&P §17529.5 gives a private right of action at $1,000 per email for misleading headers or subjects.
  - Gmail permanently rejects non-compliant bulk mail (Nov 2025), and Microsoft rejects non-compliant senders above 5K/day (May 2025). Keep SPF, DKIM and DMARC aligned, use one-click unsubscribe, and keep complaint rates low.

**Success metric and kill line**
- Offer the plan to every new site deal for 90 days, plus to 100 existing customers.
- **Go:** at least 8% attach, and Presence Plan churn at or below 6%/mo.
- **Base case** (verify-6 model): about 15% attach at $129, with 75% gross margin.

### B. Co-op-funded marketing retainer for brand dealers (BUILD ONLY IF at least 10% of the base are brand dealers): verified 4.0 overall, 5.0 within the segment

**What it is.** HVAC (and some outdoor power equipment and appliance) manufacturers reimburse dealers for part of their marketing spend through co-op programs. For eligible dealers, sell a **website + SEO + local marketing retainer at ~$500–900/mo**, where the pitch is "up to 50% of this is manufacturer-funded". The agents prepare the pre-approvals and claims.

This is a **close-rate and retention feature** for a high-revenue segment. It is **not** a standalone "we recover your unclaimed co-op" business; that version was killed at 2.5/10.

**Verified program facts (2026)**
- **Carrier/Bryant (US):** 50% reimbursement against a 1.5–2% purchase accrual.
  - Site build, hosting, SEO and annual support **are eligible**.
  - Requirements: pre-approval, an SEO plan submitted in advance, a prominent brand logo, and that brand's products only.
  - Claims are due within 60 days, and there is a hard 15 December cutoff.
  - Agency fees on media are eligible up to 17% of media, shown as a separate line.
- **Carrier Canada:** URL, hosting and maintenance are **not** eligible. Funds are clawed back if the site stops being Carrier-exclusive within 12 months.
- **Trane:** prorated by the share of the site devoted to HVAC.
- **Rheem:** 1% accrual; a website is a precondition, not a claimable item. The portal closes 8 December.
- **Claim-preparation fees were not listed as eligible anywhere.** Charge for the marketing service, not for filing claims.
- **Closed doors (approved-vendor lock-in), so skip these:**
  - Yamaha pays 70% only through 3 approved agencies.
  - Honda allows approved SEM vendors only.
  - Kawasaki has one approved website vendor.
  - Polaris runs a Certified Web Program.
  - Lennox has a preferred-supplier network.
- **Powersports is largely closed. HVAC (Carrier, Bryant, Trane) is the open door.**
- **Typical accrual:** a small HVAC or OPE dealer accrues about $5–30K a year (est.). Ignore the old "$14–35B unclaimed" headline, which is a 2016 trade-group figure.

**Pipeline integration**
1. **Find:** classify existing customers and prospects by the brands shown on their site and in manufacturer dealer locators.
2. **Build the deliverable:** a one-page digest of that brand's co-op rules plus an estimated annual accrual range.
3. **Outreach:** "Your new site and SEO can be up to 50% Carrier-funded." Pitch existing customers first.
4. **Deliver:** submit the pre-approval before work starts, keep proof-of-performance logs (screenshots, invoices, ad reports), submit the claim packet within the deadline, and track the 15 December cutoff.

**Human touchpoints**
- the dealer grants delegated access to their co-op portal (never shared logins)
- OEM pre-approval edge cases
- about 3 hr per retainer per month

**Competitors**
- COOPABLE (auto): $1,000–1,500/mo.
- Contingency claim agencies take 15–25% of reimbursement.
- OEM-certified platforms (PowerChord, Dealer Spike/LeadVenture, Surefire Local) bundle co-op with their services.
- CoopReclaim is in free early access, with $99/mo planned.

**Validation and kill line.** Audit the brand programs of 20 existing brand-carrying customers. **Kill if** fewer than 5 have at least $2K/yr of unspent accrual, or fewer than 2 convert to the retainer.

### C. Annual bill-review referral (OPPORTUNISTIC, not a product): verified 3.5/10

**What it is.** Once a year, the monthly report offers a free review of the customer's internet, phone/UCaaS and card-processing bills. Agents compare the bills against current market offers. If switching saves money, the customer is referred through a technology-advisor master agent (Telarus, Avant, Intelisys and similar), which pays recurring residuals.

**Realistic economics**
- Supplier commissions are usually 15–20% of the monthly recurring charge, and the advisor keeps about 70–85% of that.
- A $100/mo cable internet line pays about $8–16/mo; a 10-seat UCaaS line about $40–55/mo.
- Merchant processing pays about $15–40/mo per account, and 10–25% of those accounts are lost each year.
- A realistic bundled customer is worth about **$30–100/mo**. The first residual arrives about 60–120 days after install, and chargebacks can claw back up to about 12 months.
- Spiffs (up-front bonuses) mostly require deals above $250 to $1,000 of new monthly recurring revenue, so they rarely apply to small SMBs.

**Guardrails**
- **Do NOT include energy/electricity brokerage.** It requires per-state broker licensing (e.g. TX, IL, PA, OH) and was killed at 1.5/10.
- Comcast and Spectrum pay one-time bounties, not residuals.

**Kill line.** Offer it to 100 customers. **Kill if** fewer than 15 upload bills or fewer than 5 switch within 60 days.

### D. Contractor paperwork add-on (ONLY for commercial or public-works subcontractor customers): verified 3.0/10, 4.0 in segment

This covers prevailing-wage certified payroll, safety prequalification profiles (ISNetworld, Avetta, Veriforce) and lien/preliminary-notice deadlines.

**Build it only if** at least 20% of the base are commercial subcontractors. Even then, price at or below existing done-for-you services:
- Wellstanding: $995 setup + $249/mo
- Contractor Compliance Pros: $350 for three platforms
- QuickComply: ~$150/mo

Sell it as part of the bundle, not head-to-head on price.

**Kill line:** under 3% attach in a 30-day offer.

## 3. Do NOT build these (verified as weak or saturated)

| Idea | Verdict | Why |
|---|---|---|
| Restaurant website + online ordering to cut delivery commissions | KILLED 2.5 | DoorDash gives restaurants a free site and ordering; Owner.com (~$81M ARR) dominates. Use "DoorDash-routed order button" only as an audit signal. |
| AI phone receptionist / missed-call text-back | Saturated | Tens of thousands of GoHighLevel resellers sell it. |
| ADA/accessibility overlay widgets | Avoid | Commoditized, and the FTC acted against accessiBe. A one-time accessibility fix as part of a rebuild is fine; don't sell overlay subscriptions. |
| Standalone "AI visibility" report product | 3.5 | BrightLocal includes it from $31/mo. It only works inside the Presence Plan. |
| White-labelling our outbound engine for other agencies | KILLED 2.5 | Prices are collapsing, there is 6–8%/mo churn, and the sender carries CAN-SPAM liability for every client's claims. Demo-site generators already sell for $105 per 1,000 sites (Apify). |
| Energy brokerage | KILLED 1.5 | Per-state licensing. |
| Standalone co-op claim-filing desk | KILLED 2.5 | Claim fees aren't eligible, and agencies already do it free with their services. |

## 4. Expected impact (verify-6 model, steady state about 12 months after launch)

| | N = 100 | N = 500 | N = 2,000 |
|---|---|---|---|
| Added MRR, base case (A at 15% attach + B for 2.5% of N + C for 5% of N) | ~$3.9K | ~$19.4K | ~$77.7K |
| Added ARR, base case | ~$47K | ~$233K | ~$932K |
| Added ARR, downside | ~$21K | ~$109K | ~$436K |
| Human load | ~15 hr/mo | ~75 hr/mo | ~2 FTE |

There is also a retention dividend. Customers with 2 or more products churn at about 3.0%/mo versus 4.9%/mo, worth roughly $1.5–1.7K/mo of saved core revenue after a year at N = 500.

## 5. Suggested build order

1. **Week 1:** answer the Section 1 questions from our data, and report back before building.
2. **Weeks 1–3:**
   - Add the stacked defect audit signals to the prospecting crawler.
   - Build Presence Plan delivery: review requests and responses, GBP tasks, citation checks, and the monthly report with sampled AI mentions.
   - Add the plan as the default line item in the site offer.
3. **Weeks 3–4:** offer the plan to 100 existing customers and to every new deal, and start the 90-day measurement.
4. **Month 2 (if the brand-dealer share is at least 10%):** run the co-op audit of 20 customers, then decide whether to build add-on B.
5. **Month 3:** add the annual bill-review offer to the report template (C).
6. **Ongoing:** track attach rate, plan churn, core churn by product count, and human hours per customer. Apply each kill line.
