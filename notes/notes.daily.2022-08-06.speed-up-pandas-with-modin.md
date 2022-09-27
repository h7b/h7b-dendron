---
id: hjk1cclc3moaigsdottqlq2
title: Speed up Pandas with Modin
desc: Speed up Pandas with Modin
updated: 1661177228372
created: 1659741812764
tags:
  - cat.tut
  - topic.data
---
# How to Speed Up Pandas with Modin

ref: [Towards Data Science](https://towardsdatascience.com/how-to-speed-up-pandas-with-modin-84aa6a87bcdb)

The [[pandas|notes.tutorial.python.packages.pandas]] library provides easy-to-use data structures like pandas DataFrames as well as tools for data analysis. One issue with pandas is that it wasn’t designed for analyzing a large amount of data like 100 GB or 1 TB datasets. [^1]

[^1]: [Wes McKinney | Apache Arrow and the "10 Things I Hate About pandas"](https://wesmckinney.com/blog/apache-arrow-pandas-internals/#:~:text=To%20put%20it%20simply%2C%20we%20weren%27t%20thinking%20about%20analyzing%20100%20GB%20or%201%20TB%20datasets%20in%202011.%20Nowadays%2C%20my%20rule%20of%20thumb%20for%20pandas%20is%20that%20you%20should%20have%205%20to%2010%20times%20as%20much%20RAM%20as%20the%20size%20of%20your%20dataset)

Fortunately, there is the [Modin](https://github.com/modin-project/modin) library. It can handle the datasets that pandas can't.

Modin is a drop-in replacement for pandas. While pandas is single-threaded, Modin lets you instantly speed up your workflows by scaling pandas so it uses all of your cores. Modin works especially well on larger datasets, where pandas becomes painfully slow or runs out of memory.

By simply replacing the import statement, Modin offers users effortless speed and scale for their pandas workflows.
![modin-import](https://github.com/modin-project/modin/raw/master/docs/img/Import.gif){max-width: 300px, display: block, margin: 0 auto}


The charts below show the speedup you get by replacing pandas with Modin
![modin-speed-comparison](https://github.com/modin-project/modin/raw/master/docs/img/Modin_Speedup.svg){max-width: 300px, display: block, margin: 0 auto}