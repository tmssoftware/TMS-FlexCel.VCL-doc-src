---
uid: TXlsFile.GetHeaderOrFooterImage
description: TXlsFile.GetHeaderOrFooterImage
---

# TXlsFile\.GetHeaderOrFooterImage Method

This method returns the images associated to a given section of the header or footer\.
There can be only one image per section, and you refer it from the header string  \(see [TExcelFile.PageHeader](../../FlexCel.Core/TExcelFile/PageHeader.md) and [TExcelFile.PageFooter](../../FlexCel.Core/TExcelFile/PageFooter.md)\) by writing &amp;G\.
NOTE THAT YOU CAN ONLY USE HEADER AND FOOTER GRAPHICS ON EXCEL XP AND NEWER\. Excel 2000 and 97 will still open the file, but they will show no graphics\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.GetHeaderOrFooterImage(const headerAndFooterKind: <a href="../../FlexCel.Core/THeaderAndFooterKind.md">THeaderAndFooterKind</a>; const section: <a href="../../FlexCel.Core/THeaderAndFooterPos.md">THeaderAndFooterPos</a>; var imageType: <a href="../../FlexCel.Core/TXlsImgType.md">TXlsImgType</a>; const outStream: TStream); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**headerAndFooterKind**|[THeaderAndFooterKind](../../FlexCel.Core/THeaderAndFooterKind.md)|Type of page for which we want to retrieve the image\. You will normally get this value from [THeaderAndFooter.GetHeaderAndFooterKind](../../FlexCel.Core/THeaderAndFooter/GetHeaderAndFooterKind.md)\.|
|const|**section**|[THeaderAndFooterPos](../../FlexCel.Core/THeaderAndFooterPos.md)|Section of the header or footer for which we want to retrieve the image\.|
|var|**imageType**|[TXlsImgType](../../FlexCel.Core/TXlsImgType.md)|**Returns** the image type for the data returned\. \(If it is a bmp, jpg or other\)|
|const|**outStream**|TStream|Stream where the image data will be copied\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

