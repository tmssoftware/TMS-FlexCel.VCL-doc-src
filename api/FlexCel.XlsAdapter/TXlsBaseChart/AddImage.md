---
uid: TXlsBaseChart.AddImage
description: TXlsBaseChart.AddImage
---

# TXlsBaseChart\.AddImage Method

## Overloads

* [TXlsBaseChart\.AddImage\(TUIImage, IImageProperties\)](#txlsbasechartaddimagetuiimage-iimageproperties)
* [TXlsBaseChart\.AddImage\(TBytes, IImageProperties\)](#txlsbasechartaddimagetbytes-iimageproperties)
* [TXlsBaseChart\.AddImage\(TStream, IImageProperties\)](#txlsbasechartaddimagetstream-iimageproperties)
* [TXlsBaseChart\.AddImage\(string, IImageProperties\)](#txlsbasechartaddimagestring-iimageproperties)
* [TXlsBaseChart\.AddImage\(TBytes, TXlsImgType, IImageProperties\)](#txlsbasechartaddimagetbytes-txlsimgtype-iimageproperties)
* [TXlsBaseChart\.AddImage\(TStream, TXlsImgType, IImageProperties\)](#txlsbasechartaddimagetstream-txlsimgtype-iimageproperties)

# TXlsBaseChart\.AddImage\(TUIImage, IImageProperties\)
Adds a new image to the active sheet\. If you don't have the image already created, prefer using [AddImage\(TStream, IImageProperties\)](AddImage.md#txlsbasechartaddimagetstream-iimageproperties), as it is faster\.
Note that for SVG images, xlsx files store both a PNG and SVG image\. To enter an SVG image, use [AddImageAlternate](AddImageAlternate.md)

## Remarks

Saving a WMF or EMF Image is not currently supported by the \.NET framework\.
If you pass a MetaFile to this method, it will be saved as png\.
For inserting a REAL wmf into excel use [AddImage\(TStream, IImageProperties\)](AddImage.md#txlsbasechartaddimagetstream-iimageproperties)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsBaseChart/index.md">TXlsBaseChart</a>.AddImage(const img: <a href="../../FlexCel.Core/TUIImage/index.md">TUIImage</a>; imageProperties: <a href="../../FlexCel.Core/IImageProperties/index.md">IImageProperties</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**img**|[TUIImage](../../FlexCel.Core/TUIImage/index.md)|Image to insert\.|
||**imageProperties**|[IImageProperties](../../FlexCel.Core/IImageProperties/index.md)|Image size/position|


## See also

* [TXlsBaseChart](../TXlsBaseChart/index.md)

# TXlsBaseChart\.AddImage\(TBytes, IImageProperties\)
Adds an image to the active sheet\. It will try to automatically guess/convert the image type of the data to the better fit\.
Note that for SVG images, xlsx files store both a PNG and SVG image\. To enter an SVG image, use [AddImageAlternate](AddImageAlternate.md)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsBaseChart/index.md">TXlsBaseChart</a>.AddImage(const data: TBytes; imageProperties: <a href="../../FlexCel.Core/IImageProperties/index.md">IImageProperties</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**data**|TBytes|Image data\.|
||**imageProperties**|[IImageProperties](../../FlexCel.Core/IImageProperties/index.md)|Image Properties\.|


## See also

* [TXlsBaseChart](../TXlsBaseChart/index.md)

# TXlsBaseChart\.AddImage\(TStream, IImageProperties\)
Adds an image to the active sheet\.
Note that for SVG images, xlsx files store both a PNG and SVG image\. To enter an SVG image, use [AddImageAlternate](AddImageAlternate.md)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsBaseChart/index.md">TXlsBaseChart</a>.AddImage(const aStream: TStream; imageProperties: <a href="../../FlexCel.Core/IImageProperties/index.md">IImageProperties</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aStream**|TStream|Stream containing the image data\.|
||**imageProperties**|[IImageProperties](../../FlexCel.Core/IImageProperties/index.md)|Placement and other properties of the image\.|


## See also

* [TXlsBaseChart](../TXlsBaseChart/index.md)

# TXlsBaseChart\.AddImage\(string, IImageProperties\)
Adds an image to the active sheet\.
Note that for SVG images, xlsx files store both a PNG and SVG image\. To enter an SVG image, use [AddImageAlternate](AddImageAlternate.md)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsBaseChart/index.md">TXlsBaseChart</a>.AddImage(const fileName: string; imageProperties: <a href="../../FlexCel.Core/IImageProperties/index.md">IImageProperties</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**fileName**|string|Name of the file in disk containing the image data\.|
||**imageProperties**|[IImageProperties](../../FlexCel.Core/IImageProperties/index.md)|Placement and other properties of the image\.|


## See also

* [TXlsBaseChart](../TXlsBaseChart/index.md)

# TXlsBaseChart\.AddImage\(TBytes, TXlsImgType, IImageProperties\)
Adds an image to the active sheet\.
Note that for SVG images, xlsx files store both a PNG and SVG image\. To enter an SVG image, use [AddImageAlternate](AddImageAlternate.md)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsBaseChart/index.md">TXlsBaseChart</a>.AddImage(const data: TBytes; const imageType: <a href="../../FlexCel.Core/TXlsImgType.md">TXlsImgType</a>; imageProperties: <a href="../../FlexCel.Core/IImageProperties/index.md">IImageProperties</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**data**|TBytes|byte array with the image data\.|
|const|**imageType**|[TXlsImgType](../../FlexCel.Core/TXlsImgType.md)|Type of image you are inserting \(bmp, jpg, etc\)\.|
||**imageProperties**|[IImageProperties](../../FlexCel.Core/IImageProperties/index.md)|Placement and other properties of the image\.|


## See also

* [TXlsBaseChart](../TXlsBaseChart/index.md)

# TXlsBaseChart\.AddImage\(TStream, TXlsImgType, IImageProperties\)
Adds an image to the active sheet\.
Note that for SVG images, xlsx files store both a PNG and SVG image\. To enter an SVG image, use [AddImageAlternate](AddImageAlternate.md)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsBaseChart/index.md">TXlsBaseChart</a>.AddImage(const aStream: TStream; const imageType: <a href="../../FlexCel.Core/TXlsImgType.md">TXlsImgType</a>; imageProperties: <a href="../../FlexCel.Core/IImageProperties/index.md">IImageProperties</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aStream**|TStream|Stream containing the image data\.|
|const|**imageType**|[TXlsImgType](../../FlexCel.Core/TXlsImgType.md)|Type of image you are inserting \(bmp, jpg, etc\)\.|
||**imageProperties**|[IImageProperties](../../FlexCel.Core/IImageProperties/index.md)|Placement and other properties of the image\.|


## See also

* [TXlsBaseChart](../TXlsBaseChart/index.md)

