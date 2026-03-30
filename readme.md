# Net Revenue Management in Excel — Case Study

A full business case built in Excel around HealthMax, a fictitious FMCG supplier operating in the shampoo market. The work covers everything from market share analysis and portfolio profitability to identifying growth opportunities, evaluating promotions, and building a 2024 revenue forecast with a waterfall breakdown.

This one goes well beyond pivot tables. It's a structured NRM workflow — the kind used by category managers and commercial analysts at real FMCG companies like Unilever, P&G, or Nestlé.

Built as part of the [Net Revenue Management in Excel](https://www.datacamp.com/courses/case-study-net-revenue-management-in-excel) case study on DataCamp.

---

## Context

HealthMax competes in the shampoo category with two brands:
- **Starbust** — three product lines (Ultra Soft, Extra Shiny, Strong Hair) in 100ml, 150ml, and 200ml
- **Shinez** — one product line (Repair) in 100ml, 125ml, 150ml, and 200ml

The external market includes 25+ competing brands across suppliers. The full analysis spans 2018–2024, using both internal sales data and external market data by brand, region, subcategory, and month.

---

## Workbook Structure

| Sheet | Purpose |
|---|---|
| `External Data` | Raw market data: units/values by brand, region, subcategory, month (2018–2023) |
| `internal sales data` | HealthMax portfolio: pricing, COGS, volumes, margins, contribution |
| `Market Share` | PivotTable — brand market share by year (2018–2023) |
| `Sales until 2022` | Category total value sales: 2018–2022 |
| `MAT Value Total Category` | Moving Annual Total for the full category |
| `HealthMax Growth` | YoY growth by brand (Shinez vs Starbust) |
| `Profitability Matrix` | Net sales contribution vs. gross margin per SKU |
| `New Category Opportunity` | Subcategory growth rates + organic shampoo unit forecast |
| `Organic Shampoo Launch` | New product P&L: HerbEssentials and Herbashine |
| `50ml Shampoo 2024` | Pack size opportunity — proposed 50ml SKU financials |
| `Promotion Analysis` | ROI calculation for three 2022 Shinez promotions |
| `Promotion Graph` | Monthly sales data underpinning the promotion baseline |
| `Forecast 2024` | FORECAST.ETS model with confidence bounds |
| `Waterfall` | Net sales bridge: 2023 estimate → 2024 projection |
| `Brands per Supplier` | Supplier-to-brand mapping reference |

---

## Analysis Breakdown

### 1. Market Share (2018–2023)

HealthMax's two main competitors and their share trajectory:

| Brand | 2018 | 2022 | 2023 |
|---|---|---|---|
| Harmonix | 19.1% | 26.1% | **24.2%** |
| **Starbust** (HealthMax) | **28.9%** | 22.1% | 20.8% |
| Vitalize | 16.8% | 13.6% | 12.3% |
| **Shinez** (HealthMax) | 10.1% | 9.4% | **10.1%** |
| Diamond Shine | 6.3% | 8.6% | 13.0% |
| Lavender Bloom | 0.7% | 4.5% | 6.2% |

Starbust has lost ~8 percentage points of market share since 2018. Diamond Shine and Lavender Bloom are both gaining fast. Shinez has held relatively stable.

### 2. HealthMax Portfolio — Internal Sales 2022

Total Net Sales 2022: **$20,480,715**

| SKU | Volume | Net Price | Net Sales | Gross Margin | Contribution |
|---|---|---|---|---|---|
| Shinez Repair 100ml | 1,089,532 | $3.50 | $3,813,362 | 67.1% | **18.6%** |
| Starbust Ultra Soft 100ml | 1,156,348 | $3.10 | $3,584,679 | 70.97% | 17.5% |
| Starbust Ultra Soft 150ml | 693,809 | $3.50 | $2,428,332 | 65.7% | 11.9% |
| Starbust Extra Shiny 100ml | 693,809 | $2.90 | $2,012,046 | 67.2% | 9.8% |
| Shinez Repair 125ml | 466,942 | $4.25 | $1,984,504 | 69.4% | 9.7% |
| Shinez Repair 150ml | 389,118 | $5.10 | $1,984,502 | 70.6% | 9.7% |
| Starbust Ultra Soft 200ml | 289,087 | $5.00 | $1,445,435 | 70.0% | 7.1% |
| Shinez Repair 200ml | 233,471 | $6.00 | $1,400,826 | 71.7% | 6.8% |
| Starbust Strong Hair 100ml | 346,904 | $2.80 | $971,331 | 64.3% | 4.7% |
| Starbust Strong Hair 150ml | 231,270 | $3.70 | $855,699 | 64.9% | 4.2% |

Shinez Repair 200ml has the **highest gross margin (71.7%)** but the lowest volume among Shinez SKUs — a pricing architecture observation worth actioning.

### 3. HealthMax YoY Growth (Shinez vs Starbust)

| Year | Shinez | Starbust |
|---|---|---|
| 2019 | -1.9% | -6.0% |
| 2020 | +7.7% | +1.8% |
| 2021 | +0.9% | +1.2% |
| 2022 | +6.7% | ~0.0% |

Shinez is growing. Starbust has been effectively flat since 2020. The portfolio balance is shifting.

### 4. New Category Opportunity — Subcategory Growth (2018–2022)

| Subcategory | Growth Rate |
|---|---|
| **Organic** | **+275.8%** |
| Moisturizing | +19.1% |
| Anti-dandruff | +11.5% |
| Volumizing | -11.0% |
| Color-safe | -35.2% |

Organic is the standout. The subcategory nearly tripled in four years. Estimated organic shampoo units sold in the category in 2024: **~1,020,899 units**.

New product launch modeled — two organic SKUs:
- **HerbEssentials** — estimated 10% unit market share, net price $3.50, COGS $1.35
- **Herbashine** — estimated 12% unit market share, net price $2.75, COGS $0.90

### 5. Pack Size Opportunity — 50ml SKU

A 50ml entry-tier SKU for Starbust was modeled at retail price $7.50 and net price $2.30 — lower gross margin than existing lines but targeting a volume/accessibility play. Estimated incremental volume: ~115,635 units based on a 10% uplift assumption on the 100ml Starbust Ultra Soft base.

### 6. Promotion ROI Analysis — Shinez 2022

Three promotions run on Shinez across 2022, evaluated against a baseline of **$840,836** in average monthly sales:

| Promotion | Mechanism | Month | Sales | Uplift | Cost | ROI |
|---|---|---|---|---|---|---|
| 1 | Buy 2, get 1 free | Apr | $1,445,626 | $604,790 | $620,000 | **-2.5%** |
| 2 | Buy 2, get 20% off | Aug | $1,198,708 | $357,872 | $320,000 | **+11.8%** |
| 3 | 2nd at 50% off | Nov | $1,413,646 | $572,810 | $540,000 | **+6.1%** |

Promotion 1 ("Buy 2, get 1 free") generated the highest absolute uplift but was the only loss-making promotion at -2.5% ROI — the cost of giving away a free unit exceeded the revenue gained. Promotion 2 was the most efficient.

### 7. Forecast 2024 — FORECAST.ETS

Total category market values (historical + forecast):

| Year | Market Value |
|---|---|
| 2018 | $30,685,269 |
| 2019 | $29,261,549 |
| 2020 | $30,370,933 |
| 2021 | $30,710,796 |
| 2022 | $31,442,892 |
| **2023 (forecast)** | **$31,635,316** |
| **2024 (forecast)** | **$31,946,453** |

HealthMax's 2022 market ratio (net sales / market value): **65.1%**

Applying that ratio to the 2024 forecast: **estimated HealthMax net sales 2024 ≈ $20,809,000**

### 8. Revenue Waterfall — 2023 to 2024

| Component | Value |
|---|---|
| Estimated Net Sales 2023 | $20,606,060 |
| + Natural Growth | +$202,654 |
| + Organic Shampoo Launch | +$336,897 |
| + 50ml SKU Launch | +$265,960 |
| **= Estimated Net Sales 2024** | **$21,411,570** |

Three distinct growth buckets with quantified contributions — this is the core NRM output.

---

## Excel Techniques Used

- PivotTables with calculated fields (market share, YoY growth, MAT)
- `SUMIFS` for YTD and MAT accumulation across multi-column criteria
- `VLOOKUP` for promotion value lookups against monthly sales data
- `FORECAST.ETS` and `FORECAST.ETS.CONFINT` for time series projection with confidence intervals
- Structured table references (`[[#This Row],[column]]` syntax throughout)
- Waterfall chart driven by linked formulas across sheets
- Gross margin, net sales contribution, and ROI calculated columns

---

## Key Findings

- **Starbust is losing share** — down from 28.9% in 2018 to 20.8% in 2023 while Harmonix and Diamond Shine gain
- **Shinez Repair 200ml has the best gross margin (71.7%)** but remains underpenetrated volumetrically
- **Organic shampoo is the fastest-growing subcategory** — +275.8% growth 2018–2022, with ~1M units projected in 2024
- **"Buy 2, get 1 free" is a money-losing promotion** — the only one of three with negative ROI (-2.5%), despite generating the largest sales uplift in absolute terms
- **Three growth levers identified for 2024**: natural growth ($203K), organic launch ($337K), and 50ml SKU ($266K) — combined adding ~$805K to net sales

---

## Files

```
├── Net_Revenue_Management_Case_Study.xlsx
├── README.md
├── certificate.pdf
├── datasets/
└── screenshots/
    ├── market_share_pivot.png
    ├── profitability_matrix.png
    ├── new_category_opportunity.png
    ├── promotion_roi.png
    ├── forecast_2024.png
    └── waterfall_chart.png
```

---

## How to Open

1. Open `Net_Revenue_Management_Case_Study.xlsx` in Microsoft Excel (2016 or later)
2. If prompted, enable editing and allow content — FORECAST.ETS requires calculation to be active
3. Refresh all PivotTables if values appear stale (Data → Refresh All)
4. Start with `Market Share` and `internal sales data`, then follow the NRM workflow through to `Waterfall`

---

## Course

[Case Study: Net Revenue Management in Excel](https://www.datacamp.com/courses/case-study-net-revenue-management-in-excel) — DataCamp
