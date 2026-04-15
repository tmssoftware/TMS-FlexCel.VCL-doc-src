---
uid: IExcelChart.AddImage
description: IExcelChart.AddImage
---

# IExcelChart\.AddImage Method

## Overloads

* [IExcelChart\.AddImage\(TUIImage, IImageProperties\)](#iexcelchartaddimagetuiimage-iimageproperties)
* [IExcelChart\.AddImage\(TBytes, IImageProperties\)](#iexcelchartaddimagetbytes-iimageproperties)
* [IExcelChart\.AddImage\(TStream, IImageProperties\)](#iexcelchartaddimagetstream-iimageproperties)
* [IExcelChart\.AddImage\(string, IImageProperties\)](#iexcelchartaddimagestring-iimageproperties)
* [IExcelChart\.AddImage\(TBytes, TXlsImgType, IImageProperties\)](#iexcelchartaddimagetbytes-txlsimgtype-iimageproperties)
* [IExcelChart\.AddImage\(TStream, TXlsImgType, IImageProperties\)](#iexcelchartaddimagetstream-txlsimgtype-iimageproperties)

# IExcelChart\.AddImage\(TUIImage, IImageProperties\)
Adds a new image to the active sheet\. If you don't have the image already created, prefer  using [AddImage\(TStream, IImageProperties\)](AddImage.md#iexcelchartaddimagetstream-iimageproperties), as it is faster\.
Note that for SVG images, xlsx files store both a PNG and SVG image\. To enter an SVG image, use [IEmbeddedObjects.AddImageAlternate](../IEmbeddedObjects/AddImageAlternate.md)

## Remarks

Saving a WMF or EMF Image is not currently supported by the \.NET framework\.
If you pass a MetaFile to this method, it will be saved as png\.
For inserting a REAL wmf into excel use [AddImage\(TStream, IImageProperties\)](AddImage.md#iexcelchartaddimagetstream-iimageproperties)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../IExcelChart/index.md">IExcelChart</a>.AddImage(const img: <a href="../TUIImage/index.md">TUIImage</a>; imageProperties: <a href="../IImageProperties/index.md">IImageProperties</a>); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**img**|[TUIImage](../TUIImage/index.md)|Image to insert\.|
||**imageProperties**|[IImageProperties](../IImageProperties/index.md)|Image size/position|


## See also

* [IExcelChart](../IExcelChart/index.md)

# IExcelChart\.AddImage\(TBytes, IImageProperties\)
Adds an image to the active sheet\. It will try to automatically guess/convert the image type of the data to the better fit\.
Note that for SVG images, xlsx files store both a PNG and SVG image\. To enter an SVG image, use [IEmbeddedObjects.AddImageAlternate](../IEmbeddedObjects/AddImageAlternate.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../IExcelChart/index.md">IExcelChart</a>.AddImage(const data: TBytes; imageProperties: <a href="../IImageProperties/index.md">IImageProperties</a>); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**data**|TBytes|Image data\.|
||**imageProperties**|[IImageProperties](../IImageProperties/index.md)|Image Properties\.|


## See also

* [IExcelChart](../IExcelChart/index.md)

# IExcelChart\.AddImage\(TStream, IImageProperties\)
Adds an image to the active sheet\.
Note that for SVG images, xlsx files store both a PNG and SVG image\. To enter an SVG image, use [IEmbeddedObjects.AddImageAlternate](../IEmbeddedObjects/AddImageAlternate.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../IExcelChart/index.md">IExcelChart</a>.AddImage(const aStream: TStream; imageProperties: <a href="../IImageProperties/index.md">IImageProperties</a>); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aStream**|TStream|Stream containing the image data\.|
||**imageProperties**|[IImageProperties](../IImageProperties/index.md)|Placement and other properties of the image\.|


## See also

* [IExcelChart](../IExcelChart/index.md)

# IExcelChart\.AddImage\(string, IImageProperties\)
Adds an image to the active sheet\.
Note that for SVG images, xlsx files store both a PNG and SVG image\. To enter an SVG image, use [IEmbeddedObjects.AddImageAlternate](../IEmbeddedObjects/AddImageAlternate.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../IExcelChart/index.md">IExcelChart</a>.AddImage(const fileName: string; imageProperties: <a href="../IImageProperties/index.md">IImageProperties</a>); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**fileName**|string|Name of the file in disk containing the image data\.|
||**imageProperties**|[IImageProperties](../IImageProperties/index.md)|Placement and other properties of the image\.|


## See also

* [IExcelChart](../IExcelChart/index.md)

# IExcelChart\.AddImage\(TBytes, TXlsImgType, IImageProperties\)
Adds an image to the active sheet\.
Note that for SVG images, xlsx files store both a PNG and SVG image\. To enter an SVG image, use [IEmbeddedObjects.AddImageAlternate](../IEmbeddedObjects/AddImageAlternate.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../IExcelChart/index.md">IExcelChart</a>.AddImage(const data: TBytes; const imageType: <a href="../TXlsImgType.md">TXlsImgType</a>; imageProperties: <a href="../IImageProperties/index.md">IImageProperties</a>); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**data**|TBytes|byte array with the image data\.|
|const|**imageType**|[TXlsImgType](../TXlsImgType.md)|Type of image you are inserting \(bmp, jpg, etc\)\.|
||**imageProperties**|[IImageProperties](../IImageProperties/index.md)|Placement and other properties of the image\.|


## See also

* [IExcelChart](../IExcelChart/index.md)

# IExcelChart\.AddImage\(TStream, TXlsImgType, IImageProperties\)
Adds an image to the active sheet\.
Note that for SVG images, xlsx files store both a PNG and SVG image\. To enter an SVG image, use [IEmbeddedObjects.AddImageAlternate](../IEmbeddedObjects/AddImageAlternate.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../IExcelChart/index.md">IExcelChart</a>.AddImage(const aStream: TStream; const imageType: <a href="../TXlsImgType.md">TXlsImgType</a>; imageProperties: <a href="../IImageProperties/index.md">IImageProperties</a>); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aStream**|TStream|Stream containing the image data\.|
|const|**imageType**|[TXlsImgType](../TXlsImgType.md)|Type of image you are inserting \(bmp, jpg, etc\)\.|
||**imageProperties**|[IImageProperties](../IImageProperties/index.md)|Placement and other properties of the image\.|


## See also

* [IExcelChart](../IExcelChart/index.md)

