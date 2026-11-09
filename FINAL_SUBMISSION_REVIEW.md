# ACG 6805 Fall 2026 — Final Rubric and Submission Review

Project: Financial Statement Red Flag Analyzer  
Contributors: Kate La Russo and Cassidy Beale  
Portfolio: https://cassidyb926-sketch.github.io/financial-red-flag-analyzer/

This checklist is based on the supplied Fall 2026 Portfolio Project instructions. It is a readiness review, **not a prediction of the professor's grade**.

## Required deliverables

| # | Deliverable | Evidence / location | Status |
|---|---|---|---|
| 1 | Professional opportunity: problem, target user, current practice, measurable improvement | Overview; audit associates and financial analysts; manual review baseline; team-reported 20 vs. 7 minutes | Documented |
| 2 | Theory/design matrix with five required columns | Theory section; agency theory, decision usefulness, professional skepticism | Documented |
| 3 | Functional prototype, not slides alone | Downloadable Excel analyzer; interactive website shows saved data | Present; live recalculation still to test |
| 4 | Solution description: inputs, assumptions, interpretation | Overview, Dashboard, Theory, Governance | Documented |
| 5 | Testing, baseline, and revisions | Testing section: 69/69 ratio checks, 24/24 risk labels, 12/12 scenario retests, 65% team-reported time reduction; N/A safeguards | Partially independently verified; revision chronology could be strengthened |
| 6 | Governance: data, privacy, AI, human review, limitations, prohibited uses | Governance section | Documented; student review required |
| 7 | Recruiter-facing webpage **or** video/other presentation, plus resume bullet | GitHub Pages website; Team section resume bullet | Documented; video not required |

## Grading categories (20% each)

1. **Professional problem and innovation value:** Clear retail financial-statement screening use case. Consider whether the team can explain why manual ratio analysis is insufficient and what is genuinely new about the combined workflow.
2. **Accounting theory and professional judgment:** Five-column matrix links theory to specific design features and test evidence. Risk thresholds remain judgmental.
3. **Functionality:** Workbook and saved-data website exist. Live Microsoft Excel formula-refresh test is still outstanding. Independent source verification is incomplete.
4. **Testing, validation, demonstrated value:** Saved arithmetic and classification retests are documented. The team reported a 20-minute manual review and a 7-minute assisted review, but timing was not independently observed. Step 40 documents three Walmart total-liabilities corrections (FY2023: 159,443 to 159,206; FY2024: 162,050 to 161,828; FY2025: 163,402 to 163,131, USD millions), excluding redeemable noncontrolling interest from liabilities. The source-reconciliation worksheet reports 186 populated amounts matched or corrected, distinct from the later independent 66-record check.
5. **Professional portfolio communication:** Live website, separate contributor descriptions, and a resume-ready bullet are present. Verify the link, workbook download, mobile rendering, and the team contributions for accuracy.

## Additional automated QA (November 9, 2026)

- **Workbook package:** The Step 47 verification-results XLSX archive passed its ZIP integrity check and contains 33 worksheet XML parts.
- **Independent QA sheets:** Reopened the verification-results workbook using the spreadsheet engine. Its QA summary reports 69/69 ratio calculations, 3 expected N/A results, 12/12 scenarios, and 24/24 risk classifications; zero arithmetic/scenario/risk failures.
- **Website script:** Node.js syntax check passed for the local website's `script.js`.
- **Data consistency:** All 24 embedded JavaScript dashboard records exactly match `dashboard-data.json`; each fiscal year has eight ratios.
- **Saved risk counts:** FY2023: 4 Low, 3 Moderate, 0 High, 1 N/A; FY2024: 4 Low, 3 Moderate, 0 High, 1 N/A; FY2025: 3 Low, 4 Moderate, 0 High, 1 N/A.

**Scope:** These are local-file syntax, data-consistency, package-integrity, and saved-result checks. They do not prove the deployed GitHub Pages site renders in a real browser, independently authenticate all SEC source inputs, or demonstrate Microsoft Excel's live recalculation after an input edit.

## Remaining gates — do not mark complete without evidence

- **Source tie-out:** The source-verification register has 198 records: 66 individually matched, 120 populated records not independently checked, and 12 unresolved N/A records. Confirm figures from primary reports before claiming complete verification. Document annual-report page/statement, units, fiscal period, and any derivation.
- **Live Excel test:** Open the final `Financial_Red_Flag_Analyzer.xlsx` in desktop Microsoft Excel. Save a copy; change a selected numeric input; recalculate; confirm the dependent ratio and risk label change appropriately; restore the input and confirm values return. Record actual observed cell addresses and outcomes. A saved-cache check is not a substitute.
- **Revision evidence:** Step 40 documents three Walmart liabilities corrections with before/after values and the redeemable-noncontrolling-interest rationale. Confirmed by direct inspection of the Step 47 workbook Financial Data sheet: Walmart FY2023/FY2024/FY2025 total liabilities are 159,206 / 161,828 / 163,131 (USD millions), respectively. A live Microsoft Excel input-change recalculation/retest is still outstanding. Withholding Target interest coverage when unsupported is a documented safeguard, but do not claim it resulted from a test unless that sequence is evidenced.
- **Peer comparability:** Check fiscal-year alignment, 53-week period effects, interest-coverage definitions, and Walmart redeemable noncontrolling interest presentation.
- **AI disclosure:** Website states that AI assisted documentation, website content, and verification workflows. Confirm this accurately describes the team's work and meets any separate instructor disclosure rule.
- **Submission method:** Confirm the professor's requested delivery format or LMS fields; the supplied instructions specify deliverables but not a unique upload format or due date.

## Resume bullet (proposed)

Co-developed an Excel-based financial statement red flag analyzer evaluating eight ratios for Target, Walmart, and Costco across FY2023–FY2025; implemented historical and peer-based risk screening, validated saved ratio and scenario results, and documented a team-reported 65% reduction in review time.

## Interpretation safeguards

This is an educational risk-screening prototype, not an audit opinion or evidence of fraud. No independently verified, generalized time-savings claim is made. The website dashboard displays saved workbook results rather than live financial data.
