# ECOA / Regulation B (Equal Credit Opportunity Act)

**Citation:** 12 C.F.R. Part 1002
**Source:** Electronic Code of Federal Regulations (ecfr.gov), pasted directly by user
**Authority:** 12 U.S.C. 5512, 5581; 15 U.S.C. 1691b
**Current as of:** 3/13/2026

**Note:** Full Part 1002 is extensive (includes Subpart B on Small Business Lending Data Collection). This file contains the key Subpart A provisions relevant to Desata. Full text available at ecfr.gov.

---

## §1002.1 Authority, scope and purpose

**(b) Purpose.** To promote the availability of credit to all creditworthy applicants without regard to race, color, religion, national origin, sex, marital status, or age (provided the applicant has the capacity to contract); to the fact that all or part of the applicant's income derives from any public assistance program; or to the fact that the applicant has in good faith exercised any right under the Consumer Credit Protection Act.

---

## §1002.2 Definitions (key terms)

**Adverse action (§1002.2(c)):**
(1) Includes:
- Refusal to grant credit in substantially the amount or terms requested (unless counteroffer is accepted)
- Termination of an account or unfavorable change in terms
- Refusal to increase credit available to an applicant who applied for an increase

**Applicant (§1002.2(e)):** Any person who requests or has received an extension of credit from a creditor, including any person who is or may become contractually liable regarding an extension of credit.

**Creditor (§1002.2(l)):** A person who, in the ordinary course of business, regularly participates in a credit decision, including setting the terms of the credit. **Also includes a person who, in the ordinary course of business, regularly refers applicants or prospective applicants to creditors, or selects or offers to select creditors to whom requests for credit may be made.** A person is not a creditor regarding any violation committed by another creditor unless the person knew or had reasonable notice of the violation before becoming involved.

**Credit scoring system (§1002.2(p)):** A system that evaluates creditworthiness mechanically based on key attributes. To qualify as "empirically derived, demonstrably and statistically sound," must be: based on empirical data comparing creditworthy and non-creditworthy applicants; developed for legitimate business interests; developed using accepted statistical principles; and periodically revalidated.

**Prohibited basis (§1002.2(z)):** Race, color, religion, national origin, sex, marital status, or age; the fact that income derives from public assistance; or the fact that the applicant has exercised rights under the Consumer Credit Protection Act.

---

## §1002.4 General rules

**(a) Discrimination.** A creditor shall not discriminate against an applicant on a prohibited basis regarding any aspect of a credit transaction.

**(b) Discouragement.** A creditor shall not make any oral or written statement, in advertising or otherwise, to applicants or prospective applicants that would discourage on a prohibited basis a reasonable person from making or pursuing an application.

**Official Interpretation — Effects test (Comment 6(a)-2):** The Act and regulation may prohibit a creditor practice that is discriminatory in effect because it has a disproportionately negative impact on a prohibited basis, even though the creditor has no intent to discriminate and the practice appears neutral on its face, unless the creditor practice meets a legitimate business need that cannot reasonably be achieved as well by means that are less disparate in their impact.

---

## §1002.5 Rules concerning requests for information

**(a)(1)** Except as otherwise provided, a creditor may request any information in connection with a credit transaction.

**(b)** A creditor shall not inquire about the race, color, religion, national origin, or sex of an applicant or any other person in connection with a credit transaction (with limited exceptions for self-testing and monitoring).

---

## §1002.6 Rules concerning evaluation of applications

**(a) General rule.** A creditor may consider any information obtained, so long as it is not used to discriminate on a prohibited basis. Congress intended an "effects test" concept to be applicable (citing Griggs v. Duke Power Co., 401 U.S. 424 (1971)).

**(b)(1)** A creditor shall not take a prohibited basis into account in any system of evaluating creditworthiness.

**(b)(9)** Except as otherwise permitted or required by law, a creditor shall not consider race, color, religion, national origin, or sex in any aspect of a credit transaction.

---

## §1002.9 Notifications

**(a)(1) Timing:** A creditor shall notify an applicant of action taken within:
- 30 days after receiving a completed application (approval, counteroffer, or adverse action)
- 30 days after taking adverse action on an incomplete application
- 30 days after taking adverse action on an existing account
- 90 days after notifying of a counteroffer if applicant does not accept

**(a)(2) Content of adverse action notice:** Must include:
- Statement of the action taken
- Name and address of the creditor
- Statement of ECOA provisions (§701(a))
- Name and address of the administering Federal agency
- Either: (i) statement of specific reasons, or (ii) disclosure of right to request reasons within 60 days

**(b)(2) Statement of specific reasons:** Must be specific and indicate the principal reason(s). Statements that the action was based on "internal standards" or that the applicant "failed to achieve a qualifying score" are **insufficient**.

---

## §1002.15 Incentives for self-testing and self-correction

Self-test results are privileged if: the test was voluntary, the creditor takes appropriate corrective action, and the results are not voluntarily disclosed. Privilege applies to government examinations and proceedings under ECOA.

---

## §1002.16 Enforcement, penalties and liabilities

Civil liability for actual and punitive damages. Punitive damages limited to $10,000 individual / $500,000 or 1% net worth for class actions. Five-year statute of limitations. Attorney General may bring pattern-or-practice cases.

---

## Relevance to Desata

### Is Desata a "creditor" under Reg B?

The definition of "creditor" in §1002.2(l) is critical. It includes not only entities that make credit decisions, but also **persons who regularly refer applicants to creditors or select creditors to whom requests for credit may be made.** If ClarifiED's recommendation engine is interpreted as "selecting" lenders for borrowers, Desata could be classified as a creditor subject to ECOA.

### Key risks:

1. **Algorithmic discrimination:** If ClarifiED's recommendation algorithm produces results that disproportionately affect borrowers of a particular race, national origin, sex, or other prohibited basis, the effects test applies — even without intent to discriminate.

2. **Adverse action notices:** If Desata is a creditor and ClarifiED filters out certain lenders for certain borrowers, this could constitute adverse action requiring specific-reason notices.

3. **Information restrictions:** If Desata is a creditor, §1002.5(b) restricts what information can be requested about applicants (race, sex, etc.) except for monitoring purposes.

4. **Self-testing privilege:** If Desata conducts algorithmic bias testing, results may be privileged under §1002.15 if the testing is voluntary and corrective action is taken.

### The "effects test" from Official Interpretation:
Even a neutral-appearing algorithm can violate ECOA if it has a disproportionately negative impact on a prohibited basis, unless it meets a legitimate business need that cannot be achieved by less disparate means. This applies to ClarifiED's methodology.
