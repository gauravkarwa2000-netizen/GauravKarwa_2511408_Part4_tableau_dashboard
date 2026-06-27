# Dashboard Story — Retail Executive Performance Review
**Prepared for: Leadership Team | Data Period: Jan 2024 – Dec 2025 | Total Orders: 4,200**

---

## 1. Executive Summary

Over the two-year period from January 2024 to December 2025, the business generated **₹217M in total revenue** and **₹33.3M in profit**, reflecting an overall profit margin of **15.3%**. Technology is the undisputed growth engine, contributing nearly 85% of all profits. However, several structural risks are visible: Furniture operates at dangerously thin margins, discounts above 20% are destroying value, and the Home Office segment — our highest revenue group — also returns the most products.

The dashboard tells a story of strong top-line performance masking an uneven and fragile profit architecture. Leadership must act now to diversify the profit base, control discount leakage, and reduce category-level return risk.

---

## 2. What Is Performing Well

**Technology is a standout performer.** With ₹153.9M in sales and an 18.2% profit margin, it outperforms every other category by a significant margin. Accessories, Phones, and Copiers are all profitable sub-categories driving consistent returns.

**The South region leads in absolute revenue** (₹64.7M) and profit (₹9.99M), followed closely by the North. All four regions maintain comparable margins (~15%), which reflects disciplined pricing and operational consistency across geographies.

**Home Office customers are the highest-value segment**, generating ₹74.5M in sales. Customer ratings across all segments average above 4.0/5.0, suggesting general satisfaction with products.

**Zero-discount orders deliver exceptional margins** (20.6%), demonstrating that the product portfolio can command full-price sales when discounting is avoided.

---

## 3. What Is Underperforming

**Furniture is a margin crisis.** Despite generating ₹51.6M in sales, it produces only ₹3.6M in profit — a 6.9% margin. Tables and Bookcases both operate at approximately 5.7% margins, making them the lowest-performing sub-categories in the entire portfolio. Any increase in shipping cost or return frequency in this category will push it into unprofitability.

**Office Supplies is a volume story without a profit story.** It contributes just ₹1.7M of profit on ₹11.5M in sales (14.8% margin). While this is acceptable, Office Supplies sub-categories such as Paper, Binders, Storage, and Art generate the smallest absolute profit figures across the dashboard.

**Discount rates above 20% are net value destroyers.** Orders in the 21–30% discount bracket earned only an 8.0% margin, and orders above 30% generated a net loss of ₹102,000. These deals are not strategic — they are erosive.

---

## 4. What Risks Are Visible

**Category concentration risk is the single largest structural vulnerability.** Technology contributes 84.2% of total profit. A demand slowdown, competitive disruption, or supply chain disruption in Technology would have catastrophic effects on the company's bottom line, with no strong profit backstop from Furniture or Office Supplies.

**Home Office's return rate of 5.6%** — significantly higher than Corporate (4.0%) and Consumer (3.8%) — creates hidden cost exposure. Returns in high-value categories like Furniture are particularly costly to process and re-stock.

**Standard Class shipping delays** affect customer satisfaction for a subset of orders. Forty-five orders experienced delivery delays exceeding 7 days, a threshold at which customer churn risk rises materially.

**Discount policy is decentralised.** The presence of orders at 30%+ discounts suggests individual sales reps or channel partners have broad discretion over pricing. Without guardrails, this will continue to erode margins.

---

## 5. What Opportunities Are Visible

**Technology cross-sell into underperforming regions.** While the South leads in Technology revenue, East and West show lower penetration. Targeted marketing campaigns in these regions could unlock meaningful incremental profit at Technology's superior 18.2% margin.

**Furniture pricing and SKU optimisation.** If Furniture margins can be improved from 6.9% to 12%+ through better supplier pricing, SKU rationalisation, and smarter discounting controls, it would add over ₹2.6M in incremental annual profit.

**Campaign channel diversification.** A significant number of orders are driven by Organic traffic and Social media. The Paid and Referral channels show meaningful contribution but have room to grow. Email and Referral campaigns tend to attract higher-value orders — these should receive increased investment.

**Customer rating as a loyalty lever.** Orders with customer ratings of 4.5 and above are likely to correlate with repeat purchases. Identifying and doubling down on the product-segment-region combinations that drive high ratings will reduce Customer Acquisition Cost over time.

---

## 6. Recommended Business Actions

| Priority | Action | Owner | Timeline |
|---|---|---|---|
| 1 | Cap all discounts at 20%; require VP approval for any exception | Sales Operations | 30 days |
| 2 | Review and rationalise bottom 5 Furniture SKUs by margin | Category Management | 60 days |
| 3 | Launch April–May promotional campaign to address mid-year dip | Marketing | Next Q1 |
| 4 | Investigate Home Office return drivers; update product pages | Customer Experience | 60 days |
| 5 | Set Standard Class SLA flag for orders exceeding 5 days | Supply Chain | 45 days |
| 6 | Increase Paid and Referral campaign budgets by 20% | Digital Marketing | 30 days |
| 7 | Develop a 3-year category diversification roadmap | Strategy | 90 days |

---

## 7. Limitations of the Dashboard

- **No customer-level data:** The dashboard operates at the order level. We cannot track individual customer lifetime value, repeat purchase rates, or churn without customer-ID-level aggregation.
- **No cost of goods sold (COGS) breakdown:** Profit figures are as recorded. We cannot decompose profit into COGS, logistics cost, and overhead without additional data sources.
- **Return reasons are unavailable:** The dataset flags returned orders (return_flag = 1) but does not record why items were returned, limiting root-cause analysis.
- **Campaign channel has missing values:** A portion of orders have no campaign channel attributed, which may skew channel performance analysis.
- **Geographic granularity:** State and city data are available but were not mapped to Tier 1/2/3 city classifications, which could reveal important urban vs. rural demand patterns.
- **Seasonality limited to 2 years:** Two years of data may not be sufficient to distinguish structural trends from seasonal noise.

---

## 8. Suggested Next Analysis

1. **Customer cohort analysis:** Segment customers by first purchase date and track revenue, margin, and return rate over time to identify the highest-LTV cohorts.
2. **Discount elasticity modelling:** Quantify how much volume is lost when discounts are reduced by 5–10 percentage points, to determine the true net revenue impact of tightening discount policy.
3. **Return root-cause analysis:** Collect and categorise return reasons for the next 6 months to identify whether returns are driven by product defects, delivery damage, expectation mismatch, or other factors.
4. **Geographic demand mapping:** Overlay sales data with state-level GDP and retail penetration data to identify under-served high-potential markets.
5. **Predictive churn model:** Use customer rating scores, return history, and order frequency to build an early-warning model for at-risk customers.

---

*This story was constructed from the Executive Dashboard built in Tableau using dashboard_sales_data.xlsx. All figures are based on 4,200 orders recorded between January 2024 and December 2025.*
