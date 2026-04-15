---
uid: TExcelFile.GetHeaderOrFooterImage
description: TExcelFile.GetHeaderOrFooterImage
---

# TExcelFile\.GetHeaderOrFooterImage Method

## Overloads

* [TExcelFile\.GetHeaderOrFooterImage\(THeaderAndFooterKind, THeaderAndFooterPos, TXlsImgType, TStream\)](#texcelfilegetheaderorfooterimagetheaderandfooterkind-theaderandfooterpos-txlsimgtype-tstream)
* [TExcelFile\.GetHeaderOrFooterImage\(THeaderAndFooterKind, THeaderAndFooterPos, TXlsImgType\)](#texcelfilegetheaderorfooterimagetheaderandfooterkind-theaderandfooterpos-txlsimgtype)

# TExcelFile\.GetHeaderOrFooterImage\(THeaderAndFooterKind, THeaderAndFooterPos, TXlsImgType, TStream\)
This method returns the images associated to a given section of the header or footer\.
There can be only one image per section, and you refer it from the header string  \(see [PageHeader](PageHeader.md) and [PageFooter](PageFooter.md)\) by writing &amp;G\.
NOTE THAT YOU CAN ONLY USE HEADER AND FOOTER GRAPHICS ON EXCEL XP AND NEWER\. Excel 2000 and 97 will still open the file, but they will show no graphics\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.GetHeaderOrFooterImage(const headerAndFooterKind: <a href="../THeaderAndFooterKind.md">THeaderAndFooterKind</a>; const section: <a href="../THeaderAndFooterPos.md">THeaderAndFooterPos</a>; var imageType: <a href="../TXlsImgType.md">TXlsImgType</a>; const outStream: TStream); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**headerAndFooterKind**|[THeaderAndFooterKind](../THeaderAndFooterKind.md)|Type of page for which we want to retrieve the image\. You will normally get this value from [THeaderAndFooter.GetHeaderAndFooterKind](../THeaderAndFooter/GetHeaderAndFooterKind.md)\.|
|const|**section**|[THeaderAndFooterPos](../THeaderAndFooterPos.md)|Section of the header or footer for which we want to retrieve the image\.|
|var|**imageType**|[TXlsImgType](../TXlsImgType.md)|**Returns** the image type for the data returned\. \(If it is a bmp, jpg or other\)|
|const|**outStream**|TStream|Stream where the image data will be copied\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.GetHeaderOrFooterImage\(THeaderAndFooterKind, THeaderAndFooterPos, TXlsImgType\)
This method returns the images associated to a given section of the header or footer\.
There can be only one image per section, and you refer it from the header string  \(see [PageHeader](PageHeader.md) and [PageFooter](PageFooter.md)\) by writing &amp;G\.
NOTE THAT YOU CAN ONLY USE HEADER AND FOOTER GRAPHICS ON EXCEL XP AND NEWER\. Excel 2000 and 97 will still open the file, but they will show no graphics\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetHeaderOrFooterImage(const headerAndFooterKind: <a href="../THeaderAndFooterKind.md">THeaderAndFooterKind</a>; const section: <a href="../THeaderAndFooterPos.md">THeaderAndFooterPos</a>; var imageType: <a href="../TXlsImgType.md">TXlsImgType</a>): TBytes; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**headerAndFooterKind**|[THeaderAndFooterKind](../THeaderAndFooterKind.md)|Type of page for which we want to retrieve the image\. You will normally get this value from [THeaderAndFooter.GetHeaderAndFooterKind](../THeaderAndFooter/GetHeaderAndFooterKind.md)\.|
|const|**section**|[THeaderAndFooterPos](../THeaderAndFooterPos.md)|Section of the header or footer for which we want to retrieve the image\.|
|var|**imageType**|[TXlsImgType](../TXlsImgType.md)|**Returns** the image type for the data returned\. \(If it is a bmp, jpg or other\)|


## Returns

Bytes for the image\. Null if there is no image on this position\.

## See also

* [TExcelFile](../TExcelFile/index.md)

