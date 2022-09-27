---
id: GL15No9zOJVd97bsZbRVd
title: Sql Join
desc: ''
updated: 1639186890737
created: 1639185844341
---
# A Brief Introduction to SQL Joins

ref: [Love Spreadsheets | Medium](https://lovespreadsheets.medium.com/a-brief-yet-comprehensive-introduction-to-sql-joins-de2fa412d2e), [W3Schools](https://www.w3schools.com/sql/sql_join.asp), [JavaTpoint](https://www.javatpoint.com/types-of-sql-join)

A `SQL` `JOIN` describes the process of merging rows in two different tables or files together.

![sql-join](https://miro.medium.com/max/875/1*1U4-pT7IbAc6SJjeDbo6Ig.png){max-width: 300px, display: block, margin: 0 auto}

4 types of joins
![types-join](https://miro.medium.com/max/875/1*ZYCxupdz7nC0bLiwm8_3ZA.png){max-width: 300px, display: block, margin: 0 auto}

(INNER) JOIN: Returns records that have matching values in both tables
![inner-join](https://static.javatpoint.com/sqlpages/images/types-of-sql-join.png){max-width: 300px, display: block, margin: 0 auto}
```sql
SELECT Orders.OrderID, Customers.CustomerName, Orders.OrderDate
FROM Orders
INNER JOIN Customers ON Orders.CustomerID=Customers.CustomerID;
```

LEFT (OUTER) JOIN: Returns all records from the left table, and the matched records from the right table
![left-join](https://static.javatpoint.com/sqlpages/images/types-of-sql-join4.png){max-width: 300px, display: block, margin: 0 auto}

RIGHT (OUTER) JOIN: Returns all records from the right table, and the matched records from the left table
![right-join](https://static.javatpoint.com/sqlpages/images/types-of-sql-join6.png){max-width: 300px, display: block, margin: 0 auto}

FULL (OUTER) JOIN: Returns all records when there is a match in either left or right table
![full-join](https://static.javatpoint.com/sqlpages/images/types-of-sql-join8.png){max-width: 300px, display: block, margin: 0 auto}
