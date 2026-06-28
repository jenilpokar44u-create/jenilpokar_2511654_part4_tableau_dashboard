# Chart Selection Justification Report

## 1. Sales and Profit Trend over Time (Line Chart)
* **Question Answered:** How are our monthly sales and profit margins trending throughout the fiscal year?
* **Why it's appropriate:** Line charts are the golden standard for continuous time-series data. They allow leadership to instantly identify seasonal spikes, trailing dips, and historical trajectories.
* **Encoding Strategy:** Columns: `Order Date` (Continuous Month). Rows: `Sales` (Line) and `Profit` (Dual-Axis Line colored differently to contrast volume against net returns).
* **Design Principle Applied:** Used a dual-axis layout with clean axis synchronization to keep time-series comparisons spatially aligned.
* **Mistake Avoided:** Avoided using a crowded bar chart, which chops up time visually and obscures fluid trend analysis.

## 2. Regional Financial Performance (Geographic Map & Highlight Table)
* **Question Answered:** Which states and regions are driving top-line revenue versus bottom-line profit margins?
* **Why it's appropriate:** Geographic maps instantly ground regional performance for executives, while an adjacent highlight table uses color density to isolate structural underperformance without visual clutter.
* **Encoding Strategy:** Map: `State` on Detail, `Sales` on Size, and `Profit Margin` on Color. Highlight Table: Rows: `Region`. Columns: `Measure Names`. Color driven by `Profit Margin`.
* **Design Principle Applied:** Implemented a diverging color scheme (centered at 0% margin) to instantly separate profitable territories from loss-making zones.
* **Mistake Avoided:** Avoided using a basic pie chart for regional market share, which fails to communicate actual profitability structures.

## 3. Category & Sub-Category Performance Hierarchy (Nested Horizontal Bar Chart)
* **Question Answered:** Which specific product lines are driving our revenue growth, and where are the margin leaks?
* **Why it's appropriate:** Horizontal bar charts provide an intuitive, scannable layout for categorical comparisons, offering clean text readability for long labels like sub-category names.
* **Encoding Strategy:** Rows: `Category`, `Sub-Category`. Columns: `Sales`. Color encoding driven directly by `Profit`.
* **Design Principle Applied:** Applied descending sorting by sales volume to instantly give the viewer clear visual hierarchy.
* **Mistake Avoided:** Avoided using an over-segmented treemap, which becomes unreadable when evaluating a mix of highly positive and highly negative values.

## 4. Discount vs. Profit Margins (Scatter Plot)
* **Question Answered:** Is there an identifiable point where our promotional discount rates destroy product profitability?
* **Why it's appropriate:** Scatter plots are ideal for evaluating relationships and distributions between two continuous numerical variables.
* **Encoding Strategy:** X-Axis: `Discount`. Y-Axis: `Profit Margin`. Detail Level: `Order Id`. Color: `Category`.
* **Design Principle Applied:** Added a linear trendline to visually demonstrate the negative correlation between aggressive markdowns and profitability.
* **Mistake Avoided:** Avoided grouping discounts into generic bar charts, which hides the granular operational realities of individual transactions.

## 5. Fulfillment & Delivery Analysis (Stacked Horizontal Bar Chart)
* **Question Answered:** Which shipping modes are failing to meet delivery windows, and what is the distribution of delays?
* **Why it's appropriate:** A stacked horizontal layout allows easy comparison of proportional volumes across our calculated `Shipping Delay Bucket` dimensions.
* **Encoding Strategy:** Rows: `Ship Mode`. Columns: `Count of Order Id` (as a % of total row). Color: `Shipping Delay Bucket`.
* **Design Principle Applied:** Maintained a clean sequential color progression representing severity (Fast, Standard, Delayed) to keep the data intuitive.
* **Rule Avoided:** Avoided using raw counts alone, shifting instead to a percentage-of-total calculation so that high-volume tiers do not mask the underlying delivery performance of smaller shipping options.
