---
uid: TFlexCelPdfExport.UseFauxStyles
description: TFlexCelPdfExport.UseFauxStyles
---

# TFlexCelPdfExport.UseFauxStyles Property

When a font doesn't have a bold, italic or bold\-italic variant, FlexCel can't export bold, italic or bold\-italic characters to the pdf respectively\. When this property is true \(the default\), FlexCel will try to "fake" those missing styles by using a wider pen width for the characters to simulate bold, or doing a slant transform to simulate italics\.


The results of a simulated bold or italic can be not great, so if you prefer that FlexCel doesn't try to simulate bold or italics, then you can set this property to false\. If this property is false and the font you are using doesn't have bold or italics variants, then the pdf won't show bold or italics for that font\.



You can use [TFlexCelTrace](../../FlexCel.Core/TFlexCelTrace/index.md) to know when FlexCel is using faux bolds or italics\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelPdfExport/index.md">TFlexCelPdfExport</a>.UseFauxStyles: Boolean</code></pre>

## See also

* [TFlexCelPdfExport](../TFlexCelPdfExport/index.md)

