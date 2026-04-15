---
uid: TXlsFile.AddImageAlternate
description: TXlsFile.AddImageAlternate
---

# TXlsFile\.AddImageAlternate Method

Adds an image to the active sheet\.
Currently this method is only needed for SVG images, since SVG images are stored as both PNG and SVG inside the xlsx file\. This method allows you to supply both images\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.AddImageAlternate(const PNGData: TBytes; imageProperties: <a href="../../FlexCel.Core/IImageProperties/index.md">IImageProperties</a>; const aSVGBlip: <a href="../../FlexCel.Core/TSVGBlip/index.md">TSVGBlip</a>); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**PNGData**|TBytes|Image data for the PNG file that will be used as a backup for the SVG\. This data **must** be in PNG file format\.|
||**imageProperties**|[IImageProperties](../../FlexCel.Core/IImageProperties/index.md)|Image Properties\.|
|const|**aSVGBlip**|[TSVGBlip](../../FlexCel.Core/TSVGBlip/index.md)|Data for the SVG image to be added\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

