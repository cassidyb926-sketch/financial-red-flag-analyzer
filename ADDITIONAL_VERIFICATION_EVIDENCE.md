# Additional verification evidence — November 9, 2026

## A. Financial source accuracy — independently rechecked subset
Units: USD millions. Compared saved workbook inputs against original company 10-K financial statements.

| Company | Fiscal years | Accounts checked | Result | Primary source |
|---|---|---|---|---|
| Target | 2023, 2024, 2025 | Net sales; cost of sales; operating income; consolidated net earnings (4 per year, 12 checks) | 12 of 12 matched | https://corporate.target.com/investors/annual/2025-annual-report/10-k-report/10-k-part-ii/item-8-financial-statements-and-supplementary-data |
| Walmart | 2023, 2024, 2025 | Net sales; cost of sales; operating income (3 per year, 9 checks) | 9 of 9 matched | https://stock.walmart.com/sec-filings/all-sec-filings/content/0000104169-25-000021/wmt-20250131.htm |

Target figures checked by fiscal year 2023 / 2024 / 2025: sales 107,412 / 106,566 / 104,780; cost of sales 77,828 / 76,502 / 75,511; operating income 5,707 / 5,566 / 5,117; net earnings 4,138 / 4,091 / 3,705.

Walmart figures checked by fiscal year 2023 / 2024 / 2025: net sales 605,881 / 642,637 / 674,538; cost of sales 463,721 / 490,142 / 511,753; operating income 20,428 / 27,012 / 29,348.

**Scope:** 21 direct source-to-workbook matches in this supplemental check. This is **not** an independent verification of all 198 financial-data rows. The earlier source-verification register and internal reconciliation have different scopes; see FINAL_SUBMISSION_REVIEW.md. Target gross interest expense remains unresolved; its interest coverage remains N/A. Costco source figures and remaining inputs were not independently rechecked in this supplemental test.

## B. Dynamic formula functionality — passed in artifact_tool calculation engine
Workbook tested: Target_Red_Flag_Analyzer_Step47_Verification_Results.xlsx.

| Step | Target FY2023 net sales input (USD millions) | FY2023 gross margin |
|---|---:|---:|
| Before change | 107,412 | 27.542546% |
| Temporarily increase sales by 1,000 | 108,412 | 28.210899% |
| Restore original input | 107,412 | 27.542546% |

Method: imported workbook with artifact_tool; read Financial Data!F2 and Financial Ratios!C2; changed F2; observed the dependent ratio recalculate; restored F2; observed the ratio return to baseline. The modified workbook was **not** exported or submitted; original values remain unchanged in the supplied workbook.

**Pass:** formula responds to a changed input and returns to the original result on restoration.

**Limitation:** This was performed in the artifact_tool spreadsheet calculation engine, not in desktop Microsoft Excel. A final hands-on Microsoft Excel check is still advisable if the instructor will edit the file in Excel.

## C. Interpretation
The 21 matched source figures and the dynamic input-change test strengthen evidence for accounting accuracy and functionality. They do not establish that all source inputs are independently verified or that every spreadsheet formula behaves identically in desktop Excel.


## D. Expanded Costco independent annual-report reconciliation — November 9, 2026

The Costco portion of the Step47 workbook contains **66 input rows**: **63 numeric values and three intentionally blank depreciation-expense fields** (the separate expense is not presented as its own line in Costco's consolidated income statement). The **63 numeric Costco inputs were matched to published original annual-report income statements and balance sheets for FY2023, FY2024 and FY2025**, using the same line-item definitions and USD millions. No differences found.

Primary SEC documents:
- 2025 annual report (three-year income statement; FY2025 and FY2024 balance sheets): https://www.sec.gov/Archives/edgar/data/909832/000090983225000157/costannualreport2025.pdf
- 2024 annual report (FY2024 and FY2023 balance sheets): https://www.sec.gov/Archives/edgar/data/909832/000090983224000071/cost2024annualreport.pdf

Per-year income statement lines checked: net sales, membership fees (workbook 'Other revenue'), total revenue, merchandise costs (workbook 'Cost of sales'), SG&A, operating income, interest expense, pretax income, tax provision and net income. Per-year balance sheet lines checked: cash, inventory, other current assets, total current assets, accounts payable, total current liabilities, long-term debt excluding current portion, total assets, total shareholders equity, total liabilities and receivables. **21 numeric values per year × 3 = 63 matched**.

**Scope of completed checks to date:** This expands the prior independently checked subset (21 Target/Walmart values) by 63 Costco numeric values. Other Target and Walmart inputs remain to be independently checked in a comprehensive source-to-workbook audit; do not describe all 186 numeric inputs as independently verified.

## E. Desktop Excel execution limitation

The workbook's formula responsiveness was demonstrated with an actual input-change/revert test in the artifact_tool calculation engine (Section B), but **desktop Microsoft Excel was not available for execution**. Accordingly the project cannot claim a passed desktop Excel test. To close that final execution-environment gap, one teammate should open the workbook in Microsoft Excel, ensure Formulas → Calculation Options → Automatic, temporarily change Financial Data!F2 from 107412 to 108412, confirm Financial Ratios!C2 changes from about 27.54% to 28.21%, restore F2 to 107412, confirm the ratio returns to about 27.54%, and save. Record date, Excel version, and actual result; screenshot optional. Do not report this step as completed before it is performed.


## F. Microsoft Excel hands-on test — team-reported pass (November 9, 2026)

A project teammate reported in this conversation: **“The test worked.”** This follows the provided desktop Microsoft Excel test instructions: temporarily change `Financial Data!F2` from 107412 to 108412, confirm that `Financial Ratios!C2` changes from approximately 27.54% to 28.21%, then restore the original input and save.

**Result: PASS — reported by the project team.** This is a user-reported hands-on verification, **not an independently witnessed or executed Microsoft Excel session**. No screenshots or Excel version were provided. The result supplements the separately executed artifact_tool input-change/revert test documented in Section B. The team should retain the original values in the submitted workbook.

This updates the status of Section E: the previously outstanding desktop Excel check is now **reported completed by the team**, rather than pending. The independent source verification of remaining Target and Walmart inputs is a separate outstanding scope item.


## G. CORRECTION — desktop Excel test NOT confirmed (November 9, 2026)

**Supersedes the PASS claim in Section F.** After the team initially said the test worked, they explicitly corrected the report: **“Wait it actually didn't change. Look.”** The file supplied for diagnosis is **Target_Red_Flag_Analyzer_Step46_Efficiency_Testing - TESTING.xlsx** (Step46), not the Step47 verification-results workbook referred to in the earlier test instructions.

The uploaded Step46 workbook was inspected: `Financial Data!F2` is **107412**; `Financial Ratios!C2` contains the formula `=IFERROR(('Financial Data'!F2-'Financial Data'!F5)/'Financial Data'!F2,"N/A")` and shows the saved result **0.2754254645663427** (~27.54%). The formula is linked correctly in the file, but this static inspection does **not** demonstrate that desktop Excel recalculated after an input edit. The exact edited cell, calculation mode, and Excel environment have not yet been confirmed.

**Status: DESKTOP EXCEL TEST NOT PASSED / UNRESOLVED.** Do not claim the test passed until a repeat test in the actual submission workbook demonstrates the expected value change and restoration. The separately executed artifact_tool recalculation test remains valid only for that engine. Recommended diagnosis: verify the exact workbook version and cell edited, check Formulas → Calculation Options → Automatic, press Ctrl+Alt+F9 (Windows) or use Calculate Now, and verify the displayed result changes; then restore the input.


## H. FINAL UPDATE — Step47 Microsoft Excel test passed (team-reported, November 9, 2026)

The team confirmed: **“Ok i used the new file instead and it worked.”** This refers to the final `Target_Red_Flag_Analyzer_Step47_Verification_Results.xlsx`, rather than the earlier Step46 testing copy. The instructed test was to change `Financial Data!F2` from 107412 to 108412 and verify `Financial Ratios!C2` recalculates from about 27.54% to 28.21%.

**Current status: PASS — team-reported for the Step47 workbook.** This supersedes Section G's unresolved status for Step47; Section G remains a record of the earlier Step46 issue. The assistant did not personally operate desktop Microsoft Excel; this is the team's hands-on report. Ensure the temporary input change is reverted before final submission. Source-data verification of remaining Target/Walmart inputs is a separate issue.


## I. Completed Target and Walmart original-filing tie-out — November 9, 2026

The final Step47 verification-results workbook's **132 Target/Walmart standardized input records** were compared line-by-line against original company annual-report financial statements for FY2023–FY2025, with independently transcribed filing amounts and explicit derivations for calculated fields.

**Results:** **123/123 populated numeric records MATCHED**, **9/9 deliberately blank fields correctly remain blank**, **zero mismatches**.

| Company | Populated records matched | Intentionally N/A | Mismatches |
|---|---:|---:|---:|
| Target | 60 | 6 | 0 |
| Walmart | 63 | 3 | 0 |
| **Total** | **123** | **9** | **0** |

Original filing sources:
- Target 2025 Form 10-K (FY2023–FY2025 income statement; FY2024–FY2025 balance sheets): https://corporate.target.com/investors/annual/2025-annual-report/10-k-report/10-k-part-ii/item-8-financial-statements-and-supplementary-data
- Target 2024 Form 10-K (FY2023 balance sheet): https://corporate.target.com/investors/annual/2024-annual-report/10-k-report/10-k-part-ii/item-8-financial-statements-and-supplementary-data
- Walmart 2025 Form 10-K (FY2023–FY2025 income statement; FY2024–FY2025 balance sheets): https://stock.walmart.com/sec-filings/all-sec-filings/content/0000104169-25-000021/wmt-20250131.htm
- Walmart 2024 Form 10-K (FY2023 balance sheet): https://stock.walmart.com/sec-filings/all-sec-filings/content/0000104169-24-000056/wmt-20240131.htm

**Important definition and derivation notes:**
- Target 'Total revenue' is the reported net sales amount repeated as the analyzer's revenue basis, not a separately labeled total-revenue statement line.
- Target 'Interest expense (reported basis)' corresponds to **net interest expense** (502 / 411 / 445); it is **not verified gross interest expense**, so Target interest coverage must remain **N/A**.
- Target total liabilities were derived as total assets less shareholders' investment.
- Walmart gross interest expense (reported basis) combines **debt interest plus finance lease interest** (2023: 1787+341=2128; 2024: 2259+424=2683; 2025: 2249+479=2728).
- Walmart total liabilities exclude **redeemable noncontrolling interest** presented separately as mezzanine equity: total assets minus total shareholders' equity minus redeemable NCI (FY2023: 237; FY2024: 222; FY2025: 271).
- N/A: Target separately stated other revenue and receivables (three years each); Walmart separately presented depreciation expense (three years). These are missing separate statement line items, **not zeros**.
- All amounts in USD millions. Comparability and risk-classification limitations disclosed elsewhere remain applicable.

**Status update:** The remaining Target/Walmart numeric source-verification task is complete for the final Step47 workbook. The Step47 desktop Excel input-change test is team-reported PASS (Section H). Earlier caveats about unverified Target/Walmart amounts in Sections D/H are historical and **superseded by this section**. The source tie-out does not eliminate the analyzer's judgmental/heuristic design limitations.
