---
uid: TXlsxChart.GetImageAlternate
description: TXlsxChart.GetImageAlternate
---

# TXlsxChart\.GetImageAlternate Method

Returns an image and its type\. Currently this method is the same as [TXlsBaseChart.GetImage](../TXlsBaseChart/GetImage.md) for all images except SVG\.
For SVG images, xlsx files store both a PNG and SVG image\. In those cases, this method will return the SVG image\. To get the PNG, call [TXlsBaseChart.GetImage](../TXlsBaseChart/GetImage.md)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsxChart/index.md">TXlsxChart</a>.GetImageAlternate(const imageIndex: Integer; const objectPath: string; out imageType: <a href="../../FlexCel.Core/TXlsImgType.md">TXlsImgType</a>; const outStream: TStream; const usesObjectIndex: Boolean); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**imageIndex**|Integer|Index of the image\. \(1 based\)|
|const|**objectPath**|string|Object path to the image when it is a grouped image\. For toplevel images you can use String\.Empty\. In other case, you need to use the value returned by [TXlsBaseChart.GetObjectProperties](../TXlsBaseChart/GetObjectProperties.md)<br />If it is "absolute"\(it starts with "\\\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\\\1\\\\2\\\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\\\3"|
|out|**imageType**|[TXlsImgType](../../FlexCel.Core/TXlsImgType.md)|**Returns** the image type for the data returned\. \(If it is a bmp, jpg or other\)|
|const|**outStream**|TStream|Stream where the image data will be copied\.|
|const|**usesObjectIndex**|Boolean|If false \(the default\) then imageIndex is an index to the list of images\.<br />When true imageIndex is an index to the list of all objects in the sheet\. When you have the object id, you can avoid calling ObjectIndexToImageIndex which is a slow method, by setting this parameter to true\.|


## See also

* [TXlsxChart](../TXlsxChart/index.md)

