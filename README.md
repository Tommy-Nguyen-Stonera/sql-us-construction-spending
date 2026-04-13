# US Construction Spending Analysis (2002-2025)

[View Interactive Report](https://htmlpreview.github.io/?https://raw.githubusercontent.com/Tommy-Nguyen-Stonera/sql-us-construction-spending/main/report.html)

## Overview

This project analyses 24 years of monthly US construction spending data to understand long-term sector trends, crisis impacts, and where the market sits today. It covers the pre-GFC boom, the crash, a decade-long recovery, the COVID shock, and the post-2020 acceleration.

## Dataset

- Source: US Census Bureau / FRED
- Record count: 288 monthly observations
- Time period: January 2002 to December 2025
- Key tables:
  - TotalSpending, ResidentialSpending, NonResidentialSpending (all joined on Date)
  - Values reported in millions of dollars (seasonally adjusted annual rate)

## Research Questions

1. What is the long-term nominal growth rate of US construction spending from 2002 to 2025?
2. Which sector drives more growth overall: residential or non-residential?
3. How did the GFC and COVID compare in severity and speed of recovery?
4. Are there seasonal patterns at a macro level across the full dataset?
5. Is spending currently accelerating or decelerating relative to recent years?
6. How deep was the GFC drawdown, and how long did full recovery take?
7. How is the residential vs non-residential balance shifting on a quarterly basis?

## Data Model

Three flat CSV tables, each with monthly date and a spending value column, joined on Date in SQL Server. No dimensional tables or complex keys. All analysis runs from these three joined columns.

## What Was Analysed

- Long-term nominal growth from 2002 to 2025 with CAGR calculation
- Residential vs non-residential sector growth comparison
- GFC and COVID impact: drawdown depth, duration, and recovery timeline
- Monthly seasonal index across all 24 years to test for patterns
- Year-over-year growth rate trend to assess current acceleration or deceleration
- Residential share of total spending tracked quarterly over the full period

## Key Insights

1. Total spending grew 158%, from $848M to $2.19B monthly, at a 4.0% CAGR over 24 years.
2. The GFC was devastating: total spending fell 37%, residential fell 64%. Recovery took nearly a full decade from the 2006 peak.
3. COVID barely registered as a pullback (down 2.8%), then triggered the fastest growth in the dataset. 2022 was the biggest single growth year on record at 14.9%.
4. Residential share swung from 56% before the GFC crash down to 29% at the trough, and has since recovered to 49%, showing the sector has structurally rebuilt.
5. Seasonal variation at the macro level is surprisingly weak, with only a 4% spread across months, meaning demand signals are structural rather than seasonal.
6. Non-residential spending has been more stable across both crises, which means it is a relatively more predictable revenue base for suppliers.

## Recommendations

1. Size residential exposure carefully. It crashed 64% in the GFC and took a decade to recover. For suppliers reliant on residential, having a non-residential hedge reduces cycle risk significantly.
2. Monitor year-over-year growth rate as a leading indicator. The 2022 peak at 14.9% was unlikely to sustain, and deceleration since then signals a normalisation worth pricing into forward plans.
3. Do not over-rotate on seasonal demand planning at a macro level. The 4% seasonal spread means inventory and staffing decisions should be driven by structural trends, not month-to-month patterns.
4. Target recovery periods strategically. Both the GFC and COVID showed that the steepest spending ramp happens in the 12 to 24 months after the bottom, which is the highest-ROI window for expanding market share.

## Tools

SQL Server, T-SQL, FRED / US Census data

## Files

- `queries/us_construction_spending_analysis.sql` - 8 query blocks
- `report.html` - Interactive report
- `data/` - total, residential, nonresidential construction CSVs
