---
uid: IOneImgExportInfo
description: IOneImgExportInfo
---

# IOneImgExportInfo Interface

Holds information needed to export one of the workbook sheets, so it is only calculated once\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">IOneImgExportInfo = interface(IInterface);</code></pre>

## Methods

|Name|Description|
|---|---|
|[RestorePagePrint&#8203;Range](RestorePagePrintRange.md)|Restores the original print range\. Internal use\.<br />|


## Properties

|Name|Description|
|---|---|
|[TotalPages](TotalPages.md)|Total pages on the ActiveSheet\.<br />|
|[CurrentPrintArea](CurrentPrintArea.md)|Area that is currently being printed\. A print area might consist in many independent areas\.<br />|
|[PaintClipRect](PaintClipRect.md)|Coordinates to print\. One per every isolated range in the print area of the sheet\.<br />|
|[PagePrintRange](PagePrintRange.md)|Range that has been printed\. Note that before printing, the values here are invalid and you should use [PrintRanges](PrintRanges.md)|
|[PageBounds](PageBounds.md)|Limits of the page in inches/100\.<br />|
|[PrintRanges](PrintRanges.md)|Range that will be printed\.<br />One per every isolated range in the print area of the sheet\.<br />|
|[ZoomUsed](ZoomUsed.md)|The final zoom that will be used in the sheet after applying print to fit or other factors\.<br />|
|[PrintRange](PrintRange.md)|Range that will be printed\. When the print area is composed of different non\-contiguous parts you should use [PrintRanges](PrintRanges.md) to get all the parts\.<br />|
|[CurrentPage](CurrentPage.md)|Last page printed on this sheet\.<br />|


