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
