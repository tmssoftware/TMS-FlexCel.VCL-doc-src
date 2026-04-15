---
uid: TFlexCelPrintDocument.PrintSheet
description: TFlexCelPrintDocument.PrintSheet
---

# TFlexCelPrintDocument\.PrintSheet Method

## Overloads

* [TFlexCelPrintDocument\.PrintSheet](#tflexcelprintdocumentprintsheet)
* [TFlexCelPrintDocument\.PrintSheet\(Integer, Integer, Integer, Integer\)](#tflexcelprintdocumentprintsheetinteger-integer-integer-integer)

# TFlexCelPrintDocument\.PrintSheet
Prints the activesheet on the current XlsFile\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelPrintDocument/index.md">TFlexCelPrintDocument</a>.PrintSheet; overload;</code></pre>

## See also

* [TFlexCelPrintDocument](../TFlexCelPrintDocument/index.md)

# TFlexCelPrintDocument\.PrintSheet\(Integer, Integer, Integer, Integer\)
Prints the active sheet on the current XlsFile\. You can define which is the first page to print and the global count of pages, so the page numbers on headers and footers of the excel file correspond with the actual pages on the printout\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelPrintDocument/index.md">TFlexCelPrintDocument</a>.PrintSheet(const startPageToDisplay: Integer; totalPagesToDisplay: Integer; startPageToPrint: Integer = 1; totalPagesToPrint: Integer = -1); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**startPageToDisplay**|Integer|First page that the headers and footers on the xls file will show\. If you are printing only one sheet, this can be 1\. If you are exporting more than one sheet in the same process, you will want to set StartPage to the actual page on the printout\.|
||**totalPagesToDisplay**|Integer|The total number of pages to display on Excel headers and footers\.<br />If you are printing only one sheet, set it to \-1, and it will be calculated automatically\.<br />If not, please supply here the total number of pages the file will have so FlexCel can show footers like "page 1 of 50"|
||**startPageToPrint**|Integer|**Optional**: Default value is 1<br /><br />First page on the file to print \(first page is 1\)\.|
||**totalPagesToPrint**|Integer|**Optional**: Default value is -1<br /><br />How many pages will be printed\. If you specify a negative number here \(the default\), all pages from startPageToPrint will be printed\.|


## See also

* [TFlexCelPrintDocument](../TFlexCelPrintDocument/index.md)

