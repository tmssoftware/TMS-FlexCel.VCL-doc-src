---
uid: TXlsFile.SetHeaderOrFooterImage
description: TXlsFile.SetHeaderOrFooterImage
---

# TXlsFile\.SetHeaderOrFooterImage Method

This method sets the image associated to a given section of the header or footer\.
There can be only one image per section, and you refer it from the header string  \(see [TExcelFile.PageHeader](../../FlexCel.Core/TExcelFile/PageHeader.md) and [TExcelFile.PageFooter](../../FlexCel.Core/TExcelFile/PageFooter.md)\) by writing &amp;G\.
NOTE THAT YOU CAN ONLY USE HEADER AND FOOTER GRAPHICS ON EXCEL XP AND NEWER\. Excel 2000 and 97 will still open the file, but they will show no graphics\.
ALSO, NOTE that only setting the image will not display it\. You need to write &amp;G in  the corresponding [TExcelFile.PageHeader](../../FlexCel.Core/TExcelFile/PageHeader.md) or [TExcelFile.PageFooter](../../FlexCel.Core/TExcelFile/PageFooter.md)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetHeaderOrFooterImage(const headerAndFooterKind: <a href="../../FlexCel.Core/THeaderAndFooterKind.md">THeaderAndFooterKind</a>; const section: <a href="../../FlexCel.Core/THeaderAndFooterPos.md">THeaderAndFooterPos</a>; const data: TBytes; const imageType: <a href="../../FlexCel.Core/TXlsImgType.md">TXlsImgType</a>; properties: <a href="../../FlexCel.Core/IHeaderOrFooterImageProperties/index.md">IHeaderOrFooterImageProperties</a>); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**headerAndFooterKind**|[THeaderAndFooterKind](../../FlexCel.Core/THeaderAndFooterKind.md)|Type of page for which we want to set the image\. You will normally get this value from [THeaderAndFooter.GetHeaderAndFooterKind](../../FlexCel.Core/THeaderAndFooter/GetHeaderAndFooterKind.md)\.|
|const|**section**|[THeaderAndFooterPos](../../FlexCel.Core/THeaderAndFooterPos.md)|Section of the header or footer for which we want to set the image\.|
|const|**data**|TBytes|Image data\.|
|const|**imageType**|[TXlsImgType](../../FlexCel.Core/TXlsImgType.md)|The image type for the data sent\. \(If it is a bmp, jpg or other\)|
||**properties**|[IHeaderOrFooter&#8203;Image&#8203;Properties](../../FlexCel.Core/IHeaderOrFooterImageProperties/index.md)|Image size\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

