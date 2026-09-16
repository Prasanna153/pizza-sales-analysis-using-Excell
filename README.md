# 🍕 Pizza Sales Dashboard — Excel

An end-to-end sales analysis of a pizza restaurant's full year of orders (2015),
built as an interactive Excel dashboard with pivot tables, pivot charts and slicers,
and backed by a Python script that reproduces every number in the report.

![Dashboard preview](assets/dashboard_preview.png)

> The image above is generated from the raw data by `analysis/generate_report.py`.
> The interactive version lives in `data/pizza_sales_dashboard.xlsx` — open it in
> Excel and use the slicers to filter by month, day, category and size.

## Key results

| Metric | Value |
| --- | --- |
| Total revenue | $817,860 |
| Total orders | 21,350 |
| Pizzas sold | 49,574 |
| Average order value | $38.31 |
| Average pizzas per order | 2.32 |
| Average orders per day | 59.6 |

## What the data says

- **Two clear rush windows.** Lunch (12–1 pm) and dinner (5–7 pm) carry the day;
  12 pm alone accounts for 2,520 orders. Everything before 11 am and after 10 pm is noise.
- **Friday is the best day** (3,538 orders), Sunday the worst (2,624) — a ~35% spread
  that should drive staffing, not gut feel.
- **Large is the money size.** L pizzas bring in $375k, 46% of revenue; XL and XXL
  together are under 2% and are arguably not worth the menu space.
- **Demand is flat year-round.** Monthly revenue sits between $64k and $73k with no
  real seasonality — July is the peak, September and October the softest.
- **Categories are evenly matched** ($194k–$220k each), but individual pizzas are not:
  Thai Chicken ($43.4k) earns nearly four times what Brie Carre ($11.6k) does.

Full write-up with the supporting numbers: [`docs/insights.md`](docs/insights.md).

## Repository structure

```
.
├── data/
│   └── pizza_sales_dashboard.xlsx   # raw data + pivot tables + interactive dashboard
├── analysis/
│   ├── generate_report.py           # rebuilds every KPI and the preview image
│   ├── kpi_summary.csv              # headline metrics
│   └── breakdowns.csv               # revenue/orders/quantity by 6 dimensions
├── docs/
│   └── insights.md                  # findings and recommendations
└── assets/
    └── dashboard_preview.png        # dashboard image used in this README
```

## The workbook

| Sheet | Contents |
| --- | --- |
| `Table1` | 48,620 order lines — the raw fact table, plus derived Month / Day / Hour columns |
| `Sheet3` | Pivot tables feeding the charts |
| `Sheet4` | The dashboard: KPI cards, 6 pivot charts, slicers |

Fields: `order_id`, `pizza_id`, `quantity`, `order_date`, `order_time`, `unit_price`,
`total_price`, `pizza_size`, `pizza_category`, `pizza_ingredients`, `pizza_name`.

## Reproducing the analysis

```bash
pip install -r requirements.txt
python analysis/generate_report.py
```

This re-reads the workbook and rewrites `analysis/kpi_summary.csv`,
`analysis/breakdowns.csv` and `assets/dashboard_preview.png`.

## Skills demonstrated

Excel pivot tables · pivot charts · slicers · dashboard design · data cleaning ·
KPI definition · Python (pandas, matplotlib) · business storytelling

## Data

Public "Pizza Place Sales" dataset — one calendar year (1 Jan – 31 Dec 2015) of
transaction-level orders. Used here for portfolio and learning purposes.
