## Answer the following questions and provide the SQL queries used to find the answer.

    
### Question 1: Which cities and countries have the highest level of transaction revenues on the site?**


#### SQL Queries:

	CREATE OR REPLACE VIEW highest_revenue_cities_countries_view AS
	SELECT country, city,
	    	SUM(totalTransactionRevenue) AS totalRevenueInMillions
	FROM all_sessions
	WHERE totalTransactionRevenue IS NOT NULL
	  	AND city <> 'Unknown'
	  	AND country <> 'Unknown'
	GROUP BY country, city
	ORDER BY totalRevenueInMillions DESC;
	
	SELECT *
	FROM highest_revenue_cities_countries_view
	ORDER BY totalRevenueInMillions DESC
	LIMIT 10;

#### Answer:

![image](https://github.com/Nathan-13/SQL-Project/assets/28906249/4ef4032d-40f8-4ba6-931a-d27e5e8a5fec)


### Question 2: What is the average number of products ordered from visitors in each city and country?**


#### SQL Queries:

-- Calculate the average number of products ordered for each city and country
	CREATE VIEW average_ordered_quantity_view AS
	SELECT al.country, al.city, 
		ROUND(AVG(p.orderedquantity), 2) AS avg_ordered_quantity
	FROM all_sessions al
	JOIN products p ON al.productsku = p.sku
	WHERE al.country <> 'Unknown'
	    	AND al.city <> 'Unknown'
	GROUP BY al.country, al.city;
	
	SELECT *
	FROM average_ordered_quantity_view
	ORDER BY avg_ordered_quantity DESC;


#### Answer:

![image](https://github.com/Nathan-13/SQL-Project/assets/28906249/1d98b73a-2640-4a10-aa64-df914525e104)



### Question 3: Is there any pattern in the types (product categories) of products ordered from visitors in each city and country?**


#### SQL Queries:

	CREATE VIEW top_selling_products_view AS
	SELECT al.country, al.city,
		al.v2productname AS top_selling_product,
	    	SUM(p.orderedquantity) AS total_quantity_sold
	FROM all_sessions al
	JOIN products p ON al.productsku = p.sku
	WHERE al.country <> 'Unknown'
		AND al.city <> 'Unknown'
	GROUP BY al.v2productname, al.country, al.city;
	
	
	SELECT *
	FROM top_selling_products_view
	ORDER BY total_quantity_sold DESC;


#### Answer:

![image](https://github.com/Nathan-13/SQL-Project/assets/28906249/e4046ffd-4174-467d-90dd-0c021b0a8353)




### Question 4: What is the top-selling product from each city/country? Can we find any pattern worthy of noting in the products sold?**


#### SQL Queries:

![image](https://github.com/Nathan-13/SQL-Project/assets/28906249/d0a20f6b-98c3-465d-90d8-78144e528ec6)


#### Answer:

![image](https://github.com/Nathan-13/SQL-Project/assets/28906249/4bddec89-0ba5-40fd-aac5-cb810fb62a15)



When I look at the best-selling items, I notice that certain products such as the "Google Kick Ball," "Google 22 oz Water Bottle," and "YouTube Custom Decals" are consistently in demand in various locations worldwide. This indicates that these products have a wide-ranging appeal and could be a component of a global marketing plan.

### Question 5: Can we summarize the impact of revenue generated from each city/country?**

#### SQL Queries:

	CREATE VIEW revenue_summary_view AS
	SELECT al.country, al.city,
		al.v2productname AS top_selling_product,
		SUM(p.orderedquantity) AS total_quantity_sold,
		SUM(p.orderedquantity * al.productprice) AS total_revenue
	FROM all_sessions al
	JOIN products p ON al.productsku = p.sku
	WHERE al.country <> 'Unknown'
	AND al.city <> 'Unknown'
	GROUP BY al.country, al.city, al.v2productname;
	
	SELECT *
	FROM revenue_summary_view
	ORDER BY total_revenue DESC;

#### Answer:

![image](https://github.com/Nathan-13/SQL-Project/assets/28906249/184955e1-1ede-4e39-9e68-2d37c4c3b7fd)






