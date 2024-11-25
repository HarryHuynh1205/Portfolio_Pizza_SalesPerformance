## PIZZA SALES PERFORMANCE _ PORTFOLIO

## TABLE OF CONTENT
1. [INTRODUCTION](#INTRODUCTION)
2. [KEY QUESTIONS](#KEY-QUESTIONS)
3. [SKILLS vs TOOLS](#SKILLS-vs-TOOLS)
4. [ANALYSIS vs INSIGHTS](#ANALYSIS-vs-INSIGHTS)
5. [VISUALIZATIONS](#VISUALIZATIONS)
6. [CONCLUSION](#CONCLUSION)
7. [HOW TO ACCESS THE PROJECT](#HOW-TO-ACCESS-THE-PROJECT)
8. [USING SQL QUERIES](#USING-SQL-QUERIES)

## 1. INTRODUCTION:
**Project Title:** Pizza Sales Performance Analysis

**Overview:**
This project analyzes pizza sales data to identify key trends, customer preferences, and timely insights into sales patterns can significantly impact operations, from inventory management to marketing campaigns. This analysis simulates a real-world scenario to improve decision-making using historical sales data.

**Why is this Data set?**
I chose this data set because it represents a realistic scenario in the food and beverage industry. The data set has 4 CSV Excel Sheets which help me practice with Sub-query and Join query.

## 2. KEY QUESTIONS:

**Key Questions** 
   1. Which types of pizzas were most popular across different customer segments?
   2. What were the peak sales hours or days?
   3. How many pizzas were sold per day?
   4. Are there any trends in order sizes and types?
      
**Dataset**  

  The project involved 4 CSV files containing:
   1. [Order_Details.csv](https://github.com/user-attachments/files/17858426/order_details.csv): Order_detail_id, Order_id, Pizza_id, Quantity, Unit_price, Total_price.
   2. [Orders.csv](https://github.com/user-attachments/files/17858575/orders.csv): Order_id, Date, Time.
   3. [Pizzas.csv](https://github.com/user-attachments/files/17858658/pizzas.csv): Pizza_id, Pizza_type_id, Size, Price.
   4. [Pizza_Types.csv](https://github.com/user-attachments/files/17858621/pizza_types.csv): Pizza_type_id, Name, Category, Ingredients.

The data link source from Kaggle: [Pizza Sales Data](https://www.kaggle.com/datasets/mysarahmadbhat/pizza-place-sales)

## 3. SKILLS vs TOOLS:
### Tools:
  - Excel for data cleaning and calculations
  - SQL for additional analysis
  - Tableau for interactive dashboards

### Skills:
  - Data cleaning and transformation
  - Exploratory data analysis (EDA)
  - Data visualization and storytelling

### Data Cleaning/Preparation:
In the initial data preparation phase, we performed the following tasks:
  - Removed duplicates and handled missing values.
  - Data cleaning and formatting.
  - Standardized date-time format for analysis
  - Found the relationships for sheet to sheet
  - Joined datasets using Excel and SQL

### Exploratory Data Analysis:
**EDA** involved exploring the sales data to answer key questions, such as:

  **1. Sales Trends**
   1. What are the total sales over time (daily, weekly or monthly)?
   2. What is the busiest time of day for pizza orders (e.g., breakfast, lunch or dinner)?
   3. Is there a steady growth or decline in sales revenue over the analyzed period?
   
  **2. Pizza Preferences**
   1. Which pizza category or size are the most popular?
   2. What is the average and total numbers of pizzas sold per day? 
   3. Compare the quantity of Total Quantity and Total Order per Category
   4. What were the best and lowest-paid pizza name?

### Data Analysis:
Include some interesting code/features worked with in **MySQL**:
   1. **SELECT** * **FROM** table 1 **WHERE** cond = 2;
   2. **SELECT** * **FROM** table 1 **WHERE** cond = 2 **GROUP BY** column1 **ORDER BY** column2;
   3. **WITH window_ETC** 
      + ROW_NUMBER()
      + RANK()
   4. **JOIN Query**
   5. **SUB-Query**

## 4. ANALYSIS vs INSIGHTS:

Key Insights:
   1. People tended to buy pizzas increasingly on weekdays during lunch and dinner time, especially on Fridays (the busiest)
   2. The Classic Deluxe pizza was the most popular among customers; however, the Barbecue Chicken pizza brought the most revenue.
   3. The Large(L) size of pizzas generated the highest revenue.
   4. Promotions on family-size orders could increase revenue further, especially on Fridays and weekends.

## 5. VISUALIZATIONS:

The Tableau dashboard includes:
   1. A sales trend **line chart** to visualize peak hours.
   2. A **bar chart** showing the highest revenue per day in weeks.
   3. A **pie chart** demonstrating which sizes were chosen most by revenue
   4. A second **line chart** showing the number of pizzas sold per day and estimating the numbers averagely
   5. A second **bar chart** to present the quantities of category pizzas selected by Total Number sold and Total Orders
   6. The Six of **Bar Charts** presenting the Best and Lowest-Paid Pizzas by Revenue, Total Quantity, Total Order
   7. **_Data Visualization_ ([Pizza_Sales_Dashboard.twb](https://public.tableau.com/app/profile/harry.huynh/viz/Pizza_Sales_Dashboard_17321793664470/BestvsWorstPizzaDashboard))**

## 6. CONCLUSION:

The analysis revealed that large (L) pizzas generate the highest revenue, with Classic Deluxe pizza and Barbecue Chicken pizza being the most popular choices among customers. Sales peak during lunch and dinner hours and most crowded on Fridays, highlighting key times for promotional efforts.

_Recommendations:_
  - Focus marketing campaigns on weekends and evenings to capture peak sales times.
  - Launch combo deals or promotions featuring the most popular pizza types.
  - Improve inventory planning for pizza dough and their ingredients during peak periods.

_Limitation:_
  - Should add customer feedback data to analyze satisfaction levels.
  - Incorporate delivery time and costs for delivery optimization.
  - Be outdated because it was in 2015. 
  - Should add locations for being more particular

## 7. HOW TO ACCESS THE PROJECT:

Download the files from this repository:

  - **1. [Order_Details.csv](https://github.com/user-attachments/files/17858426/order_details.csv)**
  - **2. [Orders.csv](https://github.com/user-attachments/files/17858575/orders.csv)**
  - **3. [Pizzas.csv](https://github.com/user-attachments/files/17858658/pizzas.csv)**
  - **4. [Pizza_Types.csv](https://github.com/user-attachments/files/17858621/pizza_types.csv)**

Open the Tableau Packaged Workbook **([Pizza_Sales_Dashboard.twb](https://public.tableau.com/app/profile/harry.huynh/viz/Pizza_Sales_Dashboard_17321793664470/BestvsWorstPizzaDashboard))** in Tableau Public.

View the interactive dashboard here: 
- **OVERVIEW PIZZA DASHBOARD**
![Overview Pizza Dashboard](https://github.com/user-attachments/assets/1a9b8d69-95ea-44e2-84bc-4854d97f9cd6)

- **BEST vs WORST BEST DASHBOARD**
![Best vs Worst Pizza Dashboard](https://github.com/user-attachments/assets/89d83bc9-c052-48bf-adde-da25659532f0)


## 8. USING SQL QUERIES:

```sql

-- A. OVERALL INFORMATION:
-- 1. TOTAL REVENUE
      SELECT sum(total_price)
      FROM order_details;

-- 2. AVERAGE REVENUE PER ORDER
      SELECT count( distinct order_id) AS Total_Orders, 
             sum(total_price)/count( distinct order_id)  AS Avg_Per_Order
      FROM order_details;

-- 3. TOTAL ORDERS
      SELECT count(order_id)
      FROM orders;

-- 4. TOTAL PIZZAS SOLD
      SELECT sum(quantity) AS Total_Pizzas
      FROM order_details;

-- 5. TOTAL PIZZA TYPES
      SELECT count(pizza_type_id) AS Pizza_Types
      FROM pizza_types;






-- B. EXPLORATORY DATA ANALYSIS (EDA):
-- SALES TRENDS
-- 1. IS THERE A STEADY GROWTH OR DECLINE IN SALES REVENUE OVER THE ANALYZED PERIOD?
      SELECT `month`,
             sum(Total_revenue)
      FROM ( SELECT SUBSTRING(`date`,6,2) AS `month`,
                    Order_details.total_price AS Total_revenue
             FROM orders
             LEFT JOIN Order_details ON Order_details.Order_id = orders.Order_id) AS Hour_Revenue
      GROUP BY SUBSTRING(`date`,6,2)
      ORDER BY 1; 
-- Sales Figures were fluctuated in 2015.


-- AVG REVENUE per ORDER
      SELECT count(distinct O.order_id) AS Order_num, 
             sum(OD.Total_price), 
             sum(OD.Total_price)/count(distinct O.order_id) AS Avg_Per_Order
      FROM orders AS O
      LEFT JOIN Order_details AS OD ON OD.Order_id = O.Order_id; 


-- 2.  WHAT IS THE BUSIEST TIME OF DAY FOR PIZZA ORDERS (E.G., BREAKFAST, LUNCH OR DINNER)?
-- PEAK HOURS
      SELECT `hour`,
             sum(Total_revenue)
      FROM ( SELECT HOUR(orders.`time`) AS `Hour`,
             Order_details.total_price AS Total_revenue
             FROM orders
             LEFT JOIN Order_details ON Order_details.Order_id = orders.Order_id) AS Hour_Revenue
      GROUP BY `hour`
      ORDER BY 2 DESC; 
-- the rush hours at lunch and dinner times -> scheduling more staffs and ordering more supplying materials


-- 3. WHAT ARE THE TOTAL SALES OVER TIME (DAILY OR MONTHLY)?
-- DAILY:
-- Number of Pizza Sold Per Day (Average)
      SELECT sum(quantity)/31 AS Num_Pizza_perday
      FROM order_details;
-- to estimate the amount of pizza dough needed (1600)


-- NUMBER OF PIZZA SOLD PER DAY 
      SELECT SUBSTRING(`date`,9,2) AS `day`,
             sum(quantity) As total_quantity_perday
      FROM orders AS o
      JOIN Order_details AS OD ON OD.order_id = o.order_id
      GROUP BY SUBSTRING(`date`,9,2)
      ORDER BY sum(quantity) DESC;
-- The busiest days on 15th and 1st day -> to schdelue to more staffs and prepare for more ingredients


-- MONTHLY
      SELECT SUBSTRING(`date`,6,2) AS `month`,
             sum(quantity) As total_quantity_perday
      FROM orders AS o
      JOIN Order_details AS OD ON OD.order_id = o.order_id
      GROUP BY SUBSTRING(`date`,6,2)
      ORDER BY sum(quantity) DESC;
-- to schdelue to more staffs and prepare for more ingredients






-- C. PIZZA PREFERENCES
-- 1. WHICH PIZZA CATEGORY OR SIZE ARE THE MOST POPULAR?
-- PIZZA CATEGORY (top quantity and revenue)
      SELECT pt.category, 
             count(od.quantity) As total_quantity,
             sum(total_price) As Total_Revenue
      FROM pizza_types as Pt
      JOIN Pizzas AS p ON p.pizza_type_id = Pt.pizza_type_id
      JOIN Order_details AS od ON od.pizza_id = P.pizza_id
      GROUP BY pt.category;
-- The Classic category were the best seller


-- PIZZA SIZES:
      SELECT p.size,
             count(OD.quantity) AS total_quantity,
             sum(Od.Total_price) AS revenue
      FROM pizzas As p
      LEFT JOIN Order_details AS OD ON OD.pizza_id = p.pizza_id
      GROUP BY p.size
      ORDER BY count(OD.quantity) DESC;
-- to know the favourite size and the amount of dough

-- 2. COMPARE THE QUANTITY OF TOTAL QUANTITY AND TOTAL ORDER PER CATEGORY
-- TOTAL QUANTITY BY CATEGORY
      SELECT pt.category, 
             sum(od.quantity) As total_quantity
      FROM pizza_types as Pt
      JOIN Pizzas AS p ON p.pizza_type_id = Pt.pizza_type_id
      JOIN Order_details AS od ON od.pizza_id = p.pizza_id
      GROUP BY pt.category;
-- to understand the bestseller category which ingredients should be available in store


-- TOTAL ORDERS BY CATEGORY
      SELECT pt.category, 
             count(DISTINCT o.order_id) As total_order
      FROM pizza_types as Pt
      JOIN Pizzas AS p ON p.pizza_type_id = Pt.pizza_type_id
      JOIN Order_details AS od ON od.pizza_id = P.pizza_id
      JOIN Orders AS o ON o.order_id = od.order_id
      GROUP BY pt.category;
-- to understand the bestseller category which ingredients should be available in store


-- 3. WHAT WERE THE BEST AND LOWEST-PAID PIZZA NAME?
-- BEST AND WORST PIZZA:
-- (TOP5) NAME + TOTAL QUANTITY 
      SELECT  pt.name,
              sum(od.quantity)
      FROM pizza_types AS pt
      JOIN pizzas AS p ON pt.pizza_type_id = p.pizza_type_id
      JOIN order_details AS od ON od.pizza_id = p.pizza_id
      GROUP BY pt.name
      ORDER BY sum(od.quantity) DESC; 


-- (BOTTOM5) NAME + TOTAL QUANTITY
      SELECT  pt.name,
              sum(od.quantity)
      FROM pizza_types AS pt
      JOIN pizzas AS p ON pt.pizza_type_id = p.pizza_type_id
      JOIN order_details AS od ON od.pizza_id = p.pizza_id
      GROUP BY pt.name
      ORDER BY sum(od.quantity) ASC;


-- (TOP5) NAME + TOTAL REVENUE 
      SELECT  pt.name,
              sum(od.total_price)
      FROM pizza_types AS pt
      JOIN pizzas AS p ON pt.pizza_type_id = p.pizza_type_id
      JOIN order_details AS od ON od.pizza_id = p.pizza_id
      GROUP BY pt.name
      ORDER BY sum(od.total_price) DESC;


-- (BOTTOM5) NAME + TOTAL REVENUE
      SELECT  pt.name,
              sum(od.total_price)
      FROM pizza_types AS pt
      JOIN pizzas AS p ON pt.pizza_type_id = p.pizza_type_id
      JOIN order_details AS od ON od.pizza_id = p.pizza_id
      GROUP BY pt.name
      ORDER BY sum(od.total_price) ASC;


-- (TOP5) NAME + TOTAL ORDERS
      SELECT  pt.name,
              count(distinct od.order_id) AS total_order
      FROM pizza_types AS pt
      JOIN pizzas AS p ON pt.pizza_type_id = p.pizza_type_id
      JOIN order_details AS od ON od.pizza_id = p.pizza_id
      JOIN orders AS o ON o.order_id = od. order_id
      GROUP BY pt.name
      ORDER BY  count(distinct od.order_id) DESC;


-- (BOTTOM5) NAME + TOTAL ORDERS
      SELECT  pt.name,
              count(distinct od.order_id) AS total_order
      FROM pizza_types AS pt
      JOIN pizzas AS p ON pt.pizza_type_id = p.pizza_type_id
      JOIN order_details AS od ON od.pizza_id = p.pizza_id
      JOIN orders AS o ON o.order_id = od. order_id
      GROUP BY pt.name
      ORDER BY  count(distinct od.order_id) ASC;
