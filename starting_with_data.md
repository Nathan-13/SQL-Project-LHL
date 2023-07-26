### Question 1: What referral sites generate the most traffic to the website?

#### SQL Queries:
    SELECT channelGrouping, COUNT(*) AS traffic_count
    FROM analytics
    WHERE channelGrouping IS NOT NULL
    GROUP BY channelGrouping
    ORDER BY traffic_count DESC;

#### Answer: 

![image](https://github.com/Nathan-13/SQL-Project/assets/28906249/e85fc897-ef09-448d-9f5a-b90188a95976)


### Question 2:  What are the website's top 10 most frequently viewed products?

#### SQL Queries:
      SELECT v2productname, COUNT(*) AS view_count
      FROM all_sessions
      GROUP BY v2productname
      ORDER BY view_count DESC
      LIMIT 10;

#### Answer:

![image](https://github.com/Nathan-13/SQL-Project/assets/28906249/00d977e2-7f92-46a4-af7a-bc8245079986)


### Question 3: Summarize ordered quantities with the stock levels for products.

#### SQL Queries:
      SELECT productsku, name,
          SUM(total_ordered) AS total_ordered_quantity,
          stocklevel
      FROM sales_report
      GROUP BY productsku, name, stocklevel
      HAVING SUM(total_ordered) > stocklevel;

#### Answer:

![image](https://github.com/Nathan-13/SQL-Project/assets/28906249/52b75cfc-5478-4c0e-9b22-35a1b27acaa5)


### Question 4: What are the product names and categories of the products customers order?

#### SQL Queries:

      SELECT visitid, al.productsku, 
      	al.v2productname AS productname, 
      	al.v2productcategory AS productcategory
      FROM all_sessions al
      JOIN products p ON al.productsku = p.sku
      GROUP BY visitid, al.productsku, productname, productcategory
      ORDER BY visitid
      LIMIT 10;

#### Answer:

![image](https://github.com/Nathan-13/SQL-Project/assets/28906249/5fda508c-5174-40b9-bdd7-79b35ef5ed7d)


Question 5: 

SQL Queries:

Answer:
