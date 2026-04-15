---
uid: TFlexCelPrintDocument.BitmapDPI
description: TFlexCelPrintDocument.BitmapDPI
---

# TFlexCelPrintDocument.BitmapDPI Property

When using a bitmap to print \([PrintAsBitmap](PrintAsBitmap.md) is true\), this property specifies the resolution for the temporary bitmap that will be sent to the printer\. The higher the resolution the better quality of the print, but also the more memory, network time and processing time it will take\.
**Important:** A value of 0 means creating bitmaps with the native printer resolution\. This will give the best quality, but the bitmap can be big\. A negative value means no bitmap used, and it is the same as setting [PrintAsBitmap](PrintAsBitmap.md) = false\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelPrintDocument/index.md">TFlexCelPrintDocument</a>.BitmapDPI: Integer</code></pre>

## See also

* [TFlexCelPrintDocument](../TFlexCelPrintDocument/index.md)

