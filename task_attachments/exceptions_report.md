# Exceptions report

Reference date 2026-09-30. Rule numbers refer to rules.md (v3).

## 1. Products not published (draft)

| SKU | Product | Issue | Rule | Action |
|---|---|---|---|---|
| P05 | Ipamorelin | **purity below 98.0** — Newest COA MAL-26-2186 (PP-2608-016, 2026-08-20) shows purity 97.6 %. The older MAL-26-9779 (PP-2601-010, 98.4 %) is not used. | 9 | Draft; COA values kept; client asked to retest or replace the batch |
| P07 | CJC-1295 (with DAC) | **identity failed** — NPT-RS-84830 CJC-1295 DAC PP-2606-018: observed 3651.0 Da vs theoretical 3647.2 Da, a difference of 3.8 Da (> 1.0). | 9 | Draft; client asked to repeat the mass-spec identity test |
| P08 | Sermorelin | **COA older than 12 months** — Only COA MAL-26-1950 is lot PP-2507-020, tested 2025-08-20, which is before 2025-09-30. The sheet lists PP-2602-006 / 2026-02-10, but no COA supports that lot. | 9 | Draft; COA values used over the sheet (rule 6); client asked for a COA tested within 12 months |
| P10 | Semaglutide | **conflicting COAs** — MAL-26-1614 (2026-07-15, 99.2 %, obs 4113.9) and NPT-RS-83434 (2026-07-18, 98.4 %, obs 4114.0) are both lot PP-2607-002. Neither is marked as a revision and they disagree on purity. | 4, 9 | Draft; only coa_batch and coa_url filled; other coa_* blank; client asked to confirm which report is correct |
| P12 | Retatrutide | **size conflict** — NPT-RS-83434 declares 0,012 g = 12 mg; the sheet has 10 mg. price_list.csv has no Retatrutide 12 mg row (only 10 and 20). | 8, 9 | Draft; sheet price 229.00 kept; coa_size_mg shows the COA value 12; client asked to confirm the size and add a price |
| P18 | Melanotan II | **no COA** — No COA in coa/ matches Melanotan II. | 9, 10 | Draft; all coa_* blank; sheet price 46.00 kept (matches price list) |
| P23 | LL-37 | **purity below 98.0** — NPT-RS-83434 LL-37 PP-2608-007 purity 96.9 %. | 9 | Draft; client asked to retest or replace the batch |
| P24 | Hexarelin | **missing field** — MAL-26-1812 leaves the test date blank, and the sheet Test_Date_Listed is also blank. | 7, 9 | Draft; coa_test_date blank; client asked for a COA showing the missing test date |
| P28 | KPV | **COA older than 12 months** — Only COA CBA-2554937 is lot PP-2508-031, tested 09/12/2025 = 2025-09-12, which is before 2025-09-30. | 9 | Draft; client asked for a COA tested within 12 months |

## 2. Values taken from the sheet ("from sheet", rule 7)

| SKU | Product | Field | Value used | Reason |
|---|---|---|---|---|
| P04 | GHK-Cu | batch | PP-2605-008 | field blank on chosen COA MAL-26-1791.pdf; sheet has a value. Older COAs not consulted (rule 7). |
| P19 | DSIP | purity | 98.8 | field blank on chosen COA MAL-26-3028.pdf; sheet has a value. Older COAs not consulted (rule 7). |

Note: P24 Hexarelin test date is blank on both the COA and the sheet, so it is a missing field (see section 1).

## 3. Sheet and chosen COA disagree (COA wins, rule 6)

| SKU | Product | Field | Sheet | COA (used) | Source PDF |
|---|---|---|---|---|---|
| P01 | BPC-157 | batch | PP-2607-004 | PP-2608-003 | MAL-26-6305.pdf |
| P01 | BPC-157 | test date | 2026-07-20 | 2026-08-12 | MAL-26-6305.pdf |
| P05 | Ipamorelin | batch | PP-2601-010 | PP-2608-016 | MAL-26-2186.pdf |
| P05 | Ipamorelin | test date | 2026-01-14 | 2026-08-20 | MAL-26-2186.pdf |
| P05 | Ipamorelin | purity | 98.4 | 97.6 | MAL-26-2186.pdf |
| P08 | Sermorelin | batch | PP-2602-006 | PP-2507-020 | MAL-26-1950.pdf |
| P08 | Sermorelin | test date | 2026-02-10 | 2025-08-20 | MAL-26-1950.pdf |
| P11 | Tirzepatide | size (mg) | 10 | 15 | MAL-26-2408.pdf |
| P12 | Retatrutide | size (mg) | 10 | 12 | NPT-RS-83434.pdf |
| P15 | Selank | batch | PP-2608-005 | PP-2512-018 | MAL-26-7955.pdf |
| P15 | Selank | test date | 2026-08-14 | 2025-12-04 | MAL-26-7955.pdf |
| P15 | Selank | purity | 99.1 | 98.7 | MAL-26-7955.pdf |
| P20 | Kisspeptin-10 | batch | PP-2602-003 | PP-2608-010 | NPT-RS-50433.pdf |
| P20 | Kisspeptin-10 | test date | 2026-02-08 | 2026-08-02 | NPT-RS-50433.pdf |
| P20 | Kisspeptin-10 | purity | 99.1 | 98.6 | NPT-RS-50433.pdf |
| P26 | GHRP-6 | batch | PP-2601-019 | PP-2606-025 | MAL-26-3181.pdf |
| P26 | GHRP-6 | test date | 2026-01-21 | 2026-06-16 | MAL-26-3181.pdf |

P10 Semaglutide: the sheet (PP-2607-002, 2026-07-15, 99.2 %) agrees with MAL-26-1614 but not with NPT-RS-83434 (2026-07-18, 98.4 %). Because the two reports conflict, the product is held (section 1).

## 4. Price changes (rule 8)

| SKU | Product | Old | New | Reason |
|---|---|---|---|---|
| P11 | Tirzepatide | 179.00 | 249.00 | COA MAL-26-2408.pdf declares 15 mg vs sheet 10 mg; price list Tirzepatide 15 mg = 249.00 (rule 8 size corrected) |
| P16 | Semax | 48.00 | 52.00 | sheet price 48.00 differs from price list 52.00 for Semax 5 mg (rule 8) |
| P25 | GHRP-2 | 39.00 | 36.00 | sheet price 39.00 differs from price list 36.00 for GHRP-2 5 mg (rule 8) |

P12 Retatrutide is not a price change: there is no 12 mg price row, so the sheet price is kept and the product is held for a size conflict.

## 5. Products with more than one COA, or with an ignored COA

| SKU | Product | COA results | Used | Ignored / not used (why) | Rule |
|---|---|---|---|---|---|
| P01 | BPC-157 | 2 | MAL-26-6305.pdf (PP-2608-003, 2026-08-12) | MAL-26-3471.pdf PP-2510-012 2025-11-02 — ignored: older test date than chosen MAL-26-6305.pdf | 5 |
| P02 | BPC-157 | 2 | NPT-RS-84830.pdf (PP-2607-021, 2026-07-21) | NPT-RS-33688.pdf PP-2602-008 2026-02-17 — ignored: older test date than chosen NPT-RS-84830.pdf | 5 |
| P03 | TB-500 | 2 | CBA-2551750.pdf (PP-2509-007, 2025-10-09) | CBA-2585319.pdf PP-2502-004 2025-03-04 — ignored: older test date than chosen CBA-2551750.pdf | 5 |
| P05 | Ipamorelin | 2 | MAL-26-2186.pdf (PP-2608-016, 2026-08-20) | MAL-26-9779.pdf PP-2601-010 2026-01-14 — ignored: older test date than chosen MAL-26-2186.pdf | 5 |
| P06 | CJC-1295 (no DAC) | 2 | CBA-2512337.pdf (PP-2606-017, 2026-06-30) | CBA-2547931.pdf PP-2512-005 2025-12-05 — ignored: older test date than chosen CBA-2512337.pdf | 5 |
| P09 | Tesamorelin | 2 | CBA-2528140.pdf (PP-2606-014, 2026-06-25) | CBA-2566510.pdf PP-2606-014 2026-06-25 — ignored: superseded by revision CBA-2528140.pdf | 4 |
| P10 | Semaglutide | 2 | none | MAL-26-1614.pdf PP-2607-002 2026-07-15 — not used: conflicting reports for same batch (product held); NPT-RS-83434.pdf PP-2607-002 2026-07-18 — not used: conflicting reports for same batch (product held) | 4 |
| P13 | AOD-9604 | 2 | MAL-26-8104.pdf (PP-2607-009, 2026-07-28) | MAL-26-7851.pdf PP-2603-014 2026-03-11 — ignored: older test date than chosen MAL-26-8104.pdf | 5 |
| P14 | Epitalon | 2 | CBA-2509156.pdf (PP-2603-022, 2026-04-03) | CBA-2531544.pdf PP-2510-009 2025-10-28 — ignored: older test date than chosen CBA-2509156.pdf | 5 |
| P15 | Selank | 2 | MAL-26-7955.pdf (PP-2512-018, 2025-12-04) | MAL-26-2486.pdf PP-2608-005 2026-08-14 — ignored: report stamped VOID | 3 |
| P16 | Semax | 2 | NPT-RS-84830.pdf (PP-2608-002, 2026-08-06) | NPT-RS-99391.pdf PP-2510-011 2025-10-14 — ignored: older test date than chosen NPT-RS-84830.pdf | 5 |
| P17 | PT-141 | 2 | CBA-2507747.pdf (PP-2606-030, 2026-06-11) | CBA-2574115.pdf PP-2601-027 2026-01-09 — ignored: older test date than chosen CBA-2507747.pdf | 5 |
| P19 | DSIP | 2 | MAL-26-3028.pdf (PP-2607-024, 2026-07-30) | MAL-26-4657.pdf PP-2603-002 2026-03-05 — ignored: older test date than chosen MAL-26-3028.pdf | 5 |
| P20 | Kisspeptin-10 | 3 | NPT-RS-50433.pdf (PP-2608-010, 2026-08-02) | NPT-RS-50433.pdf PP-2602-003 2026-02-08 — ignored: older test date than chosen NPT-RS-50433.pdf; NPT-RS-50433.pdf PP-2605-001 2026-05-12 — ignored: older test date than chosen NPT-RS-50433.pdf | 5 |
| P22 | Thymosin Alpha-1 | 2 | MAL-26-2013.pdf (PP-2606-012, 2026-06-19) | MAL-26-7499.pdf PP-2512-022 2025-12-19 — ignored: older test date than chosen MAL-26-2013.pdf | 5 |
| P25 | GHRP-2 | 2 | CBA-2528977.pdf (PP-2607-012, 2026-07-23) | CBA-2506105.pdf PP-2511-003 2025-11-06 — ignored: older test date than chosen CBA-2528977.pdf | 5 |
| P26 | GHRP-6 | 2 | MAL-26-3181.pdf (PP-2606-025, 2026-06-16) | MAL-26-5744.pdf PP-2601-019 2026-01-21 — ignored: older test date than chosen MAL-26-3181.pdf | 5 |
| P29 | Cagrilintide | 2 | MAL-26-3363.pdf (PP-2607-030, 2026-07-31) | MAL-26-9858.pdf PP-2603-017 2026-03-26 — ignored: older test date than chosen MAL-26-3363.pdf | 5 |

## 6. COA results that match no product (rule 2)

| File | Product as printed | Lot | Why no match | Action |
|---|---|---|---|---|
| NPT-RS-33688.pdf | Thymosin Beta-4 (full length) (5 mg, 4963.4 Da) | PP-2606-040 | full-length Thymosin Beta-4 (4963.4 Da) is not TB-500 (fragment, 889.0 Da); no product matches | ignored |
| NPT-RS-50433.pdf | Pinealon (10 mg, 359.4 Da) | PP-2607-033 | Pinealon is not in products.csv | ignored |

## 7. Ignored reports

- MAL-26-2486.pdf (Selank PP-2608-005, 2026-08-14, 99.1 %) is stamped **VOID — issued in error, do not use**. It is ignored completely (rule 3). P15 Selank uses MAL-26-7955 (PP-2512-018, 2025-12-04) instead.
- CBA-2566510.pdf (Tesamorelin PP-2606-014, Revision 1, 97.8 %) is superseded by CBA-2528140.pdf (Revision 2, 98.6 %, peak integration error corrected). Revision 2 is used (rule 4).

## 8. Interpretation notes

- CBA prints both CJC-1295 COAs without "DAC". The theoretical mass of 3367.9 Da (vs 3647.2 Da for the DAC form on NPT-RS-84830) identifies them as CJC-1295 (no DAC), so both were matched to P06.
- NPT "Thymosin Beta-4 (full length)" (4963.4 Da) is not TB-500, which is the Thymosin Beta-4 fragment at 889.0 Da on the CBA COAs.
- BPC-157 lines were split by declared amount: 5 mg → P01, 10 mg (0,010 g) → P02.
- P12 coa_size_mg shows the COA amount (12 mg, rule 6) while the price stays the sheet price, as rule 8 requires for a size conflict.
- P10 has no single chosen COA, so neither Semaglutide line counts as "used" in the supplier scorecard.
