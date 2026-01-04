# Pizza_Sales_Dashboard

**Interactive Power BI Dashboard powered by SQL**  
Pizza sales analytics: Orders, revenue, busiest days, top categories

**View Dashboard Screenshots:** 
- **Overview**: 
![Overview](https://github.com/carla58-58/Pizza_Sales_Dashboard_Data_Analysis/blob/main/image5.png)

- **Top Sellers**: 
![Top Sellers](https://github.com/carla58-58/Pizza_Sales_Dashboard_Data_Analysis/blob/main/image6.jpg)

## 1. Data Pipeline Overview
- **Complete ETL Pipeline**:
Raw CSV (48K rows) → SQL Server Import → KPI Queries → Power Query Cleaning → DAX Measures → Interactive Dashboard

## 1. Project Overview

**Objective:**  
Analyze pizza sales performance across dates, categories, and metrics (Jan 15-Dec data).

**Key Metrics Tracked:**
- **Total Revenue**: $817,860 ✓
- **Total Orders**: 21,350 unique orders ✓  
- **Total Pizzas**: 49,574 sold ✓
- **Avg Order Value**: $38.30 ✓
- **Peak Day**: Friday (8,176 orders) ✓

**Dataset Features:**
- Date range (daily/monthly)
- Pizza categories/revenue/quantity
- Orders by day/time
- Top/worst performers

## 2. Dashboard Features

**Interactive Filters:**
✅ Date range (Jan15-Dec)
✅ Pizza category slicer
✅ Top/Bottom rankings

**Key Visualizations:**
- **KPIs**: Orders (8176 peak), Avg daily (38.1%)
- **Bar charts**: Busiest days (Fri>Sat), Top sellers (Supreme/California)
- **Line charts**: Monthly order trends
- **Pie charts**: % sales by category
- **Tables**: Top 5/5 worst pizzas

**Video Features Implemented:**
✅ New Card Visuals (June 2023 Power BI)
✅ Navigator buttons (Home ↔ Sellers)
✅ Action filters (click-to-filter)
✅ Power Query cleaning
✅ SQL → Power BI validation

## 3. Key Findings

- **Fridays peak** (8,176 orders—38% above average)
- **Supreme dominates** (38% revenue share)
- **Monthly growth** visible in trends
- **California #2** consistent performer
- **Worst sellers** easily identified for menu review

## 4. SQL Data Pipeline
Extracted all KPIs with production-ready queries:

-- 1. Total Revenue 
SELECT SUM(total_price) AS Total_Revenue FROM pizza_sales;

-- 2. Busiest Day (Friday Peak) 
SELECT DATENAME(DW, order_date) AS order_day, 
       COUNT(DISTINCT order_id) AS Total_orders
FROM pizza_sales GROUP BY DATENAME(DW, order_date);

-- 3. Avg Order Value ($38.30) 
SELECT SUM(total_price)/COUNT(DISTINCT order_id) AS Avg_Order_Value 
FROM pizza_sales;

-- 4-5. Additional: Total Pizzas, Orders per Day

- **Full SQL**: ![SQL](https://github.com/carla58-58/Pizza_Sales_Dashboard_Data_Analysis/blob/main/SQL_queries)


## 5. Technologies

📊 Power BI (full dashboard)

🗄️ SQL (ETL & KPIs)

🔗 DAX (KPIs, rankings, % calculations)

📈 Slicers & date intelligence

📊 Category breakdowns & top-N visuals

Pipeline: SQL → Power BI! 💾➡️📊.

## 6. End-to-End Workflow

**Step 1: Raw Data**  
`pizza_sales.csv` (48,620 pizza orders, Jan-Dec 2015)

**Step 2: SQL Server**  
- Import CSV → Create `pizza_sales` table  
- Write 10+ queries (KPIs, trends, rankings)  
- Export results → Document validation

**Step 3: Power BI**  
- Connect to SQL Server database  
- Power Query: Data cleaning/transformations  
- DAX: Custom measures (Avg Order Value, % calculations)  
- Build 2 dashboards + navigation buttons

**Step 4: Validation**  
All Power BI KPIs **match SQL query results exactly**

