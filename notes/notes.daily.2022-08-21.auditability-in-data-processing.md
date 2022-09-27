---
id: h31lphnl52486gcystbpu0s
title: Auditability in Data Processing
desc: A way to ensure auditability in data processing
updated: 1661777162013
created: 1661119107689
tags:
  - topic.data
  - cat.read
---
# A way to ensure auditability in data processing

ref: [Petrica Leuca](https://medium.com/@petrica.leuca/a-way-to-ensure-auditability-in-data-processing-f7664b70ec2b)

The trinity of data management: traceability, auditability and reproducibility.

## Data auditability

Data auditability has 2 main components:
- Be able to provide an overview of how you work with data — data quality, data processing standards and data user management
- Be able to assess how performant or efficient your way of working with data is

![basic-question](https://miro.medium.com/max/1400/0*fPA1GLWwVRChTrsl.png){max-width: 300px, display: block, margin: 0 auto}

set of standard metadata
- CreatedBy
- UpdatedBy
- CreatedTimestamp
- UpdatedTimestamp

## Data processing design

We start with data loaded into a raw layer (or stage) and from there we transform and process it into the integration layer. On top of the integration layer, other data-marts or layers might be created.

![data-processing-design](https://miro.medium.com/max/1400/0*jmMnvc_XcgRjd-cM.png){max-width: 300px, display: block, margin: 0 auto}

- The source can be any other application generating data
- Then the data is loaded into the raw/stage layer as an exact copy of what was received from the source
- The integration layer is the layer in which data modeling activities happen
    - technical: creating surrogate keys, adding technical validity intervals, creating foreign keys OR
    - functional: adding attributes which make sense from a business perspective (type of the user, number of log-ins etc)