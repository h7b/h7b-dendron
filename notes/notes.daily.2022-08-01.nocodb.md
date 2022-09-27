---
id: mv7zqu87q0r7n2eajuoua94
title: Self-Host Nocodb
desc: How to Self Host NocoDB
updated: 1661608797026
created: 1659306900451
tags: cat.tut
---
# How to Self-Host NocoDB

## How to Self-Host NocoDB on Fly.io

ref: [kevinquinn.fun](https://kevinquinn.fun/blog/how-to-self-host-nocodb-on-fly.io/)

This guide will set Nocodb up on Fly.io with a SQLite backend.

With Fly.io,
- you will have to add credit card information to the account, so keep your usage to the free tier and you’ll have no issues
- the free tier supports up to [3GB storage for each account](https://fly.io/docs/about/pricing/#free-allowances). This free volume offered by Fly.io is persistent (ie. data is permanently stored for free, as long as the storage size does not pass the 3GB limit).[^1]

[^1]: https://fly.io/blog/free-postgres/

Other hosting provider that can also deploy Nocodb
- [Railway](https://railway.app/)
- [Heroku - 1 Click Deploy](https://docs.nocodb.com/getting-started/installation/#1-click-deploy-to-heroku)
    - Heroku Postgres free plan (name: Hobby Dev) has a limit of 10k rows
    - Heroku removes their free plan since 2022-10-26 [^1], so this option is not suitable to test the deployment
- [Render](https://render.com/)
    - [Render’s free database plan](https://render.com/docs/free#free-postgresql-databases) allows you to run a PostgreSQL database (1GB storage) that automatically expires 90 days after creation

[^1]: https://help.heroku.com/RSBRUH58/removal-of-heroku-free-product-plans-faq

## Related resources

- [Deploy NocoDB on Northflank](https://northflank.com/guides/deploy-nocodb-on-northflank)
- [Beebom | 10 Best Airtable Alternatives You Should Try](https://beebom.com/best-airtable-alternatives/)