---
uid: TFlexCelSVGExport.RasterizeSVGImages
description: TFlexCelSVGExport.RasterizeSVGImages
---

# TFlexCelSVGExport.RasterizeSVGImages Property

If false \(the default\) then FlexCel will export SVG images inside the Excel file as SVG images inside the generated SVG\.
If true, FlexCel will convert the SVG images to PNG and embed the PNG inside the SVG\. This might be more accurate specially if the embedded SVG uses fonts that might not be present in the client machine\. See [S V G Files Inside Xlsx Files](xref:SVGFilesInsideXlsxFiles) for more information\.


## Remarks

Even when this property is false, there might be cases where FlexCel rasterizes the image anyway\.
This can happen if the image has effects, like for example a color overlay, which we need to apply\. Only images without effects will be rendered as SVG\.

## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelSVGExport/index.md">TFlexCelSVGExport</a>.RasterizeSVGImages: Boolean</code></pre>

## See also

* [TFlexCelSVGExport](../TFlexCelSVGExport/index.md)

