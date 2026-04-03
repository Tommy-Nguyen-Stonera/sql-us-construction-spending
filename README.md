# US Construction Spending Analysis (2002-2025)

[View Interactive Report](https://htmlpreview.github.io/?https://raw.githubusercontent.com/Tommy-Nguyen-Stonera/sql-us-construction-spending/main/report.html)

24 years of monthly US construction spending data from Census Bureau/FRED. 288 months of data covering the pre-GFC boom, the crash, recovery, COVID, and the current market.

## Key Findings

- Total spending grew 158% ($848M to $2.19B monthly) with 4.0% CAGR
- GFC was devastating: total -37%, residential -64%
- Recovery took nearly a full decade (2006 peak to 2016 recovery)
- COVID barely registered (-2.8% dip), then triggered the fastest growth in the dataset
- 2022 was the biggest growth year on record at +14.9%
- Residential share swung from 56% down to 29% and back to 49% within 15 years
- Seasonal variation is surprisingly weak at the macro level (only 4% spread)

## Tools

SQL Server, T-SQL, FRED/US Census data

## Files

- `queries/us_construction_spending_analysis.sql` - 8 query blocks
- `report.html` - Interactive report
- `data/` - total, residential, nonresidential construction CSVs
