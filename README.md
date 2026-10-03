# Superstore Sales Analytics Dashboard

An end-to-end sales analysis of 1,952 US Superstore order lines (Jan–Jun 2015), cleaned and visualized as an interactive dashboard.

**Live dashboard:** https://claude.ai/artifact/1JbM8Gijp2zmMpGoThxBuL

---

## Overview

This project takes raw, messy retail transaction data and turns it into a decision-ready analytics dashboard — covering sales trends, regional performance, category mix, and profit leakage.

- **Orders analyzed:** 1,365 orders / 1,952 line items
- **Customers:** 1,130
- **Period:** Jan 1 – Jun 30, 2015
- **Tools:** Python (Pandas) for cleaning & aggregation, Chart.js for the dashboard

## Key Insights

- **Total sales:** $1,924,337.88 | **Total profit:** $224,077.61 (11.64% margin)
- **Average order value:** $1,409.77
- The **South region is operating at a net loss**, while other regions stay profitable — a clear red flag for regional strategy.
- A handful of **sub-categories are consistently losing money** even though they generate sales, which points to pricing or discounting issues rather than demand issues.
- **Office Supplies, Furniture, and Technology** show very different sales-to-profit ratios, meaning the highest-revenue category isn't necessarily the most profitable one.

## Data Cleaning

Raw data had a few quality issues, handled before analysis:

| Issue | Fix |
|---|---|
| Missing `Product Base Margin` values | Imputed with column median |
| Inconsistent `Order Priority` label (`"Critical "` with trailing space) | Normalized to `"Critical"` |
| `Order Date` / `Ship Date` stored as text | Parsed to proper datetime |

## Dashboard Sections

1. **KPI summary** — sales, profit, margin, orders, customers, AOV
2. **Monthly trend** — sales (bar) vs. profit (line) over time
3. **Regional breakdown** — sales by region, highlighting the South region loss
4. **Category / segment / ship mode mix**
5. **Top sub-categories by sales** vs. **sub-categories losing the most money**
6. **Top 10 products and top 10 customers by sales**

## Project Structure

```
├── data/
│   ├── row_data.csv          # raw source data
│   └── cleaned_data.csv      # cleaned dataset
├── dashboard/
│   └── superstore_dashboard.html   # self-contained interactive dashboard
├── scripts/
│   └── analysis.py           # cleaning + aggregation script
└── README.md
```

## How to Run

```bash
pip install -r requirements.txt
python scripts/analysis.py
```

Then open `dashboard/superstore_dashboard.html` in any browser — no server required.

---

**Author:** Ayush Kumar
**Contact:** ayushk65808@gmail.com
