# Equipment normalization issues

These are fictional equipment records, not records of people. The original equipment.json is preserved.

## Row counts

- Total input rows: 10
- Valid (retained, nonempty) rows: 9
- Removed rows: 1 — input position 6, an empty object with no source_row.
- Only rows whose fields are all null, empty, or whitespace are eligible for removal. Zero is not empty. Retained rows can still have flagged values.

## Normalization

Leading/trailing whitespace was trimmed from text fields other than qty. Each retained source_row was preserved. Status aliases available, 可借, and 可出借 were mapped to available; borrowed and 借出 were mapped to borrowed. No quantity was changed or guessed.

## Quantity issues

| source_row | Original qty | Issue | Action |
|---|---|---|---|
| 7 | "" (empty string) | Missing quantity | Preserved exactly; clarification needed |
| 8 | -1 | Negative quantity | Preserved exactly; clarification needed |

The other quantities are numeric zero or positive integers. Row 10's qty of 0 is accepted. No uncertain value was replaced with zero.

## Unknown statuses

| source_row | Original status | Normalized status |
|---|---|---|
| 9 | 待盤點 | unknown |

The intended status for row 9 remains unresolved.

## Shared item IDs

All rows sharing an item_id were retained. Comparisons below use normalized fields; source_row is a traceability field and remains distinct.

| item_id | source rows | Matching fields | Conflicting fields |
|---|---|---|---|
| EQ01 | 1, 4 | item_id: EQ01; name: Marker / 白板筆; qty: 4; status: available | None among item fields; source_row differs (1 vs 4) |
| EQ02 | 2, 5 | item_id: EQ02; name: Extension cord / 延長線; status: borrowed | qty: row 2 = 2, row 5 = 3; source_row differs (2 vs 5) |

For EQ01, source row 1 originally had surrounding whitespace in item_id/name and status 可借; row 4 had status available. For EQ02, original statuses were borrowed (row 2) and 借出 (row 5). Their normalized statuses match.

Matching names do not prove that records describe the same physical items. Neither shared-ID group was merged or removed. Confirm whether EQ01's repeated records are intentional and resolve EQ02's quantity conflict before interpreting totals.

## Checks performed

- Parsed normalized.json as an array with nine objects.
- Confirmed retained source rows are 1, 2, 3, 4, 5, 7, 8, 9, and 10.
- Compared every retained qty value and type with its source; all are unchanged.
- Checked trimming and expected status mappings for all retained rows.
- Confirmed both shared-ID groups retain all source rows.
- Confirmed input totals equal retained plus removed rows (10 = 9 + 1).
- Compared the original file's SHA-256 before and after output creation; unchanged.

## Still unresolved

Quantities for rows 7 and 8, the intended status for row 9, and the meaning of shared IDs require clarification. No real-world inventory accuracy or approval was inferred.