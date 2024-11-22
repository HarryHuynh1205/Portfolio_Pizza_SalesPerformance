## PIZZA SALES PERFORMANCE _ PORTFOLIO

## 1. Introduction:
**Project Title:** Pizza Sales Performance Analysis

**Overview:**
This project analyzes pizza sales data to identify key trends, customer preferences, and timely insights into sales patterns can significantly impact operations, from inventory management to marketing campaigns. This analysis simulates a real-world scenario to improve decision-making using historical sales data.

## 2. Why is this Data set?:
I chose this data set because it represents a realistic scenario in the food and beverage industry. The data set has 4 CSV Excel Sheets which help me practice with Sub-query and Join query.

## 3. Key Questions Explored:
   1. Which types of pizzas were most popular across different customer segments?
   2. What were the peak sales hours or days?
   3. How many pizzas were sold per day?
   4. Are there any trends in order sizes and types?

## 4. Data Preparation:
The project involved 4 CSV files containing:
   1. [Order_Details.csv](https://github.com/user-attachments/files/17858426/order_details.csv): Order_detail_id, Order_id, Pizza_id, Quantity, Unit_price, Total_price.
   2. [Orders.csv](https://github.com/user-attachments/files/17858575/orders.csv): Order_id, Date, Time.
   3. [Pizzas.csv](https://github.com/user-attachments/files/17858658/pizzas.csv): Pizza_id, Pizza_type_id, Size, Price.
   4. [Pizza_Types.csv](https://github.com/user-attachments/files/17858621/pizza_types.csv): Pizza_type_id, Name, Category, Ingredients.
   
Steps Taken:
  - Removed duplicates and handled missing values.
  - Standardized date-time format for analysis.
  - Joined datasets using Excel and SQL.

## 5. Skills and Tools Used:
### Tools:
  - Excel for data cleaning and calculations
  - SQL for additional analysis
  - Tableau for interactive dashboards

### Skills:
  - Data cleaning and transformation
  - Exploratory data analysis (EDA)
  - Data visualization and storytelling

### Data Cleaning/Preparation:
  - In the initial data preparation phase, we performed the following tasks:
  - Found and deleting duplicates.
  - Data cleaning and formatting.
  - Found the relationships for sheet to sheet

### Exploratory Data Analysis:
**EDA** involved exploring the sales data to answer key questions, such as:

  **1. Sales Trends**
   1. What are the total sales over time (daily, weekly or monthly)?
   2. Are there seasonal patterns or specific times (e.g., weekdays and weekends) with higher sales?
   3. What is the busiest time of day for pizza orders (e.g., breakfast, lunch or dinner)?
   4. Is there a steady growth or decline in sales revenue over the analyzed period?
   
  **2. Pizza Preferences**
   1. Which pizza category or size are the most popular?
   2. What is the average and total numbers of pizzas sold per order? 
   3. Compare the quantity of Total Quantity and Total Order per Category
   4. What were the best and lowest-paid pizza name?
   5. What kinds of pizza name generate more revenue?

## 5.5 Data Analysis:
Include some interesting code/features worked with in **MySQL**:
   1. **SELECT** * **FROM** table 1 **WHERE** cond = 2;
   2. **SELECT** * **FROM** table 1 **WHERE** cond = 2 **GROUP BY** column1 **ORDER BY** column2;
   3. **WITH window_ETC** 
      + ROW_NUMBER()
      + RANK()
   4. **JOIN Query**
   5. **Sub-Query**

## 6. Analysis and Insights:
Key Insights:
   1. People tended to buy pizzas increasingly on weekdays during lunch and dinner time, especially on Fridays (the busiest)
   2. The Classic Deluxe pizza was the most popular among customers; however, the Barbecue Chicken pizza brought the most revenue.
   3. Large (L) size of pizzas generated the highest revenue.
   4. Promotions on family-size orders could increase revenue further, especially on Fridays and weekends.

## 7. Visualizations:
The Tableau dashboard includes:
   1. A sales trend line chart to visualize peak hours.
   2. A bar chart showing the highest revenue per day in weeks.
   3. A heat map to identify peak sales days and times.
   4. A pie chart demonstrating which sizes were chosen most by revenue
   5. A second line chart showing the number of pizzas sold per day and estimating the numbers averagely
   6. A second bar chart to present the quantities of category pizzas selected by Total Number sold and Total Orders
   7. The Six of Bar Charts presenting the Best and Lowest-Paid Pizzas by Revenue, Total Quantity, Total Order
   _**8. Data Visualization (Tableau)**_

## 8. Conclusion:
The analysis revealed that large (L) pizzas generate the highest revenue, with Classic Deluxe pizza and Barbecue Chicken pizza being the most popular choices among customers. Sales peak during lunch and dinner hours and most crowded on Fridays, highlighting key times for promotional efforts.

_Recommendations:_
  - Focus marketing campaigns on weekends and evenings to capture peak sales times.
  - Launch combo deals or promotions featuring the most popular pizza types.
  - Improve inventory planning for pizza dough and their ingredients during peak periods.

## 9. Limitation:
  - Should add customer feedback data to analyze satisfaction levels.
  - Incorporate delivery time and costs for delivery optimization.
  - Be outdated because it was in 2015. 
  - Should add locations for being more particular

## 10. How to Access the Project:
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


## USING SQL TO FIND Exploratory Data Analysis (EDA):

1     **-- REVENUE BY HOURS --> Find the crowded time (breakfast, lunch, dinner)**
2     **-- PEAK HOURS**
3      SELECT `hour`, 
4             sum(Order_details.total_price) AS Total_revenue
5      FROM ( SELECT HOUR(orders.`time`) AS `Hour`, 
6                    Order_details.total_price 
7             FROM orders
8             LEFT JOIN Order_details ON Order_details.Order_id = orders.Order_id) AS Hour_Revenue
9      GROUP BY `hour`
10     ORDER BY 2 DESC; 
11     -- to find out the rush hours for scheduling more staffs and ordering more supplying materials

1      **-- REVENUE BY MONTHS --> Find the busiest months => hope to find seasonal patterns**
2      SELECT `month`, 
3              sum(Order_details.total_price) AS Total_revenue
4      FROM ( SELECT MONTH(orders.`date`) AS `month`, 
5                    Order_details.total_price 
6             FROM orders AS o
7             LEFT JOIN Order_details ON Order_details.Order_id = orders.Order_id) AS Hour_Revenue
8      GROUP BY `month`
9      ORDER BY sum(Total_revenue) DESC;

1      **-- AVG REVENUE per ORDER**
2      SELECT count(distinct O.order_id) AS Order_num, 
3      sum(OD.Total_price), 
4      sum(OD.Total_price)/count(distinct O.order_id) AS Avg_Per_Order
5      FROM orders AS o
6      LEFT JOIN Order_details AS OD ON OD.Order_id = O.Order_id; 


1      **-- REVENUE BY TOTAL ORDERS**
2      SELECT count(distinct O.order_id) AS Order_num, 
3      sum(OD.Total_price), 
4      sum(OD.Total_price)/count(distinct O.order_id) AS Avg_Per_Order
5      FROM orders AS O
6      LEFT JOIN Order_details AS OD ON OD.Order_id = O.Order_id;


1      **-- REVENUE BY SIZES**
2      -- REVENUE per Size
3      SELECT p.size, 
4      count(OD.quantity) AS total_quantity, 
5      sum(Od.Total_price) AS revenue
6      FROM pizzas As p
7      LEFT JOIN Order_details AS OD ON OD.pizza_id = p.pizza_id
8      GROUP BY p.size
9      ORDER BY count(OD.quantity) DESC; 
10      -- to know the favourite size and the amount of dough


1      **-- PIZZAS SOLD PER DAY:**
2      **-- Average Number of Pizza Sold Per Day**
3      SELECT sum(quantity)/31 AS Num_Pizza_perday
4     FROM order_details; 
5     -- to estimate the amount of pizza dough needed


1      **PIZZA SOLD PER DAY: DATE(date) + TOTAL QUANTITY**
2      **-- Number of Pizza Sold Per Day (1st -31st)**
3      SELECT SUBSTRING(`date`,9,2) AS `day`, 
4      sum(quantity) As total_quantity_perday
5      FROM orders AS o
6      JOIN Order_details AS OD ON OD.order_id = o.order_id
7      GROUP BY SUBSTRING(`date`,9,2); 
8      -- to schdelue to more staffs and prepare for more ingredients


1      -- I want to compare the number of category's pizza chosen by their Total Order vs Total Quantity, if there is interesting
2      **-- TOTAL QUANTITY sold by CATEGORY:** 
3      SELECT pt.category, 
4      sum(od.quantity) As total_quantity
5      FROM pizza_types as Pt
6      JOIN Pizzas AS p ON p.pizza_type_id = Pt.pizza_type_id
7      JOIN Order_details AS od ON od.pizza_id = p.pizza_id
8      GROUP BY pt.category; 
9      -- to understand the bestseller category which ingredients should be available in store

1      **-- TOTAL ORDERS sold by CATEGORY:** 
2      SELECT pt.category, 
3      count(DISTINCT o.order_id) As total_order
4      FROM pizza_types as Pt
5      JOIN Pizzas AS p ON p.pizza_type_id = Pt.pizza_type_id
6      JOIN Order_details AS od ON od.pizza_id = P.pizza_id
7      JOIN Orders AS o ON o.order_id = od.order_id
8      GROUP BY pt.category; 
9      -- to understand the bestseller category which ingredients should be available in store
10      -- Then I want to know more about the Revenue of each Category which I can help understand the customer preference and estimate the inventory suppliers

1      **-- TOTAL REVENUE sold by CATEGORY**
2      SELECT pt.category, 
3      sum(total_price) As Revenue
4      FROM pizza_types as Pt
5      JOIN Pizzas AS p ON p.pizza_type_id = Pt.pizza_type_id
6      JOIN Order_details AS od ON od.pizza_id = P.pizza_id
7      GROUP BY pt.category; 
8      -- to know the bestseller which should have more promotions or the lowest-paid pizza should be changed their recipes or getting more promotion if needed


1      **-- BEST and WORST PIZZA:**
2      -- BEST and WORST PIZZA:
3      -- (Top5) Name + Total QUANTITY 
4      SELECT  pt.name,
5      sum(od.quantity)
6      FROM pizza_types AS pt
7      JOIN pizzas AS p ON pt.pizza_type_id = p.pizza_type_id
8      JOIN order_details AS od ON od.pizza_id = p.pizza_id
9      GROUP BY pt.name
10      ORDER BY sum(od.quantity) DESC; 


1      -- (Bottom5) Name + Total QUANTITY
2      SELECT  pt.name,
3      sum(od.quantity)
4      FROM pizza_types AS pt
5      JOIN pizzas AS p ON pt.pizza_type_id = p.pizza_type_id
6      JOIN order_details AS od ON od.pizza_id = p.pizza_id
7      GROUP BY pt.name
8      ORDER BY sum(od.quantity) ASC;


1      -- (Top5) Name + Total REVENUE 
2      SELECT  pt.name,
3      sum(od.total_price)
4      FROM pizza_types AS pt
5      JOIN pizzas AS p ON pt.pizza_type_id = p.pizza_type_id
6      JOIN order_details AS od ON od.pizza_id = p.pizza_id
7      GROUP BY pt.name
8      ORDER BY sum(od.total_price) DESC;


1      -- (Bottom5) Name + Total REVENUE
2      SELECT  pt.name,
3      sum(od.total_price)
4      FROM pizza_types AS pt
5      JOIN pizzas AS p ON pt.pizza_type_id = p.pizza_type_id
6      JOIN order_details AS od ON od.pizza_id = p.pizza_id
7      GROUP BY pt.name
8      ORDER BY sum(od.total_price) ASC;


1      -- (Top5) Name + Total ORDERS
2      SELECT  pt.name,
3      count(distinct od.order_id) AS total_order
4      FROM pizza_types AS pt
5      JOIN pizzas AS p ON pt.pizza_type_id = p.pizza_type_id
6      JOIN order_details AS od ON od.pizza_id = p.pizza_id
7      JOIN orders AS o ON o.order_id = od. order_id
8      GROUP BY pt.name
9      ORDER BY  count(distinct od.order_id) DESC;


1      -- (Bottom5) Name + Total ORDERS
2      SELECT  pt.name,
3      count(distinct od.order_id) AS total_order
4      FROM pizza_types AS pt
5      JOIN pizzas AS p ON pt.pizza_type_id = p.pizza_type_id
6      JOIN order_details AS od ON od.pizza_id = p.pizza_id
7      JOIN orders AS o ON o.order_id = od. order_id
8      GROUP BY pt.name
9      ORDER BY  count(distinct od.order_id) ASC;







