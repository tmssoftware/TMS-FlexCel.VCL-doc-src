---
uid: TFlexCelHtmlExport.FixIE6TransparentPngSupport
description: TFlexCelHtmlExport.FixIE6TransparentPngSupport
---

# TFlexCelHtmlExport.FixIE6TransparentPngSupport Property

By default, Internet explorer does not support transparent PNGs\. Normally this is not an issue, since Excel uses  little transparency\. But if you rely on transparent images and don't want to use gif images instead of png, you can set this property to true\. It will add special code to the HTML file to support transparent images in IE6\.
**Note:** If setting this property to false, you might want to set [ImageBackground](ImageBackground.md) to Colors\.White instead of TUIColor\.Empty to ensure images have no transparent background\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelHtmlExport/index.md">TFlexCelHtmlExport</a>.FixIE6TransparentPngSupport: Boolean</code></pre>

## See also

* [TFlexCelHtmlExport](../TFlexCelHtmlExport/index.md)

