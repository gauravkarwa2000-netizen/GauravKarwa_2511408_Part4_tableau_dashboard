# Chart Selection Justification
**Executive Dashboard — Retail Performance | Tableau Workbook: executive_dashboard.twbx**

---

## 1. Sales Trend View — Line Chart

**Question Answered:** How are total sales and profit evolving month over month across the two-year period?

**Why This Chart Type:** A line chart is the standard and most readable choice for continuous time-series data. It allows the viewer to immediately identify trends, seasonal dips, and growth trajectories. Bars would work for comparing discrete months but would obscure the trend pattern that a line makes instantly visible.

**Fields Used:**
- X-Axis: Order Date (Month/Year)
- Y-Axis: SUM(Sales), SUM(Profit) — dual axis
- Color: Blue for Sales, Orange for Profit (distinct, accessible palette)
- Label: Final month values labelled for quick reference

**Design Principle Applied:** Pre-attentive attribute use — color distinguishes Sales from Profit without requiring the viewer to look at a legend repeatedly. The dual axis is labelled clearly to avoid confusion about scale.

**Mistake Avoided:** Not starting the Y-axis at zero would exaggerate small changes. The axis starts at zero to maintain honest scale. Avoided using a stacked area chart, which would have merged the two metrics visually and made the profit trend unreadable.

---

## 2. Regional Performance View — Filled Map + Bar Chart

**Question Answered:** Which regions and states are driving the most sales and profit? Are there geographic underperformers?

**Why This Chart Type:** A filled map (choropleth) provides instant geographic context — the viewer immediately sees which parts of India are strong and which are weak. A supporting bar chart by region provides precise comparisons that the map colour gradients cannot convey accurately.

**Fields Used:**
- Map: State (geographic dimension), filled by SUM(Sales)
- Color: Sequential blue gradient — darker = higher sales
- Bar chart: Region on rows, SUM(Sales) and SUM(Profit) on columns
- Label: Sales value and margin % on bars

**Design Principle Applied:** Spatial encoding — using geography to encode data aligns with how human cognition naturally interprets regional performance. The sequential colour scale avoids the "traffic light" trap of implying good/bad at arbitrary thresholds.

**Mistake Avoided:** Did not use a pie chart for regional share, which would have made precise comparison nearly impossible. Avoided using a diverging colour scale (which implies a neutral midpoint that doesn't exist in sales data).

---

## 3. Category Profitability View — Horizontal Bar Chart + Treemap

**Question Answered:** Which categories and sub-categories are most and least profitable? Where are margins being destroyed?

**Why This Chart Type:** A horizontal bar chart makes it easy to compare absolute profit values across categories and sub-categories because labels read naturally left-to-right. A treemap is used alongside to show the relative contribution of each sub-category to overall sales, making it easy to spot high-revenue/low-profit combinations (e.g., Furniture Tables).

**Fields Used:**
- Bar Chart: Sub-category on rows, SUM(Profit) on columns, sorted descending
- Color: Red for negative profit, Green for positive profit
- Treemap: Category > Sub-category hierarchy, Size = SUM(Sales), Color = Profit Margin (calculated field)
- Label: Margin % displayed on treemap cells

**Design Principle Applied:** Diverging colour on the treemap encodes profit margin — red cells immediately draw attention to loss-making or thin-margin sub-categories, directing executive attention to areas of risk.

**Mistake Avoided:** Did not use a 3D bar chart (distorts relative heights and adds no information). Avoided using a pie chart for sub-category share (too many slices to read clearly).

---

## 4. Customer Segment View — Grouped Bar Chart

**Question Answered:** How does revenue, profit, and return behaviour differ across Consumer, Corporate, and Home Office segments?

**Why This Chart Type:** A grouped bar chart allows direct side-by-side comparison of the same metric (Sales, Profit, Returns) across three discrete segments. The grouping makes it immediately clear which segment leads on each dimension.

**Fields Used:**
- X-Axis: Customer Segment
- Y-Axis: SUM(Sales) primary, with a second bar for SUM(Profit)
- Color: One colour per metric (consistent palette across dashboard)
- Label: Values and return rate % annotated

**Design Principle Applied:** Comparison encoding — grouping bars by segment makes relative performance visible at a glance without requiring the viewer to mentally subtract values.

**Mistake Avoided:** Did not use a stacked bar, which would have prevented easy per-segment comparison. Did not mix chart types in the same view unnecessarily.

---

## 5. Shipping Performance View — Bar Chart

**Question Answered:** How does delivery time vary by shipping mode? Which mode creates the most delays?

**Why This Chart Type:** A bar chart comparing average delivery days by shipping mode is simple, direct, and immediately actionable. The business question is categorical (ship mode) vs. quantitative (days), which maps naturally to bars.

**Fields Used:**
- X-Axis: Ship Mode
- Y-Axis: AVG(Delivery Days)
- Color: Sequential from green (fast) to red (slow) based on average days
- Reference Line: A horizontal line at 5 days marking the internal SLA threshold

**Design Principle Applied:** Reference line provides context — viewers immediately see which ship modes breach the acceptable threshold without requiring external benchmarks.

**Mistake Avoided:** Did not use a line chart (ship modes are categories, not a continuous sequence). Avoided sorting by alphabet — sorted by avg delivery time descending so the slowest mode appears first, directing immediate attention.

---

## 6. Discount vs. Profit View — Scatter Plot

**Question Answered:** Is there a relationship between the discount applied and the resulting profit? Where does profitability collapse?

**Why This Chart Type:** A scatter plot is the correct choice for exploring relationships between two continuous numerical variables — discount rate (X) and profit (Y). It reveals the distribution, clusters, and outliers that a bar chart or table would hide.

**Fields Used:**
- X-Axis: Discount (continuous, 0–0.45)
- Y-Axis: Profit (continuous, can be negative)
- Color: Category (to show if discount-profit dynamics differ by category)
- Size: SUM(Sales) (larger circles = higher revenue orders)
- Reference Line: X = 0.20, Y = 0 (profit breakeven line)

**Design Principle Applied:** The profit breakeven reference line (Y = 0) and the 20% discount threshold (X = 0.20) divide the scatter into four quadrants, making it immediately clear that the upper-left quadrant (low discount, positive profit) is the target zone.

**Mistake Avoided:** Avoided using a line chart to show discount vs. profit (would imply a single ordered sequence rather than a distribution). Avoided plotting aggregated averages only — showing individual orders reveals the full variance and outliers.

---

## 7. Return Analysis View — Highlight Table (Heat Map)

**Question Answered:** Which combinations of category and customer segment have the highest return rates?

**Why This Chart Type:** A highlight table (heat map) is ideal for showing a matrix of values across two categorical dimensions. The colour intensity immediately draws the eye to the highest return-rate cells without requiring the viewer to read every number.

**Fields Used:**
- Rows: Category
- Columns: Customer Segment
- Color: Return Rate (calculated field: SUM(Return Flag) / COUNT(Order ID)), sequential red scale
- Label: Return rate % displayed in each cell

**Design Principle Applied:** Pre-attentive colour encoding — the darkest red cells immediately signal the highest-risk combinations (e.g., Furniture × Home Office) without any conscious effort from the viewer.

**Mistake Avoided:** Did not use a bar chart for this view, which would have required 9 separate bars and made matrix-level pattern recognition difficult. Avoided using absolute return counts — rates are used instead to make segments of different sizes comparable.

---

## Dashboard-Level Design Principles

| Principle | Implementation |
|---|---|
| **Consistent colour palette** | Blue = Sales, Orange = Profit, Red = Risk/Loss, Green = Positive throughout all views |
| **Clear hierarchy** | KPI cards at the top (total sales, total profit, return rate, avg order value) → category/region views in the middle → drill-down detail at the bottom |
| **Minimal clutter** | Grid lines suppressed in most views; borders removed from charts; tooltips provide detail on hover |
| **Readable titles** | Every chart has a plain-English title describing what it shows, not what data it uses |
| **Appropriate sorting** | Bars sorted by value (descending) by default throughout; time charts sorted chronologically |
| **Interactive filters** | Region, Category, Customer Segment, Ship Mode, Date Range, Campaign Channel — all connected as dashboard-level filters so selecting in one chart filters all others |
| **Honest scales** | All axes start at zero; dual-axis charts labelled on both sides; no truncated scales |
