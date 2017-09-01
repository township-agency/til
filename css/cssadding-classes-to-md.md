Turns out, you can add one (or multiple) classes to markdown, specifically when we're using our Jekyll sites, it becomes really useful.

If you have a document as such in Jekyll

```md
---
layout: client
title: Close5
---

# Close5

{: .blockquote}
We really enjoy this client.

{: .blockquote .is-featured}
They teach us so much
```

Rendered output will end up becoming

```html
<h1 id="close5">Close5</h1>
<p class="blockquote">We really enjoy this client.</p>
<p class="blockquote is-featured">They teach us so much</p>
```

Cool! Now style away!
