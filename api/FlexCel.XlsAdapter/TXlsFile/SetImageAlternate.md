---
uid: TXlsFile.SetImageAlternate
description: TXlsFile.SetImageAlternate
---

# TXlsFile\.SetImageAlternate Method

Sets the image data and / or image properties of an existing image\.
Currently this method is only needed for SVG images, since SVG images are stored as both PNG and SVG inside the xlsx file\. This method allows you to supply both images\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetImageAlternate(const imageIndex: Integer; const PNGData: TBytes; const usesObjectIndex: Boolean; const objectPath: string; const aSVGBlip: <a href="../../FlexCel.Core/TSVGBlip/index.md">TSVGBlip</a>); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**imageIndex**|Integer|Index of the image on the sheet array \(1\-based\)|
|const|**PNGData**|TBytes|Image data for the **PNG image** that is used as a backup for the SVG image\. This data **must** be in PNG file format\.|
|const|**usesObjectIndex**|Boolean|If false \(the default\) then imageIndex is an index to the list of images\.<br />When true imageIndex is an index to the list of all objects in the sheet\. When you have the object id, you can avoid calling [TExcelFile.ObjectIndexToImageIndex](../../FlexCel.Core/TExcelFile/ObjectIndexToImageIndex.md) which is a slow method, by setting this parameter to true\.|
|const|**objectPath**|string|Path to the object, when the object is grouped with others\. This parameter only has meaning if usesObjectIndex is true\.<br /><br />If it is "absolute"\(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"|
|const|**aSVGBlip**|[TSVGBlip](../../FlexCel.Core/TSVGBlip/index.md)|Image data for the **SVG image**|


## See also

* [TXlsFile](../TXlsFile/index.md)

