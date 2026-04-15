---
uid: TPageEventArgs
description: TPageEventArgs
---

# TPageEventArgs Class

Arguments passed on [TFlexCelPdfExport.BeforeGeneratePage](../TFlexCelPdfExport/BeforeGeneratePage.md), [TFlexCelPdfExport.BeforeNewPage](../TFlexCelPdfExport/BeforeNewPage.md) and [TFlexCelPdfExport.AfterGeneratePage](../TFlexCelPdfExport/AfterGeneratePage.md)

## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">TPageEventArgs = class(EventArgs);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new Argument\.<br />|


## Properties

|Name|Description|
|---|---|
|[PdfExport](PdfExport.md)|The FlexCelPdfExport component doing the export\.<br />|
|[Workbook](Workbook.md)|ExcelFile we are exporting\. Note that this might be a light clone of the workbook assigned to the FlexCelPdfExport component, so it might be different\.<br />|
|[DataFile](DataFile.md)|The file with the pdf data\.<br />|
|[CurrentPage](CurrentPage.md)|Page currently printing\.<br />|
|[CurrentPageInSheet](CurrentPageInSheet.md)|Page currently printing on the sheet printing\.<br />|
|[CurrentSheet](CurrentSheet.md)|Sheet that is currently being printed\.<br />|


