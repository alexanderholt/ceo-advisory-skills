# Destrava Analytics: Business Context Document

**Purpose:** This document is intended for AI ingestion. It provides a comprehensive description of Destrava Analytics — what the company does, why it exists, how it makes money, and where it is going — so that an AI system working on Destrava's behalf can understand the business deeply enough to assist with product development, content, strategy, and communications tasks without requiring constant re-explanation.

---

## What Destrava Is

Destrava Analytics is an early-stage fintech company serving the higher education financial aid market. It builds compliance software and data tools for college and university financial aid offices. The company's name is a play on "destravar" — to unblock in Brazilian Portuguese — which describes its mission: removing the operational friction that makes federal student aid compliance slow, error-prone, and expensive for schools.

Destrava operates at the intersection of federal regulation and institutional operations. Its products help financial aid administrators implement new federal requirements correctly, document their decisions for audits and program reviews, and eventually connect students with private lenders in a way that is transparent, compliant, and beneficial to the student.

---

## The Market Context

The U.S. federal student aid system is administered by roughly 6,000 Title IV-eligible institutions. Financial aid offices at these institutions are responsible for determining how much federal aid a student can receive, disbursing those funds correctly, and maintaining the documentation to prove it in the event of an audit or Department of Education program review. Getting this wrong carries serious consequences: repayment liabilities, loss of Title IV eligibility, and reputational damage.

The regulatory environment is in a period of unusual flux. The One Big Beautiful Bill Act (OBBBA), signed into law July 4, 2025, made sweeping changes to federal student loan programs effective July 1, 2026. These include new annual and aggregate loan limits for graduate and professional students, a new proration requirement for less-than-full-time enrollment, new parent PLUS loan caps, a $257,500 lifetime borrowing maximum, and new institutional authority to set program-level loan limits. The implementing regulations — the RISE NPRM — were published in January 2026 with a comment deadline in March 2026 and a July 1, 2026 effective date.

This creates an acute, time-sensitive compliance problem for every financial aid office in the country. Schools need to understand the new rules, update their processes, and be ready to calculate and document correctly by July 1. There is no existing software that handles the new proration requirements. The Department of Education has not built a tool. NASFAA and other associations are publishing guidance but not software. The window between rule publication and effective date is narrow, and the operational complexity is high.

---

## The Product Strategy: Free at the Base, Paid for Scale

Destrava's competitive strategy is modeled on how infrastructure software companies like Cloudflare, Stripe, and Twilio have won markets: make the core product free to drive adoption at scale, then charge for features that larger or more sophisticated users need. The lightest-weight version is always free. Revenue comes from premium tiers as schools grow into them, and from a parallel lender placement business.

This model works in the financial aid market for a specific structural reason: procurement at colleges and universities is slow and painful. Anything that requires a purchase order, a vendor agreement review, and a budget approval cycle takes months and may not happen before a critical deadline. But if a tool is free, a financial aid counselor can simply use it — today, from their browser, without asking anyone — and begin building familiarity and institutional reliance. By the time the school is ready to think about paying for software, Destrava is already the tool they know.

The long-term competitive moat is not any single feature. It is the combination of ubiquitous free adoption, high-quality compliance documentation that makes Destrava the tool auditors recognize, and a data asset that accumulates as schools use the platform over time.

---

## Current Product Roadmap

### Product 1: Pro-Rata Loan Calculator (Building Now)

The first product is a free, public web tool that calculates the correct prorated federal loan limit for a student under §685.203(m)(1) of the RISE NPRM. It is available on Destrava's public website with no account required. No student data is entered into or transmitted through the tool — it is designed from the ground up to be FERPA-safe.

The calculator handles:
- Enrollment intensity proration for less-than-full-time students
- CIP-based validation for graduate and professional degree loan limits
- Annual and aggregate limit checks for all degree levels
- The new $257,500 lifetime maximum
- Legacy borrower determination (including the expected time to credential calculation)
- Institutionally determined program loan limits under §685.203(m)(2)
- Mid-year grade level progression
- Transfer student scenarios
- Human-review flagging for unresolved edge cases (non-term programs, subscription-based programs, military leave)
- Per-payment-period disbursement schedules
- Professional judgment adjustments
- Subsidized and unsubsidized limit breakdowns

Output is a downloadable PDF calculation record with regulatory citations, suitable for a student's financial aid file and defensible in a program review. The PDF gate requires a work email address, which provides Destrava with an institution-level contact and drives analytics via a privacy-safe domain hash.

The tool is the company's beachhead: it solves an urgent, universal problem for free, establishes Destrava's credibility as a compliance resource, and begins building the school relationship and dataset that later products depend on.

**Revenue from this product:** None directly. Revenue comes from the lender tool (see below). The calculator is distribution.

### Product 2: Loan Match (Next)

The second product is a student-facing private loan comparison tool at loanmatch.app. Students who have exhausted their federal eligibility enter basic information about themselves — degree level, borrowing amount, credit profile, cosigner status — and see lenders ranked by three independently calculated ratings: Access (how easy is it to qualify), Affordability (how much will it cost), and Flexibility (how protected are you if things go wrong). Schools share a school-specific link (e.g. loanmatch.app/nyu) with students but have no role in selecting, configuring, or ordering lenders. There is no preferred lender list.

Lenders submit their product information, underwriting criteria, and terms through a submission form. The platform uses this data to calculate ratings and match students. For MVP, matching is rules-based. Future versions will add soft credit pulls and lender API integration for real pre-approved rates.

Lenders pay Destrava for access to the platform directly or via a pooled third party. Lenders pay a flat fee based on the number of states they operate in (proportional to the number of college students in the state). This is intentional: platforms like Credible and NerdWallet earn referral fees when a student takes out a loan, which creates incentives to get students to borrow and to borrow more. Destrava also believe that schools linking to commision-based marketplaces violates 20 U.S.C. § 1019(8), while our fee-based model does not. Destrava earns the same whether a student borrows or doesn’t, and the ratings are designed to benefit the borrower, not the lender or the school. That keeps the platform focused on helping the student make the right decision.

This is Destrava's primary near-term revenue source. It does not require schools to pay anything. The student gets objective, transparent loan comparisons. The lender gets a channel. Destrava earns the access fee.

**Why lenders pay:** The primary way that lenders currently generate leads is through Google and marketplaces like Nerwallet and Credible. Both of these channels are very expensive relative to Destrava’s marketplace. Furthermore, Destrava is operating through a trusted channel, the school, at a moment of high intent from the student (when they find out they have unmet need). Having a direct channel through the school is currently expensive and regulatory complex. Financial aid office relationships are expensive to build and maintain. A platform that puts lenders in front of students through an objective, merit-based, independently rated process is cleaner, cheaper, and more defensible form a consumer perspective than anything that currently exists..

### Product 3: Offer Letter (Following)

The third product is an interactive financial aid offer letter tool at offerletters.app. Schools upload their existing award letters (Excel, PDF, or docx) and Destrava parses them into a personalized, interactive student experience. Students receive a unique link where they can explore their aid package in real time — adjusting borrowing amounts and seeing monthly payments, total interest, and payoff timelines update dynamically using OBBBA's tiered standard repayment plan. Every term on the page is tappable for a plain-language explanation. An AI chatbot (MVP v2) trained on federal aid rules answers student questions in-session and escalates what it can't answer to the financial aid office.

The tool connects directly to Loan Match: when a student's aid doesn't cover the full cost, they go from seeing their unmet need to finding private loan options in one step.

Offer Letter is designed to comply with two bipartisan bills advancing through Congress that would standardize financial aid offer letters: the College Financial Aid Clarity Act (H.R. 6502) and the Understanding the True Cost of College Act (S. 1558). Schools that adopt Offer Letter will be ahead of the requirement, not behind it.

Offer Letter is free to schools in its base form. Paid premium features may be added later, but the core tool will always be free. This is where the tiered software model begins to operate: the free version drives adoption, the premium version generates subscription revenue from schools that want more.

---

## Revenue Model Summary

**Near-term (Year 1):** Lender access fees via Loan Match. Free compliance tools drive school adoption. Lenders pay for access to the platform based on estimated loan volume. No school pays anything.

**Medium-term (Years 2-3):** Premium software tiers for schools. Offer Letter and other operational tools offer free base versions with paid upgrades for larger institutions, deeper customization, and SIS integrations. Offer Letter drives adoption to low-cost enrollment management tools at a fraction of the price of exiting players. Pricing scales with institutional size and feature usage.

**Long-term:** Disrupt existing players by slowly increasing suite at much lower cost.

---

## What Destrava Is Not

Destrava is not a student-facing loan origination platform. It is not a servicer. It is not a data broker selling student information. The Pro-Rata Calculator and Loan Match collect no student-identifiable records and are FERPA-safe by design. Offer Letter does handle student education records uploaded by schools — Destrava acts as a "school official" under FERPA with appropriate data sharing agreements, encryption, and access controls in place.

Destrava is not a consulting firm that happens to have software. The software is the product. Consulting engagements may be a bridge to early revenue and product validation, not a permanent business model.

---

## Competitive Landscape

The existing players in financial aid compliance software — PowerFAIDS, Ellucian, Campus Logic (now Transact) — are large, slow-moving, and deeply integrated into student information systems. They compete on integration depth and institutional relationships, not on compliance accuracy or user experience. Their tools were not built for the OBBBA changes and will not be updated quickly.

NASFAA and state associations publish regulatory guidance but do not build software. The Department of Education publishes rules and occasionally releases reference calculators, but these are always late, often buggy, and never production-quality tools.

In the private student loan comparison space, the established players are Credible, NerdWallet, Splash, and Sparrow. All earn referral fees when a student takes out a loan — a model that creates incentives to get students to borrow and to borrow more. Destrava's Loan Match charges lenders a flat fee, not on clicks or originations, which keeps the platform aligned with the student's interest rather than the lender's.

Destrava's competitive advantages are structural, not just temporal:

**The founders wrote the rules.** Destrava's founders are deeply embedded in the higher education policy community. They helped write OBBBA. One founder was a negotiator on the RISE rulemaking — he literally helped draft the regulations that Destrava's tools implement. They have deep relationships with schools, lenders, regulators, and policymakers built through years in think tanks and Congress. No competitor has this level of regulatory fluency or these relationships.

**Speed.** Destrava is building the tools the market needs before anyone else has shipped them, targeting the July 1, 2026 effective date as a hard deadline every financial aid office in the country is aware of. First-mover advantage in compliance software is durable because once a school is using a tool, documenting their decisions with it, and building institutional muscle memory around it, switching costs are high even if the tool is free.

**No commissions.** Destrava charges flat fees on Loan Match — not referral fees, not origination-based fees. The incentive structure is clean and defensible. Loan Match's ratings methodology will be published and open to scrutiny. Transparency is the product, not a marketing claim.

---

## Key Regulatory Context an AI Should Know

- **OBBBA:** One Big Beautiful Bill Act, signed July 4, 2025. The statute that made the underlying loan limit and proration changes.
- **RISE NPRM:** The implementing regulation published January 2026 by the Department of Education. "RISE" stands for Reimagining and Improving Student Education. This is the regulatory text Destrava's compliance tools are built against.
- **§685.203(m)(1):** The specific provision requiring proration of annual loan limits for less-than-full-time enrollment. The heart of the pro-rata calculator.
- **§685.203(m)(2):** The provision giving institutions permissive authority to set lower program-level loan limits, applied consistently across all students in a program.
- **FERPA:** Family Educational Rights and Privacy Act. Governs the privacy of student education records. The Pro-Rata Calculator and Loan Match are FERPA-safe by design — no student-identifiable data touches Destrava's servers. Offer Letter handles student education records under a school official agreement with appropriate safeguards.
- **HEOA:** Higher Education Opportunity Act. Governs preferred lender list practices. The lender tool is designed to be HEOA-compliant by using a merit-based, documented evaluation framework.
- **Title IV:** The section of the Higher Education Act that authorizes federal student aid programs. A "Title IV-eligible institution" is one that participates in federal student aid.
- **COD:** Common Origination and Disbursement system. The Department of Education's system for tracking loan origination and disbursement.
- **NSLDS:** National Student Loan Data System. The federal database of student loan history. Financial aid administrators use it to look up a student's prior borrowing.
- **Legacy borrower:** Under the OBBBA, a student who was enrolled in a program of study at an institution as of June 30, 2026, and had a Direct Loan made for that program prior to July 1, 2026, retains prior-law loan limits for the expected time to credential (the lesser of three academic years or the remaining program length). This exception is institution-specific and program-specific. It terminates on withdrawal.
- **Grad PLUS elimination:** OBBBA eliminated Graduate and Professional PLUS loans for non-legacy students effective July 1, 2026. Only legacy borrowers who meet the two-part test under §685.200(b)(2)(ii) retain Grad PLUS access.
- **Award letter standardization bills:** Two bipartisan bills are advancing through Congress to standardize financial aid offer letters. The College Financial Aid Clarity Act (H.R. 6502) mandates specific content, order, and terminology with a July 1, 2029 compliance deadline. The Understanding the True Cost of College Act (S. 1558) directs the Secretary of Education to develop a standard form through consumer testing. Destrava's Offer Letter product is designed to comply with both.

---

## Tone and Positioning

Destrava positions itself as deeply expert in the regulatory detail, honest about what is and is not resolved in the rules, and on the side of financial aid administrators who are trying to do the right thing under difficult conditions and the students navigating a scary and complicated new landscape. It does not oversimplify. It does not pretend edge cases are settled when they are not. It flags human-review situations honestly rather than generating false confidence.

The brand voice is direct, precise, and collegial — the way an experienced financial aid professional would talk to a peer, not the way a software company talks to a customer.
