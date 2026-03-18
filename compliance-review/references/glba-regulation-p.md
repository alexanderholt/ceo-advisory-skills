# GLBA / Regulation P Key Provisions

**Citation:** Gramm-Leach-Bliley Act, 15 U.S.C. §§6801-6809; Regulation P, 12 C.F.R. Part 1016 (CFPB)
**Source URLs:**
- Statute: https://www.law.cornell.edu/uscode/text/15/chapter-94B
- 15 U.S.C. §6809 (definitions): https://www.law.cornell.edu/uscode/text/15/6809
- Regulation P: https://www.law.cornell.edu/cfr/text/12/part-1016
- IAPP Guide to GLBA: https://iapp.org/resources/article/guide-to-the-gramm-leach-bliley-act

**Date:** Enacted 1999; Regulation P promulgated by CFPB (transferred from FTC/banking agencies in 2011)
**Last reviewed:** March 2026

---

## Overview

Title V of GLBA requires "financial institutions" to protect the privacy of consumer financial information. Regulation P implements the privacy notice and opt-out requirements. The Safeguards Rule (16 C.F.R. Part 314, administered by FTC) addresses data security.

## Key Definitions

### Financial Institution (15 U.S.C. §6809(3))

> "any institution the business of which is engaging in financial activities as described in section 1843(k) of title 12"

This is an intentionally broad definition tied to the Bank Holding Company Act's list of "financial activities," which includes:
- Lending, exchanging, transferring, investing for others, or safeguarding money
- Insuring, guaranteeing, or indemnifying against loss
- Providing financial, investment, or economic advisory services
- **Arranging, facilitating, or making available** financial products or services

**Fintech/loan recommendation platform analysis:** The definition extends to non-bank entities. Mortgage brokers, payday lenders, check-cashing businesses, wire transfer services, tax preparers, and entities that provide investment advice or facilitate consumer credit transactions may all be covered.

> **ClarifiED relevance:** A platform that recommends specific loan products to specific borrowers — even without originating or servicing loans — could be considered to be "arranging" or "facilitating" financial products. Whether ClarifiED is a "financial institution" under GLBA depends on:
> 1. Whether it handles nonpublic personal information (NPI) of consumers
> 2. Whether its core activity is "financial" under the BHC Act definition
> 3. Whether it acts as a service provider to a financial institution (in which case the institution's GLBA obligations flow down contractually)

### Nonpublic Personal Information (NPI) (15 U.S.C. §6809(4))

Personally identifiable financial information:
- Provided by a consumer to a financial institution
- Resulting from any transaction with the consumer or any service performed for the consumer
- Otherwise obtained by the financial institution

Does NOT include publicly available information lawfully made available from government records.

### Consumer vs. Customer

- **Consumer:** An individual who obtains or has obtained a financial product or service primarily for personal/family purposes, or that individual's legal representative
- **Customer:** A consumer with a continuing relationship with the financial institution

The distinction matters because **customers** get initial and annual privacy notices; **consumers** get privacy notices only before NPI is shared with nonaffiliated third parties.

## Privacy Notice Requirements (12 C.F.R. §1016.4-1016.6)

Financial institutions must provide:
1. **Initial privacy notice** — at the time of establishing a customer relationship
2. **Annual privacy notice** — once per year during the relationship (note: institutions that meet certain conditions may be exempt from annual notice requirement under a 2015 amendment)
3. **Opt-out notice** — before disclosing NPI to nonaffiliated third parties (unless an exception applies)

The notice must describe:
- Categories of NPI collected
- Categories of NPI disclosed
- Categories of affiliates and nonaffiliated third parties to whom NPI is disclosed
- Policies for protecting former customers' NPI
- Consumer's right to opt out

## Opt-Out Right (12 C.F.R. §1016.10)

Consumers must be given a reasonable opportunity to opt out before a financial institution discloses NPI to a nonaffiliated third party, unless an exception applies.

## Key Exceptions to Opt-Out (12 C.F.R. §1016.13-1016.15)

NPI may be shared **without** opt-out in certain circumstances:
- **Service provider exception:** Sharing with nonaffiliated third parties that perform services for or on behalf of the financial institution, provided the institution enters into a contractual agreement requiring the third party to maintain confidentiality
- Disclosures to protect against fraud
- Disclosures with consent
- Disclosures required by law
- Disclosures to comply with legal process

> **ClarifiED relevance:** If ClarifiED operates as a service provider to institutions or lenders (rather than as a financial institution itself), the service provider exception is the likely pathway. The contracting institution would need to:
> 1. Include ClarifiED in its privacy notice as a service provider
> 2. Execute a contract requiring ClarifiED to maintain confidentiality
> 3. Restrict ClarifiED from using or redisclosing NPI beyond the contracted purpose

## Safeguards Rule (16 C.F.R. Part 314)

Administered by the FTC for non-bank financial institutions. Requires:
- Designation of a qualified individual to oversee the information security program
- Risk assessment
- Implementation of safeguards (access controls, encryption, MFA, etc.)
- Oversight of service providers
- Incident response plan

Higher education institutions are subject to the Safeguards Rule for student financial aid data.

## Enforcement

- CFPB has enforcement authority for most financial institutions
- FTC has authority over non-bank financial institutions
- State attorneys general may bring actions
- No federal private right of action

## Gaps and Notes

- **Source of text:** Drawn from training knowledge cross-referenced against search results from law.cornell.edu and IAPP. Full statutory/regulatory text was not directly fetched.
- **Higher education intersection:** Title IV institutions are considered "financial institutions" under GLBA for purposes of student financial aid administration. See FTC guidance and 16 C.F.R. Part 314 applicability.
- **Verify before relying:** Confirm current regulatory text at https://www.ecfr.gov/current/title-12/chapter-X/part-1016
- **Open question for ClarifiED:** Whether a no-commission loan recommendation engine that does not originate, service, or broker loans is itself a "financial institution" under GLBA, or whether it operates only as a service provider to institutions that are financial institutions, is a question that likely requires legal counsel.
