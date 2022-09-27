---
id: Aze1wOlLDNc77zLwC2Dce
title: Newsletter Form
desc: ''
updated: 1637611228593
created: 1637611115599
---
# Embed newsletter form into Dendron-published page

Demonstration from [Subscribe page of Dendron blog](https://blog.dendron.so/notes/jCoayBWmLrfn2W4WrOR9x/)

```
---
id: jCoayBWmLrfn2W4WrOR9x
title: Subscribe
desc: ''
updated: 1634853707725
created: 1634853707725
---

Enjoy the blog? Subscribe to our newsletter!

<form
  action="https://buttondown.email/api/emails/embed-subscribe/dendron"
  method="post"
  target="popupwindow"
  onsubmit="window.open('https://buttondown.email/dendron', 'popupwindow')"
  class="embeddable-buttondown-form"
>
  <label for="bd-email">Enter your email</label>
  <input type="email" name="email" id="bd-email" />
  <input type="submit" value="Subscribe" />
  <p></p>
</form>


Newsletters not your thing? You can also follow us elsewhere on the interwebs:

* Join [Dendron on Discord](https://discord.com/invite/xrKTUStHNZ)
* Follow [Dendron on Twitter](https://twitter.com/dendronhq)
* Checkout [Dendron on GitHub](https://github.com/dendronhq)
```
