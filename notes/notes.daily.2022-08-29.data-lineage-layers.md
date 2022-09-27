---
id: u5thbbu3s2chwsooiir870n
title: Data Lineage Layers
desc: The many layers of data lineage
updated: 1662304084910
created: 1662303331195
tags:
  - cat.read
  - topic.data
---
# The many layers of data lineage

ref: [Borja Vazquez](https://medium.com/data-monzo/the-many-layers-of-data-lineage-2eb898709ad3)

Having a map showing how data evolves from its sources to its destination is the dream of any organisation. A map where we can navigate through our data assets without having to navigate first between loads of tools and colleagues.

![data-lineage-map](https://miro.medium.com/max/875/1*JiUdDZhMzs-ZKDWOTqh9fA.png){max-width: 300px, display: block, margin: 0 auto}

Performance layer
- What’s making this reporting model finish so late?
- What’s the delay introduced to reporting models if this model is merged in production?
- Overlaying performance data over a [Direct Acyclic Graph (DAG)](https://en.wikipedia.org/wiki/Directed_acyclic_graph) can provide a much richer understanding on how single tasks can affect the whole data pipeline performance.

![performance-layer](https://miro.medium.com/max/875/1*HQtCb5Wc2bzP22n4aKdrvw.png){max-width: 300px, display: block, margin: 0 auto}

Usage layer
- Are there any unused models in the warehouse?
- Is this column being used at all?
- Having a clear understanding of who and how data is being used is one of the first steps to keeping a healthy and fit to purpose warehouse

![model-usage](https://miro.medium.com/max/875/1*Km0MG1dGu9SQRt2fAw-h7Q.png){max-width: 300px, display: block, margin: 0 auto}

Data quality layer
- What’s blocking the execution of my models?
- Which models are lacking tests? And documentation?
- We should think about the data quality layer as a set of layers portraying how good a model is: Are the tables and columns documented? Are the data models meeting their services of agreement? Do they have a defined owner?

![quality-layer](https://miro.medium.com/max/875/1*ZMDteoFuLDYemyMqDkWYLQ.png){max-width: 300px, display: block, margin: 0 auto}

Ability to zoom into the right granularity
- In an ideal lineage map, we can browse through the different granularity levels of data lineage, while keeping the quality layer when drilling down

![zoom-granularity](https://miro.medium.com/max/750/1*qXK-1pi7usQidxPEDzBCxA.gif){max-width: 300px, display: block, margin: 0 auto}