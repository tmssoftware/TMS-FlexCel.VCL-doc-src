---
uid: TFlexCelPdfExport.PdfType
description: TFlexCelPdfExport.PdfType
---

# TFlexCelPdfExport.PdfType Property

Defines the type of pdf being created\. Note that if you set this property to other value than standard, other properties might be ignored\. For example, when creating a PDF/A file all fonts must be embedded so  the value of the FontEmbed property will be ignored\.
See the [TagMode](TagMode.md) property to determine if the file will be PDF/A\-na or PDF/A\-nb\. If tagging is true \(the default\) the generated files will be "a"\. If not, they will be "b", since b doesn't require tagging\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelPdfExport/index.md">TFlexCelPdfExport</a>.PdfType: <a href="../../FlexCel.Pdf/TPdfType.md">TPdfType</a></code></pre>

## See also

* [TFlexCelPdfExport](../TFlexCelPdfExport/index.md)

