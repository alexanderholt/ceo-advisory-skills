# Colorado AI Act (SB 24-205)

**Citation:** Colorado SB 24-205, codified at C.R.S. §§6-1-1701 through 6-1-1707
**Source URLs:**
- Bill page: https://leg.colorado.gov/bills/sb24-205
- Signed text (PDF): https://content.leg.colorado.gov/sites/default/files/2024a_205_signed.pdf
- ABA analysis: https://www.americanbar.org/groups/business_law/resources/business-law-today/2024-july/colorado-enacts-law-regulating-high-risk-artificial-intelligence-systems/
- CDT FAQ: https://cdt.org/insights/faq-on-colorados-consumer-artificial-intelligence-act-sb-24-205/
- NAAG Deep Dive: https://www.naag.org/attorney-general-journal/a-deep-dive-into-colorados-artificial-intelligence-act/

**Date:** Signed May 17, 2024
**Effective date:** Originally February 1, 2026; **delayed to June 30, 2026** by SB 25B-004 (signed August 28, 2025)
**Last reviewed:** March 2026

---

## Why This Matters for ClarifiED

A loan recommendation engine that makes or substantially influences decisions about which financial products borrowers are shown is almost certainly a **high-risk AI system** under this law. Any Colorado borrower who receives a recommendation from ClarifiED triggers coverage. This is the most operationally significant AI-specific law in the United States as of March 2026.

---

## Key Definitions

### High-Risk Artificial Intelligence System

> Any artificial intelligence system that, when deployed, **makes, or is a substantial factor in making, a consequential decision**.

### Consequential Decision

A decision that has a **material legal or similarly significant effect** on the provision or denial of, or the cost or terms of:
1. Education enrollment or an education opportunity
2. Employment or an employment opportunity
3. **A financial or lending service**
4. An essential government service
5. Health-care services
6. Housing
7. Insurance
8. A legal service

> **ClarifiED relevance:** Loan recommendations that affect which lending products a borrower sees, or the terms shown, fall squarely within category (3) — financial or lending service. ClarifiED is almost certainly deploying a high-risk AI system under this definition.

### Algorithmic Discrimination

Any condition in which the use of an AI system results in an unlawful differential treatment or impact that disfavors an individual or group of individuals on the basis of:
- Age, color, disability, ethnicity, genetic information, limited proficiency in English, national origin, race, religion, reproductive health, sex, veteran status, or other classification protected under Colorado or federal law

### Deployer

Any person doing business in Colorado that deploys a high-risk AI system. "Deploy" means to use a high-risk AI system or to make a high-risk AI system available to make or be a substantial factor in making a consequential decision.

### Developer

Any person doing business in Colorado that develops or intentionally and substantially modifies an AI system.

> **ClarifiED may be both a developer and a deployer** — it develops the recommendation algorithm and deploys it (or makes it available to institutions that deploy it). Both roles carry obligations.

---

## Deployer Obligations

### General Duty of Care (§6-1-1702)

Deployers must use **reasonable care to protect consumers from any known or reasonably foreseeable risks of algorithmic discrimination**.

### Rebuttable Presumption of Reasonable Care

A deployer is **presumed** to have used reasonable care if it complies with ALL of the following:

#### 1. Risk Management Policy and Program
- Must specify principles, processes, and personnel used to identify, document, and mitigate risks of algorithmic discrimination
- Must be reasonably designed to prevent algorithmic discrimination
- Must be regularly reviewed and updated

#### 2. Impact Assessment (Annual)
- Must be completed for each high-risk AI system
- Must include:
  - Purpose, intended use cases, and deployment context of the system
  - Analysis of whether the system poses risks of algorithmic discrimination
  - Description of data used by the system, including training data
  - Description of outputs produced by the system
  - Transparency measures
  - Post-deployment monitoring measures
  - Description of how the system is used to make or substantially influence consequential decisions
- Must be reviewed **annually**
- Must be updated when significant changes are made
- Must be provided to the Colorado Attorney General upon request within 90 days

#### 3. Consumer Notification
If the high-risk AI system makes, or is a substantial factor in making, a consequential decision concerning a consumer, the deployer must notify the consumer of:
- That a high-risk AI system is being used to make or substantially influence the decision
- A description of the system in plain language
- Contact information for the deployer
- A description of the types of data processed and the outputs produced
- If a consumer has been subjected to an adverse decision: the principal reason(s) for the decision

#### 4. Consumer Rights
- **Right to correct** incorrect personal data processed by the high-risk AI system
- **Right to appeal** an adverse consequential decision — **via human review** if technically feasible

#### 5. Annual Review
- Review deployment of each high-risk AI system at least annually

---

## Developer Obligations (§6-1-1703)

Developers must:
1. **Make available to deployers:**
   - A general description of the types of high-risk AI systems the developer has developed or intentionally and substantially modified
   - Documentation to assist deployers in understanding outputs and monitoring the system
   - A description of the type of data used to train the system
   - Known or reasonably foreseeable limitations, risks, and intended benefits
   - Information about how the system was evaluated for performance and mitigation of algorithmic discrimination

2. **Make available a summary** of the types of high-risk AI systems developed and managed, on the developer's website

3. **Report known or reasonably foreseeable risks** of algorithmic discrimination to the Colorado Attorney General and to deployers within 90 days of discovery

---

## Enforcement

- **Exclusive enforcement:** Colorado Attorney General
- **No private right of action**
- Violations treated as deceptive trade practices under the Colorado Consumer Protection Act
- AG may seek injunctive relief, civil penalties, and other remedies
- The impact assessment is **not** a public record and is protected from disclosure (except to the AG)

---

## Timeline

| Date | Event |
|------|-------|
| May 17, 2024 | SB 24-205 signed into law |
| August 28, 2025 | SB 25B-004 delays effective date |
| **June 30, 2026** | **Current effective date** |

> **Note:** There has been active discussion about further amendments or delays. Monitor the Colorado General Assembly for any 2026 session changes.

---

## ClarifiED Compliance Implications

1. **Classification:** ClarifiED's recommendation engine is likely a high-risk AI system (consequential decision re: financial/lending services)
2. **Both developer and deployer:** Desata may bear obligations in both roles
3. **Impact assessment:** Required annually; must analyze algorithmic discrimination risk across protected classes
4. **Consumer notification:** Every borrower who receives a recommendation must be notified that AI is involved, with plain-language description and contact info
5. **Appeal right:** Borrowers must be able to appeal adverse recommendations through human review
6. **Data correction:** Borrowers must be able to correct personal data the algorithm used
7. **Risk management:** Must have documented policy and program for identifying and mitigating discrimination risks
8. **AG reporting:** Must report known risks of algorithmic discrimination within 90 days

---

## Gaps and Notes

- **Source of text:** Key provisions drawn from web search results (Colorado General Assembly, ABA, CDT, NAAG analyses) and training knowledge. The signed bill text PDF was identified but not directly fetched due to tool limitations.
- **Full text:** Available at https://content.leg.colorado.gov/sites/default/files/2024a_205_signed.pdf — should be downloaded and reviewed in full.
- **SB 25B-004 amendments:** The delay bill may have included substantive amendments beyond the date change. Verify at https://leg.colorado.gov/bills/sb25b-004
- **Verify before relying:** This is the most operationally significant law for ClarifiED. Full legal review of the signed text is essential before launch.
