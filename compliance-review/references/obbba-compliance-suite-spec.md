# Product Spec: Pro-Rata Loan Calculator

**Version:** March 2026
**Prepared for:** Nick Clarke
**Status:** V1 MVP

---

## Overview

The Pro-Rata Loan Calculator is a free, public web tool that calculates the correct prorated annual federal loan limit for a student under §685.203(m)(1) of the RISE NPRM, effective July 1, 2026. It checks prorated annual limits, annual and aggregate limits for all degree levels including new CIP-specific professional limits, and the new $257,500 lifetime maximum. It flags cases that require manual determination due to unresolved regulatory guidance.

The tool is available on Destrava's public website with no account required. No student data of any kind is entered into or transmitted through the tool. The printed or downloaded output includes blank fields for the counselor to record student information by hand.

Usage is tracked via Google Analytics at the aggregate and referrer level only.

---

## What the Tool Does Not Collect

No student name, student ID, or any student-identifiable information is entered into the tool at any point. These fields do not exist in the interface. The PDF output includes blank labeled lines — "Student Name: _______________" and "Student ID: _______________" — for the counselor to complete by hand after printing.

---

## Institution Setup

Presented as a brief configuration step the first time the tool is used: "Before your first calculation, confirm your institution's settings. This takes about two minutes."

Setup inputs are stored in the browser (localStorage) and pre-filled on return visits. Editable at any time from a Settings link.

### Setup fields

**Number of payment periods in your Title IV academic year.** Numeric, whole number, 1–6. Helper text: "Enter the number of payment periods that make up your institution's academic year for Title IV purposes. Common values: 2 for semester schools, 3 for trimester or standard quarter schools, 4 for four-quarter schools. Do not count summer terms that are headers or trailers outside the standard aid year — check your institution's academic year definition if unsure."

The term fraction for all proration calculations is derived as an exact rational value of 1 ÷ number of payment periods. This fraction is stored and calculated as an exact rational number throughout all intermediate steps. Decimal approximation is applied only at the final rounding step. For example, a school with 3 payment periods stores a term fraction of exactly 1/3, never 0.333.

**Full-time credit standard.** Numeric, accepts one decimal place, 9–21. Helper text: "The minimum credits per term your institution defines as full-time. Most institutions use 12. Check your academic catalog or ask your registrar if unsure."

**Financial Aid Office contact information.** Name, address, phone. Optional — auto-populates the downloaded calculation record. Email is collected separately at PDF download time (see PDF email gate).

---

## Calculator Interface

### Input fields

| Field | Type | Notes |
|---|---|---|
| Dependency status | Radio: Dependent / Independent | Helper note: "Select the dependency status that applies after any dependency override determination, not the FAFSA default. If a dependency override has been granted through professional judgment, use the adjudicated status." |
| Parent PLUS denied? | Radio: Yes / No | Shown only when Dependency status = Dependent and Degree level = Undergraduate. Helper text: "If the student's parent has been denied a Direct PLUS Loan, the student becomes eligible for additional unsubsidized loan amounts at the independent tier." |
| Degree level | Radio: Undergraduate / Graduate / Professional | Drives loan limit schedule and CIP check. For programs awarding both a graduate and professional degree: select Professional if more than 50% of the credit hours count toward the professional degree; otherwise select Graduate. |
| Grade level | Dropdown: Freshman / Sophomore / Junior / Senior | Shown only for Undergraduate. Helper note: "Use the student's grade level at the time of this disbursement. If the student advances a grade level mid-year (e.g., becomes a Sophomore after Fall term), they gain access to the higher annual limit for subsequent terms." |
| Grade level changes mid-year? | Radio: Yes / No | Shown only for Undergraduate when Full academic year is selected. If Yes: the Grade Level dropdown is replaced by two dropdowns: Term 1 Grade Level and Term 2 Grade Level. The tool runs a connected two-term calculation as described in Step 7 (Mid-Year Progression). |
| Loan type | Radio: Subsidized / Unsubsidized / Both | Subsidized not available for Graduate or Professional. |
| Prior subsidized borrowing | Numeric, accepts cents, optional | Shown only for Undergraduate, only when Loan type includes Subsidized. Helper text: "Enter the total subsidized loans this student has borrowed across all prior enrollment. The undergraduate subsidized aggregate limit is $23,000. If this student is near or over that amount, subsidized eligibility may be exhausted — verify in NSLDS before disbursing subsidized funds. Leave blank if unknown." |
| Legacy borrower | Radio: Yes / No / Help me determine | "Help me determine" opens the legacy borrower decision tree. |
| Program type | Dropdown: Standard term / Non-term / Subscription-based | Non-term and subscription-based trigger human-review flag immediately. |
| Consortium agreement | Radio: Yes / No | Helper text: "A consortium agreement is an arrangement where a student takes credits at a host institution but their home institution packages their aid." Yes triggers human-review flag. |
| CIP code | Text, 6 digits, optional | Shown when Degree level = Professional. Info box (collapsible, visible by default): "Enter the CIP code to validate that this program qualifies for professional loan limits. Under §685.102, a professional degree requires more than the right CIP code — the program must also be at the doctoral level, require at least six years of postsecondary education, and generally require professional licensure. The CIP code confirms the field of study; you confirm the program meets the other criteria. Your registrar can provide the CIP code. If left blank, no CIP validation is run." Not shown for Graduate degree level — selecting Graduate applies graduate limits regardless of CIP code. A counselor unsure whether a student is Graduate or Professional should make that determination based on the §685.102 definition before running the calculation. |
| Enrollment period | Radio: Full academic year / Single term / Final term of program | |
| Credits enrolled this term | Numeric, accepts one decimal place | Helper text: "Enter the student's Title IV-eligible credit load, not their raw registered credits. Repeated coursework may not count toward enrollment intensity for Title IV purposes — exclude any course the student has already passed and is retaking for a second time. This version of the tool does not accommodate clock-hour programs. [Let us know if you'd like to see clock-hour support added.]" The bracketed text links to a Destrava feedback form. |
| Credits enrolled next term | Numeric, accepts one decimal place | Shown only when Full academic year selected. Optional — if blank, calculator uses single-term method for the full year. |
| Enrollment intensity changes between terms? | Radio: Yes / No | Shown when Full academic year selected. If Yes, separate credit fields appear for each term and the tool calculates unequal per-term disbursements under the §685.303 waiver. |
| Outstanding principal balance — prior Title IV loans | Numeric, accepts cents (e.g. 24381.50) | All degree levels. Helper text: "Enter the outstanding principal balance of this student's prior federal loans — not the total amount ever borrowed. If a student borrowed $30,000 but has paid down $10,000, enter $20,000. Do not include capitalized interest. Do not include any PLUS loans (Parent PLUS or Graduate PLUS) — the $257,500 lifetime maximum and degree-level aggregate limits apply only to non-PLUS federal loans. This figure is available from NSLDS or the student's COD record. Do not include amounts borrowed in the current award year — those are captured in the YTD field. For graduate students who have previously been professional students (or vice versa), enter the combined non-PLUS outstanding balance." |
| YTD disbursed this award year | Numeric, accepts cents (e.g. 5250.00) | All degree levels. Total already disbursed in the current award year, including amounts from a prior institution if this is a transfer student. Helper text: "Include amounts disbursed at any institution in this award year. For transfer students, include what the sending institution disbursed this year. For spring-only or other single-term enrollments, include any amounts disbursed at this institution earlier in the same award year, even if the student withdrew from those earlier terms." |
| Institutional program limit | Numeric, accepts cents, optional | Info box: "If your institution has established a lower annual loan limit for this specific program under §685.203(m)(2), enter it here. The calculator will use this figure as the base for proration instead of the statutory maximum. Leave blank if your institution has not set a program-specific limit for this program." Validation: if the entered limit equals or exceeds the statutory maximum for the applicable degree level and grade level, the calculation is blocked and an inline error appears: "The institutional limit you entered ($[X]) must be lower than the statutory maximum ($[Y]). Institutional limits under §685.203(m)(2) may only reduce — not match or increase — the statutory limit." The counselor must correct the value before proceeding. The tool does not auto-correct silently. Re-validation triggers on any change to degree level, grade level, or institutional limit field — not only on initial entry. When a valid institutional limit is entered, it replaces the statutory annual limit in all subsequent calculation steps. The output and PDF note: "Prorated based on institutional program limit of $[X] per §685.203(m)(2), not the statutory maximum of $[Y]." |
| Military leave this term | Radio: Yes / No | Yes triggers human-review flag. |

### Legacy borrower decision tree

Activated when the counselor selects "Help me determine." Presented as a step-by-step decision sequence. Uses the exact two-part test from §685.203(b)(2)(iv)(B).

**Step 1.** "Was this student enrolled in a program of study at your institution as of June 30, 2026?" Yes / No. If No → not a legacy borrower under this provision. Close tree, set field to No.

**Step 2.** "Was a Direct Loan made to this student prior to July 1, 2026, for that program of study?" Yes / No. If No → not a legacy borrower. A student who was enrolled but did not borrow (for example, a Pell-only student) does not qualify under the regulatory text. Close tree, set field to No.

**If both Yes — Step 3.** "Is this student still within their 'expected time to credential' for this program?"

Display definition: "Under §685.102, 'expected time to credential' is the lesser of: (a) three academic years, or (b) the program length (as published in the institution's catalog or official materials for a full-time student) minus the period the student has already completed. Example: a three-year J.D. program where the student has completed two years has one year of expected time to credential remaining. A student who has exceeded this window no longer qualifies for the legacy exception even if they passed Steps 1 and 2."

Two sub-fields appear:
- Program length (in academic years, as published in catalog): numeric
- Period already completed (in academic years): numeric
- Calculated remaining: program length minus completed, displayed automatically
- Cap: if calculated remaining exceeds three academic years, display is capped at three and a note explains the regulatory ceiling

If calculated remaining is zero or negative → "This student's expected time to credential has elapsed. The legacy exception no longer applies. New loan limits under §685.203(b)(2)(iv)(A) apply." Close tree, set field to No.

If calculated remaining is greater than zero → "Based on your answers, this student appears to meet the conditions for the legacy borrower exception under §685.203(b)(2)(iv)(B) and retains prior-law loan limits for approximately [X] remaining academic year(s)."

Display note after the Yes determination:

> "Important: This exception is program-specific. If the student has switched to a different program of study, the exception no longer applies — unless the change was a change of major within the same degree or certificate, which counts as the same program of study. The exception also terminates if the student withdraws under §668.22 or otherwise ceases to be enrolled. You make the final determination and should document your reasoning in the student's file."

The decision tree pre-fills the legacy borrower radio button based on the outcome. The counselor can override it.

---

## Calculation Logic

### Step 1: Immediate human-review flags

Check before any calculation:
- Program type = Non-term → human-review flag
- Program type = Subscription-based → human-review flag
- Military leave = Yes → human-review flag
- Consortium agreement = Yes → human-review flag

If any flag triggers, skip to human-review output.

### Step 2: Legacy borrower

If Yes: skip proration. Output the full applicable prior-law annual limit. Display note: "This student is a legacy borrower and retains prior-law loan limits under §685.203(b)(2)(iv)(B). Proration under §685.203(m)(1) does not apply. The exception terminates if the student withdraws or ceases enrollment."

### Step 3: Applicable annual loan limit

**Undergraduate — Dependent:**

| Grade Level | Subsidized Max | Total (Dependent) | Total (PLUS Denied — uses Independent tier unsubsidized) |
|---|---|---|---|
| Freshman | $3,500 | $5,500 | $9,500 |
| Sophomore | $4,500 | $6,500 | $10,500 |
| Junior / Senior | $5,500 | $7,500 | $12,500 |

**Undergraduate — Independent (or Dependent with PLUS denial):**

| Grade Level | Subsidized Max | Total |
|---|---|---|
| Freshman | $3,500 | $9,500 |
| Sophomore | $4,500 | $10,500 |
| Junior / Senior | $5,500 | $12,500 |

Aggregate limits — Undergraduate:
- Dependent: $31,000 total ($23,000 subsidized max)
- Independent (or dependent with PLUS denial): $57,500 total ($23,000 subsidized max)

**Graduate:** $20,500 annual.

Aggregate limits — Graduate:
- Student who is not and has never been a professional student: $100,000
- Student who is or has been a professional student: $200,000, minus amounts borrowed as a professional student

**Professional:** $50,000 annual. Aggregate: $200,000, minus any subsidized loan amounts and any amounts borrowed as a graduate student.

**Lifetime maximum (all students, §685.203(j)(2)):** $257,500 across all non-PLUS federal loans, without regard to amounts repaid, forgiven, canceled, or discharged. This limit excludes all PLUS loans — parent PLUS and graduate PLUS — which do not count against it. When counselors enter prior borrowing figures, they must exclude any PLUS amounts. The NSLDS "Total Debt" figure includes PLUS; counselors must use only the non-PLUS sub/unsub outstanding balance. Legacy exception applies under the same two-part test; terminates on withdrawal.

**PLUS loans (informational, displayed separately — not subject to proration, not calculated by this tool):**

Parent PLUS is borrowed by the parent, not the student. The §685.203(m)(1) proration formula applies to loans "that student may borrow" and does not reach parent PLUS by its plain text. Parent PLUS is not prorated.

What does apply to parent PLUS on or after July 1, 2026:
- Annual limit: $20,000 minus other financial assistance as defined in Section 480(i) of the Act. This cap replaced the prior cost-of-attendance limit.
- Aggregate limit: $65,000, without regard to amounts repaid, forgiven, canceled, or discharged. Returned loan funds do not count against this limit.
- Cost of attendance constraint (§685.203(j)(1)): no Direct Loan including PLUS may exceed COA minus other estimated financial assistance, regardless of the dollar caps above.
- Legacy exception: same two-part test as other loan types. Terminates on withdrawal under §668.22 or cessation of enrollment. A student who changes majors within the same degree or certificate remains in the same program of study for PLUS purposes.

Graduate and Professional PLUS: beginning July 1, 2026, graduate and professional students may not borrow Direct PLUS Loans unless they qualify for the legacy exception under §685.200(b)(2)(ii). Non-legacy graduate and professional students have no PLUS access. Display note directing counselor to §685.200(b)(2) if they have a legacy graduate or professional PLUS question.

### Step 4: Prior subsidized borrowing check (Undergraduate, if entered)

If prior subsidized borrowing is entered and equals or exceeds $23,000: display warning on output, above the calculated limit: "This student's prior subsidized borrowing ($[X]) is at or near the $23,000 aggregate subsidized limit. Subsidized eligibility may be fully exhausted. Verify remaining subsidized eligibility in NSLDS before disbursing any subsidized loans. This tool does not perform a complete SULA analysis."

If prior subsidized borrowing is entered and is between $18,000 and $23,000: display caution: "This student's prior subsidized borrowing ($[X]) is approaching the $23,000 aggregate subsidized limit. Verify remaining subsidized eligibility in NSLDS."

### Step 5: CIP validation (Professional only, if CIP entered)

CIP code is only shown and only checked when the counselor has selected Professional as the degree level. The CIP check validates the counselor's Professional selection — it does not upgrade a Graduate selection to Professional. Degree level drives the loan limit; CIP confirms the field of study for a Professional selection.

Extract first four digits of entered CIP code. Check against qualifying intermediate groups:

| First 4 Digits | Programs |
|---|---|
| 2201 | Law |
| 5112 | Medicine, Osteopathic Medicine, Podiatric Medicine |
| 5120 | Pharmacy |
| 5104 | Dentistry, Chiropractic |
| 0108 | Veterinary Medicine |
| 5117 | Optometry |
| 3906 | Divinity / Ministry, Rabbinical Studies |
| 4228 | Clinical Psychology (Psy.D. or Ph.D.) |

Match found and degree level = Professional → confirm professional limits apply. Display: "CIP code confirmed within a qualifying professional degree program group."

No match and degree level = Professional → human-review flag. Display: "The CIP code entered does not match a recognized professional degree program group. Verify that this program meets all four criteria for a professional degree under §685.102 before applying professional loan limits."

No CIP entered and degree level = Professional → no CIP validation run. Professional limits apply based on the counselor's selection. No flag generated — the counselor is responsible for confirming the program qualifies.

Degree level = Graduate → Step 5 is skipped entirely. Graduate limits apply.

### Step 6: Aggregate and lifetime maximum checks

```
Projected aggregate = prior borrowing + YTD disbursed this year + prorated limit (from Step 7)
```

Check projected aggregate against: applicable degree-level aggregate limit, and $257,500 lifetime maximum.

If either is exceeded: display warning on output, above the calculated limit. Warning does not block the calculation output.

### Step 7: Enrollment intensity proration

**Rounding rule.** Per §685.203(m)(1), enrollment intensity is rounded to the nearest whole percentage point before being applied to the annual limit. Calculate the percentage, round to the nearest whole integer, then multiply by the annual limit. Do not round intermediate term calculations separately — sum all terms to full precision first, then round the final dollar amount down to the nearest dollar.

**Subsidized and unsubsidized proration — applied separately.**

Enrollment intensity is applied to the subsidized limit and the total limit independently. The prorated unsubsidized amount available is the prorated total minus the prorated subsidized limit.

For a dependent Junior at 50% intensity: subsidized limit $5,500 × 50% = $2,750 prorated subsidized. Total limit $7,500 × 50% = $3,750 prorated total. Unsubsidized available: $3,750 − $2,750 = $1,000.

The output must display prorated subsidized limit and prorated unsubsidized limit as separate line items, not only the prorated total.

**Term fraction.** Derived from institution setup as the exact rational value 1 ÷ number of payment periods. Never stored or used as a truncated decimal. Examples: semester school = 1/2 exactly; 3-period school = 1/3 exactly; 4-period school = 1/4 exactly.

**Developer note — floating-point math.** JavaScript uses IEEE 754 floating-point arithmetic, which cannot represent fractions like 1/3 exactly and produces rounding errors in financial calculations (e.g., 0.1 + 0.2 = 0.30000000000000004). Financial aid audits check to the penny. All intermediate calculations must therefore either (a) use a precise decimal library such as `decimal.js` or `fraction.js`, or (b) convert all dollar amounts to integer cents (multiply by 100), perform all multiplication and division in integer space, apply `Math.floor()` once at the final step, and divide by 100 for display. Native float arithmetic on dollar amounts without one of these mitigations is not acceptable.

**Full academic year, same intensity all terms:**
```
Enrollment intensity % = round(credits enrolled ÷ full-time credit standard × 100) %
Prorated subsidized limit = subsidized limit × (enrollment intensity % ÷ 100)
Prorated total limit = total annual limit × (enrollment intensity % ÷ 100)
Prorated unsubsidized available = prorated total − prorated subsidized
Round all three figures down to nearest dollar at this step only.
```

**Full academic year, different intensity each term (§685.303 waiver):**
```
Term fraction = 1 ÷ number of payment periods (exact rational, e.g. 1/3 not 0.333)
For each term:
  Term intensity % = round(credits enrolled that term ÷ full-time credit standard × 100) %
  Term subsidized limit (unrounded) = subsidized limit × term fraction × (term intensity % ÷ 100)
  Term total limit (unrounded) = total annual limit × term fraction × (term intensity % ÷ 100)
Prorated subsidized limit = sum of all term subsidized limits (unrounded)
Prorated total limit = sum of all term total limits (unrounded)
Prorated unsubsidized available = prorated total − prorated subsidized
Round all three figures down to nearest dollar at this step only.
```

**Single term or final term (§685.203(m)(1)(i)):**
```
Term fraction = 1 ÷ number of payment periods (exact rational)
Enrollment intensity % = round(credits enrolled ÷ full-time credit standard × 100) %
Prorated subsidized limit = subsidized limit × term fraction × (enrollment intensity % ÷ 100)
Prorated total limit = total annual limit × term fraction × (enrollment intensity % ÷ 100)
Prorated unsubsidized available = prorated total − prorated subsidized
Round all three figures down to nearest dollar at this step only.
```

**Final-term students enrolled less than full-time:** §685.203(m)(1) controls via the "notwithstanding" clause. The §685.203(h) remaining-period-of-study proration does not apply simultaneously.

**Mid-year grade level progression (undergraduate, full academic year):**

Annual loan limits are cumulative for the academic year. When a student advances a grade level mid-year, the Term 2 disbursement is not calculated independently and summed — it is the remainder of the Term 2 annual limit after accounting for what was already awarded in Term 1.

```
Term fraction = 1 ÷ number of payment periods (exact rational)

Step A — Term 1:
  Term 1 intensity % = round(Term 1 credits ÷ full-time standard × 100) %
  Term 1 subsidized limit = Term 1 subsidized annual limit × term fraction × (Term 1 intensity % ÷ 100)
  Term 1 total limit = Term 1 total annual limit × term fraction × (Term 1 intensity % ÷ 100)
  (Do not round yet)

Step B — Term 2 ceiling:
  Term 2 intensity % = round(Term 2 credits ÷ full-time standard × 100) %
  Term 2 max annual subsidized prorated = Term 2 subsidized annual limit × (Term 2 intensity % ÷ 100)
  Term 2 max annual total prorated = Term 2 total annual limit × (Term 2 intensity % ÷ 100)

Step C — Term 2 disbursement:
  Term 2 subsidized = Term 2 max annual subsidized prorated − Term 1 subsidized limit
  Term 2 total = Term 2 max annual total prorated − Term 1 total limit
  (Do not round yet)

Step D — Final:
  Prorated subsidized limit = Term 1 subsidized + Term 2 subsidized
  Prorated total limit = Term 1 total + Term 2 total
  Prorated unsubsidized = Prorated total − Prorated subsidized
  Round all three down to nearest dollar (once, at this step only)
```

Output displays both the overall prorated annual limit and the per-term breakdown: Term 1 amount and Term 2 amount.

Example: Dependent Freshman (Term 1, half-time) becomes Sophomore (Term 2, half-time), semester school.
- Term 1: $5,500 annual total × 50% intensity × 1/2 term = $1,375
- Term 2 ceiling: $6,500 annual total × 50% intensity = $3,250
- Term 2 disbursement: $3,250 − $1,375 = $1,875
- Total for year: $1,375 + $1,875 = $3,250 (not $1,375 + $1,625 = $3,000 as a naive sum would produce)

**Transfer students mid-year:** The tool uses the receiving institution's full-time credit standard and academic year definition. YTD disbursed includes amounts from the sending institution in the same award year.

### Step 8: Overload credits

If credits entered exceed the full-time credit standard, display confirmation before calculating: "You entered [X] credits, which exceeds your institution's full-time standard of [Y]. Overload credits do not increase the loan limit. The calculation will use [Y] as the enrollment denominator. Continue?"

---

## Output Display

### Auto-calculated result

- Prorated annual loan limit — large and prominent
- Remaining available this award year (prorated limit minus YTD disbursed). If this formula results in a negative number, display remaining available as $0.00 and trigger a high-contrast red warning box: "Warning: YTD disbursements exceed this student's prorated limit by $[absolute value of the negative amount]. The student is not eligible for additional funds. Review prior disbursements for a potential overaward."
- Any aggregate or SULA warnings — warning box above the limit
- **Per-payment-period disbursement schedule:**
  - Equal disbursement: prorated limit ÷ number of terms, shown per term in a table
  - Unequal disbursement (§685.303 waiver): each term's calculated limit shown separately
  - Table format: Term | Disbursement Amount
- Calculation breakdown: annual limit used, enrollment intensity percentage (rounded), term share if applicable, each step with regulatory citation
- **PLUS loan information block** (displayed separately below main result, for dependent undergrads and grad/professional students): applicable parent PLUS annual cap ($20,000 minus other aid) and aggregate cap ($65,000), with a clear note that parent PLUS is not subject to enrollment intensity proration under §685.203(m)(1). For graduate and professional students, a note that PLUS is unavailable on or after July 1, 2026 unless the student qualifies for the legacy exception, with a reference to §685.200(b)(2)
- Institution name and Financial Aid Office contact (from setup)
- Date and time of calculation
- Disclaimer: "This calculation does not account for professional judgment adjustments or a complete SULA analysis. If PJ has been exercised or subsidized eligibility is a concern, verify before disbursing."

**Actions:** Download PDF, Print, Run another calculation, Apply professional judgment adjustment.

**PDF email gate.** Downloading a PDF requires a work email address. The calculator is fully functional without one — the gate applies only to PDF download. At the point of first PDF download, a prompt appears inline: "Enter your work email to download this record. [Work email field] [Download PDF]." The email is saved to localStorage for the session so subsequent downloads do not re-prompt. The domain is hashed and sent to analytics as described above.

### Professional judgment adjustment

A collapsible section below the result, labeled "Apply a professional judgment adjustment."

Fields:
- Adjustment amount (numeric, positive or negative dollar amount)
- Notes (free text — counselor documents the basis for the adjustment)

When an adjustment is entered, the output updates to show:
- Calculated limit: $[X]
- PJ adjustment: +/- $[Y]
- **Adjusted limit: $[Z]**

Disclaimer within the PJ section: "Professional judgment adjustments must be documented in the student's file per 34 CFR 685.301. This tool records the adjustment amount and your notes in the downloaded PDF but does not substitute for required file documentation."

The PJ adjustment and notes appear in the downloaded PDF.

### Transfer student note on output

When YTD disbursed is greater than zero: "YTD disbursed ($[X]) has been subtracted from the prorated limit to show remaining availability. For transfer students, confirm this figure includes amounts disbursed by the sending institution in the current award year."

---

## Human-Review Flag Output

Displayed instead of a calculated result when auto-calculation is not possible.

Shows:
- Header: "This case requires manual review"
- Trigger that caused the flag (plain language)
- Full regulatory explanation
- "What you need to determine" checklist
- All inputs entered, displayed for reference
- Determination section (completed in the browser, never transmitted):
  - Loan limit applied (numeric)
  - Basis for determination (dropdown: Institutional policy / Legal counsel guidance / ED guidance / Other)
  - ED guidance reference if applicable (text)
  - Notes (free text)
  - Counselor name (text)
  - Date of determination (date, pre-filled with today)

**Actions:** Download PDF (pre-filled with all inputs, flag explanation, and determination fields as completed), Print, Run another calculation.

### Flag display text

**Non-term program:**
> This case requires manual review. Non-term programs are excluded from the §685.203(m)(1) proration formula. The regulatory treatment for non-term programs has not been finalized in the RISE NPRM.
>
> What you need to determine:
> 1. Which loan limit provisions apply to this student's non-term program under current regulatory guidance.
> 2. The specific limit you are applying and your basis for that determination.

**Subscription-based program:**
> This case requires manual review. Subscription-based programs are excluded from the §685.203(m)(1) proration formula. ED invited public comment on how the schedule of reductions applies to these programs but has not issued guidance.
>
> What you need to determine:
> 1. Which loan limit provisions apply to this student's subscription-based program.
> 2. The specific limit you are applying and your basis for that determination.

**Military leave:**
> This case requires manual review. The RISE NPRM does not address how enrollment-intensity proration applies during a term in which a student is on military leave. LOA grandfathering is settled — a servicemember called to active duty retains the interim exception under §685.203(b)(2)(iv)(B) — but proration treatment for the absent term itself is not addressed.
>
> What you need to determine:
> 1. Whether this student's military leave qualifies for LOA grandfathering.
> 2. What loan limit, if any, applies for the absent term.
> 3. The basis for your determination.

**Consortium agreement:**
> This case requires manual review. The tool assumes single-institution enrollment. Under a consortium agreement, the credit load, full-time credit standard, and academic calendar may be split across institutions, and the home institution must determine the applicable enrollment intensity based on the combined arrangement.
>
> What you need to determine:
> 1. The Title IV-eligible credit load across both institutions for this term.
> 2. The applicable full-time credit standard for proration purposes.
> 3. The enrollment intensity and resulting prorated limit.

**Professional CIP not recognized:**
> This case requires manual review. The CIP code entered ([code]) does not match a recognized professional degree program group under the OBBBA definition. Before applying professional loan limits, verify that this program qualifies. If it does not qualify, graduate limits apply ($20,500 annual / applicable aggregate).
>
> What you need to determine:
> 1. Whether this program qualifies as a professional degree program.
> 2. Which annual and aggregate limits apply.
> 3. The basis for your determination.

---

## Downloaded PDF Record

Generated in the browser. Never sent to or stored on Destrava's servers.

**PDF contents:**
- Header: "Destrava Analytics — Pro-Rata Loan Calculator — Calculation Record"
- Institution name and Financial Aid Office contact (from setup)
- Date and time of calculation
- Blank lines: "Student Name: _______________" and "Student ID: _______________"
- All inputs entered
- Output: prorated limit, per-period disbursement schedule, any warnings, and PJ adjustment if applied; or "Human Review Required" with full flag explanation and determination fields as completed
- Calculation breakdown with regulatory citations
- Footer: "Generated using the Destrava Analytics Pro-Rata Loan Calculator based on §685.203(m)(1) of the RISE NPRM (January 30, 2026). This tool will be updated when the final rule is published. Verify all calculations against the final rule before July 1, 2026. This tool does not perform a complete SULA analysis or account for professional judgment adjustments unless entered manually above."

---

## Final Rule Update Architecture

The calculation engine and edge case routing layer are separate components. Each human-review trigger maps to a configuration parameter: either "route to human review with [explanation text]" or "auto-calculate using [formula]." Both routing logic and explanation text are configurable without code deployment.

When the final rule resolves an edge case, Destrava updates the configuration. The change takes effect immediately for all users.

**Day-of-final-rule notification:**

Banner on the tool homepage when the final rule publishes: "The RISE final rule was published on [date]. This tool has been updated. [See what changed]"

The PDF footer updates automatically to cite the final rule once published.

Draft the banner and "what changed" page in advance so they deploy the day the final rule publishes.

---

## Error States

| Situation | Display |
|---|---|
| Setup not completed | Calculator fields locked. Banner: "Complete your institution settings before running a calculation. [Complete settings]" |
| Non-numeric entry in numeric field | Inline: "Please enter a whole number." |
| Credits exceed full-time standard | Confirmation prompt before calculating (see Step 8) |
| CIP code not 6 digits | Inline: "CIP codes are 6 digits. Example: 220101 for Law." |
| Aggregate or lifetime limit exceeded | Warning box on output above the calculated limit |
| PDF generation fails | "We couldn't generate your PDF. Please try printing this page directly (Ctrl+P or Cmd+P)." |

---

## Analytics

Google Analytics tracks tool usage at aggregate and referrer level only. No student data, no counselor data.

Events tracked:
- Tool loaded
- Setup completed
- Calculation run (degree level, enrollment period, program type, legacy borrower outcome, whether CIP check triggered, whether PJ adjustment applied — no student data)
- Human-review flag triggered (trigger type)
- PDF downloaded
- Print initiated

**Institution identification via email domain hash.** Referrer headers are unreliable for B2B identification — financial aid counselors frequently access tools via bookmarks, direct URL entry, or campus firewalls that strip referrer data, producing large volumes of unusable "direct/(none)" traffic.

When a counselor enters their email address at PDF download, the tool extracts the domain (e.g., nyu.edu from financial.aid@nyu.edu), hashes it client-side using SHA-256, and sends the hash as a custom GA event parameter. No email address or PII is transmitted to analytics — only the one-way hash. This provides a highly accurate, privacy-compliant signal of which institutions are actively using the tool, including users who never create an account.

Referrer domain is retained as a secondary signal for sessions where no email has been entered.

---

## Out of Scope for V1

- Accounts and saved records
- Program Loan Limit Manager
- Clock-hour program calculations (info box directs counselors to contact Destrava to request this feature)
- Full SULA / 150% calculation (simplified subsidized aggregate check only)
- Role-based access control
- SSO / SAML
- SIS integration of any kind
- Batch calculation (a note on the tool page reads: "Need to run calculations for multiple students at once? Contact us at info@destrava.co to learn about batch processing options.")
- Student-facing portal
- Multi-campus configuration
- Real-time NSLDS data
- PLUS loan calculations of any kind (parent PLUS is not subject to proration; grad/professional PLUS eligibility is informational only)
