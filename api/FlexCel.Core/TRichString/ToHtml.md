---
uid: TRichString.ToHtml
description: TRichString.ToHtml
---

# TRichString\.ToHtml Method

## Overloads

* [TRichString\.ToHtml\(TCoreExcelFile, TFlxFormat, THtmlVersion, THtmlStyle, TEncoding\)](#trichstringtohtmltcoreexcelfile-tflxformat-thtmlversion-thtmlstyle-tencoding)
* [TRichString\.ToHtml\(TCoreExcelFile, TFlxFormat, THtmlVersion, THtmlStyle, TEncoding, IHtmlFontEvent\)](#trichstringtohtmltcoreexcelfile-tflxformat-thtmlversion-thtmlstyle-tencoding-ihtmlfontevent)

# TRichString\.ToHtml\(TCoreExcelFile, TFlxFormat, THtmlVersion, THtmlStyle, TEncoding\)
Returns the rich string content as an HTML Formatted string\. **Note: This method is for advanced uses only\. Normally you would just use [TExcelFile.GetHtmlFromCell\(Integer, Integer, THtmlVersion, THtmlStyle, TEncoding\)](../TExcelFile/GetHtmlFromCell.md#texcelfilegethtmlfromcellinteger-integer-thtmlversion-thtmlstyle-tencoding)**

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TRichString/index.md">TRichString</a>.ToHtml(const aWorkbook: TCoreExcelFile; const aCellFormat: <a href="../TFlxFormat/index.md">TFlxFormat</a>; const htmlVersion: <a href="../THtmlVersion.md">THtmlVersion</a>; const htmlStyle: <a href="../THtmlStyle.md">THtmlStyle</a>; const aEncoding: TEncoding): string; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aWorkbook**|TCoreExcelFile|ExcelFile where the cell is\.|
|const|**aCellFormat**|[TFlxFormat](../TFlxFormat/index.md)|Format of the cell where this string is\.|
|const|**htmlVersion**|[THtmlVersion](../THtmlVersion.md)|Version of the html returned\. In XHTML, single tags have a "/" at the end, while in 4\.0 they don't\.|
|const|**htmlStyle**|[THtmlStyle](../THtmlStyle.md)|Specifies whether to use CSS or not\.|
|const|**aEncoding**|TEncoding|Encoder used to return the string\. Use UTF\-8 for normal cases\.|


## Returns

The string formatted as an HTML string\.

## See also

* [TRichString](../TRichString/index.md)

# TRichString\.ToHtml\(TCoreExcelFile, TFlxFormat, THtmlVersion, THtmlStyle, TEncoding, IHtmlFontEvent\)
Returns the rich string content as an HTML Formatted string\. **Note: This method is for advanced uses only\. Normally you would just use [TExcelFile.GetHtmlFromCell\(Integer, Integer, THtmlVersion, THtmlStyle, TEncoding\)](../TExcelFile/GetHtmlFromCell.md#texcelfilegethtmlfromcellinteger-integer-thtmlversion-thtmlstyle-tencoding)**

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TRichString/index.md">TRichString</a>.ToHtml(const aWorkbook: TCoreExcelFile; const aCellFormat: <a href="../TFlxFormat/index.md">TFlxFormat</a>; const htmlVersion: <a href="../THtmlVersion.md">THtmlVersion</a>; const htmlStyle: <a href="../THtmlStyle.md">THtmlStyle</a>; const aEncoding: TEncoding; const OnHtmlFont: <a href="../IHtmlFontEvent/index.md">IHtmlFontEvent</a>): string; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aWorkbook**|TCoreExcelFile|ExcelFile where the cell is\.|
|const|**aCellFormat**|[TFlxFormat](../TFlxFormat/index.md)|Format of the cell where this string is\.|
|const|**htmlVersion**|[THtmlVersion](../THtmlVersion.md)|Version of the html returned\. In XHTML, single tags have a "/" at the end, while in 4\.0 they don't\.|
|const|**htmlStyle**|[THtmlStyle](../THtmlStyle.md)|Specifies whether to use CSS or not\.|
|const|**aEncoding**|TEncoding|Encoder used to return the string\. Use UTF\-8 for normal cases\.|
|const|**OnHtmlFont**|[IHtmlFontEvent](../IHtmlFontEvent/index.md)|Provide this parameter to customize what to do when different fonts are found in the string\.|


## Returns

The string formatted as an HTML string\.

## See also

* [TRichString](../TRichString/index.md)

