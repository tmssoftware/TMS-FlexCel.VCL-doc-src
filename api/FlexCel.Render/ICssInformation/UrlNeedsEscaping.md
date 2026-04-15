---
uid: ICssInformation.UrlNeedsEscaping
description: ICssInformation.UrlNeedsEscaping
---

# ICssInformation.UrlNeedsEscaping Property

If true \(the default\) the link you provide in [Url](Url.md) is not escaped and will be escaped by FlexCel\.
So for example, the link "http://my site" will be escaped to "http://my%%20site"\.
If the link you provided was already escaped, then set this variable to false\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../ICssInformation/index.md">ICssInformation</a>.UrlNeedsEscaping: Boolean</code></pre>

## See also

* [ICssInformation](../ICssInformation/index.md)

