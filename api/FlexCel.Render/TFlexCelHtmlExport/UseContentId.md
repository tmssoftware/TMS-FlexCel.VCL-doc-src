---
uid: TFlexCelHtmlExport.UseContentId
description: TFlexCelHtmlExport.UseContentId
---

# TFlexCelHtmlExport.UseContentId Property

When exporting to **MHTML**, some mail clients might have problems understanding the newer "Content\-Location" header to show the images\.
When this property is true, we will use the older "Content\-Id" header that is better supported than Content Location in the mime headers to reference the images\. You are strongly encouraged to keep this property true in order to maximize the number of mail readers compatible\. When Exporting to HTML \(not MHTML\), this property has no effect\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelHtmlExport/index.md">TFlexCelHtmlExport</a>.UseContentId: Boolean</code></pre>

## See also

* [TFlexCelHtmlExport](../TFlexCelHtmlExport/index.md)

