---
uid: TExcelFile.SetHeaderOrFooterImage
description: TExcelFile.SetHeaderOrFooterImage
---

# TExcelFile\.SetHeaderOrFooterImage Method

## Overloads

* [TExcelFile\.SetHeaderOrFooterImage\(THeaderAndFooterKind, THeaderAndFooterPos, TBytes, IHeaderOrFooterImageProperties\)](#texcelfilesetheaderorfooterimagetheaderandfooterkind-theaderandfooterpos-tbytes-iheaderorfooterimageproperties)
* [TExcelFile\.SetHeaderOrFooterImage\(THeaderAndFooterKind, THeaderAndFooterPos, TBytes, TXlsImgType, IHeaderOrFooterImageProperties\)](#texcelfilesetheaderorfooterimagetheaderandfooterkind-theaderandfooterpos-tbytes-txlsimgtype-iheaderorfooterimageproperties)

# TExcelFile\.SetHeaderOrFooterImage\(THeaderAndFooterKind, THeaderAndFooterPos, TBytes, IHeaderOrFooterImageProperties\)
This method sets the image associated to a given section of the header or footer\.
There can be only one image per section, and you refer it from the header string  \(see [PageHeader](PageHeader.md) and [PageFooter](PageFooter.md)\) by writing &amp;G\.
NOTE THAT YOU CAN ONLY USE HEADER AND FOOTER GRAPHICS ON EXCEL XP AND NEWER\. Excel 2000 and 97 will still open the file, but they will show no graphics\.
ALSO, NOTE that only setting the image will not display it\. You need to write &amp;G in  the corresponding [PageHeader](PageHeader.md) or [PageFooter](PageFooter.md) This methods will try to automatically guess/convert the image type of the data to the better fit\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetHeaderOrFooterImage(const headerAndFooterKind: <a href="../THeaderAndFooterKind.md">THeaderAndFooterKind</a>; const section: <a href="../THeaderAndFooterPos.md">THeaderAndFooterPos</a>; data: TBytes; properties: <a href="../IHeaderOrFooterImageProperties/index.md">IHeaderOrFooterImageProperties</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**headerAndFooterKind**|[THeaderAndFooterKind](../THeaderAndFooterKind.md)|Type of page for which we want to set the image\. You will normally get this value from [THeaderAndFooter.GetHeaderAndFooterKind](../THeaderAndFooter/GetHeaderAndFooterKind.md)\.|
|const|**section**|[THeaderAndFooterPos](../THeaderAndFooterPos.md)|Section of the header or footer for which we want to set the image\.|
||**data**|TBytes|Image data\.|
||**properties**|[IHeaderOrFooter&#8203;Image&#8203;Properties](../IHeaderOrFooterImageProperties/index.md)|Image Size\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetHeaderOrFooterImage\(THeaderAndFooterKind, THeaderAndFooterPos, TBytes, TXlsImgType, IHeaderOrFooterImageProperties\)
This method sets the image associated to a given section of the header or footer\.
There can be only one image per section, and you refer it from the header string  \(see [PageHeader](PageHeader.md) and [PageFooter](PageFooter.md)\) by writing &amp;G\.
NOTE THAT YOU CAN ONLY USE HEADER AND FOOTER GRAPHICS ON EXCEL XP AND NEWER\. Excel 2000 and 97 will still open the file, but they will show no graphics\.
ALSO, NOTE that only setting the image will not display it\. You need to write &amp;G in  the corresponding [PageHeader](PageHeader.md) or [PageFooter](PageFooter.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetHeaderOrFooterImage(const headerAndFooterKind: <a href="../THeaderAndFooterKind.md">THeaderAndFooterKind</a>; const section: <a href="../THeaderAndFooterPos.md">THeaderAndFooterPos</a>; const data: TBytes; const imageType: <a href="../TXlsImgType.md">TXlsImgType</a>; properties: <a href="../IHeaderOrFooterImageProperties/index.md">IHeaderOrFooterImageProperties</a>); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**headerAndFooterKind**|[THeaderAndFooterKind](../THeaderAndFooterKind.md)|Type of page for which we want to set the image\. You will normally get this value from [THeaderAndFooter.GetHeaderAndFooterKind](../THeaderAndFooter/GetHeaderAndFooterKind.md)\.|
|const|**section**|[THeaderAndFooterPos](../THeaderAndFooterPos.md)|Section of the header or footer for which we want to set the image\.|
|const|**data**|TBytes|Image data\.|
|const|**imageType**|[TXlsImgType](../TXlsImgType.md)|The image type for the data sent\. \(If it is a bmp, jpg or other\)|
||**properties**|[IHeaderOrFooter&#8203;Image&#8203;Properties](../IHeaderOrFooterImageProperties/index.md)|Image size\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

