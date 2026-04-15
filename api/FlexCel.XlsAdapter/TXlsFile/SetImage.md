---
uid: TXlsFile.SetImage
description: TXlsFile.SetImage
---

# TXlsFile\.SetImage Method

Sets the image data and / or image properties of an existing image\.
Note that for SVG images, xlsx files store both a PNG and SVG image\. To enter an SVG image, use [TExcelFile.SetImageAlternate](../../FlexCel.Core/TExcelFile/SetImageAlternate.md)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetImage(const imageIndex: Integer; data: TBytes; const imageType: <a href="../../FlexCel.Core/TXlsImgType.md">TXlsImgType</a>; const usesObjectIndex: Boolean; const objectPath: string); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**imageIndex**|Integer|Index of the image on the sheet array \(1\-based\)|
||**data**|TBytes|Image data\.|
|const|**imageType**|[TXlsImgType](../../FlexCel.Core/TXlsImgType.md)|Image type of the new data\.|
|const|**usesObjectIndex**|Boolean|If false \(the default\) then imageIndex is an index to the list of images\.<br />When true imageIndex is an index to the list of all objects in the sheet\. When you have the object id, you can avoid calling [TExcelFile.ObjectIndexToImageIndex](../../FlexCel.Core/TExcelFile/ObjectIndexToImageIndex.md) which is a slow method, by setting this parameter to true\.|
|const|**objectPath**|string|Path to the object, when the object is grouped with others\. This parameter only has meaning if usesObjectIndex is true\.<br /><br />If it is "absolute"\(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"|


## See also

* [TXlsFile](../TXlsFile/index.md)

