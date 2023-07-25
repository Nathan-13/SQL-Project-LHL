### What issues will you address by cleaning the data?
Cleaning the data is an essential step in the data preparation process that aims to address various issues 
and inconsistencies present in the dataset. I can improve its quality, accuracy, and reliability, making
it more suitable for analysis and decision-making. Here are some of the issues I addressed in this process:

• Handling inconsistent data: 
For the "all_sessions" table, find distinct inconsistent values in the "country" and "city" columns and update with a standardized value:
Example is 'RÃ©union' to 'Reunion' and 'CÃ´te dâ€™Ivoire' to 'Ivory Coast'.

• Standardizing values:
For the "all_sessions" table, remove leading/trailing whitespaces from the "v2ProductName" column

For the "products" table, remove leading/trailing whitespaces from the "name" column

• Duplicates: Duplicate records in a dataset can lead to misleading analysis results and waste computational resources. 
Cleaning data involves removing or merging duplicates to maintain data integrity.

Therefore, I query some selected columns in the tables for duplicates and identify the unique identify of each tables. Also, it
allows me to classify my tables into fact and dims categories. 

Inaccurate Data: Incorrect data entries can result from human errors or system glitches. Cleaning data involves verifying and correcting inaccurate data points to improve the overall data quality.




### Queries:
Below, provide the SQL queries you used to clean your data.

-- Handling inconsistent data: 

-- For the "all_sessions" table, find distinct inconsistent values in the "country" column and update with a standardized value:
SELECT DISTINCT country
FROM all_sessions;

UPDATE all_sessions
SET country = CASE
    WHEN country = 'RÃ©union' THEN 'Reunion'
    WHEN country = 'CÃ´te dâ€™Ivoire' THEN 'Ivory Coast'
    ELSE country
END;


SELECT DISTINCT city
FROM all_sessions;

UPDATE all_sessions
SET city = CASE 
    WHEN city = 'not available in demo dataset' THEN country
    ELSE city
END;


-- Standardizing values:

--For the "all_sessions" table, remove leading/trailing whitespaces from the "v2ProductName" column
UPDATE all_sessions
SET v2ProductName = TRIM(v2ProductName);

--For the "products" table, remove leading/trailing whitespaces from the "name" column
UPDATE products
SET name = TRIM(name);

-- exploring available data for total transaction revenue.
SELECT COUNT(*) AS Total
FROM all_sessions
WHERE totaltransactionrevenue IS NOT NULL