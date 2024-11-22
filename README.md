## PIZZA SALES PERFORMANCE _ PORTFOLIO

## 1. Introduction
**Project Title:** Pizza Sales Performance Analysis

**Overview:**
This project analyzes pizza sales data to identify key trends, customer preferences, and timely insights into sales patterns can significantly impact operations, from inventory management to marketing campaigns. This analysis simulates a real-world scenario to improve decision-making using historical sales data.

## 2. Why is this Data set?
I chose this data set because it represents a realistic scenario in the food and beverage industry. The data set has 4 CSV Excel Sheets which help me practice with Sub-query and Join query.

## 3. Key Questions Explored
1. Which types of pizzas were most popular across different customer segments?
2. What were the peak sales hours or days?
3. How many pizzas were sold per day?
4. Are there any trends in order sizes and types?

## 4. Data Preparation
The project involved 4 CSV files containing:
1. [order_details.csv](https://github.com/user-attachments/files/17858426/order_details.csv): Order_detail_id, Order_id, Pizza_id, Quantity, Unit_price, Total_price.
2. **Orders:** Order_id, Date, Time.
3. **Pizzas:** Pizza_id, Pizza_type_id, Size, Price.
4. **Pizza Types:** Pizza_type_id, Name, Category, Ingredients.
   
Steps Taken:
- Removed duplicates and handled missing values.
- Standardized date-time format for analysis.
- Joined datasets using Excel and SQL.

## 5. Skills and Tools Used
### Tools:
- Excel for data cleaning and calculations
- SQL for additional analysis
- Tableau for interactive dashboards

### Skills:
- Data cleaning and transformation
- Exploratory data analysis (EDA)
- Data visualization and storytelling

### Data Cleaning/Preparation
- In the initial data preparation phase, we performed the following tasks:
- Found and deleting duplicates.
- Data cleaning and formatting.
- Found the relationships for sheet to sheet

### Exploratory Data Analysis
EDA involved exploring the sales data to answer key questions, such as:
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

## 5.5 Data Analysis
Include some interesting code/features worked with in **MySQL**:
1. **SELECT** * **FROM** table 1 **WHERE** cond = 2;
2. **SELECT** * **FROM** table 1 **WHERE** cond = 2 **GROUP BY** column1 **ORDER BY** column2;
3. **WITH window_ETC** 
   + ROW_NUMBER()
   + RANK()
4. **JOIN Query**
5.** Sub-Query**

## 6. Analysis and Insights
Key Insights:
1. People tended to buy pizzas increasingly on weekdays during lunch and dinner time, especially on Fridays (the busiest)
2. The Classic Deluxe pizza was the most popular among customers; however, the Barbecue Chicken pizza brought the most revenue.
3. Large (L) size of pizzas generated the highest revenue.
4. Promotions on family-size orders could increase revenue further, especially on Fridays and weekends.

## 7. Visualizations
The Tableau dashboard includes:
1. A sales trend line chart to visualize peak hours.
2. A bar chart showing the highest revenue per day in weeks.
3. A heat map to identify peak sales days and times.
4. A pie chart demonstrating which sizes were chosen most by revenue
5. A second line chart showing the number of pizzas sold per day and estimating the numbers averagely
6. A second bar chart to present the quantities of category pizzas selected by Total Number sold and Total Orders
7. The Six of Bar Charts presenting the Best and Lowest-Paid Pizzas by Revenue, Total Quantity, Total Order
8. **Data Visualization (Tableau)**

## 8. Conclusion
The analysis revealed that large (L) pizzas generate the highest revenue, with Classic Deluxe pizza and Barbecue Chicken pizza being the most popular choices among customers. Sales peak during lunch and dinner hours and most crowded on Fridays, highlighting key times for promotional efforts.

_Recommendations:_
- Focus marketing campaigns on weekends and evenings to capture peak sales times.
- Launch combo deals or promotions featuring the most popular pizza types.
- Improve inventory planning for pizza dough and their ingredients during peak periods.

## 9. Limitation
- Should add customer feedback data to analyze satisfaction levels.
- Incorporate delivery time and costs for delivery optimization.
- Be outdated because it was in 2015. 
- Should add locations for being more particular

## 10. How to Access the Project
Download the files from this repository:
- **1. Order_details.csv**
- **2. Orders.csv**
- **3. Pizzas.csv**
- **4. Pizza_types.csv**

Open the Tableau Packaged Workbook **([Pizza_Sales_Dashboard.twb](https://public.tableau.com/app/profile/harry.huynh/viz/Pizza_Sales_Dashboard_17321793664470/BestvsWorstPizzaDashboard))** in Tableau Public.

View the interactive dashboard here: 
- **OVERVIEW PIZZA DASHBOARD**
![Overview Pizza Dashboard](https://github.com/user-attachments/assets/1a9b8d69-95ea-44e2-84bc-4854d97f9cd6)

- **BEST vs WORST BEST DASHBOARD**
![Best vs Worst Pizza Dashboard](https://github.com/user-attachments/assets/89d83bc9-c052-48bf-adde-da25659532f0)
