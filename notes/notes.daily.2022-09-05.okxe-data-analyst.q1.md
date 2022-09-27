---
id: 6auprdojvrk0wjgjv8uot6t
title: Q1
desc: Okxe Data Analyst
updated: 1663289656575
created: 1663281032850
---
# Q1 (Basic)

## Question

Write a query to calculate the number of new registered users each month. Please order the result, so we can see the most recent months first.

## Answer

Query:

```sql
SELECT 
  MONTH(users.registered_at) AS month, 
  COUNT(*) AS nb_registered_user
FROM  users
GROUP BY month
ORDER BY month DESC;
```

Reasoning: The `COUNT(*)` function is used with a `GROUP BY` clause to return the number of elements in each group (month).

## Related

- [stackoverflow | count new users by each months in sql](https://stackoverflow.com/questions/63224042/count-new-users-by-each-months-in-sql)
- [stackoverflow | Order by descending date - month, day and year](https://stackoverflow.com/questions/4676139/order-by-descending-date-month-day-and-year)
- [mysqltutorial | MySQL COUNT](https://www.mysqltutorial.org/mysql-count/)
- [mysqltutorial | MySQL SELECT](https://www.mysqltutorial.org/mysql-select-statement-query-data.aspx)
- [mysqltutorial | MySQL ORDER BY](https://www.mysqltutorial.org/mysql-order-by/)