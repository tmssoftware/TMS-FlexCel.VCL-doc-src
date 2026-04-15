---
uid: TImageInformationEventArgs.ImageLinkNeedsEscaping
description: TImageInformationEventArgs.ImageLinkNeedsEscaping
---

# TImageInformationEventArgs.ImageLinkNeedsEscaping Property

If true \(the default\) the link you provide in [ImageLink](ImageLink.md) is not escaped and will be escaped by FlexCel\.
So for example, the link "http://my site" will be escaped to "http://my%%20site"\.
If the link you provided was already escaped, then set this variable to false\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TImageInformationEventArgs/index.md">TImageInformationEventArgs</a>.ImageLinkNeedsEscaping: Boolean</code></pre>

## See also

* [TImageInformationEventArgs](../TImageInformationEventArgs/index.md)

