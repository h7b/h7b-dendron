---
id: 5ifybn9iiz4x91zm98yickq
title: Q4
desc: Okxe Data Analyst
updated: 1663450620690
created: 1663281048001
---
# Q4 (Advanced)

## Question

Write a query to find the product_id which has the second highest sales revenue in May 2022. The expected output is the product_id itself only.

## Answer

Query:

```sql
SELECT
  DISTINCT product_id
FROM (
  SELECT
    sales.product_id,
    SUM(sales.value) OVER (
      PARTITION BY sales.product_id
      ) totalSalesByProduct
  FROM sales
  WHERE
    YEAR(sales.sales_date) = 2022 AND
    MONTH(sales.sales_date) = 5
  ORDER BY totalSalesByProduct DESC
  ) SalesByProduct2022May
LIMIT 1 OFFSET 1;
```

Reasoning:
- the general idea is creating a *derived table* [^1] called "SalesByProduct2022May" that gets the sales revenue in May 2022 of each "product_id". Sort this "SalesByProduct2022May" table by `DESC` order of "totalSalesByProduct". Then print out the expected "product_id" using `LIMIT` clause.
- in details
    - a *subquery* [^2] that search for a sorted table, consisting of: product_id and "totalSalesByProduct" realized only in May 2022
    ```sql
    SELECT
      sales.product_id,
      SUM(sales.value) OVER (
        PARTITION BY sales.product_id
        ) totalSalesByProduct
    FROM sales
    WHERE
      YEAR(sales.sales_date) = 2022 AND
      MONTH(sales.sales_date) = 5
    ORDER BY totalSalesByProduct DESC
    ```
    - The `SUM()` works as a *window function* [^3] that operates on a set of rows defined by the contents of the `OVER` clause. The window function reports the total sales by "product_id" and output the result in each row, which made multiple duplicated rows for each "product_id"
    ![subquery-result](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-09-16_053854_HiPK4fWUi.jpg?ik-sdk-version=javascript-1.4.3&updatedAt=1663299580557){max-width: 300px, display: block, margin: 0 auto}
    - The table resulting from subquery is already sorted by "totalSalesByProduct". After having removed the duplicates (via the *`DISTINCT` clause* [^4] in the main query), we use *`LIMIT` clause* [^5] with offset value to take only the 1st row of the constrained rows. This is the "product_id" with 2nd-highest-sales in May 2022.

[^1]: https://www.mysqltutorial.org/mysql-derived-table/
[^2]: https://www.mysqltutorial.org/mysql-subquery/
[^3]: https://www.mysqltutorial.org/mysql-window-functions/
[^4]: https://www.mysqltutorial.org/mysql-distinct.aspx
[^5]: https://www.mysqltutorial.org/mysql-limit.aspx

## Related

- [mysqltutorial | MySQL RANK Function](https://www.mysqltutorial.org/mysql-window-functions/mysql-rank-function/)
- [stackoverflow | Find Salesperson's second highest sale SQL](https://stackoverflow.com/questions/33990682/find-salespersons-second-highest-sale-sql)
- [stackoverflow | SQL Server - Second highest sales query](https://stackoverflow.com/questions/51998538/sql-server-second-highest-sales-query)