---
id: 292zb2cskctjpso56apnhtl
title: Q3
desc: Okxe Data Analyst
updated: 1663294194375
created: 1663281042180
---
# Q3 (Intermediate)

## Question

Write a query to calculate the number of transactions and the sales revenue (based on transaction value) that we obtained in the first quarter of 2022 from each province of Vietnam. The expected output is as follows.

## Answer

Query:

```sql
SELECT 
  locations.province AS province_name,
  COUNT(sales.id) AS transaction_count,
  SUM(sales.value) AS sales_revenue
FROM sales
INNER JOIN users ON users.id = sales.user_id
INNER JOIN locations ON locations.id = users.location_id
WHERE 
  YEAR(sales.sales_date) = 2022 AND
  QUARTER(sales.sales_date) = 1
GROUP BY province_name;
```

Reasoning:
- the relationship between 3 tables (users, sales, locations) is visualized in the ER diagram
- first, we join all 3 tables by inner join type
    - the inner join clause includes only matching rows from both tables "users" and "sales", using the value in the "user_id" column of "sales" table and the "id" column of "users" table to match
    - similarly for both tables "users" and "locations"
- then we specify a search condition for the rows returned by the query, by limiting only the sales order made in the 1st quarter of 2022
- lastly we define the 3 required columns as province_name, transaction_count and sales_revenue

## Related

- [mysqltutorial | MySQL Join](https://www.mysqltutorial.org/mysql-join/)
- [mysqltutorial | MySQL Temporary Table](https://www.mysqltutorial.org/mysql-temporary-table/)
- [mysqltutorial | The Ultimate Guide To MySQL DATE and Date Functions](https://www.mysqltutorial.org/mysql-date/)
- [stackoverflow | How to Create SELECT for Total sales for each region](https://stackoverflow.com/questions/56135993/how-to-create-select-for-total-sales-for-each-region)