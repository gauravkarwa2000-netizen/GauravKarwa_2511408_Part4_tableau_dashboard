# Business Insights — Executive Dashboard
**Retail Leadership Team | Period: Jan 2024 – Dec 2025**

---

## Calculated Fields Used

| Calculated Field | Logic |
|---|---|
| **Profit Margin** | `[Profit] / [Sales]` |
| **Cost** | `[Sales] - [Profit]` |
| **Average Order Value** | `SUM([Sales]) / COUNT([Order ID])` |
| **Return Rate** | `SUM([Return Flag]) / COUNT([Order ID])` |
| **Shipping Delay Bucket** | IF [Delivery Days] = 0 THEN "Same Day" ELSEIF [Delivery Days] <= 2 THEN "Fast (1–2 days)" ELSEIF [Delivery Days] <= 4 THEN "Standard (3–4 days)" ELSEIF [Delivery Days] <= 6 THEN "Slow (5–6 days)" ELSE "Delayed (7+ days)" END |

---

## Insight 1 — Sales Trend: Consistent Revenue with Notable Dips in Mid-Year

**Observation:** Monthly sales ranged from approximately ₹7.5M (May 2024) to over ₹10.5M (Feb 2024), with the overall two-year total reaching ₹217M. Mid-year months (April–May) show consistent dips each year.

**Data Evidence:** May 2024 recorded ₹7.46M — the lowest monthly revenue across the two-year period. February 2024 peaked at ₹10.49M.

**Business Interpretation:** Retail demand follows a cyclical pattern. The mid-year slump in April–May likely reflects a post-Q1 slowdown and the absence of a major promotional event in that window.

**Recommended Action:** Plan a targeted promotional campaign in April–May (e.g., a summer sales event or bundle discount) to flatten the mid-year dip and maintain revenue momentum.

---

## Insight 2 — Regional Performance: South Leads, East and West Are Comparable

**Observation:** The South region generated the highest sales (₹64.7M, 29.8% of total) and profit (₹9.99M). The North follows with ₹54.6M in sales. East and West are closely matched at ₹48.9M each.

**Data Evidence:**
- South: ₹64.7M sales, ₹9.99M profit (15.4% margin)
- North: ₹54.6M sales, ₹8.31M profit (15.2% margin)
- West: ₹48.9M sales, ₹7.40M profit (15.1% margin)
- East: ₹48.9M sales, ₹7.60M profit (15.6% margin)

**Business Interpretation:** All four regions maintain similar profit margins (~15%), indicating consistent pricing and cost management. The South's lead in absolute revenue likely reflects a larger customer base or higher-value orders, not better margins.

**Recommended Action:** Investigate what's driving South's volume advantage — whether it's customer density, better campaign penetration, or product mix — and replicate successful tactics in East and West.

---

## Insight 3 — Category Profitability: Technology Dominates; Furniture Has Lowest Margin

**Observation:** Technology contributes ₹153.9M in sales (70.9% of total) and ₹28.0M in profit (84.2% of total profit). Furniture generates ₹51.6M in sales but only ₹3.6M in profit (6.9% margin). Office Supplies contributes ₹11.5M in sales and ₹1.7M in profit (14.8% margin).

**Data Evidence:**
- Technology margin: 18.2%
- Office Supplies margin: 14.8%
- Furniture margin: 6.9%

**Business Interpretation:** Furniture is a high-revenue but low-margin category. Sub-categories like Tables (₹731K profit from ₹12.9M sales) and Bookcases (₹711K from ₹12.5M) are barely profitable, suggesting either heavy discounting or high cost of goods.

**Recommended Action:** Review Furniture pricing and discount policies. Consider phasing out consistently loss-making SKUs or renegotiating supplier contracts to improve Furniture margins above 10%.

---

## Insight 4 — Customer Segment Behavior: Home Office Has Highest Revenue and Return Rate

**Observation:** Home Office generated the highest sales (₹74.5M) and profit (₹11.6M) among the three segments. However, Home Office also accounts for the most returns (82 out of 191 total, or 43% of all returns).

**Data Evidence:**
- Home Office: ₹74.5M sales, 82 returns (return rate ~5.6%)
- Corporate: ₹70.6M sales, 56 returns (return rate ~4.0%)
- Consumer: ₹71.9M sales, 53 returns (return rate ~3.8%)

**Business Interpretation:** Home Office customers are the most valuable segment by revenue but also the most dissatisfied or uncertain about purchases. This elevated return rate may indicate product-fit issues or unmet expectations from this segment.

**Recommended Action:** Conduct a post-purchase survey for Home Office customers. Investigate the top returned product categories for this segment and improve product descriptions or size/spec guidance to reduce return-driven margin erosion.

---

## Insight 5 — Discount Impact: Higher Discounts Destroy Profit

**Observation:** Orders with 0% discount generated the highest aggregate profit (₹13.5M from ₹65.8M in sales — a 20.6% margin). As discounts increase, profit margin collapses. Orders with discounts above 30% generated a net loss of ₹102K.

**Data Evidence:**
- 0% discount: ₹13.5M profit (20.6% margin)
- 1–10% discount: ₹9.8M profit (17.0% margin)
- 11–20% discount: ₹6.6M profit (13.6% margin)
- 21–30% discount: ₹3.5M profit (8.0% margin)
- 31%+ discount: −₹102K profit (net loss)

**Business Interpretation:** Discounting is eroding company profitability. Every 10 percentage points of discount reduces the profit margin by roughly 4–6 points. Orders above 30% discount are unprofitable and should be eliminated.

**Recommended Action:** Cap individual order discounts at 20%. Introduce an approval workflow for any discount above 15% to ensure minimum margin thresholds are met. Replace blanket discounting with targeted loyalty rewards.

---

## Insight 6 — Shipping Performance: Standard Class Used Most but Causes Most Delays

**Observation:** Standard Class is the most frequently used shipping mode. Its average delivery time is 4.71 days compared to 1.77 days for First Class, 2.68 days for Second Class, and 0.40 days for Same Day. A total of 45 orders experienced delivery of more than 7 days.

**Data Evidence:**
- Standard Class: avg 4.71 delivery days
- First Class: avg 1.77 days
- Second Class: avg 2.68 days
- Same Day: avg 0.40 days
- 45 orders: delivery days > 7 (all likely Standard Class)

**Business Interpretation:** The reliance on Standard Class shipping is appropriate for cost management, but the tail of severely delayed orders (7+ days) risks customer dissatisfaction and returns. Given that all ship modes carry similar profit margins (~13%), there is room to upgrade chronic delay cases without hurting margins.

**Recommended Action:** Set an SLA flag for Standard Class orders exceeding 5 days. For customers in regions with historically longer delivery times, proactively offer Second Class at standard pricing to maintain satisfaction.

---

## Insight 7 — Return Pattern: Furniture Has Highest Return Volume; Technology Returns Are Lowest

**Observation:** Furniture accounts for 88 out of 191 total returns (46%), despite being the second-largest category by sales. Technology, which is the largest sales category, has only 42 returns (22% of all returns).

**Data Evidence:**
- Furniture: 88 returns (return rate ~5.5% of Furniture orders)
- Office Supplies: 61 returns (return rate ~4.4%)
- Technology: 42 returns (return rate ~3.1%)

**Business Interpretation:** Furniture's high return rate is compounded by its already thin margins. Each returned Furniture item is disproportionately costly to process. Technology's low return rate aligns with its high-margin profile, suggesting strong product-market fit.

**Recommended Action:** Introduce a stricter Furniture returns policy with a 15-day return window and mandatory product condition review. Invest in better Furniture product photography and specification pages to reduce expectation mismatch before purchase.

---

## Insight 8 — Business Risk & Opportunity: Technology Growth vs. Furniture Loss Exposure

**Observation:** Technology generates 70.9% of all revenue and 84.2% of all profit. However, over-reliance on one category creates business concentration risk. Meanwhile, Furniture (23.8% of sales) operates at near-breakeven margins in some sub-categories (Tables: 5.7% margin; Bookcases: 5.7% margin).

**Data Evidence:**
- Technology profit contribution: ₹28.0M / ₹33.3M total = 84.2%
- Furniture Tables margin: ₹731K / ₹12.9M = 5.7%
- Furniture Bookcases margin: ₹711K / ₹12.5M = 5.7%

**Business Interpretation:** If Technology demand softens (e.g., post-upgrade cycle, new competitor entry), the company has no strong secondary profit engine. Furniture is a strategic liability rather than an asset at current margins.

**Recommended Action:** Develop a category diversification roadmap. Set a 3-year target to grow Office Supplies revenue by 25% and improve Furniture average margin to 12% through pricing, SKU rationalization, and supplier renegotiation. Reduce single-category revenue concentration below 60%.

---

*Document prepared for leadership review. All figures sourced from dashboard_sales_data.xlsx (4,200 orders, Jan 2024 – Dec 2025).*
