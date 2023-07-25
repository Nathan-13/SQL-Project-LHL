# Final-Project-Transforming-and-Analyzing-Data-with-SQL

## Project/Goals
The goal of this project is to analyze e-commerce sales data to gain insights into customer behavior, 
product performance, and revenue patterns. By examining the data, I aim to answer questions related to 
top-selling products, revenue generated from different regions, and any patterns in customer buying behavior.

## Process
### Part 1: Loading csv Files into Database
I create a new Postgre database called ecommerce and set up tables for each .csv file provided for this project. 
The .csv files includes: 
	• all_sessions
	• products
	• analytics
	• sales_by_sku
	• sales_report

### Data Exploration and Preparation:
• I began by exploring the provided e-commerce sales data, which includes information 
about product orders, customer visits, and revenue generated.

• Cleaned data by handling missing values, inconsistent data formats, identify duplicates, inaccurate data 
and ensuring data integrity.

### Analyzing Revenue by City and Country:
• Used SQL queries to group data by city and country to calculate the total revenue generated from each location.
• Identified regions contributing the most to revenue.

### Identifying Top-Selling Products:
• Used SQL queries to group data by product SKU and calculate the total revenue for each product.
• Identified the top-selling products based on revenue.

## Results
(fill in what you discovered this data could tell you and how you used the data to answer those questions)

## Challenges 
• Data Quality: Dealing with missing or inconsistent data required thorough data cleaning and validation. Also there were 
incomplete data columns for example TotalTransactionRevenue, missing names of cities and countries, sales tax, 
and absent of uniques identifier in analytics table.
Query Performance: Optimizing complex SQL queries for large datasets to ensure efficient execution.
Limited Data Dimensions: Certain insights may require additional data dimensions, such as customer demographics 
or marketing channels.

## Future Goals
• Top-Selling Products: Identified the top-selling products based on revenue, which can help in optimizing inventory 
and marketing strategies.
• Revenue by City and Country: Discovered regions that contribute the most to revenue, allowing for targeted 
marketing efforts and sales strategies.
• Customer Behavior: Analyzed the average number of products ordered per visit, identifying potential upselling 
opportunities and improving customer experience.
