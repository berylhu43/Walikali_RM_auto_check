# Walikali RM Auto Check

Automated data verification scripts for cross-checking endline survey data across three sources: coordinator records, Chicago team records, and SurveyCTO submissions.

## Files

### `RM_member_check.Rmd`
Verifies endline survey data for **evaded members**. It merges records from the coordinator, Chicago team, and SurveyCTO, standardizes date formats and status spellings, and produces a consolidated tracking table saved to `RM13.xlsx` (sheet: `member`). It also identifies which members are pending survey completion by team.

### `RM_villager_check.Rmd`
Verifies endline survey data for **villagers**. It follows the same pipeline — merging coordinator, Chicago, and SurveyCTO data — and outputs results to `RM13.xlsx` (sheet: `villager`). It additionally flags incomplete household survey pairs (missing `ma1` or `mp1` entries) and villagers not yet surveyed by team.

## Dependencies

```r
library(readxl)
library(dplyr)
library(writexl)
library(openxlsx)
```

## Input Files

The scripts read from local Dropbox paths. Key inputs include:
- Coordinator Excel lists (evaded members and villagers)
- Chicago team verification sheets
- SurveyCTO CSV exports (Part I and Part II)

## Output

Results are written to `RM11.xlsx` `RM12.xlsx`  `RM13.xlsx` with separate sheets for `member` and `villager` data.
