---
uid: TFlexCelPdfExport.Kerning
description: TFlexCelPdfExport.Kerning
---

# TFlexCelPdfExport.Kerning Property

By default, pdf does not do any kerning with the fonts\. This is, on the string "AVANT", it won't compensate the spaces between "A" and "V"\. \(they should be smaller\)  If you turn this property on, FlexCel will calculate the kerning and add it to the generated file\.
The result file will be a little bigger because of the kerning info on all strings, but it will also look a little better\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelPdfExport/index.md">TFlexCelPdfExport</a>.Kerning: Boolean</code></pre>

## See also

* [TFlexCelPdfExport](../TFlexCelPdfExport/index.md)

