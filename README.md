# US Construction Spending Analysis (2002-2025)
> **[View Interactive Report](https://htmlpreview.github.io/?https://raw.githubusercontent.com/Tommy-Nguyen-Stonera/sql-us-construction-spending/main/report.html)** — Full analysis with findings, methodology, and insights


![SQL Server](https://img.shields.io/badge/SQL_Server-T--SQL-CC2927?style=for-the-badge&logo=microsoftsqlserver&logoColor=white)
![FRED Data](https://img.shields.io/badge/Source-FRED_%7C_US_Census-003DA5?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Complete-2ea44f?style=for-the-badge)
![Records](https://img.shields.io/badge/Records-288_Months-blue?style=for-the-badge)

> **A deep-dive into 24 years of US construction spending data, through the lens of someone who sells the materials that go into these buildings.**

---

## Why This Project Exists

Working in building materials sales for over five years, I have seen firsthand how construction spending cycles ripple through the entire supply chain. When residential construction booms, our stone and surface orders surge. When it crashes, we feel it months before the headline numbers catch up. I have always understood these patterns intuitively from the sales floor, but I wanted to put real numbers behind what I was experiencing.

So I pulled 24 years of monthly construction spending data from the US Census Bureau and Federal Reserve (FRED) and wrote the queries I wished I had access to when I was trying to forecast demand, plan inventory, or explain to a client why lead times were blowing out.

This is not a textbook exercise. Every question in this analysis came from a real situation I have encountered in the industry: Why did our residential orders collapse in 2008 while commercial held up for another 18 months? Why did COVID barely dent total spending but completely reshape our product mix? How long does a downturn actually last before volumes recover?

The answers are in the data. And some of them surprised me.

---

## The Thinking Flow

My analysis follows a deliberate sequence. Each question naturally led to the next:

**"What is the long-term trend?"** I started here because everyone talks about construction being a growth industry, but I wanted the actual compound growth rate. **The answer: 4.0% CAGR over 24 years, but wildly uneven.** Some years grew 15%, others fell 15%. That unevenness is what matters when you are planning inventory six months ahead.

**"Residential vs non-residential - which sector is driving growth?"** This is the question that matters most in building materials. Different products go to different sectors. **I discovered the residential share swung from 56% down to 29% and back to 49% within 15 years.** That is not a gradual shift. That is a complete market restructuring that happened twice.

**"How bad was the GFC really?"** I was in the early stages of my career during the recovery, but the older guys at work still talk about 2008-2011 like a war. **The data proved them right: total spending fell 37%, but residential specifically crashed 64%.** Two-thirds of residential construction spending evaporated. That context explains why the industry is still psychologically cautious about overbuilding.

**"What happened during COVID?"** This one genuinely surprised me. I expected a crash. **Total construction only dipped 2.8%.** Construction was deemed essential, and the residential boom that followed was one of the fastest sector accelerations in the dataset. Within two years, spending hit all-time records.

**"Are there seasonal patterns?"** In building materials, we plan around seasonality. **The data shows only a 4.2% spread between the weakest month (January) and strongest (December)** on seasonally adjusted figures. The seasonal signal is much weaker than I expected, which tells me our order seasonality comes more from project timing than macro spending patterns. This raises an interesting question: if macro construction spending is nearly flat across months, why do our building materials orders spike so sharply in Q2-Q3? The answer probably lies in regional weather patterns and builder scheduling rather than anything visible in national spending data — but I would need sub-national data to confirm that.

**"What does the momentum look like month-to-month?"** Rolling averages strip out the noise. **The 12-month rolling average reveals that the post-COVID construction boom was actually more sustained than the pre-GFC boom.** It lasted longer and reached higher absolute levels.

**"How long did the GFC recovery actually take?"** This is the question clients ask when they are worried about a downturn. **It took until June 2016 - nearly a full decade - for total construction spending to recover to pre-GFC peak levels.** Residential took even longer. That is a sobering number when someone asks "how bad could it get?"

**"How is the sector mix shifting now?"** The most recent data shows **non-residential has taken the lead again, driven by manufacturing and infrastructure spending.** The residential share has stabilised around 42-43% since 2023, down from the 49-51% peak during the COVID housing boom.

---

## Key Findings

### 1. Construction spending grew 158% from 2002 to 2024
Average monthly spending rose from $848M to $2.19B. The US construction industry effectively doubled and then some over this period, with a CAGR of 4.0% - but that smooth average masks extreme volatility.

### 2. The GFC was a genuine catastrophe - 37% total decline, 64% residential
Total construction spending peaked at $1.206B/month in 2006 and bottomed at $758M in 2011. But the residential sector was devastated: from $684M/month down to $244M/month. For every dollar of residential construction happening at the peak, only 36 cents was being spent at the trough.

I initially looked at the GFC decline using peak-to-trough on monthly figures, which showed a 37% drop. But monthly data is noisy — a single bad month can overstate the decline. When I recalculated using 12-month rolling averages, the decline was smoother but the trough was nearly identical. That told me the GFC decline was not a statistical artefact of volatile monthly data — it was a sustained, multi-year contraction.

### 3. Recovery took nearly a decade
Total spending did not return to pre-GFC levels until June 2016 - nearly 10 years after the peak. This is the number I cite when clients ask about downside risk. Economic recoveries in construction are measured in years, not quarters.

### 4. The residential/non-residential balance completely inverted during the GFC
Residential went from 56.4% of total spending in 2005 to just 28.7% in 2009. Non-residential actually peaked in 2008 because commercial projects already in the pipeline kept spending flowing even as residential collapsed. This 18-month lag between sectors is critical for supply chain planning.

### 5. COVID barely registered as a dip - then triggered a historic boom
Total construction only fell 2.8% during the worst of COVID (March-June 2020). By late 2021, spending was up 29% from pre-COVID levels. Construction was deemed essential and the combination of low interest rates, remote work demand, and stimulus spending created the fastest growth period in the dataset.

### 6. 2022 was the biggest growth year on record: +14.9%
Even bigger than the pre-GFC boom years of 2004 (+11.1%) and 2005 (+12.7%). The post-COVID construction surge was historically unprecedented in both speed and magnitude.

### 7. Non-residential spending hit $1.27B/month in December 2023 - an all-time high
Driven by the CHIPS Act, IRA manufacturing incentives, and infrastructure investment. This is a structural shift, not just a cycle. The manufacturing construction boom is reshaping where spending goes.

### 8. Seasonal variation is surprisingly weak at the macro level
On seasonally adjusted data, the spread between the strongest and weakest months is only about 4%. December averages 2.0% above the annual mean while January sits 2.2% below. This tells me that order-level seasonality in building materials is driven more by regional weather and project timing than by national spending patterns.

### 9. The worst single-month YoY decline was -17.5% in October 2009
The worst monthly momentum reading in the dataset came well after the GFC officially ended (June 2009). Construction spending is a lagging indicator, and the pain continued long after the recession was technically over.

### 10. 2025 shows the first annual decline since 2011
Early 2025 data shows spending tracking about 1% below 2024. After years of growth, the market may be entering a plateau. For building materials, this means shifting from "how do we keep up with demand" to "how do we maintain margins in a flat market."

---

## What Surprised Me

**The COVID non-event.** I genuinely expected COVID to show up as a significant construction downturn. A 2.8% dip is barely visible in the data. The fact that construction was classified as essential work meant the sector never really shut down, and the demand that followed was explosive.

**The 18-month lag between residential and non-residential.** During the GFC, residential started collapsing in 2006 while non-residential did not peak until 2008. This lag is something I have observed anecdotally in building materials - commercial project pipelines have much longer lead times - but seeing it so clearly in the data was striking. If you sell to both sectors, the residential market is your early warning system.

**How long recovery actually takes.** A decade to get back to pre-GFC spending levels. That is not what you hear in optimistic industry forecasts. It fundamentally shapes how I think about risk management and cash reserves in this industry.

**The structural shift toward non-residential.** I expected the residential share to recover to pre-GFC levels, but it never did. Even during the COVID housing boom, residential only briefly touched 51% before falling back to 42%. The US is building more factories, data centres, and infrastructure relative to housing than it was 20 years ago.

---

## Dataset Overview

| Attribute | Detail |
|---|---|
| **Source** | US Census Bureau / Federal Reserve Economic Data (FRED) |
| **Metric** | Value of Construction Put in Place (millions USD, seasonally adjusted annual rate) |
| **Period** | January 2002 - December 2025 |
| **Frequency** | Monthly |
| **Records** | 288 observations per series |
| **Series** | Total, Residential, Non-Residential construction spending |

The data represents the estimated value of construction work done during each month, including new construction, additions, alterations, and major replacements. Values are seasonally adjusted and expressed at annual rates in millions of dollars.

---

## SQL Techniques Used

| Technique | Queries | Purpose |
|---|---|---|
| **CTEs (Common Table Expressions)** | Q1, Q3, Q5, Q6, Q7 | Multi-step calculations, readability |
| **Window Functions - LAG()** | Q1, Q6, Q7 | Year-over-year and period comparisons |
| **Window Functions - AVG() OVER()** | Q5 | Rolling 12-month averages |
| **Window Functions - MAX() OVER()** | Q7 | Running peak calculations |
| **PIVOT** | Q4 | Monthly-to-columnar seasonal view |
| **CASE Expressions** | Q3 | Economic period classification |
| **JOINs** | Q2, Q5, Q8 | Multi-series analysis |
| **DATEPART / Date Functions** | Q4, Q8 | Temporal grouping |
| **Aggregate Functions** | All | SUM, AVG, MIN, MAX, COUNT |
| **NULL Handling** | Q1, Q2, Q4 | NULLIF, ISNULL for safe division |

---

## Files

| File | Description |
|---|---|
| `queries/us_construction_spending_analysis.sql` | Full T-SQL analysis - 8 annotated query blocks |
| `report.html` | Interactive HTML report with findings and insights |
| `data/total_construction.csv` | Total construction spending (FRED: TTLCONS) |
| `data/residential_construction.csv` | Residential construction spending (FRED: TLRESCONS) |
| `data/nonresidential_construction.csv` | Non-residential construction spending (FRED: TLNRESCONS) |
| `README.md` | This file - project overview, findings, methodology |

---

## How to Run

1. Install [SQL Server Express](https://www.microsoft.com/en-us/sql-server/sql-server-downloads) (free)
2. Import the three CSV files from `data/` as tables (`TotalSpending`, `ResidentialSpending`, `NonResidentialSpending`)
3. Open `queries/us_construction_spending_analysis.sql` in SSMS
4. Run each query block sequentially - each is self-contained with its own CTE chain

---

## A Note on AI Tools

I used AI coding assistants as a sounding board when I hit T-SQL syntax issues or needed to sanity-check my approach to window function framing. The analysis questions, business context, and all interpretations are my own work, drawn from my experience in the building materials industry.

---

**Tommy Nguyen** | [GitHub](https://github.com/Tommy-Nguyen-Stonera) | [Portfolio](https://tommy-nguyen-stonera.vercel.app)
