# 🌍 Global Retail Sales Dashboard — Power BI

An interactive Power BI dashboard analyzing global retail sales, profit, discounts, returns, products, customers, and shipping performance to support data-driven business decisions.

**Prepared by:** Velagada Dayana

![Total Sales](https://img.shields.io/badge/Total%20Sales-12.64M-blue)
![Total Profit](https://img.shields.io/badge/Total%20Profit-1.47M-green)
![Profit Margin](https://img.shields.io/badge/Profit%20Margin-11.61%25-brightgreen)
![Return Rate](https://img.shields.io/badge/Return%20Rate-4.68%25-orange)

---

## 📸 Dashboard Preview

### Main Dashboard
[Global Retail Sales Dashboard](assets/main_dashboard.png)

### Region Details — Drill-Through Page
[Region Details](assets/region_details.png)

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

Source data: `GlobalSuperstore_Data.xlsx`

| Table | Type | Purpose | Key Columns |
|---|---|---|---|
| **Orders** | Fact Table | All sales transactions | Order ID, Order Date, Ship Date, Ship Mode, Customer, Segment, Region, Market, Category, Sub-Category, Product Name, Sales, Quantity, Discount, Profit, Shipping Cost, Order Priority |
| **Returns** | Dimension Table | Identifies which orders were returned | Returned (Yes/No), Order ID, Market |
| **People** | Dimension Table | Assigns a sales manager to each Region | Person, Region |

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
Total Profit              = SUM(Orders[Profit])
Total Quantity             = SUM(Orders[Quantity])
Profit Margin %            = DIVIDE([Total Profit], [Total Sales], 0)
Return Rate %              = DIVIDE(COUNTROWS(Returned Orders), COUNTROWS(Orders), 0)
Average Shipping Cost      = AVERAGE(Orders[Shipping Cost])
Top 10 Products by Sales   = RANKX(ALL(Orders[Product Name]), [Total Sales])
```

## 📊 Dashboard KPI Cards

| KPI | Value |
|---|---|
| 💰 Total Sales | 12.64M |
| 📈 Total Profit | 1.47M |
| 📊 Profit Margin % | 11.61% |
| ↩️ Return Rate % | 4.68% |

## 📈 Dashboard Visuals

**Main Dashboard**

| Visual | Type | Description |
|---|---|---|
| Total Sales, Total Profit, Profit Margin %, Return Rate % | KPI Cards | High-level summary of overall business performance |
| Monthly Sales Trend | Line Chart | Tracks sales month-over-month across the year |
| Sales by Region | Bar Chart | Compares total sales across Central, South, North, Oceania, and Southeast Asia |
| Segment Contribution | Donut Chart | Breaks down sales share by Consumer, Corporate, and Home Office |
| Top 10 Products by Sales | Bar Chart | Ranks best-selling products (Apple, Cisco, Motorola, Nokia smartphones, etc.) |
| Sales vs Target | Gauge | Compares actual sales (12.64M) against a target of 25.29M |
| Year / Region / Segment / Category | Slicers | Interactive filters that update all visuals on the page |

**Region Details (Drill-Through Page)**

| Visual | Type | Description |
|---|---|---|
| Total Sales, Total Profit, Profit Margin % | KPI Cards | Region-level performance summary |
| Sales by Product | Bar Chart | Product-level sales for the selected region |
| Profit by Product | Bar Chart | Product-level profit for the selected region |
| Sales and Profit by Customer | Table | Customer-level breakdown with conditional formatting flagging negative profit in red |
| US Regional Map | Map Visual | Highlights sub-regions (e.g., North Central, South, West) within the selected region |

## 🔍 Key Business Insights (Q&A)

**Q1. Which regions have the highest and lowest profits?**
Central is the most profitable region, with about $311.40K in profit. Canada has the lowest profit, at about $17.82K.

**Q2. Are discounts reducing profits in some orders?**
Yes. Higher discounts tend to reduce profit margins. Deep discounts, especially above 30%, can result in very low or negative profit. Discounts should be used selectively rather than applied across all orders.

**Q3. Which segments are most profitable?**
Consumer is the most profitable segment, at about $749.24K in profit. Corporate comes second at about $441.21K. Home Office is the lowest at about $277.01K. Consumer should remain a key focus while improving Home Office performance.

**Q4. How many orders are returned per region?**
Canada has the highest number of returned orders and is the main region requiring attention. Other regions have comparatively fewer returns. This suggests return-related issues in Canada should be investigated, particularly around delivery, product quality, and customer expectations.

**Q5. Which products generate the most revenue?**
Apple Smart Phone is the top-selling product, generating approximately $87K in sales. Other strong products include Cisco Smart Phone, Motorola Smart Phone, and Nokia Smart Phone.

**Q6. Which shipping modes are most cost-effective?**
Standard Class is the dominant and most cost-effective shipping mode. It accounts for roughly 59% of sales/orders and generates the highest overall profit among shipping modes. The business should encourage Standard Class where fast delivery isn't essential.

**Q7. Are regional sales managers achieving balanced performance?**
No, performance is not fully balanced. Aaron Bergman (Central) manages the strongest region, and North is also performing strongly, while other regions lag behind.

**Q8. Which regions lead and lag in total sales?**
Central leads with $2.8M in sales, followed by South ($1.6M), North ($1.2M), and Oceania ($1.1M). Canada is the smallest region shown, at $67K in sales.

**Q9. How does each customer segment contribute to total sales?**
Consumer drives 51.48% of total sales ($6.51M), Corporate contributes 30.25% ($3.82M), and Home Office is the smallest segment at 18.27% ($2.31M).

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
- **DAX functions** — SUM, AVERAGE, DIVIDE, COUNTROWS, RANKX
- **Core visuals** — line, bar, and donut charts plus a KPI gauge
- **Slicers** for Year, Region, Segment, and Category
- **Drill-through pages** from Region → Product → Customer
- **Conditional formatting** to flag negative profit in red

## ✅ Conclusion

This project delivers an interactive Global Retail Sales Dashboard built in Power BI, analyzing sales, profit, discounts, returns, products, and shipping performance. It identifies high- and low-performing regions, products, and customer segments, quantifies the impact of discounts and returns on profitability, and compares shipping modes and regional performance — giving management a clear, data-driven view of the business.

---

## 📁 Repository Structure

```
├── Global_Retail_Sales_Project.pbix      # Power BI dashboard file
├── GlobalSuperstore_Data.xlsx            # Source data (Orders, Returns, People)
├── Global_Retail_Sales_Project_PPT.pptx  # Project presentation
├── assets/
│   ├── main_dashboard.png                # Main dashboard screenshot
│   └── region_details.png                # Region details drill-through screenshot
└── README.md
```

## 🚀 How to Use

1. Clone this repository
2. Open `Global_Retail_Sales_Project.pbix` in [Power BI Desktop](https://powerbi.microsoft.com/desktop/)
3. Explore the dashboard using the Year, Region, Segment, and Category slicers
4. Click on a region bar to drill through to the **Region Details** page

## 🧰 Tools Used

- Power BI Desktop
- DAX
- Power Query
- Microsoft Excel (source data)
