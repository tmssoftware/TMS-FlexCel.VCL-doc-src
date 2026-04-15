---
uid: TFlexCelPdfExport.ExportSheet
description: TFlexCelPdfExport.ExportSheet
---

# TFlexCelPdfExport\.ExportSheet Method

## Overloads

* [TFlexCelPdfExport\.ExportSheet](#tflexcelpdfexportexportsheet)
* [TFlexCelPdfExport\.ExportSheet\(Integer, Integer\)](#tflexcelpdfexportexportsheetinteger-integer)
* [TFlexCelPdfExport\.ExportSheet\(Integer, Integer, Integer, Integer\)](#tflexcelpdfexportexportsheetinteger-integer-integer-integer)

# TFlexCelPdfExport\.ExportSheet
Exports the activesheet on the current XlsFile\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelPdfExport/index.md">TFlexCelPdfExport</a>.ExportSheet; overload;</code></pre>

## See also

* [TFlexCelPdfExport](../TFlexCelPdfExport/index.md)

# TFlexCelPdfExport\.ExportSheet\(Integer, Integer\)
Exports the active sheet on the current XlsFile\. You can define which is the first page to print and the global count of pages, so the  page numbers on headers and footers of the excel file correspond with the actual pages on the pdf\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelPdfExport/index.md">TFlexCelPdfExport</a>.ExportSheet(const startPageToDisplay: Integer; const totalPagesToDisplay: Integer); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**startPageToDisplay**|Integer|First page that the headers and footers on the xls file will show\. If you are exporting only one sheet to the pdf file, this can be 1\. If you are exporting more than one sheet to the same pdf file, you will want to set StartPage to the actual page on the pdf\.|
|const|**totalPagesToDisplay**|Integer|The total number of pages to display on Excel headers and footers\. If you are exporting only one sheet to the pdf file, set it to \-1, and it will be calculated automatically\. If not, please supply here the total number of pages the file will have so FlexCel can show footers like "page 1 of 50"|


## See also

* [TFlexCelPdfExport](../TFlexCelPdfExport/index.md)

# TFlexCelPdfExport\.ExportSheet\(Integer, Integer, Integer, Integer\)
Exports the active sheet on the current XlsFile\. You can define which is the first page to print and the global count of pages, so the  page numbers on headers and footers of the excel file correspond with the actual pages on the pdf\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelPdfExport/index.md">TFlexCelPdfExport</a>.ExportSheet(const startPageToDisplay: Integer; totalPagesToDisplay: Integer; const startPageToExport: Integer; const totalPagesToExport: Integer); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**startPageToDisplay**|Integer|First page that the headers and footers on the xls file will show\. If you are exporting only one sheet to the pdf file, this can be 1\. If you are exporting more than one sheet to the same pdf file, you will want to set StartPage to the actual page on the pdf\.|
||**totalPagesToDisplay**|Integer|The total number of pages to display on Excel headers and footers\. If you are exporting only one sheet to the pdf file, set it to \-1, and it will be calculated automatically\. If not, please supply here the total number of pages the file will have so FlexCel can show footers like "page 1 of 50"|
|const|**startPageToExport**|Integer|First page on the file to export \(first page is 1\)\.|
|const|**totalPagesToExport**|Integer|How many pages will be exported\. If you specify a negative number here \(the default\), all pages from startPageToExport will be exported\.|


## See also

* [TFlexCelPdfExport](../TFlexCelPdfExport/index.md)

