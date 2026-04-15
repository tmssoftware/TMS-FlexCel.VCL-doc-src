---
uid: TExcelFile.SetImage
description: TExcelFile.SetImage
---

# TExcelFile\.SetImage Method

## Overloads

* [TExcelFile\.SetImage\(Integer, TBytes\)](#texcelfilesetimageinteger-tbytes)
* [TExcelFile\.SetImage\(Integer, TUIImage\)](#texcelfilesetimageinteger-tuiimage)
* [TExcelFile\.SetImage\(Integer, TBytes, TXlsImgType\)](#texcelfilesetimageinteger-tbytes-txlsimgtype)
* [TExcelFile\.SetImage\(Integer, TBytes, Boolean, string\)](#texcelfilesetimageinteger-tbytes-boolean-string)
* [TExcelFile\.SetImage\(Integer, TUIImage, Boolean, string\)](#texcelfilesetimageinteger-tuiimage-boolean-string)
* [TExcelFile\.SetImage\(Integer, TBytes, TXlsImgType, Boolean, string\)](#texcelfilesetimageinteger-tbytes-txlsimgtype-boolean-string)

# TExcelFile\.SetImage\(Integer, TBytes\)
Sets the image data for an existing image\. It will try to automatically guess/convert the image type of the data to the better fit\.
Note that for SVG images, xlsx files store both a PNG and SVG image\. To enter an SVG image, use [SetImageAlternate](SetImageAlternate.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetImage(const imageIndex: Integer; data: TBytes); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**imageIndex**|Integer|Index of the image on the sheet array \(1\-based\)|
||**data**|TBytes|Image data\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetImage\(Integer, TUIImage\)
Sets the image data for an existing image\.
Note that for SVG images, xlsx files store both a PNG and SVG image\. To enter an SVG image, use [SetImageAlternate](SetImageAlternate.md)

## Remarks

Saving a WMF or EMF Image is not currently supported by the \.NET framework\.
If you pass a MetaFile to this method, it will be saved as PNG\.
For inserting a REAL wmf into excel use [AddImage\(TStream, TXlsImgType, IImageProperties\)](AddImage.md#texcelfileaddimagetstream-txlsimgtype-iimageproperties)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetImage(const imageIndex: Integer; const Img: <a href="../TUIImage/index.md">TUIImage</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**imageIndex**|Integer|Image Index\. 1\-Based\.|
|const|**Img**|[TUIImage](../TUIImage/index.md)|Image to replace\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetImage\(Integer, TBytes, TXlsImgType\)
Sets the image data and / or image properties of an existing image\.
Note that for SVG images, xlsx files store both a PNG and SVG image\. To enter an SVG image, use [SetImageAlternate](SetImageAlternate.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetImage(const imageIndex: Integer; data: TBytes; const imageType: <a href="../TXlsImgType.md">TXlsImgType</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**imageIndex**|Integer|Index of the image on the sheet array \(1\-based\)|
||**data**|TBytes|Image data\.|
|const|**imageType**|[TXlsImgType](../TXlsImgType.md)|Image type of the new data\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetImage\(Integer, TBytes, Boolean, string\)
Sets the image data for an existing image\. It will try to automatically guess/convert the image type of the data to the better fit\.
Note that for SVG images, xlsx files store both a PNG and SVG image\. To enter an SVG image, use [SetImageAlternate](SetImageAlternate.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetImage(const imageIndex: Integer; data: TBytes; const usesObjectIndex: Boolean; const objectPath: string); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**imageIndex**|Integer|Index of the image on the sheet array \(1\-based\)|
||**data**|TBytes|Image data\.|
|const|**usesObjectIndex**|Boolean|If false \(the default\) then imageIndex is an index to the list of images\.<br />When true imageIndex is an index to the list of all objects in the sheet\. When you have the object id, you can avoid calling [ObjectIndexToImageIndex](ObjectIndexToImageIndex.md) which is a slow method, by setting this parameter to true\.|
|const|**objectPath**|string|Path to the object, when the object is grouped with others\. This parameter only has meaning if usesObjectIndex is true\.<br /><br />If it is "absolute"\(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetImage\(Integer, TUIImage, Boolean, string\)
Sets the image data for an existing image\.
Note that for SVG images, xlsx files store both a PNG and SVG image\. To enter an SVG image, use [SetImageAlternate](SetImageAlternate.md)

## Remarks

Saving a WMF or EMF Image is not currently supported by the \.NET framework\.
If you pass a MetaFile to this method, it will be saved as png\.
For inserting a REAL wmf into excel use [AddImage\(TStream, TXlsImgType, IImageProperties\)](AddImage.md#texcelfileaddimagetstream-txlsimgtype-iimageproperties)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetImage(const imageIndex: Integer; const Img: <a href="../TUIImage/index.md">TUIImage</a>; const usesObjectIndex: Boolean; const objectPath: string); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**imageIndex**|Integer|Image Index\. 1\-Based\.|
|const|**Img**|[TUIImage](../TUIImage/index.md)|Image to replace\.|
|const|**usesObjectIndex**|Boolean|If false \(the default\) then imageIndex is an index to the list of images\.<br />When true imageIndex is an index to the list of all objects in the sheet\. When you have the object id, you can avoid calling [ObjectIndexToImageIndex](ObjectIndexToImageIndex.md) which is a slow method, by setting this parameter to true\.|
|const|**objectPath**|string|Path to the object, when the object is grouped with others\. This parameter only has meaning if usesObjectIndex is true\.<br /><br />If it is "absolute"\(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetImage\(Integer, TBytes, TXlsImgType, Boolean, string\)
Sets the image data and / or image properties of an existing image\.
Note that for SVG images, xlsx files store both a PNG and SVG image\. To enter an SVG image, use [SetImageAlternate](SetImageAlternate.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetImage(const imageIndex: Integer; data: TBytes; const imageType: <a href="../TXlsImgType.md">TXlsImgType</a>; const usesObjectIndex: Boolean; const objectPath: string); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**imageIndex**|Integer|Index of the image on the sheet array \(1\-based\)|
||**data**|TBytes|Image data\.|
|const|**imageType**|[TXlsImgType](../TXlsImgType.md)|Image type of the new data\.|
|const|**usesObjectIndex**|Boolean|If false \(the default\) then imageIndex is an index to the list of images\.<br />When true imageIndex is an index to the list of all objects in the sheet\. When you have the object id, you can avoid calling [ObjectIndexToImageIndex](ObjectIndexToImageIndex.md) which is a slow method, by setting this parameter to true\.|
|const|**objectPath**|string|Path to the object, when the object is grouped with others\. This parameter only has meaning if usesObjectIndex is true\.<br /><br />If it is "absolute"\(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"|


## See also

* [TExcelFile](../TExcelFile/index.md)

