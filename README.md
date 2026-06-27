# GauravKarwa_2511408_Part4_tableau_dashboard# Executive Sales Dashboard — Tableau Project
**Repository:** `studentname_studentid_part4_tableau_dashboard`
**Course Part:** Part 4 — Tableau Executive Dashboard & Data Storytelling

---

## 1. Business Problem Summary

The retail leadership team requires a centralised executive dashboard to monitor and interpret sales performance across regions, categories, customer segments, and time periods. Without a consolidated view, leadership cannot quickly identify underperforming areas, discount leakage, return risk, or shipping inefficiencies. This dashboard transforms 4,200 raw order records into actionable business intelligence, enabling faster and better-informed decisions.

---

## 2. Dataset Description

**File:** `data/dashboard_sales_data.xlsx`
**Records:** 4,200 orders
**Period:** January 2024 – December 2025

| Column | Type | Description |
|---|---|---|
| order_id | Text | Unique order identifier |
| order_date | Date | Date the order was placed |
| ship_date | Date | Date the order was shipped |
| customer_id | Text | Unique customer identifier |
| customer_segment | Categorical | Consumer, Corporate, Home Office |
| region | Categorical | North, South, East, West |
| state | Text | Indian state |
| city | Text | City of delivery |
| category | Categorical | Furniture, Office Supplies, Technology |
| sub_category | Categorical | 17 product sub-categories |
| product_name | Text | Product name |
| ship_mode | Categorical | Same Day, First Class, Second Class, Standard Class |
| sales | Numeric | Order revenue (₹) |
| quantity | Numeric | Units ordered |
| discount | Numeric | Discount rate (0 to 0.45) |
| profit | Numeric | Net profit (₹) — can be negative |
| return_flag | Binary | 1 = returned, 0 = not returned |
| delivery_days | Numeric | Days from order to delivery |
| customer_rating | Numeric | Rating out of 5.0 |
| campaign_channel | Categorical | Organic, Paid, Social, Email, Referral |

---

## 3. Tableau Workbook Description

**File:** `tableau/executive_dashboard.twbx`

The packaged workbook contains the following sheets and one executive dashboard:

| Sheet Name | View Type | Purpose |
|---|---|---|
| Sales Trend | Line Chart | Monthly sales and profit over time |
| Regional Performance | Map + Bar | Sales and profit by region and state |
| Category Profitability | Bar + Treemap | Profit and margin by category/sub-category |
| Customer Segment View | Grouped Bar | Revenue, profit, return rate by segment |
| Shipping Performance | Bar Chart | Avg delivery days by shipping mode |
| Discount vs Profit | Scatter Plot | Relationship between discount rate and profit |
| Return Analysis | Highlight Table | Return rate by category × segment |
| Executive Dashboard | Dashboard | Consolidated view of all 7 sheets with filters and KPIs |

---

## 4. Calculated Fields Created

| Field Name | Formula | Purpose |
|---|---|---|
| **Profit Margin** | `[Profit] / [Sales]` | Measures profitability as a percentage of revenue |
| **Cost** | `[Sales] - [Profit]` | Derives cost of goods/services |
| **Average Order Value** | `SUM([Sales]) / COUNT([Order ID])` | Average revenue per transaction |
| **Return Rate** | `SUM([Return Flag]) / COUNT([Order ID])` | Percentage of orders returned |
| **Shipping Delay Bucket** | `IF [Delivery Days] = 0 THEN "Same Day" ELSEIF [Delivery Days] <= 2 THEN "Fast (1–2 days)" ELSEIF [Delivery Days] <= 4 THEN "Standard (3–4 days)" ELSEIF [Delivery Days] <= 6 THEN "Slow (5–6 days)" ELSE "Delayed (7+ days)" END` | Categorises delivery speed for comparison |

---

## 5. Dashboard Components

The Executive Dashboard includes:

- **KPI Cards (3):** Total Sales (₹217M), Total Profit (₹33.3M), Overall Return Rate (4.5%), Average Order Value
- **Charts/Views (7):** Sales Trend, Regional Map, Category Profitability, Segment Comparison, Shipping Performance, Discount vs Profit Scatter, Return Analysis Heatmap
- **Dashboard Title:** "Retail Executive Performance Dashboard — 2024–2025"
- **Clean layout:** KPIs at top, trend in middle, breakdowns below

---

## 6. Filters and Interactions

| Filter | Type | Connected Views |
|---|---|---|
| Region | Dropdown / Quick filter | All sheets |
| Category | Dropdown / Quick filter | All sheets |
| Customer Segment | Dropdown / Quick filter | All sheets |
| Ship Mode | Dropdown / Quick filter | Shipping and Trend views |
| Date Range | Date range slider | Sales Trend, Regional |
| Campaign Channel | Dropdown | Segment, Sales Trend |

**Dashboard Actions:**
- Clicking a region on the map filters all other views to that region
- Clicking a category bar in the profitability view drills down into sub-categories
- Hovering on any data point shows a tooltip with Sales, Profit, Margin %, and Order Count

---

## 7. Key Business Insights

1. **Technology drives 84% of profit** at an 18.2% margin — it is the primary profit engine.
2. **Furniture margins are dangerously thin** at 6.9%; Tables and Bookcases operate near breakeven.
3. **Discounts above 20% erode all value** — orders at 30%+ discount generate a net loss.
4. **Home Office is the highest-revenue segment** (₹74.5M) but also has the highest return rate (5.6%).
5. **South region leads** in sales (₹64.7M) and profit; all regions maintain comparable 15% margins.
6. **Standard Class shipping averages 4.7 days** with 45 orders exceeding 7 days, creating satisfaction risk.
7. **Mid-year (April–May) shows consistent revenue dips** — a gap period with no major promotions.
8. **Furniture accounts for 46% of all returns** despite being the second category by sales.

---

## 8. Dashboard Story Summary

The business is healthy at the top line (₹217M revenue, 15.3% margin) but structurally fragile. Technology's outsized profit contribution (84%) creates dangerous concentration risk. Furniture operates near breakeven despite significant revenue. Discounting is unconstrained and destroying margins at higher levels. The Home Office segment is simultaneously the most valuable and the most problematic. Immediate actions needed: cap discounts at 20%, investigate Furniture margins, and address Home Office return drivers.

Full story: `outputs/dashboard_story.md`

---

## 9. Assumptions and Limitations

- `order_date` and `ship_date` were stored as Excel serial numbers; converted to dates using Tableau's built-in date parsing.
- `delivery_days` is calculated as ship_date − order_date. A value of 0 is treated as Same Day delivery, not a data error.
- `profit` values can be negative (loss-making orders) — this is intentional in the dataset and reflects discounted/high-cost orders.
- `campaign_channel` has some missing values (~3% of rows); these are excluded from channel-level analysis.
- `return_flag = 1` indicates the order was returned; no return reason data is available.
- All monetary values are assumed to be in Indian Rupees (₹).
- State names are Indian states; geographic mapping uses Tableau's built-in India map role.

---

## 10. Screenshots Included

| File | Description |
|---|---|
| `screenshots/full_dashboard.png` | Complete executive dashboard with all views and KPIs |
| `screenshots/sales_trend_view.png` | Monthly sales and profit trend line chart |
| `screenshots/regional_performance_view.png` | India map and regional bar chart |
| `screenshots/category_profitability_view.png` | Category and sub-category profit bars and treemap |
| `screenshots/filter_interaction_view.png` | Dashboard with South region filter active showing cross-filtering |

> **Note:** Screenshots are taken from the Tableau Desktop workbook at 1920×1080 resolution. The Tableau packaged workbook (`executive_dashboard.twbx`) must be opened in Tableau Desktop (version 2022.1 or later) or Tableau Public to view the interactive version.

---

## Folder Structure

```
part4_tableau_dashboard/
├── data/
│   └── dashboard_sales_data.xlsx
├── tableau/
│   └── executive_dashboard.twbx
├── outputs/
│   ├── dashboard_story.md
│   ├── business_insights.md
│   └── chart_selection_justification.md
├── screenshots/
│   ├── full_dashboard.png
│   ├── sales_trend_view.png
│   ├── regional_performance_view.png
│   ├── category_profitability_view.png
│   └── filter_interaction_view.png
└── README.md
```
