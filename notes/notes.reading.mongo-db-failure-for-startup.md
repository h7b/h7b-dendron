---
id: qIPhaFw1xzQkBCRfjodtC
title: Mongo DB Failure for Startup
desc: ''
updated: 1647564074015
created: 1642814355483
---
# Reading 2022-01-22

## Metadata

- Ref:: [nemil](https://www.nemil.com/mongo/index.html)
- Title:: On MongoDB, a three-part series on MongoDB and startups
- Author:: Nemil Dalal
- Year of publication:: 2017
- Category:: Blog
- Topic:: 

## Notes from reading

In this series, the author explain his view on why so many startups chose MongoDB over traditional SQL database like PostgreSQL. 

It turned out that the reason could be
- hype of nosql
- the talent of marketing from 10gen (previous name of MongoDB) (eg. content marketing disguised as engineering lessons) and their customer support team
- schemaless methodology

> The MongoDB docs tell you what it’s good at, without emphasizing what it’s not good at

Frankly, nosql like MongoDB is not appropriate for transaction-required operations, like financial apps.

![database-decision](https://www.nemil.com/mongo/img/database-decisions.png){max-width: 300px, display: block, margin: 0 auto}

Always evaluate the tradeoffs, then choose the appropriate tools for different use cases. Don't follow the hype. It's always hard to do. 