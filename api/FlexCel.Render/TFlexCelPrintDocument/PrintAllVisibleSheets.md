---
uid: TFlexCelPrintDocument.PrintAllVisibleSheets
description: TFlexCelPrintDocument.PrintAllVisibleSheets
---

# TFlexCelPrintDocument\.PrintAllVisibleSheets Method

This method will print all the visible sheets on an xls file\.
Different than calling PrintSheet for each sheet, this method can keep the page number growing on each sheet, without resetting it\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelPrintDocument/index.md">TFlexCelPrintDocument</a>.PrintAllVisibleSheets(const resetPageNumberOnEachSheet: Boolean; startPageToPrint: Integer = 1; totalPagesToPrint: Integer = -1); virtual;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**resetPageNumberOnEachSheet**|Boolean|If true, each new sheet will reset the page number shown on Excel headers and footers\.|
||**startPageToPrint**|Integer|**Optional**: Default value is 1<br /><br />First page on the file to print \(first page is 1\)\.|
||**totalPagesToPrint**|Integer|**Optional**: Default value is -1<br /><br />How many pages will be printed\. If you specify a negative number here \(the default\), all pages from startPageToPrint will be printed\.|


## See also

* [TFlexCelPrintDocument](../TFlexCelPrintDocument/index.md)

