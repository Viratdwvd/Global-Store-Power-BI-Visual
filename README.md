<img width="1161" height="658" alt="image" src="https://github.com/user-attachments/assets/1ef53d70-b479-45d8-af98-7d731e65dfbb" /><img width="1161" height="658" alt="image" src="https://github.com/user-attachments/assets/95c1ebae-a9bc-4bc4-9f09-d6d1d7446fdd" />📊 Global Sales Performance Dashboard | Power BI
📌 Project Overview
This project presents an end-to-end Sales Performance Dashboard built using Power BI to analyze business performance across time, customers, products, regions, and shipping modes.
The solution uses a star schema data model, Power Query transformations, and DAX measures to deliver interactive insights for decision-making.
🎯 Business Objectives
Monitor overall Sales, Profit, and Orders
Identify top-performing products and categories
Analyze regional performance
Track sales trends over time
Enable dynamic filtering and drill-down analysis
🗂 Dataset
Dataset Used: Global Superstore
⭐ Fact Table
Fact_Sales
Order ID
Order Date Clean
Ship Date Clean
Customer ID
Product ID
Sales
Profit
Quantity
Discount
Shipping Cost
Market
Region
Segment
Ship Mode
Order Priority

⭐ Dimension Tables

🏗 Data Model

A Star Schema was implemented:
One-to-Many relationships from dimensions → Fact table
Single direction filtering
Dedicated Date table (marked as Date Table)
Optimized for performance and accurate aggregations
⚙ Data Transformation (Power Query)
Removed unnecessary columns
Cleaned and standardized text fields
Created Order Date Clean & Ship Date Clean
Corrected data types
Created dimension tables from staging query
Disabled load for staging query (performance optimization)

🧮 DAX Measures
Core Measures
Total Sales = SUM(Fact_Sales[Sales])
Total Profit = SUM(Fact_Sales[Profit])
Total Orders = DISTINCTCOUNT(Fact_Sales[Order ID])
Profit Margin = DIVIDE([Total Profit], [Total Sales])
Time Intelligence
Sales YTD = TOTALYTD([Total Sales], Dim_Date[Dim_Date])
Profit YTD = TOTALYTD([Total Profit], Dim_Date[Dim_Date])
YoY Growth =
DIVIDE(
    [Total Sales] -
    CALCULATE([Total Sales], SAMEPERIODLASTYEAR(Dim_Date[Dim_Date])),
    CALCULATE([Total Sales], SAMEPERIODLASTYEAR(Dim_Date[Dim_Date]))
)


📊 Dashboard Features
🔹 KPI Cards
Total Sales
Total Profit
Total Orders
Profit Margin %

🔹 Visualizations
📈 Sales Trend Over Time

🧩 Sales by Category (Treemap / Donut)
📦 Top Products by Sales & Profit
🌍 Regional Performance
🔹 Slicers
Order Date range
Region
Segment
Category

🔹 Interactivity
Cross filtering
Drill-down using Date hierarchy
Dynamic measure updates

⏱ Time Intelligence Implementation
Year → Month drill-down hierarchy
YTD calculations
YoY growth analysis
Continuous date axis for trend analysis


📈 Key Insights
Technology category generates the highest revenue.
Certain high-sales products have lower profit margins.
Sales show strong growth trend over time.
Regional performance varies significantly across markets.
Profitability is impacted by discount levels.

🛠 Tools & Technologies
Power BI Desktop
Power Query
DAX
Data Modeling (Star Schema)

📂 Report Pages
🧭 Overview Page

High-level KPIs
Category performance
Sales trend

📦 Product Analysis Page
Top-performing products
Profitability comparison

🚀 How to Use
Open the .pbix file
Click Refresh
Use slicers to filter data
Drill down through visuals for detailed insights


⭐ Project Highlights
End-to-end BI workflow
Optimized star schema model
Time intelligence using a dedicated Date table
Interactive and business-ready dashboard
Performance-focused Power Query design


👤 Author

Virat Dwivedi
Aspiring Data Analyst | Power BI Developer
