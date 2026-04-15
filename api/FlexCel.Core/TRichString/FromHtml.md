---
uid: TRichString.FromHtml
description: TRichString.FromHtml
---

# TRichString\.FromHtml Method

Returns a new TRichString from an HTML text\. Note that only some tags from HTML are converted, the ones that do not have correspondence on Excel rich text will be discarded\.**Note: This method is for advanced uses only\. Normally you would just use [TExcelFile.SetCellFromHtml\(Integer, Integer, string, Integer\)](../TExcelFile/SetCellFromHtml.md#texcelfilesetcellfromhtmlinteger-integer-string-integer)**

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TRichString/index.md">TRichString</a>.FromHtml(const HtmlString: string; const aCellFormat: <a href="../TFlxFormat/index.md">TFlxFormat</a>; const aWorkbook: TCoreExcelFile): <a href="../TRichString/index.md">TRichString</a>; static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**HtmlString**|string|Html string we want to convert\.|
|const|**aCellFormat**|[TFlxFormat](../TFlxFormat/index.md)|Original format of the cell where we want to enter the string\. Note that depending on the starting cell, the Rich string will be different\.<br />For example, if you have a cell with Red text and add a "hello \<b> world" string, then resulting RichString will include a RED bold "world" string|
|const|**aWorkbook**|TCoreExcelFile|File where this string will be added\.|


## Returns

A TRichString containing the converted Html\.

## See also

* [TRichString](../TRichString/index.md)

