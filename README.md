# Part 4: Tableau Executive Dashboard & Data Storytelling

## Business Problem Summary
Our corporate leadership team required an intuitive, centralized executive dashboard to transition away from static spreadsheets and actively track transactional health. This project synthesizes transactional parameters across product categories, customer behaviors, fulfillment pathways, and marketing acquisition channels to identify high-performing divisions and uncover critical margin leakages.

## Dataset Description
* **File:** `data/dashboard_sales_data.xlsx`
* **Structure:** Contains granular order-level data capturing timeline markers (`order_date`, `ship_date`), regional breakdowns (`region`, `state`, `city`), core categories, financials (`sales`, `quantity`, `discount`, `profit`), logistical flags, and campaign sources.

## Tableau Workbook Architecture
* **Packaged File Location:** `tableau/executive_dashboard.twbx`
* **Workbook Style:** Contains seven specialized sheets feeding into a centralized dashboard view optimized for an executive audience.

## Calculated Fields Created
To support deeper operational reporting, I authored 5 custom calculations in Tableau:
1. `Cost`: `[Sales] - [Profit]` (Isolates pure production/acquisition outlays).
2. `Profit Margin`: `SUM([Profit]) / SUM([Sales])` (Measures bottom-line efficiency).
3. `Average Order Value (AOV)`: `SUM([Sales]) / COUNTD([Order Id])` (Tracks transactional size).
4. `Return Rate`: `SUM([Return Flag]) / COUNT([Order Id])` (Exposes product returns risk).
5. `Shipping Delay Bucket`: Logical group mapping delivery days into Fast, Standard, or Delayed classes.

## Dashboard Components & Interactive Features
* **Summary KPI Blocks:** Three top-level metric cards monitoring Total Sales, Average Profit Margin, and Return Rate.
* **Interactive Filtering Pane:** Implemented global controls for Region, Category, Customer Segment, and Campaign Channel.
* **Dashboard Action Filter:** Clicking a primary category segment or regional block dynamically filters the underlying trends table, enabling rapid analytical deep dives.

## Strategic Insights Summary
* **The Tables Leak:** The Tables sub-category acts as a severe margin drain, running net negative returns despite high consumer volume.
* **Fulfillment Friction:** Standard Class shipping exhibits high delivery delays, threatening long-term customer retention metrics.
* **Channel Efficiency:** Organic search traffic yields significantly higher average order values and margin health than high-volume Paid Search paths.

## Key Visual Assets
* Comprehensive Dashboard Assembly: `screenshots/full_dashboard.png`
* Time-Series Trends: `screenshots/sales_trend_view.png`
* Regional Map Performance: `screenshots/regional_performance_view.png`
* Categorical Product Profitability: `screenshots/category_profitability_view.png`
* Interactive State Verification: `screenshots/filter_interaction_view.png`
