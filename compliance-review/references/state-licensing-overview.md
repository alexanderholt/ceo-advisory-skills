# NMLS State Licensing Overview — Loan Comparison/Recommendation Platforms

**Purpose:** Identify which states might require licensing for a platform that compares and recommends student loans to borrowers, focusing on states with broad "broker" or "servicer" definitions.
**Last reviewed:** March 2026

---

## The Core Question for ClarifiED

ClarifiED is a no-commission loan recommendation engine. It does not:
- Originate loans
- Fund loans
- Service loans (receive payments, maintain accounts)
- Broker loans (negotiate terms on behalf of borrowers)
- Receive compensation from lenders

The licensing question is whether any state's definition of "loan broker," "finder," "servicer," "lead generator," or similar category is broad enough to capture a platform that recommends specific loan products to specific borrowers based on their financial profile.

---

## NMLS Overview

The **Nationwide Multistate Licensing System & Registry (NMLS)** is the system of record for non-depository financial services licensing in all 50 states, DC, and U.S. territories. It is administered by the Conference of State Bank Supervisors (CSBS).

Key facts:
- NMLS provides state-by-state checklists for each license type
- Applicants can submit materials once through NMLS rather than separately to each state
- License types tracked include: mortgage lender, mortgage broker, mortgage loan originator, consumer lender, student loan servicer, money transmitter, debt collector, and others
- Website: https://mortgage.nationwidelicensingsystem.org/
- Consumer lookup: https://nmlsconsumeraccess.org/
- CSBS 50-state survey: https://www.csbs.org/50-state-survey-consumer-finance-laws

---

## Student Loan Servicer Licensing

### States Requiring Student Loan Servicer Licenses

As of 2025-2026, the following states require student loan servicers to be licensed (typically through NMLS):

| State | Regulator | Key Notes |
|-------|-----------|-----------|
| **California** | DFPI | Net worth requirement of $250,000; surety bond required. See `ca-student-loan-servicing-act.md` |
| **Connecticut** | Dept. of Banking | Early adopter; broad servicer definition |
| **Colorado** | DORA | Licensing requirement enacted |
| **District of Columbia** | DISB | Student loan servicer license required |
| **Illinois** | IDFPR | Student Loan Servicing Rights Act |
| **Kentucky** | DFI | Initial fee $5,000; covers principal office and branches |
| **Maine** | Bureau of Consumer Credit Protection | Student loan servicer license |
| **Maryland** | Office of the Commissioner of Financial Regulation | Student loan servicer license |
| **Massachusetts** | Division of Banks | Recently enacted |
| **Minnesota** | Dept. of Commerce | Fee $1,000; annual renewal by Dec 31 |
| **Mississippi** | Dept. of Banking and Consumer Finance | Student loan servicer license |
| **Nevada** | FID | Student loan servicer license |
| **New Jersey** | Dept. of Banking and Insurance | Student loan servicer license |
| **New York** | DFS | Student loan servicer license; NY DFS is an aggressive regulator |
| **Oregon** | Division of Financial Regulation | SB 485 (2021); fee $1,000 application, $500 renewal |
| **Rhode Island** | Dept. of Business Regulation | Student loan servicer license |
| **Virginia** | Bureau of Financial Institutions | Student loan servicer license |
| **Washington** | DFI | Student loan servicer license |

> **ClarifiED analysis:** As discussed in `ca-student-loan-servicing-act.md`, ClarifiED likely does NOT meet the definition of "student loan servicer" in most states because it does not receive payments, maintain accounts, or interact with borrowers to prevent default. However, the breadth of definitions varies by state. States with the broadest definitions (CT, CA, IL) should be analyzed most carefully.

---

## Loan Broker / Finder Licensing

### What Is a Loan Broker?

Most states define a loan broker (or mortgage broker, or consumer loan broker) as a person who, for compensation, arranges, negotiates, or finds loans for borrowers. The key elements are typically:
1. Acting as intermediary between borrower and lender
2. Receiving compensation (from borrower, lender, or both)
3. Negotiating or arranging specific loan terms

### States with Broad Broker Definitions — Highest Risk

| State | License Type | Risk to ClarifiED | Notes |
|-------|-------------|-------------------|-------|
| **New York** | Licensed Lender / Mortgage Broker (Banking Law §590 et seq.) | Moderate | NY DFS interprets "broker" broadly. A platform that matches borrowers to specific lenders could be viewed as brokering, even without compensation from lenders. However, the no-commission model and institutional (not borrower) contracting structure reduce risk. |
| **California** | Finance Lender License (Cal. Fin. Code §22000 et seq.) | Low-Moderate | The CFL covers "brokers" who negotiate or arrange consumer loans. ClarifiED's model (recommendations, not negotiations) likely falls outside, but DFPI has broad interpretive authority. |
| **Connecticut** | Consumer Credit Licensee | Low-Moderate | Broad definitions; active regulator. |
| **Georgia** | Industrial Loan License | Low | Broad "loan broker" definition, but typically requires compensation from borrower or lender. |
| **Massachusetts** | Mortgage Broker / Small Loan Licensee | Low-Moderate | Active regulator with broad definitions. |
| **Illinois** | Consumer Installment Loan Act licensee | Low | Defines "broker" to include arranging loans; ClarifiED's model may fall outside. |

### States with Narrow Broker Definitions — Lower Risk

Most states define loan brokers narrowly enough that a recommendation platform without lender compensation likely falls outside the definition. The critical factor in nearly every state is **compensation from the lender or borrower in connection with a specific transaction.**

ClarifiED's flat institutional fee model — where the institution pays an annual access fee and ClarifiED receives no per-transaction compensation from lenders or borrowers — is the strongest argument against broker classification.

---

## Lead Generator Considerations

Some states regulate "lead generators" in the lending context. A lead generator typically:
- Collects consumer information
- Sells or transmits that information to lenders
- Receives per-lead or per-transaction compensation

ClarifiED is NOT a lead generator because:
- It does not sell borrower information to lenders
- It does not receive per-lead compensation
- Information flows from institution to ClarifiED to borrower (not to lender)

However, if ClarifiED's architecture ever involves transmitting borrower information to lenders (even for application purposes), lead generator laws in states like California, New York, and Florida could be implicated.

---

## Recommended Approach

1. **Formal legal analysis:** Engage counsel to analyze ClarifiED's model against the licensing laws of the states where initial institutional customers are located (focus on the beta schools' states)
2. **Priority states for analysis:** New York, California, Connecticut, Massachusetts, Illinois, Pennsylvania (these have the broadest definitions and most active regulators)
3. **CSBS 50-state survey:** Use the CSBS resource at https://www.csbs.org/50-state-survey-consumer-finance-laws for current license type definitions
4. **NMLS checklists:** Review NMLS state-by-state checklists for "student loan servicer," "consumer lender," and "loan broker" license types
5. **No-action letters:** Consider seeking informal guidance or no-action letters from priority state regulators to confirm ClarifiED's model does not require licensing

---

## Data Source Disclosure

**Training knowledge:** The state lists, license types, and risk assessments above are drawn primarily from training knowledge, supplemented by web search results from NMLS, CSBS, DFPI, and state regulator websites.

**What was fetched via web search:**
- Student loan servicer licensing states (confirmed via search results listing CA, CT, MN, OR, KY, NY, MA)
- NMLS structure and application process
- CSBS 50-state survey existence

**What was NOT fetched or verified:**
- Full text of any state's broker or servicer licensing statute
- Current NMLS checklists for each state and license type
- Whether any states have enacted new licensing requirements in 2025-2026 specifically targeting AI-based or algorithmic lending recommendation platforms
- Whether any state regulators have issued guidance on recommendation platforms

**Recommended primary sources:**
- NMLS: https://mortgage.nationwidelicensingsystem.org/
- CSBS 50-State Survey: https://www.csbs.org/50-state-survey-consumer-finance-laws
- Individual state regulator websites for priority states
