---
id: n53nsaon0kp3v2hhkfoxgdg
title: Naming Conventions in SQL
desc: Naming Conventions in SQL
updated: 1663749784766
created: 1663749123181
tags: topic.data
---
# Naming Conventions in SQL

ref: [sqlshack](https://www.sqlshack.com/learn-sql-naming-conventions/)

These are only suggested and nice-to-have conventions.

- Use lower letters when naming database objects. For separating words in the database object name, use underscore
- Use singular for table names (*user*, *role*), and not plural (*users*, *roles*). The plural could lead to some weird table names later (instead of *user_has_role*, you would have *users_have_roles*, etc.)
- **Primary key column**. You should usually have only 1 column serving as a primary key. It would be the best to simply name this column “id”. You should also name your PK constraint in a meaningful way. E.g., in our database, the PK of the *call* table is named *call_pk*
- **Foreign key columns**. Since they store values from the range of primary key of the referenced table, you should use that table name and “id”, e.g. *customer_id* or *employee_id*. This will tell us that this is a foreign key column and also point to the referenced table.
- **Dates**. For dates, it’s good to describe what the date represents. Names like *start_date* and *end_date* are pretty descriptive.
- **Flags**. We could have flags marking if some action took place or not. We could use names like *is_active*, *is_deleted*
- **Foreign keys**. You should name them in such a manner that they uniquely and clearly describe what they are – which tables they relate. In our database, the foreign key that relates tables *call* and *call_outcome* is called *call_call_outcome*.
- **Stored procedures**. If the procedure uses more than 1 table, I would use a descriptive name for the procedure. E.g., if we want all customers with 5 or more calls, I would call this procedure similar to this – *p_customer_with_5_or_more_calls*