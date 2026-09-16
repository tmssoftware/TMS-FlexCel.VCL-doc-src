---
uid: IImgExportInfo
description: IImgExportInfo
---

# IImgExportInfo Interface

Holds information needed to export the pages, so it is only calculated once\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">IImgExportInfo = interface(IInterface);</code></pre>

## Methods

|Name|Description|
|---|---|
|[LightClone](LightClone.md)|Returns a light copy of a TImgExportInfo\.<br />|
|[LoadLightImg&#8203;Export&#8203;Info](LoadLightImgExportInfo.md)|Loads the export info that changes, and was saved with [ToLightImgExportInfo](ToLightImgExportInfo.md)|
|[Sheet](Sheet.md)|Returns the Image export info for one of the sheets\.<br />|
|[ToLightImgExportInfo](ToLightImgExportInfo.md)|Returns the export info that changes, so it can be cached\. This info can be later loaded with [LoadLightImg&#8203;Export&#8203;Info](LoadLightImgExportInfo.md)|
|[TotalLogicalPages](TotalLogicalPages.md)|Returns the total count of pages if ResetPageNumber&#8203;OnEach&#8203;Sheet is false, or the page count for the current sheet if true\.<br />|


## Properties

|Name|Description|
|---|---|
|[ActiveSheet](ActiveSheet.md)|TImageInfo for the active sheet\.<br />|
|[CurrentPage](CurrentPage.md)|Last page printed\.<br />|
|[CurrentSheet](CurrentSheet.md)|Sheet that is being printed\.<br />|
|[NextSheet](NextSheet.md)|Sheet of the next page to print\.<br />|
|[SheetCount](SheetCount.md)|Return the count of the sheets on the workbook\.<br />|
|[TotalPages](TotalPages.md)|Total pages to print for all the sheets\.<br />|


