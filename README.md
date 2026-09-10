Global Retail Sales Dashboard Using Power BI
Project Overview

The Global Retail Sales Dashboard is an interactive Business Intelligence project developed using Microsoft Power BI.

This project focuses on analyzing global retail sales data to understand Sales, Profit, Discounts, Returns, Products, Customers, Regions, Customer Segments, and Shipping Performance.

The dashboard provides interactive KPIs, charts, slicers, and drill-through analysis to help management understand business performance and make better data-driven decisions.

Business Problem

The company has a large amount of sales data, but it needs to understand where it is making profit and where it is facing problems.

The main business challenges are:

Profit performance varies across different regions.
High discounts may reduce overall profit.
Some customer segments contribute more profit than others.
Returned orders can affect sales and profitability.
Some products and categories generate more revenue than others.
Different shipping modes have different costs and profitability.
Regional manager performance may vary across locations.
Project Objectives
Analyze sales, profit, returns, and regional performance.
Identify which regions and customer segments drive the most profit.
Quantify how discounts and returns affect profitability.
Track actual sales against regional targets.
Identify top-performing products.
Analyze shipping mode performance.
Enable drill-through analysis from Region → Product → Customer.
Provide regional managers with a single source of truth for performance.
Support data-driven business decisions.
Tools & Technologies
Microsoft Power BI
Power Query
DAX
Microsoft Excel
Data Cleaning
Data Transformation
Data Modeling
Data Visualization
Business Intelligence
Business Analytics
Dataset

The project uses the Global Superstore retail sales dataset.

Tables Used
Table	Type	Purpose
Orders	Fact Table	Contains all sales transactions including order, ship, customer, product, sales, profit, discount, and quantity details
Returns	Dimension Table	Identifies which orders were returned
People	Dimension Table	Assigns a sales manager to each region
Important Fields
Order ID
Order Date
Ship Date
Ship Mode
Customer
Segment
Market
Region
Category
Sub-Category
Product Name
Sales
Quantity
Discount
Profit
Shipping Cost
Order Priority
Project Workflow
1. Data Collection

Collected the Global Superstore dataset containing sales, customer, product, shipping, and return information.

2. Data Cleaning & Transformation

Used Power Query to:

Check and handle missing/null values.
Correct data types for dates, numbers, and categorical columns.
Ensure Sales, Profit, Discount, and Quantity were treated as numerical fields.
Format Order Date and Ship Date as date fields.
Review Postal Code values and handle null values appropriately.
Check duplicate and unwanted records.
Verify categorical fields such as Region, Segment, Category, and Ship Mode.
3. Data Modeling

Created a data model using:

Orders as the Fact Table
Returns as a Dimension Table
People as a Dimension Table
Relationships
Orders ↔ Returns using Order ID
Orders ↔ People using Region
Key DAX Measures

Total Sales = SUM(Orders[Sales])

Total Profit = SUM(Orders[Profit])

Total Quantity = SUM(Orders[Quantity])

Profit Margin % = DIVIDE([Total Profit], [Total Sales], 0)

Return Rate % = DIVIDE(COUNTROWS(Returned Orders), COUNTROWS(Orders), 0)

Average Shipping Cost = AVERAGE(Orders[Shipping Cost])

Top 10 Products by Sales = RANKX(ALL(Orders[Product Name]), [Total Sales])
Dashboard KPIs
KPI	Value
Total Sales	$12.64M
Total Profit	$1.47M
Profit Margin %	11.61%
Return Rate %	4.68%
Dashboard Visualizations

The dashboard includes:

Monthly Sales Trend — Line Chart
Sales by Region — Bar Chart
Segment Contribution — Donut Chart
Top 10 Products by Sales — Bar Chart
Sales vs Target — Gauge
Interactive Features
Year Slicer
Region Slicer
Segment Slicer
Category Slicer
Drill-through Analysis
Conditional Formatting
Interactive KPI Cards
DAX Measures
 Business Questions & Insights
1. Which regions have the highest and lowest profits?

Central is the most profitable region with approximately $311.40K profit.

Canada has the lowest profit at approximately $17.82K.

2. Are discounts reducing profits in some orders?

Yes. Higher discounts tend to reduce profit margins.

Deep discounts, especially above 30%, can result in very low or negative profit.

Therefore, discounts should be used selectively rather than across all orders.

3. Which customer segments are most profitable?

Consumer is the most profitable segment with approximately $749.24K profit.

Corporate comes second with approximately $441.21K.

Home Office has the lowest profit at approximately $277.01K.

Therefore, Consumer customers should remain a key focus while improving Home Office performance.

4. How many orders are returned per region?

Canada has the highest number of returned orders and is the main region requiring attention.

The business should investigate return-related issues, particularly around delivery, product quality, and customer expectations.

5. Which products generate the most revenue?

Apple Smart Phone is the top-selling product, generating approximately $87K in sales.

Other strong-performing products include:

Cisco Smart Phone
Motorola Smart Phone
Nokia Smart Phone
6. Which shipping modes are most cost-effective?

Standard Class is the dominant and most cost-effective shipping mode.

It accounts for roughly 59% of sales/orders and generates the highest overall profit among shipping modes.

The business should encourage Standard Class where fast delivery is not essential.

7. Are regional sales managers achieving balanced performance?

No. Regional performance is not fully balanced.

Aaron Bergman – Central manages the strongest region, while North is also performing strongly.

Key Business Insights
Central is the strongest region in terms of profitability.
Canada has the lowest profit and requires attention.
Canada also has the highest number of returned orders.
Consumer is the largest and most profitable customer segment.
Higher discounts can negatively affect profit margins.
Apple Smart Phone is the top-selling product among the highlighted products.
Standard Class is the dominant and cost-effective shipping mode.
Regional manager performance is not fully balanced.
Business Recommendations
Optimize Discount Strategy

Avoid excessive discounts on products where margins are already low.

Focus on High-Performing Regions

Strengthen sales strategies in profitable regions while investigating weaker markets.

Monitor Returned Orders

Identify the reasons behind high returns and take corrective action.

Prioritize Top-Selling Products

Maintain adequate inventory for products generating strong sales.

Improve Segment-Focused Strategies

Develop targeted strategies for customer segments contributing more profit.

Project Files
File / Folder	Description
Global_Retail_Sales_Dashboard.pbix	Power BI dashboard containing the data model, DAX measures, visuals, slicers, and interactive analysis
Dataset/	Contains the Global Superstore dataset used for analysis
Dashboard/	Contains Power BI dashboard screenshots
Documentation/	Contains project documentation and detailed analysis
PPT/	Contains the project presentation
README.md	Contains project overview, objectives, workflow, insights, and documentation
Power BI Techniques Applied
Power Query for data cleaning and transformation
Data type conversion
Data de-duplication
Data modeling
Fact and dimension tables
DAX measures
SUM
AVERAGE
DIVIDE
COUNTROWS
RANKX
Line Charts
Bar Charts
Donut Charts
KPI Cards
Gauge
Slicers
Drill-through
Conditional Formatting
Key Challenges
Cleaning and transforming raw retail data.
Handling missing values and incorrect data types.
Creating accurate DAX measures.
Selecting appropriate visualizations.
Creating meaningful KPIs.
Implementing interactive slicers and drill-through.
Maintaining a clean and professional dashboard layout.
Conclusion

The Global Retail Sales Dashboard successfully transforms raw retail sales data into meaningful and actionable business insights using Power BI.

The project analyzes Sales, Profit, Discounts, Returns, Products, Customer Segments, Regions, and Shipping Performance.

Through Power Query, DAX, data modeling, KPIs, charts, slicers, and drill-through analysis, the dashboard provides an interactive and comprehensive view of business performance.

The analysis identified high- and low-performing regions, products, and customer segments while also highlighting the impact of discounts and returned orders on profitability.

Overall, this project demonstrates practical skills in Data Analytics, Business Intelligence, Power BI, Power Query, DAX, Data Cleaning, Data Modeling, and Data Visualization.

Future Enhancements
Automated data refresh
Real-time data integration
Sales forecasting
Profit forecasting
Customer segmentation
Predictive analytics
Advanced KPI monitoring
Skills Demonstrated

Power BI | Power Query | DAX | Data Cleaning | Data Transformation | Data Modeling | Data Visualization | Business Intelligence | Business Analytics | Excel
