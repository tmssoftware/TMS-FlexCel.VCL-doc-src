---
uid: TFlexCelPdfExport.GetFontData
description: TFlexCelPdfExport.GetFontData
---

# TFlexCelPdfExport.GetFontData Event

Use this event if you want to provide your own font information for embedding\.
Note that if you don't assign this event, the default method will be used, and this  will try to find the font on the Fonts folder\. To change the font folder, use [GetFontFolder](GetFontFolder.md) event

Note that this property applies only to this object\. To change the property for the full application, use [TPdfWriter.GetFontDataGlobal](../../FlexCel.Pdf/TPdfWriter/GetFontDataGlobal.md)

## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelPdfExport/index.md">TFlexCelPdfExport</a>.GetFontData: TGetFontDataEventHandler</code></pre>

## See also

* [TFlexCelPdfExport](../TFlexCelPdfExport/index.md)

