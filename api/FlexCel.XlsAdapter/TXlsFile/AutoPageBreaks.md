---
uid: TXlsFile.AutoPageBreaks
description: TXlsFile.AutoPageBreaks
---

# TXlsFile\.AutoPageBreaks Method

## Overloads

* [TXlsFile\.AutoPageBreaks\(Integer, Integer\)](#txlsfileautopagebreaksinteger-integer)
* [TXlsFile\.AutoPageBreaks\(Integer, TUIRectangle\)](#txlsfileautopagebreaksinteger-tuirectangle)

# TXlsFile\.AutoPageBreaks\(Integer, Integer\)
This method will create manual page breaks in the sheet to try to keep together the rows and columns marked with  [TExcelFile.KeepRowsTogether](../../FlexCel.Core/TExcelFile/KeepRowsTogether.md) and [TExcelFile.KeepColsTogether](../../FlexCel.Core/TExcelFile/KeepColsTogether.md)\.
It might be desirable to clear all manual page breaks \(with [TExcelFile.ClearPageBreaks](../../FlexCel.Core/TExcelFile/ClearPageBreaks.md)\) before calling this method, so it has more freedom to place the new ones\. If you call this method twice without removing the old page breaks, it will add the page breaks to the existing ones\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.AutoPageBreaks(const PercentOfUsedSheet: Integer; const PageScale: Integer); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**PercentOfUsedSheet**|Integer|Percentage of the sheet that must be used in any page when fitting the rows and columns\.<br />A value of zero means that no part of the sheet must be used, so FlexCel might add a page break after a single row in a page, leaving it almost completely blank\.<br /><br />A value of 50%% means that half of the page must be used\. This means that FlexCel will add a page break only if there is 50%% of the current page already used\.<br /><br />A value of 100%% will do nothing, since the sheet must be completely used, and so FlexCel can never add a page break\.<br />|
|const|**PageScale**|Integer|This parameter must be between 50 and 100, and means how much smaller page will be considered in order to calculate the page breaks\.<br /><br />A value of 100 means that the size used in the calculation will be the real size of the page, and while this will always work fine when exporting to PDF  or exporting to images, when printing from Excel might result in a page break that is placed a little after where it should go and an empty page for certain printers\.<br />\(Page size in Excel is different for different printers\) Normally a value around 95 is the recommended value for this parameter\.<br /><br />If you need to do a finer grain adjustment, you can use [TExcelFile.AutoPageBreaks\(Integer, TUIRectangle\)](../../FlexCel.Core/TExcelFile/AutoPageBreaks.md#texcelfileautopagebreaksinteger-tuirectangle)\.<br />|


## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.AutoPageBreaks\(Integer, TUIRectangle\)
This method will create manual page breaks in the sheet to try to keep together the rows and columns marked with  [TExcelFile.KeepRowsTogether](../../FlexCel.Core/TExcelFile/KeepRowsTogether.md) and [TExcelFile.KeepColsTogether](../../FlexCel.Core/TExcelFile/KeepColsTogether.md)\.
It might be desirable to clear all manual page breaks \(with [TExcelFile.ClearPageBreaks](../../FlexCel.Core/TExcelFile/ClearPageBreaks.md)\) before calling this method, so it has more freedom to place the new ones\. If you call this method twice without removing the old page breaks, it will add the page breaks to the existing ones\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.AutoPageBreaks(const PercentOfUsedSheet: Integer; const PageBounds: <a href="../../FlexCel.Core/TUIRectangle/index.md">TUIRectangle</a>); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**PercentOfUsedSheet**|Integer|Percentage of the sheet that must be used in any page when fitting the rows and columns\.<br />A value of zero means that no part of the sheet must be used, so FlexCel might add a page break after a single row in a page, leaving it almost completely blank\.<br /><br />A value of 50%% means that half of the page must be used\. This means that FlexCel will add a page break only if there is 50%% of the current page already used\.<br /><br />A value of 100%% will do nothing, since the sheet must be completely used, and so FlexCel can never add a page break\.<br />|
|const|**PageBounds**|[TUIRectangle](../../FlexCel.Core/TUIRectangle/index.md)|You can customize a custom page size here\. If width or height of this parameter is 0, the paper size specified in the file will be used\. There is normally no need to set this parameter, unless you want to fine tune the results\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

