---
id: 0f73fuk9012de4umais22bs
title: Relationships in DBMS
desc: ''
updated: 1659662736907
created: 1659661608380
---
# What are the different types of relationships in DBMS?

ref: [AfterAcademy](https://afteracademy.com/blog/what-are-the-different-types-of-relationships-in-dbms)

Any association between two entity types is called a relationship.

## Relationship

One-to-One Relationship
- A relationship exists when each record of one table is related to only one record of the other table. Such a relationship is not very common. However, it is used for security purposes
- For example, If there are two entities "Person" (Id, Name, Age, Address)and "Passport"(Passport_id, Passport_no). So, each person can have only one passport and each passport belongs to only one person
- In this example, we can easily store the passport id in the "Person" table only. But, we make another table for the "Passport" because Passport number may be sensitive data, and it should be hidden from certain users. So, by making a separate table we provide extra security that only certain database users can see it.
![one-to-one](https://s3.ap-south-1.amazonaws.com/afteracademy-server-uploads/what-are-the-different-types-of-relationships-in-dbms-one-to-one-relationship-example-e89f4cf71cbaee76.jpg){max-width: 300px, display: block, margin: 0 auto}

One-to-Many or Many-to-One Relationship
- each record of one table can be related to one or more than one record of the other table
- For example, If there are two entity type "Customer" and "Account" then each "Customer" can have more than one "Account" but each "Account" is held by only one "Customer". In this example, we can say that each Customer is associated with many Account. So, it is a one-to-many relationship. But, if we see it the other way i.e many Account is associated with one Customer then we can say that it is a many-to-one relationship.
![one-to-many](https://s3.ap-south-1.amazonaws.com/afteracademy-server-uploads/what-are-the-different-types-of-relationships-in-dbms-one-to-many-relationship-example-0d5c065e28b4f23a.jpg){max-width: 300px, display: block, margin: 0 auto}

Many-to-Many Relationship
- each record of the first table can be related to one or more than one record of the second table and a single record of the second table can be related to one or more than one record of the first table
- Example: If there are two entity type "Customer" and "Product" then each customer can buy more than one product and a product can be bought by many different customers.
![many-to-many-1](https://s3.ap-south-1.amazonaws.com/afteracademy-server-uploads/what-are-the-different-types-of-relationships-in-dbms-many-to-many-relationship-example-bd4be3b525b7bdcd.jpg){max-width: 300px, display: block, margin: 0 auto}
- In the example, we can have the "Order" entity as a linking table which links the "Customer" and "Product" entity. We can break this many-to-many relationship in two one-to-many relationships. First, each "Customer" can have many "Order" whereas each "Order" is related to only one "Customer". Second, each "Order" is related only one Product where there can many orders for the same Product
![many-to-many-2](https://s3.ap-south-1.amazonaws.com/afteracademy-server-uploads/what-are-the-different-types-of-relationships-in-dbms-many-to-many-relationship-examples-c961b29d4c8aa6a5.jpg){max-width: 300px, display: block, margin: 0 auto}

## Participation Constraints

There are two types of participation constraints
- Partial Participation
- Total Participation

Partial Participation
- exists when all the entity of an entity type is not associated with one or the other entity of another entity type
- Example: We have two entity type "Customer" and "Order". Then there can be "Customer" who have not done any order. So, here there is partial participation of the entity in the relationship.
![partial-participation](https://s3.ap-south-1.amazonaws.com/afteracademy-server-uploads/what-are-the-different-types-of-relationships-in-dbms-partial-participation-65c310d994b06e44.jpg){max-width: 300px, display: block, margin: 0 auto}

Total Participation
- exists when all the entity of an entity type is associated with one or the other entity of another entity type
- Such a relationship usually exist between a strong entity and a weak entity
- Example: We have two entity type "Employee" and "Dependent". Then all the "Dependent" entity are related to one or the other "Employee" entity. This is called total participation of the entity in the relationship. But, it may be possible that some "Employee" is not related to any of the "Dependent" entity. So, "Employee" is showing partial participation whereas the "Dependent" is showing total participation in the relationship.
![total-participation](https://s3.ap-south-1.amazonaws.com/afteracademy-server-uploads/what-are-the-different-types-of-relationships-in-dbms-total-participation-64cd6a2c1f32ab4e.jpg){max-width: 300px, display: block, margin: 0 auto}