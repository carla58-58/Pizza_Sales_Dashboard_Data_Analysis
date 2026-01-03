# Pizza_Sales_Dashboard

**Interactive Power BI Dashboard powered by SQL**  
Pizza sales analytics: Orders, revenue, busiest days, top categories

**View Dashboard Screenshots:** 
- **Overview**: 
![Overview](https://github.com/carla58-58/Pizza_Sales_Dashboard_Data_Analysis/blob/main/image5.png)

- **Top Sellers**: 
![Top Sellers](https://github.com/carla58-58/Pizza_Sales_Dashboard_Data_Analysis/blob/main/image6.jpg)

## 1. Project Overview

**Objective:**  
Analyze pizza sales performance across dates, categories, and metrics (Jan 15-Dec data).

**Key Metrics Tracked:**
- **Peak day**: 8,176 orders (Friday)
- **Total orders**: 49,574
- **Top category**: Supreme (38% sales)
- Busiest times, revenue by pizza

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

## 3. Key Findings

- **Fridays peak** (8,176 orders—38% above average)
- **Supreme dominates** (38% revenue share)
- **Monthly growth** visible in trends
- **California #2** consistent performer
- **Worst sellers** easily identified for menu review

## 4. SQL Data Pipeline
Extracted all KPIs with production-ready queries:

-- Total Revenue
SELECT SUM(total_price) AS Total_Revenue FROM pizza_sales;

-- Friday Peak (Busiest Day)
SELECT DATENAME(DW, order_date) AS order_day, 
       COUNT(DISTINCT order_id) AS Total_orders
FROM pizza_sales
GROUP BY DATENAME(DW, order_date);

-- Avg Order Value ($31.81)
SELECT SUM(total_price)/COUNT(DISTINCT order_id) AS Avg_Order_Value 
FROM pizza_sales;

- **Full SQL**: ![SQL](https://raw.githubusercontent.com/carla58-58/Pizza_Sales_Dashboard_Data_Analysis/main/SQL_queries/queries.sql)


## 5. Technologies

📊 Power BI (full dashboard)

🗄️ SQL (ETL & KPIs)

🔗 DAX (KPIs, rankings, % calculations)

📈 Slicers & date intelligence

📊 Category breakdowns & top-N visuals

Pipeline: SQL → Power BI! 💾➡️📊.
