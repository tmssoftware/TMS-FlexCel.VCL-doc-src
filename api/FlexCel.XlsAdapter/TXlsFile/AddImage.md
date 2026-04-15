---
uid: TXlsFile.AddImage
description: TXlsFile.AddImage
---

# TXlsFile\.AddImage Method

Adds an image to the active sheet\.
Note that for SVG images, xlsx files store both a PNG and SVG image\. To enter an SVG image, use [TExcelFile.AddImageAlternate](../../FlexCel.Core/TExcelFile/AddImageAlternate.md)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.AddImage(const data: TBytes; const imageType: <a href="../../FlexCel.Core/TXlsImgType.md">TXlsImgType</a>; imageProperties: <a href="../../FlexCel.Core/IImageProperties/index.md">IImageProperties</a>); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**data**|TBytes|byte array with the image data\.|
|const|**imageType**|[TXlsImgType](../../FlexCel.Core/TXlsImgType.md)|Type of image you are inserting \(bmp, jpg, etc\)\.|
||**imageProperties**|[IImageProperties](../../FlexCel.Core/IImageProperties/index.md)|Placement and other properties of the image\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

