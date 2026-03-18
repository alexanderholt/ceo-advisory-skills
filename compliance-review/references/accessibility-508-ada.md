# Section 508 / ADA Web Accessibility

**Citations:**
- Section 508 of the Rehabilitation Act: 29 U.S.C. Section 794d
- ADA Title III: 42 U.S.C. Section 12182
- Section 508 Standards: 36 C.F.R. Part 1194
- DOJ Title II Web Accessibility Rule: 28 C.F.R. Part 35 (April 2024)

**Sources:**
- Section 508 Law and Policies: https://www.section508.gov/manage/laws-and-policies/
- DOJ Title II Final Rule: https://www.ada.gov/assets/pdfs/web-rule.pdf
- DOJ Web Accessibility Guidance (2022): https://www.ada.gov/resources/web-guidance/

**Date:** Section 508 amended 1998; current standards effective January 2018. DOJ Title II web rule finalized April 2024.

---

## Section 508 of the Rehabilitation Act

### What It Requires

Section 508 (29 U.S.C. Section 794d) requires that when **federal agencies** develop, procure, maintain, or use electronic and information technology (EIT), they must ensure that the technology is **accessible to people with disabilities** — both federal employees and members of the public — unless doing so would impose an undue burden.

### Who Must Comply

**Directly:** All federal agencies and departments.

**Indirectly (via procurement):** Any technology vendor selling to or contracting with federal agencies must meet Section 508 standards. The Federal Acquisition Regulation (FAR) Subpart 39.2 requires that ICT acquisitions meet the accessibility standards at 36 C.F.R. Part 1194.

### Applicability to Vendors Serving Institutions Receiving Federal Funds

Section 508 applies **directly** only to federal agencies, not to recipients of federal funds (such as Title IV institutions). However:

1. **Federal procurement flow-down.** When federal agencies require business partners, grantees, or vendors to provide ICT deliverables, those deliverables must meet Section 508 standards. If Desata contracts with any federal agency, Section 508 compliance is required.

2. **Institutions as covered entities.** Title IV institutions receiving federal funds are not directly covered by Section 508, but they are covered by **Section 504 of the Rehabilitation Act** (29 U.S.C. Section 794), which prohibits disability discrimination by any program or activity receiving federal financial assistance. The Department of Education has interpreted Section 504 to require accessible technology in higher education.

3. **Practical effect for vendors.** Many institutions include Section 508 or WCAG 2.1 AA compliance in their procurement requirements for technology vendors, even though the legal obligation flows from Section 504 and ADA, not Section 508 directly. A Voluntary Product Accessibility Template (VPAT) documenting conformance is commonly required.

### Current Technical Standard

The U.S. Access Board's January 2017 final rule (effective January 2018) updated the Section 508 standards to incorporate **WCAG 2.0 Level AA** as the benchmark for web content and software interfaces. The standards at 36 C.F.R. Part 1194 reference the WCAG 2.0 success criteria (with some exceptions for non-web software).

---

## ADA Title III — Public Accommodations

### What It Requires

Title III of the Americans with Disabilities Act (42 U.S.C. Section 12182) prohibits discrimination on the basis of disability in "places of public accommodation." The statute lists 12 categories of public accommodations, including places of education, service establishments, and sales or rental establishments.

### Application to Websites

Courts and the DOJ have increasingly applied Title III to **websites and digital services** operated by places of public accommodation, even though the statute was written before the commercial internet existed. Key developments:

1. **DOJ position (consistent since 2010s).** The DOJ has stated in guidance, settlement agreements, and statements of interest that websites of public accommodations must be accessible under Title III. The DOJ's 2022 guidance (https://www.ada.gov/resources/web-guidance/) affirmed that "the ADA applies to web content of public accommodations."

2. **No specific technical standard under Title III (yet).** Unlike the Title II rule finalized in 2024, the DOJ has **not yet issued a regulation** specifying a particular WCAG version as the technical standard for Title III entities (private businesses). However, WCAG 2.1 AA is the de facto standard used in settlements and consent decrees.

3. **2024 Title II Rule as a signal.** In April 2024, the DOJ finalized a rule (28 C.F.R. Part 35) requiring state and local government websites to conform to **WCAG 2.1 Level AA**. Compliance dates:
   - April 24, 2026: entities serving populations of 50,000+
   - April 26, 2027: smaller entities and special district governments

   While this rule applies to Title II (state/local government) entities, it signals the standard the DOJ considers appropriate. A Title III rulemaking was expected but was not completed before the end of the Biden administration.

4. **Litigation landscape.** Private plaintiffs have brought thousands of ADA Title III lawsuits against websites. Courts in most circuits have found that inaccessible websites can violate Title III, though the circuits differ on whether a physical "nexus" is required.

### Relevance to Desata

**As a technology vendor to Title IV institutions:**
- Institutions are covered by **Section 504** (disability discrimination by federal fund recipients) and may be covered by **ADA Title II** (if public) or **Title III** (if private)
- Institutions will likely require that Desata's products (ClarifiED, loanlimit.app) meet WCAG 2.1 AA as a condition of procurement
- A VPAT documenting accessibility conformance will likely be required during the sales process

**As a website operator (desata.io, loanlimit.app, beta.loanmatch.app):**
- Desata's public-facing websites are likely subject to ADA Title III as a "service establishment" or "place of education" (for tools used by students)
- WCAG 2.1 AA is the practical standard, even absent a formal Title III regulation
- Proactive accessibility reduces litigation risk and supports institutional sales

**Recommendation:** Target WCAG 2.1 AA conformance for all Desata web properties and maintain a current VPAT/Accessibility Conformance Report (ACR).

## Notes on Completeness

This summary is based on the statutory text, DOJ guidance documents, the 2024 Title II final rule, and Section 508 policy documents from section508.gov. The DOJ's 2022 web accessibility guidance and the full text of the 2024 Title II rule are available at the source links above. The legal landscape for ADA Title III web accessibility continues to evolve — no final Title III web regulation has been issued as of this writing.
