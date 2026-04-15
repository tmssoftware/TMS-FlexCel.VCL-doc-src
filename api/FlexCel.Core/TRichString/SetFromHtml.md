---
uid: TRichString.SetFromHtml
description: TRichString.SetFromHtml
---

# TRichString\.SetFromHtml Method

## Overloads

* [TRichString\.SetFromHtml\(string, TFlxFormat, TCoreExcelFile\)](#trichstringsetfromhtmlstring-tflxformat-tcoreexcelfile)
* [TRichString\.SetFromHtml\(string, TFlxFormat, TCoreExcelFile, Boolean\)](#trichstringsetfromhtmlstring-tflxformat-tcoreexcelfile-boolean)

# TRichString\.SetFromHtml\(string, TFlxFormat, TCoreExcelFile\)
Sets the rich string content from an HTML Formatted string\. **Note: This method is for advanced uses only\. Normally you would just use [TExcelFile.SetCellFromHtml\(Integer, Integer, string, Integer\)](../TExcelFile/SetCellFromHtml.md#texcelfilesetcellfromhtmlinteger-integer-string-integer)**

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TRichString/index.md">TRichString</a>.SetFromHtml(const HtmlString: string; const aCellFormat: <a href="../TFlxFormat/index.md">TFlxFormat</a>; const aWorkbook: TCoreExcelFile); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**HtmlString**|string|String with the HTML data\.|
|const|**aCellFormat**|[TFlxFormat](../TFlxFormat/index.md)|Initial format of the cell where we want to enter the html string\.|
|const|**aWorkbook**|TCoreExcelFile|ExcelFile where the cell is\.|


## See also

* [TRichString](../TRichString/index.md)

# TRichString\.SetFromHtml\(string, TFlxFormat, TCoreExcelFile, Boolean\)
Sets the rich string content from an HTML Formatted string\. **Note: This method is for advanced uses only\. Normally you would just use [TExcelFile.SetCellFromHtml\(Integer, Integer, string, Integer\)](../TExcelFile/SetCellFromHtml.md#texcelfilesetcellfromhtmlinteger-integer-string-integer)**

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TRichString/index.md">TRichString</a>.SetFromHtml(const HtmlString: string; const aCellFormat: <a href="../TFlxFormat/index.md">TFlxFormat</a>; const aWorkbook: TCoreExcelFile; const aMsFormat: Boolean); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**HtmlString**|string|String with the HTML data\.|
|const|**aCellFormat**|[TFlxFormat](../TFlxFormat/index.md)|Initial format of the cell where we want to enter the html string\.|
|const|**aWorkbook**|TCoreExcelFile|ExcelFile where the cell is\.|
|const|**aMsFormat**|Boolean|If true, we are reading a legacy object\.|


## See also

* [TRichString](../TRichString/index.md)

