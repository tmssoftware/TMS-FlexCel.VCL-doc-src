---
uid: TFlexCelPdfExport.ExportAllVisibleSheets
description: TFlexCelPdfExport.ExportAllVisibleSheets
---

# TFlexCelPdfExport\.ExportAllVisibleSheets Method

## Overloads

* [TFlexCelPdfExport\.ExportAllVisibleSheets\(Boolean, string\)](#tflexcelpdfexportexportallvisiblesheetsboolean-string)
* [TFlexCelPdfExport\.ExportAllVisibleSheets\(string, Boolean, string\)](#tflexcelpdfexportexportallvisiblesheetsstring-boolean-string)

# TFlexCelPdfExport\.ExportAllVisibleSheets\(Boolean, string\)
This method will export all the visible sheets on an xls file to pdf\.
Different than calling ExportSheet for each sheet, this method can keep the page number growing on each sheet, without resetting it\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelPdfExport/index.md">TFlexCelPdfExport</a>.ExportAllVisibleSheets(const resetPageNumberOnEachSheet: Boolean; const bookmarkName: string); overload; virtual;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**resetPageNumberOnEachSheet**|Boolean|If true, each new sheet will reset the page number shown on Excel headers and footers\.|
|const|**bookmarkName**|string|If not null, each sheet will be added as an entry on the Bookmarks in the pdf file, under the name specified here\.<br />If you want the Bookmark window to be visible when you open the pdf file, set [TPdfWriter.PageLayout](../../FlexCel.Pdf/TPdfWriter/PageLayout.md) = [TPageLayout](../../FlexCel.Pdf/TPageLayout.md)  Also, use the [GetBookmarkInformation](GetBookmarkInformation.md) event to further customize what goes in each of the entries\.<br />|


## See also

* [TFlexCelPdfExport](../TFlexCelPdfExport/index.md)

# TFlexCelPdfExport\.ExportAllVisibleSheets\(string, Boolean, string\)
This method will export all the visible sheets on an xls file to pdf\.
This method is a shortcut for creating a filestream, calling [BeginExport](BeginExport.md) on the filestream, calling [ExportAllVisibleSheets\(Boolean, string\)](ExportAllVisibleSheets.md#tflexcelpdfexportexportallvisiblesheetsboolean-string) and then calling [EndExport](EndExport.md)\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelPdfExport/index.md">TFlexCelPdfExport</a>.ExportAllVisibleSheets(const fileName: string; const resetPageNumberOnEachSheet: Boolean; const bookmarkName: string); overload; virtual;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**fileName**|string|File where the file will be saved\.|
|const|**resetPageNumberOnEachSheet**|Boolean|If true, each new sheet will reset the page number shown on Excel headers and footers\.|
|const|**bookmarkName**|string|If not null, each sheet will be added as an entry on the Bookmarks in the pdf file, under the name specified here\.<br />If you want the Bookmark window to be visible when you open the pdf file, set [TPdfWriter.PageLayout](../../FlexCel.Pdf/TPdfWriter/PageLayout.md) = [TPageLayout](../../FlexCel.Pdf/TPageLayout.md)  Also, use the [GetBookmarkInformation](GetBookmarkInformation.md) event to further customize what goes in each of the entries\.<br />|


## See also

* [TFlexCelPdfExport](../TFlexCelPdfExport/index.md)

