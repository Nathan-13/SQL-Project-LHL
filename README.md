# Final-Project-Transforming-and-Analyzing-Data-with-SQL

## Project/Goals
This project analyzes e-commerce sales data to gain insights into customer behaviour, 
product performance, and revenue patterns. By examining the data, I aim to answer questions about 
top-selling products, revenue generated from different regions, and any patterns in customer buying behaviour.

## Process
### Part 1: Loading CSV Files into Database
I created a new Postgre database called e-commerce and set up tables for each .csv file provided for this project. 

The .csv files include: 

	• all_sessions

	• products

	• analytics

	• sales_by_sku

	• sales_report

### Data Exploration and Preparation:
• I began by exploring the provided e-commerce sales data, which includes information 
about product orders, customer visits, and revenue generated.

• Reviewed the schema and data in the "all_sessions" table to understand its structure, including columns like "city," "country," 
"transaction_revenue," and any other relevant information.

• Cleaned data by handling missing values, inconsistent data formats, identifying duplicates, inaccurate data and ensuring data integrity.

• Implement Quality Assurance (QA) process to ensure data consistency and accuracy,  involving thorough checks of complex query results.

### Analyzing Revenue by City and Country:
• Used SQL queries to group data by city and country to calculate the total revenue generated from each location.

• Identified regions contributing the most to revenue.

### Identifying Top-Selling Products:
• Used SQL queries to group data by product SKU and calculate the total revenue for each product.

• Identified the top-selling products based on revenue.

## Results
• 	Upon delving into the analytics and all_sessions tables, I gained invaluable insights into visitor 
behaviours and essential metrics like frequency, duration, product views, and engagement patterns. 
It was observed that customers who spent more time on the site viewed more products and had more visits were, 
in fact, less likely to make a purchase.

• 	The geographical analysis of the data shows a significant impact on revenue generation, with the United States
leading online shopping activity. Expanding our market presence to other countries necessitates implementing crucial 
marketing strategies. Moreover, our observations have shed light on how product preferences differ based on the development 
level of cities and countries, revealing that more prosperous regions tend to generate higher revenue.

• 	As I examine the top-selling items, it becomes evident that certain products like the "Google Kick Ball," "Google 22 oz Water Bottle," and "YouTube Custom Decals" maintain consistent demand across different locations worldwide. This suggests that these products possess a broad appeal and could serve as integral components of a global marketing strategy.

• 	Data-driven insights have become an indispensable asset for businesses and industries. By harnessing the power of data analytics and advanced technologies, organizations can optimize processes, personalize experiences, anticipate trends, and make informed decisions that lead to improved performance and a competitive edge in today's data-centric world. Embracing data-driven insights will continue to be crucial for future success and innovation.

## Challenges 
• Data Quality: Dealing with missing or inconsistent data requires thorough data cleaning and validation. Also there were 
incomplete data columns, for example, TotalTransactionRevenue, missing names of cities and countries, sales tax, 
and absent a unique identifier in the analytics table.

• Establishing Meaningful Relationships: Identifying significant and valuable connections between different tables in the dataset was challenging.

• Limited Data Dimensions: Certain insights may require additional data dimensions, such as customer demographics 
or marketing channels.

## Future Goals

In the future, I would like to focus on implementing advanced data preprocessing and cleaning techniques to ensure that the dataset is of the highest quality, facilitating accurate and reliable analysis.

Secondly, Data Visualization and Reporting would allow stakeholders and decision-makers to explore data and derive real-time insights. Identify and track relevant KPIs to monitor progress toward business objectives and make informed decisions. Storytelling with data: Construct data-driven narratives to convey findings and recommendations compellingly and understandably.

Incorporate additional data to accommodate varying tax rates in different countries.
