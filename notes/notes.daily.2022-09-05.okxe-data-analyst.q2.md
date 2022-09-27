---
id: x64tax92ab1detrlckql475
title: Q2
desc: Okxe Data Analyst
updated: 1663450242304
created: 1663281037963
---
# Q2 (Intermediate)

## Question

Write a query to calculate the number of registered users who have the last name of “Nguyen” or “Pham” respectively. The expected output is as follows.

## Answer

Query:

```sql
SELECT 
  CONCAT(
    UPPER(SUBSTRING(users.last_name FROM 1 FOR 1)), 
    LOWER(SUBSTRING(users.last_name FROM 2))
  ) AS last_name, 
  COUNT(*) AS user_count
FROM  users
WHERE 
  users.last_name LIKE 'nguyen' OR 
  users.last_name LIKE 'pham'
GROUP BY last_name
ORDER BY last_name ASC;
```

Reasoning:
- in mysql, lookup and name comparisons are not case-sensitive
- We then just need to convert the "last_name" string to proper case.
- By changing to uppercase the 1st substring derived from the "last_name" string, which contains only the 1st character. Then apply lowercase to the 2nd derived substring containing the rest. Finally, joined these 2 substrings back together and print out the results.

## Related

- [mysqltutorial | MySQL CONCAT Function](https://www.mysqltutorial.org/sql-concat-in-mysql.aspx)
- [mysqltutorial | MySQL SUBSTRING Function](https://www.mysqltutorial.org/mysql-substring.aspx)
- [mysqltutorial | MySQL WHERE](https://www.mysqltutorial.org/mysql-where/)
- [stackoverflow | How to count last names in a table without duplicating employee ID](https://stackoverflow.com/questions/59844198/how-to-count-last-names-in-a-table-without-duplicating-employee-id)
- [stackoverflow | How can I make SQL case sensitive string comparison on MySQL](https://stackoverflow.com/questions/5629111/how-can-i-make-sql-case-sensitive-string-comparison-on-mysql)
    - 
    ```sql 
    select * from user where username like binary 'a'
    ```
- [stackoverflow | Basic proper case string in generic SQL](https://stackoverflow.com/questions/33334739/basic-proper-case-string-in-generic-sql)
    - 
    ```sql
    CONCAT(UPPER(SUBSTRING(x FROM 1 FOR 1)), LOWER(SUBSTRING(x FROM 2)))
    ```