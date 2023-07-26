## Answer the following questions and provide the SQL queries used to find the answer.

    
### Question 1: Which cities and countries have the highest level of transaction revenues on the site?**


#### SQL Queries:


Answer:
![image](https://github.com/Nathan-13/SQL-Project/assets/28906249/2a96cae2-aa77-4f2f-9a74-9768c7dd5ad4)




### Question 2: What is the average number of products ordered from visitors in each city and country?**


#### SQL Queries:



Answer:





### Question 3: Is there any pattern in the types (product categories) of products ordered from visitors in each city and country?**


#### SQL Queries:

CREATE VIEW ordered_products_by_category_view AS

SELECT al.country, al.city, al.v2productcategory,

	COUNT(*) AS total_orders,

	ROUND(AVG(p.orderedquantity), 2) AS avg_ordered_quantity

FROM all_sessions al

JOIN products p ON al.productsku = p.sku

WHERE al.country <> 'Unknown'

	AND al.city <> 'Unknown'

	AND al.v2productcategory <> 'Unknown'

GROUP BY al.country, al.city, al.v2productcategory;


SELECT *

FROM ordered_products_by_category_view

ORDER BY avg_ordered_quantity DESC;


#### Answer:

country	city	v2productcategory	total_orders	avg_ordered_quantity
Chile	Santiago	Home/Lifestyle/	1	15170
United States	Kirkland	Home/Accessories/Fun/	1	15170
Russia	Moscow	Home/Accessories/Sports & Fitness/	1	15170
United States	Santa Clara	Home/Accessories/Sports & Fitness/	1	15170
United States	Council Bluffs	Home/Accessories/Fun/	1	15170
United States	San Diego	Home/Accessories/Sports & Fitness/	1	15170
United States	Detroit	Drinkware	1	10075
India	Gurgaon	Home/Drinkware/	1	8942
United States	Cambridge	Home/Drinkware/	1	8942
Brazil	Sao Paulo	Home/Accessories/Drinkware/	1	8942




### Question 4: What is the top-selling product from each city/country? Can we find any pattern worthy of noting in the products sold?**


#### SQL Queries:



Answer:





### Question 5: Can we summarize the impact of revenue generated from each city/country?**

#### SQL Queries:



Answer:







