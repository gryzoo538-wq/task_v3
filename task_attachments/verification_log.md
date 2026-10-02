# Verification log

Reference date 2026-09-30. All checks were run against the final files in this folder.

## 1. Scanned PDFs re-opened as images

Each scan was re-opened from its embedded page image, rotated upright where needed, cropped to the result block and enlarged 2x for the 72 dpi scans. Every value was compared with coa_extracted.csv.

| PDF | Orientation / quality | Values confirmed (product, amount, lot, date, purity, theor./found mass) | Result |
|---|---|---|---|
| CBA-2506105.pdf | upright, 72 dpi | GHRP-2 (Pralmorelin), 5 mg, PP-2511-003, 11/06/2025, 98.6 %, 817.9 / 817.7 | match |
| CBA-2531544.pdf | rotated 90°, 110 dpi | Epitalon (Epithalon), 10 mg, PP-2510-009, 10/28/2025, 99.1 %, 390.4 / 390.6 | match |
| CBA-2547931.pdf | upright, 110 dpi | CJC-1295, 2 mg, PP-2512-005, 12/05/2025, 98.8 %, 3367.9 / 3367.6 | match |
| CBA-2582657.pdf | rotated 180°, 110 dpi | MOTS-c, 10 mg, PP-2607-027, 07/17/2026, 98.4 %, 2174.6 / 2175.0 | match |
| MAL-26-1791.pdf | rotated 90°, 110 dpi | GHK-Cu, 50 mg, Batch/Lot BLANK (empty rule line), 2026-05-22, 98.9 %, 403.9 / 404.1 | match |
| MAL-26-2486.pdf | upright, 110 dpi, VOID stamp | Selank, 5 mg, PP-2608-005, 2026-08-14, 99.1 %, 751.9 / 752.0; stamp "VOID — issued in error - do not use" | match |
| MAL-26-3363.pdf | upright, 72 dpi | Cagrilintide, 5 mg, PP-2607-030, 2026-07-31, 98.1 %, 4409.0 / 4409.6 | match |
| MAL-26-7499.pdf | upright, 110 dpi | Thymalfasin (Thymosin Alpha-1), 5 mg, PP-2512-022, 2025-12-19, 98.5 %, 3108.3 / 3108.1 | match |
| MAL-26-8104.pdf | upright, 72 dpi | AOD-9604, 5 mg, PP-2607-009, 2026-07-28, 99.3 %, 1815.1 / 1815.4 | match |
| NPT-RS-99391.pdf | upright, 110 dpi | Oxytocin 0,002 g PP-2608-013 25.08.2026 99,5 % 1007,2 / 1007,4; Semax 0,005 g PP-2510-011 14.10.2025 98,9 % 813,9 / 813,8 | match |

Result: 10/10 scans (11 result lines) confirmed, with no transcription differences. The text-layer PDFs were also checked for embedded images or stamps; none have any, and the only revision wording is in CBA-2528140 and CBA-2566510.

## 2. Automated checks (final run)

| # | Check | Result | Detail |
|---|---|---|---|
| 1 | Text-layer PDFs: independent re-parse vs coa_extracted.csv | PASS | 39 text-layer result lines re-parsed, 0 mismatches [] |
| 2 | coa_extracted.csv covers all 41 PDFs | PASS | 41 PDFs in coa/, 41 in extraction, 50 rows |
| 3 | reading_notes.md has one entry per PDF | PASS | missing: [] |
| 4 | Every extracted line appears in reading_notes.md under its PDF | PASS | 50 lines checked; missing 0 |
| 5 | woocommerce_import.csv has 30 rows, one per sheet SKU | PASS | 30 rows |
| 6 | status_reason uses exact rule strings; publish<->ok | PASS |  |
| 7 | Every import value re-derived from extraction + sheet + price list + rules | PASS | 0 errors [] |
| 8 | Every coa_pdf exists in coa/ | PASS |  |
| 9 | price_changes.csv lists exactly the changed prices | PASS | changed={'P11': ('179.00', '249.00'), 'P16': ('48.00', '52.00'), 'P25': ('39.00', '36.00')} |
| 10 | Library rows = published products, correct order and values | PASS | 21 rows; order ['P27', 'P11', 'P01', 'P16', 'P20', 'P29', 'P19', 'P13', 'P25', 'P02', 'P21', 'P06', 'P09', 'P22', 'P26', 'P17', 'P04', 'P14', 'P15', 'P30', 'P03'] |
| 11 | Library teaser at top matches import | PASS | 21 verified COAs · average purity 98.95 % (exact mean 98.9524) |
| 12 | Feed = library (order, values) + sku/coa_url | PASS |  |
| 13 | Feed teaser numbers match import | PASS |  |
| 14 | Retest schedule: every published product, dates/days/due_soon correct | PASS | errors [] |
| 15 | Retest schedule sorted by retest_due then SKU | PASS |  |
| 16 | Featured = top 3 purity excl. due soon, with correct values | PASS | [('P14', 'Epitalon', '99.6', '2026-04-03'), ('P27', 'Oxytocin', '99.5', '2026-08-25'), ('P01', 'BPC-157', '99.4', '2026-08-12')] |
| 17 | Scorecard re-computed from extraction | PASS | [] |
| 18 | Scorecard totals: PDFs 41, lines = extraction rows, used = products with a chosen COA | PASS | pdfs 41, lines 50/50, used 28 |
| 19 | Email: every draft in SKU order with correct reason and action | PASS | [('P05', 'purity below 98.0', 'retest or replace the batch'), ('P07', 'identity failed', 'repeat the mass-spec identity test'), ('P08', 'COA older than 12 months', 'send a COA tested within the last 12 months'), ('P10', 'conflicting COAs', 'confirm which report is correct'), ('P12', 'size conflict', 'confirm the size and add a price for it'), ('P18', 'no COA', 'send a COA'), ('P23', 'purity below  |
| 20 | Email totals: draft count and USD value | PASS | 9 drafts, 768.00 USD |
| 21 | Email lists every price change | PASS |  |
| 22 | Exceptions report names every draft, price change, multi/ignored-COA product | PASS | 26 SKUs required; missing [] |
| 23 | Exceptions report names every ignored / unmatched result line | PASS | 22 ignored or not-used lines |
| 24 | Every "from sheet" value is recorded in exceptions section 2 | PASS | from-sheet values: [('P04', 'batch'), ('P19', 'purity')] |
| 25 | Provenance: every import value appears in a PDF extraction, the sheet or the price list | PASS | [] |

## 3. Value-by-value comparison of woocommerce_import.csv

For each SKU: the source line chosen, then what the import holds. Check 7 above re-derives each value independently from coa_extracted.csv, products.csv, price_list.csv and the rules, and found 0 differences.

| SKU | Status / reason | Batch | Test date | Purity | Size | Price | Source |
|---|---|---|---|---|---|---|---|
| P01 | publish / ok | PP-2608-003 | 2026-08-12 | 99.4 | 5 | 49.00 | MAL-26-6305.pdf |
| P02 | publish / ok | PP-2607-021 | 2026-07-21 | 99.1 | 10 | 85.00 | NPT-RS-84830.pdf |
| P03 | publish / ok | PP-2509-007 | 2025-10-09 | 98.9 | 5 | 59.00 | CBA-2551750.pdf |
| P04 | publish / ok | PP-2605-008 | 2026-05-22 | 98.9 | 50 | 69.00 | MAL-26-1791 + sheet batch |
| P05 | draft / purity below 98.0 | PP-2608-016 | 2026-08-20 | 97.6 | 5 | 55.00 | MAL-26-2186.pdf |
| P06 | publish / ok | PP-2606-017 | 2026-06-30 | 99.2 | 2 | 45.00 | CBA-2512337.pdf |
| P07 | draft / identity failed | PP-2606-018 | 2026-07-02 | 99.0 | 2 | 65.00 | NPT-RS-84830.pdf |
| P08 | draft / COA older than 12 months | PP-2507-020 | 2025-08-20 | 98.7 | 5 | 52.00 | MAL-26-1950.pdf |
| P09 | publish / ok | PP-2606-014 | 2026-06-25 | 98.6 | 5 | 89.00 | CBA-2528140.pdf |
| P10 | draft / conflicting COAs | PP-2607-002 | — | — | — | 119.00 | MAL-26-1614 vs NPT-RS-83434 (conflict) |
| P11 | publish / ok | PP-2608-011 | 2026-08-19 | 99.0 | 15 | 249.00 | MAL-26-2408.pdf |
| P12 | draft / size conflict | PP-2608-019 | 2026-08-27 | 98.8 | 12 | 229.00 | NPT-RS-83434.pdf |
| P13 | publish / ok | PP-2607-009 | 2026-07-28 | 99.3 | 5 | 62.00 | MAL-26-8104.pdf |
| P14 | publish / ok | PP-2603-022 | 2026-04-03 | 99.6 | 10 | 44.00 | CBA-2509156.pdf |
| P15 | publish / ok | PP-2512-018 | 2025-12-04 | 98.7 | 5 | 48.00 | MAL-26-7955.pdf |
| P16 | publish / ok | PP-2608-002 | 2026-08-06 | 99.3 | 5 | 52.00 | NPT-RS-84830.pdf |
| P17 | publish / ok | PP-2606-030 | 2026-06-11 | 98.2 | 10 | 58.00 | CBA-2507747.pdf |
| P18 | draft / no COA | — | — | — | — | 46.00 | none |
| P19 | publish / ok | PP-2607-024 | 2026-07-30 | 98.8 | 5 | 42.00 | MAL-26-3028 + sheet purity |
| P20 | publish / ok | PP-2608-010 | 2026-08-02 | 98.6 | 5 | 57.00 | NPT-RS-50433.pdf |
| P21 | publish / ok | PP-2607-027 | 2026-07-17 | 98.4 | 10 | 95.00 | CBA-2582657.pdf |
| P22 | publish / ok | PP-2606-012 | 2026-06-19 | 99.0 | 5 | 78.00 | MAL-26-2013.pdf |
| P23 | draft / purity below 98.0 | PP-2608-007 | 2026-08-22 | 96.9 | 5 | 99.00 | NPT-RS-83434.pdf |
| P24 | draft / missing field | PP-2606-021 | — | 99.2 | 5 | 49.00 | MAL-26-1812 (date blank on COA and sheet) |
| P25 | publish / ok | PP-2607-012 | 2026-07-23 | 99.1 | 5 | 36.00 | CBA-2528977.pdf |
| P26 | publish / ok | PP-2606-025 | 2026-06-16 | 99.0 | 5 | 39.00 | MAL-26-3181.pdf |
| P27 | publish / ok | PP-2608-013 | 2026-08-25 | 99.5 | 2 | 35.00 | NPT-RS-99391.pdf |
| P28 | draft / COA older than 12 months | PP-2508-031 | 2025-09-12 | 99.4 | 10 | 54.00 | CBA-2554937.pdf |
| P29 | publish / ok | PP-2607-030 | 2026-07-31 | 98.1 | 5 | 139.00 | MAL-26-3363.pdf |
| P30 | publish / ok | PP-2510-016 | 2025-11-15 | 99.3 | 2 | 34.00 | CBA-2515439.pdf |

## 4. Mismatches found and what was changed

| # | Where | Mismatch | Change | Re-check |
|---|---|---|---|---|
| 1 | Verifier (check 1, first run) | The independent re-parse of the text PDFs reported 13 of 39 lines as different. Cause: my verification regex used `\s+`, which crossed line breaks. On Coastal PDFs "Purity" matched the "Part A: Purity" heading, and blank Meridian fields captured the next line. The deliverables were not wrong. | Regex restricted to same-line whitespace (`[ \t]`), anchored to line start for Coastal labels | Re-run: 39/39 lines identical, 0 mismatches |

No mismatch was found in the deliverables themselves. Draft counts (9), published count (21), mean purity (98.95 %, exact 98.9524), library/feed order, retest dates, featured choices, scorecard totals (41 PDFs, 50 lines, 28 used), the 3 price changes and the email total (768.00 USD) all agree across files. No upstream decision had to change, so no deliverable was rebuilt after the final run.

## 5. Judgement calls (checked against the rules, recorded for review)

- **P10 Semaglutide:** two reports for lot PP-2607-002, with no revision note, disagree on purity (99.2 vs 98.4). This triggers rule 4 "conflicting COAs". Per the rule, only coa_batch and coa_url are filled, so coa_pdf is blank too. Neither line counts as "used" in the scorecard.
- **P12 Retatrutide:** coa_size_mg = 12 (COA value, rule 6). The price stays at the sheet price of 229.00 because there is no 12 mg price row (rule 8). The size conflict holds the product.
- **P06 vs P07:** the Coastal "CJC-1295" COAs have theoretical mass 3367.9 Da, so they are the no-DAC form (P06). The DAC form is 3647.2 Da (NPT, P07).
- **P03 TB-500:** the NPT "Thymosin Beta-4 (full length)" line (4963.4 Da) is a different molecule from TB-500 (889.0 Da), so it matches no product.
- **retest_schedule.csv** covers the 21 published products, since those are the COAs live on the site and the source of due_soon for featuring.
- **Rule 9 date cutoff:** a test date on or after 2025-09-30 passes. P03 (2025-10-09) and P30 (2025-11-15) pass. P08 (2025-08-20) and P28 (2025-09-12) fail.

## 6. Final re-check

Final automated run: 25/25 checks PASS, 0 FAIL. Scan re-check: 10/10 confirmed. No unresolved mismatches.
