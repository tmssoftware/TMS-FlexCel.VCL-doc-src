---
uid: TFlexCelPrintDocument.PrintAsBitmap
description: TFlexCelPrintDocument.PrintAsBitmap
---

# TFlexCelPrintDocument.PrintAsBitmap Property

If true, the file will be rendered to a bitmap and then we will print the bitmap, instead of directly printing the file\.
**Use with caution\.** See remarks

## Remarks

Rendering the image to a bitmap and then sending the bitmap to the printer will use considerably more memory, network resources and processing power than printing directly\. This property should be set to true only in cases where the printer driver is buggy and the printer cannot print directly\.



Note also that the resolution on the bitmap depends in the [BitmapDPI](BitmapDPI.md) property\.




## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelPrintDocument/index.md">TFlexCelPrintDocument</a>.PrintAsBitmap: Boolean</code></pre>

## See also

* [TFlexCelPrintDocument](../TFlexCelPrintDocument/index.md)

