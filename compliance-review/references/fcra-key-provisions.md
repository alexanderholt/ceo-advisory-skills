# FCRA Key Provisions

**Citation:** Fair Credit Reporting Act, 15 U.S.C. Sections 1681-1681x
**Source:** https://www.law.cornell.edu/uscode/text/15/chapter-41/subchapter-III
**FTC Full Text (revised May 2023):** https://www.ftc.gov/system/files/ftc_gov/pdf/fcra-may2023-508.pdf
**CFPB Examination Manual:** https://files.consumerfinance.gov/f/documents/102012_cfpb_fair-credit-reporting-act-fcra_procedures.pdf
**Date:** Originally enacted 1970. Substantially amended by FACTA (2003) and Dodd-Frank (2010). Current through May 2023 revisions.

---

## Overview

The Fair Credit Reporting Act (FCRA) regulates the collection, dissemination, and use of consumer credit information. It governs consumer reporting agencies (CRAs), furnishers of information, and users of consumer reports. The FCRA is enforced by the CFPB, the FTC, and state attorneys general.

## Key Definitions

### Consumer Report (15 U.S.C. Section 1681a(d))

A **consumer report** is any written, oral, or other communication of any information by a consumer reporting agency bearing on a consumer's:
- Credit worthiness
- Credit standing
- Credit capacity
- Character
- General reputation
- Personal characteristics
- Mode of living

...which is used or expected to be used or collected in whole or in part for the purpose of serving as a factor in establishing the consumer's eligibility for:
1. **Credit or insurance** to be used primarily for personal, family, or household purposes
2. **Employment** purposes
3. **Any other purpose** authorized under Section 1681b

**Exclusions from the definition of consumer report:**
- Reports containing information solely as to transactions or experiences between the consumer and the person making the report
- Any authorization or approval of a specific extension of credit by the issuer of a credit card
- Any report in which a person conveys a decision about a consumer's eligibility for certain products (not the underlying data)

### Consumer Reporting Agency (15 U.S.C. Section 1681a(f))

A **consumer reporting agency** (CRA) is any person which, for monetary fees, dues, or on a cooperative nonprofit basis, regularly engages in whole or in part in the practice of **assembling or evaluating** consumer credit information or other information on consumers for the purpose of **furnishing consumer reports to third parties**, and which uses any means or facility of interstate commerce for the purpose of preparing or furnishing consumer reports.

**Key structural note:** The definitions of "consumer report" and "consumer reporting agency" are circular — each depends on the other. This is intentional. It means an entity cannot escape FCRA obligations simply by labeling itself as something other than a CRA. The analysis focuses on what information actually flows through the system and how it is used.

### Permissible Purposes (15 U.S.C. Section 1681b)

A CRA may furnish a consumer report only for the following permissible purposes:

1. **Court order or federal grand jury subpoena** (Section 1681b(a)(1))
2. **Written instructions of the consumer** (Section 1681b(a)(2))
3. **Credit transactions** — to a person the agency has reason to believe intends to use the information in connection with a credit transaction involving the consumer (Section 1681b(a)(3)(A))
4. **Employment purposes** — with the consumer's written consent (Section 1681b(a)(3)(B))
5. **Insurance underwriting** (Section 1681b(a)(3)(C))
6. **Legitimate business need** — in connection with a business transaction initiated by the consumer (Section 1681b(a)(3)(F))
7. **Review of an account** to determine whether the consumer continues to meet the terms (Section 1681b(a)(3)(F)(ii))
8. **Government financial responsibility or licensing** determinations (Section 1681b(a)(3)(D))

## When a Recommendation Engine Might Trigger FCRA

This is the central FCRA question for ClarifiED and similar tools.

### The Three-Element Test

An entity triggers CRA obligations when it satisfies all three elements:
1. It **assembles or evaluates** information about consumers
2. The information bears on a consumer's credit worthiness, credit standing, credit capacity, character, etc.
3. It **furnishes** this information **to third parties** for a permissible purpose (i.e., the third party uses it to make eligibility decisions)

### When ClarifiED Likely Does NOT Trigger FCRA

A loan recommendation engine is likely **not** a CRA if:
- It presents **publicly available loan terms** (rates, fees, eligibility criteria) to borrowers without evaluating individual consumer creditworthiness
- It does **not collect or transmit individual consumer financial data** to lenders
- It does **not make or communicate eligibility determinations** — it shows options; the lender makes the decision
- It operates on **borrower-reported or institutional data** (e.g., enrollment status, loan limits) rather than third-party consumer credit data
- Information flows **from lenders to borrowers** (product comparison), not **from the engine about borrowers to lenders** (consumer reporting)

### When a Tool WOULD Trigger FCRA

A recommendation engine becomes a CRA if:
- It collects **individual consumer data** (credit score, income, debt) and uses that data to **evaluate** the consumer's fitness for specific products
- It **furnishes reports** about individual consumers to lenders or other third parties to help them make eligibility decisions
- It assembles consumer data from multiple sources and creates a **consumer profile** that is shared with third parties

### CFPB Circular 2024-01 — Related but Distinct

The CFPB's February 2024 circular on **comparison-shopping tools and digital intermediaries** (https://www.consumerfinance.gov/compliance/circulars/consumer-financial-protection-circular-2024-01/) addresses a related but distinct issue: whether comparison-shopping tools engage in **abusive** steering practices under the Consumer Financial Protection Act (12 U.S.C. Section 5531). Key points:

- Operators of comparison-shopping tools may be **covered persons** under CFPB jurisdiction
- **Steering** consumers to products based on compensation rather than consumer interest can be an abusive practice
- **Lead generators** that direct consumers to specific providers based on payments (rather than fit) may violate the abusiveness prohibition
- This analysis is separate from FCRA but reinforces the importance of transparent, non-compensatory recommendation methodology

## Key FCRA Obligations (If Triggered)

If an entity is determined to be a CRA, obligations include:

- **Accuracy** — Procedures to assure maximum possible accuracy of consumer reports (Section 1681e(b))
- **Permissible purpose verification** — Reasonable procedures to ensure reports are furnished only for permissible purposes (Section 1681e(a))
- **Consumer access** — Consumers must be able to obtain their file disclosure (Section 1681g)
- **Dispute resolution** — Must investigate consumer disputes within 30 days (Section 1681i)
- **Adverse action notices** — Users of consumer reports must provide notice when taking adverse action based on a report (Section 1681m)
- **Data security** — Must maintain reasonable procedures to protect consumer information

## Relevance to Desata

ClarifiED's design as a **no-influence, no-commission** recommendation engine with **published methodology** is structurally aligned with avoiding FCRA trigger:

1. **Direction of data flow matters.** If ClarifiED takes institutional/public loan data and presents options to borrowers (without sending borrower data to lenders), the FCRA CRA definition is unlikely to apply.

2. **No consumer data assembly for third parties.** If ClarifiED does not assemble consumer-specific information and furnish it to lenders for eligibility decisions, it is not functioning as a CRA.

3. **Published methodology protects against steering claims.** Transparent, non-compensatory ranking reduces risk under both FCRA and the CFPB abusiveness standard.

4. **Risk area to monitor.** If ClarifiED ever evolves to include features like pre-qualification, credit-based filtering, or sharing borrower application data with lenders, FCRA applicability would need to be re-evaluated.

## Notes on Completeness

This summary covers the key definitional provisions, permissible purposes, and CRA trigger analysis most relevant to Desata's operations. The full FCRA text spans Sections 1681 through 1681x and includes detailed provisions on furnisher obligations, identity theft protections, and specialty reporting agencies not covered here. The FCRA analysis for ClarifiED should be reviewed by legal counsel as the product feature set evolves.
