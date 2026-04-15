---
uid: TPdfWriter.UseLocalFontList
description: TPdfWriter.UseLocalFontList
---

# TPdfWriter.UseLocalFontList Property

**This is a setting mostly for testing, do not change unless you have a good reason,**
By default, FlexCel uses a global font list for exporting to PDF, because populating the font list is slow, and keeping it in a cache makes everything faster\. But when testing, we sometimes need to validate specific behaviors in a test, and a shared global font list can make it difficult\.
Setting this property to true will make FlexCel use a local font list for this instance of PdfWriter, so it won't interfere with other tests that might be running at the same time\.
It will also make the exporting slower\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TPdfWriter/index.md">TPdfWriter</a>.UseLocalFontList: Boolean</code></pre>

## See also

* [TPdfWriter](../TPdfWriter/index.md)

