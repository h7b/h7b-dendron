---
id: Q6n45InVXCFI76N3zMIQK
title: Integrate comments into a static site
desc: ''
updated: 1642438540652
created: 1636768617130
---
# Tools to integrate comments in your static site

ref: [darekkay](https://darekkay.com/blog/static-site-comments/), [Hacker News](https://news.ycombinator.com/item?id=29189923)


3rd party services are mostly easy to integrate. On the downside, they may hurt both performance and privacy. Comments are loaded via JavaScript, so they may not be indexed by search engines.

- [Disqus](https://disqus.com/). Probably the most popular comment hosting service. It offers a basic ads-supported plan, but it comes with some privacy, security and performance [problems](https://notes.ayushsharma.in/2017/09/im-killing-disqus-comments-on-my-blog-heres-why).
- [Facebook comments](https://developers.facebook.com/docs/plugins/comments). Another established provider with similar privacy concerns as Disqus.
- [Discourse](https://www.discourse.org/). It's a whole discussion platform, mostly used to replace classic discussion boards. It can also be utilized to host comments, as used by the co-founder Jeff Atwood on their [static blog](https://blog.codinghorror.com/).
- [Cactus Comments](https://cactus.chat/). Federated comment system, based on the Matrix protocol.
    - Dedicated [guide](https://cactus.chat/docs/integrations/mkdocs-material/) to integrate with [mkdocs-material](https://squidfunk.github.io/mkdocs-material/)
- [Cusdis](https://cusdis.com/). A new (as of April 2021) open-source project.
- [Utterances](https://utteranc.es/). A lightweight comments widget built on GitHub issues. Actively maintained as of May 2021.
- [Giscus](https://giscus.app/). A comment system powered by GitHub discussions. Heavily inspired by Utterances and actively maintained.
- [Caint](https://www.caint.casa/). A free open-source comment service.
- [Remark42](https://github.com/umputun/remark42). With 2.8k+ stars, it's a popular alternative that is actively maintained and extended.