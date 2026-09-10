# Global Retail Sales Dashboard — Power BI

An interactive Power BI dashboard analyzing global retail sales, profit, discounts, returns, products, customers, and shipping performance to support data-driven business decisions.

**Prepared by:** Velagada Dayana

---

## 📌 Project Overview

This project analyzes global retail sales data using Power BI. It covers sales, profit, discounts, returns, product performance, customer segments, and shipping performance, giving management actionable insights to improve profitability.

- Developed an interactive Global Retail Sales Dashboard using Power BI
- Analyzed sales data across regions, categories, and customer segments
- Evaluated Sales, Profit, Discounts, Returns, and Shipping Performance
- Identified high- and low-performing regions, products, and customer segments
- Built interactive KPIs, charts, and slicers to support decision-making

## 🧩 Business Problem

The company has large volumes of sales data but needed clarity on where it was profitable and where it was facing problems, including:

- Profit performance varying across regions
- High discounts potentially reducing overall profit
- Some customer segments contributing more profit than others
- Returned orders affecting sales and profitability
- Uneven product/category revenue performance
- Cost and profitability differences across shipping modes
- Variance in regional manager performance

## 🎯 Objectives

- Analyze sales, profit, returns, and regional performance to support data-driven decisions
- Identify which regions and segments drive the most profit
- Quantify how discounts and returns affect profitability
- Track actual sales against regional targets
- Enable drill-through analysis from Region → Product → Customer
- Give regional managers a single source of truth for performance

## 🗂️ Datasets

| Table | Type | Purpose |
|---|---|---|
| Orders | Fact Table | All sales transactions — order, ship, customer, product, sales, profit, discount, and quantity details |
| Returns | Dimension Table | Identifies which orders were returned (Order ID, Returned Yes/No, Market) |
| People | Dimension Table | Assigns a sales manager to each Region |

## 🧹 Data Cleaning & Transformation

- Checked for missing/null values and handled them where required
- Corrected data types for dates, numbers, and categorical columns
- Ensured Sales, Profit, Discount, and Quantity were treated as numerical fields
- Formatted Order Date and Ship Date as date fields
- Reviewed Postal Code values and handled nulls appropriately
- Checked for duplicate/unwanted records
- Verified categorical fields such as Region, Segment, Category, and Ship Mode

## 🔗 Data Model

- **Fact Table:** Orders
- **Dimension Tables:** Returns, People
- Orders ↔ Returns joined on **Order ID**
- Orders ↔ People joined on **Region**

## 📐 Key DAX Measures

```dax
Total Sales               = SUM(Orders[Sales])
Total Profit               = SUM(Orders[Profit])
Total Quantity              = SUM(Orders[Quantity])
Profit Margin %             = DIVIDE([Total Profit], [Total Sales], 0)
Return Rate %               = DIVIDE(COUNTROWS(Returned Orders), COUNTROWS(Orders), 0)
Average Shipping Cost       = AVERAGE(Orders[Shipping Cost])
Top 10 Products by Sales    = RANKX(ALL(Orders[Product Name]), [Total Sales])
```

## 📊 Dashboard KPI Cards

| KPI | Value |
|---|---|
| 💰 Total Sales | 12.64M |
| 📈 Total Profit | 1.47M |
| 📊 Profit Margin % | 11.61% |
| ↩️ Return Rate % | 4.68% |

## 📈 Dashboard Visuals

- Line Chart — Monthly Sales Trend
- Bar Chart — Sales by Region
- Donut Chart — Segment Contribution
- Bar Chart — Top 10 Products by Sales
- Gauge — Sales vs Target
- Region Details — Drill-Through Page

## 🔍 Key Business Insights

**Sales by Region:** Central leads with $2.8M in sales; Canada is the smallest region at $67K.

**Segment Contribution:** Consumer drives 51.48% of total sales ($6.51M), Corporate 30.25% ($3.82M), Home Office 18.27% ($2.31M).

**Top Products:** Apple Smart Phone leads at ~$87K in sales, followed by Cisco, Motorola, and Nokia smartphones.

**Profitability:** Central is the most profitable region (~$311.4K profit); Canada is the least (~$17.82K). Consumer is the most profitable segment (~$749.24K), followed by Corporate (~$441.21K) and Home Office (~$277.01K).

**Discounts:** Higher discounts tend to reduce profit margins — discounts above 30% can drive very low or negative profit.

**Returns:** Canada has the highest number of returned orders, suggesting issues around delivery, product quality, or customer expectations that need investigation.

**Shipping:** Standard Class is the dominant and most cost-effective shipping mode (~59% of sales/orders) and generates the highest overall profit among shipping modes.

**Regional Managers:** Performance is not fully balanced — Aaron Bergman (Central) manages the strongest region, with North also performing strongly.

## 💡 Recommendations

- **Optimize discount strategy** — avoid excessive discounts on already low-margin products
- **Focus on high-performing regions** — strengthen strategies in profitable regions while investigating weaker markets
- **Monitor returned orders** — identify root causes of high returns and take corrective action
- **Prioritize top-selling products** — maintain adequate inventory for strong performers
- **Improve segment-focused strategies** — target strategies at the most profitable customer segments

## ⚠️ Key Challenges

- Cleaning and transforming raw retail data (missing values, data types)
- Selecting the right visuals to represent performance without clutter
- Building accurate DAX measures for KPIs
- Setting up slicers, conditional formatting, and drill-through for interactivity
- Maintaining a clean, professional dashboard layout with multiple KPIs and visuals

## 🛠️ Power BI Techniques Applied

- **Power Query** — data cleaning, type conversion, de-duplication
- **Star-schema data modeling** — one fact table, two dimension tables
- **DAX functions** — SUM, AVERAGE, DIVIDE, COUNTROWS
- **Core visuals** — line, bar, and donut charts plus a KPI gauge
- **Slicers** for Year, Region, Segment, and Category
- **Drill-through pages** from Region → Product → Customer
- **Conditional formatting** to flag negative profit in red

## ✅ Conclusion

This project delivers an interactive Global Retail Sales Dashboard built in Power BI, analyzing sales, profit, discounts, returns, products, and shipping performance. It identifies high- and low-performing regions, products, and customer segments, quantifies the impact of discounts and returns on profitability, and compares shipping modes and regional performance — giving management a clear, data-driven view of the business.

---

## 📁 Repository Contents

- `Global_Retail_Sales_Project_PPT.pptx` — Full project presentation with methodology, DAX measures, and dashboard screenshots

## 🧰 Tools Used

- Power BI Desktop
- DAX
- Power Query
