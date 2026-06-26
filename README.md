# PitchSide-Pro-PowerBI-Dashboard
PitchSide Pro - Executive Analytics Hub (World Champs BCN)

# PitchSide Pro - Executive Analytics Hub | Power BI Dataviz World Champs 🏆

An executive-ready, 5-page interactive Power BI dashboard meticulously engineered for **PitchSide Pro's** digital transformation and strategic market positioning. This project was developed as an official entry for the prestigious **Power BI Dataviz World Champs** global data visualization competition.

---

## 🔗 Live & Interactive Report
*If you have a Publish to Web URL, insert it here:* 
👉 **[Launch Interactive Power BI Report (Live)]_**
**https://community.fabric.microsoft.com/t5/Contests-Gallery/PitchSide-Pro-Executive-Analytics-Hub-Round-1/m-p/5230098#M3150**

---

## 📊 Comprehensive Page-by-Page Breakdown

### 📱 Page 1: Executive Pulse
* **Strategic Purpose:** Designed for C-suite executives to monitor the core financial health and top-line performance metrics of the business at a single glance.
* **Key Performance Indicators (KPIs):**
  * `Total Net Revenue` (Overall profit scaling)
  * `YoY Net Revenue Growth %` (Year-over-Year growth velocity)
  * `Total Sessions` (Top-of-funnel traffic volume)
  * `Conversion Rate %` (Digital store efficiency)
* **Featured Visualizations:**
  * **Net Revenue Trajectory vs. Prior Year** *(Area/Line Chart)*: Seamless tracking of historical revenue trends against previous-year benchmarks.
  * **Holiday vs. Non-Holiday Revenue Share** *(Donut Chart)*: Clean categorical breakdown illustrating the impact of seasonal holiday peaks.
  * **Net Revenue Contribution by Macro Region** *(Horizontal Bar Chart)*: Instant geographical distribution showing performance across EMEA, Americas, and APAC.


---

### ⚽ Page 2: Football & Seasonality Pulse
* **Strategic Purpose:** Captures the intersection of sports retail and global event dynamics by aligning sales with major international football tournament windows and peak holiday cycles.
* **Key Metrics Focused:** Dynamic seasonal shifts, tournament month surges, and event-driven revenue spikes.
* **Featured Visualizations:**
  * **Tournament Window Trend Analysis** *(Line Chart)*: Highlights revenue velocity specifically during global sporting events.
  * **Seasonal Index & Peak Performance** *(Matrix/Column Charts)*: Breaks down monthly performance to identify predictable sales cycles.


---

### 📦 Page 3: Product & Launch Analytics
* **Strategic Purpose:** Evaluates the commercial success of limited-edition releases, product category expansions, and inventory lifecycle health.
* **Key Performance Indicators (KPIs):**
  * `Total Gross Revenue`
  * `Total Discounts Muted` (Tracking discount leakages)
  * `Product Line Margin %`
* **Featured Visualizations:**
  * **Product Category Performance Matrix** *(Matrix View)*: A deep dive into categories to analyze which products drive high volume vs. high margin.
  * **Limited Edition Launch Tracker** *(Bar Chart)*: Compares baseline products against special tournament-themed drops.

---

### 🌐 Page 4: Channel Expansion & Traffic
* **Strategic Purpose:** Bridges marketing investments with actual sales outcomes by dissecting the digital acquisition funnel across multiple platforms.
* **Key Performance Indicators (KPIs):**
  * `Total Web Sessions`
  * `Bounce Rate %`
  * `Funnel Conversion Efficiency`
* **Featured Visualizations:**
  * **Acquisition Funnel & Conversion Rates** *(Funnel/Bar Visuals)*: Tracks customer journeys from anonymous traffic to settled orders.
  * **Channel Contribution Scatter** *(Scatter Chart)*: Visualizes which online channels (Organic, Paid, Social) deliver high-quality converting traffic.


---

### 📈 Page 5: Strategic Growth & Scenario Planning
* **Strategic Purpose:** Empowers corporate leaders with exploratory tools and advanced AI-driven features to conduct root-cause analysis and map future expansion scenarios.
* **Key Elements & Advanced Visuals:**
  * **Net Revenue Drivers Breakdown** *(Decomposition Tree)*: An interactive root-cause engine allowing executives to break down revenue figures dynamically by `MacroRegion` ➡️ `Category` ➡️ `Channel`.
  * **Regional Market Position: Volume vs. Net Value** *(Scatter Chart)*: Plots `Total Orders` (X-axis) against `Total Net Revenue` (Y-axis) grouped by market regions to evaluate market efficiency.
  * **Automated Executive Insights** *(Smart Narrative)*: AI-generated textual summaries that automatically call out maximum performance anomalies and key data trends.


---

## 🏗️ Data Architecture & Modeling

The project is built on a highly optimized **Star Schema** to ensure fast calculation processing times and smooth cross-filtering behavior across all 5 pages.

* **Fact Tables:** `Sales`, `Traffic`
* **Dimension Tables:** `Date`, `Product`, `Geography`, `Channel`
* **Data Cleansing:** Implemented via Power Query (ETL) to clean null values, normalize boolean flags into analytical categories (e.g., converting `0/1` flags into descriptive titles like `"Regular Days"` and `"Holiday Peaks"`), and build robust relationship keys.

---

## 🛠️ Core DAX Framework

Below are snippets of the robust, production-grade DAX measures implemented in this solution:

```dax
// 1. Core Financial Performance
Total Net Revenue = SUM(Sales[NetRevenue])

Net Revenue LY = CALCULATE([Total Net Revenue], SAMEPERIODLASTYEAR('Date'[Date]))

YoY Net Revenue Growth % = DIVIDE([Total Net Revenue] - [Net Revenue LY], [Net Revenue LY], 0)

// 2. Traffic & Conversion Funnel
Total Sessions = SUM(Traffic[Sessions])

Total Orders = DISTINCTCOUNT(Sales[OrderID])

Conversion Rate % = DIVIDE([Total Orders], [Total Sessions], 0)

// 3. Profit Protection Metrics
Total Discounts = SUM(Sales[DiscountAmount])

Average Order Value (AOV) = DIVIDE([Total Net Revenue], [Total Orders], 0)```

-------------------------------------------------------------------------

## Created & Designed by Al-Qasem Abukashef
