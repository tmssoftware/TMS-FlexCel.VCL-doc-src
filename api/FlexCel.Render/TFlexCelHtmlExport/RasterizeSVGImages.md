---
uid: TFlexCelHtmlExport.RasterizeSVGImages
description: TFlexCelHtmlExport.RasterizeSVGImages
---

# TFlexCelHtmlExport.RasterizeSVGImages Property

If false \(the default\) then FlexCel will export SVG images inside the Excel file as SVG images inside the generated HTML\.
If true, FlexCel will convert the SVG images to PNG and embed the PNG inside the HTML\. This might be more accurate specially if the embedded SVG uses fonts that might not be present in the client machine\. See [S V G Files Inside Xlsx Files](xref:SVGFilesInsideXlsxFiles) for more information\.


## Remarks

Even when this property is false, there might be cases where FlexCel rasterizes the image anyway\.
This can happen if the image has effects, like for example a color overlay, which we need to apply\. Only images without effects will be rendered as SVG\.


It is worth noting that this property only applies to images stored as SVG inside the xlsx file\. If you want to render charts as SVG, change [SavedImagesFormat](SavedImagesFormat.md) instead\.

## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelHtmlExport/index.md">TFlexCelHtmlExport</a>.RasterizeSVGImages: Boolean</code></pre>

## See also

* [TFlexCelHtmlExport](../TFlexCelHtmlExport/index.md)

