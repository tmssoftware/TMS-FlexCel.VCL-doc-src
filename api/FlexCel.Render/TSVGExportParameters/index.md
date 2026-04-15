---
uid: TSVGExportParameters
description: TSVGExportParameters
---

# TSVGExportParameters Class

Parameters used when exporting to SVG\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">TSVGExportParameters = class(TFlexCelObject);</code></pre>

## Properties

|Name|Description|
|---|---|
|[Workbook](Workbook.md)|Excel file that we are exporting\. Note that this is a LightClone\(\) of the original ExcelFile that was passed to the export, and might have a different active sheet\. If you need to access the file from the export action,  use this parameter and not the original ExcelFile\.<br />|
|[PageNumber](PageNumber.md)|Page number we are currently exporting\.<br />|
|[SheetPageNumber](SheetPageNumber.md)|Page number in the sheet we are exporting\. Different from [PageNumber](PageNumber.md), this value is local to the current sheet, and it is reset every time we export a different sheet\. If you are exporting a single sheet \(&#8203;FlexCel&#8203;SVGExport\.&#8203;All&#8203;Visible&#8203;Sheets is false\), then this variable will have the same value as [PageNumber](PageNumber.md)|
|[TotalPages](TotalPages.md)|Total number of pages to export\.<br />|
|[TotalPagesInSheet](TotalPagesInSheet.md)|Number of pages in the sheet we are exporting\. Different from [TotalPages](TotalPages.md), this value is local to the current sheet, and it is reset every time we export a different sheet\. If you are exporting a single sheet \(&#8203;FlexCel&#8203;SVGExport\.&#8203;All&#8203;Visible&#8203;Sheets is false\), then this variable will have the same value as [TotalPages](TotalPages.md)|
|[FileStream](FileStream.md)|Stream where the image will be saved\. If you leave it null, the image won't be saved to a stream\.<br />|
|[FileName](FileName.md)|Filename where the image will be saved\. If you leave it null or empty, the image won't be saved to a file\.<br />|
|[Canceled](Canceled.md)|Set this property to true to cancel the export process\.<br />|
|[Title](Title.md)|Title to be saved with the image\. If null or empty, the svg image will have no title tag\.<br />|
|[Description](Description.md)|Description to be saved with the image\. If null or empty, the svg image will have no description tag\.<br />|
|[ExtraSVGAttributes](ExtraSVGAttributes.md)|Extra attributes that will be added to the \<svg> definition\. Keep it null to not add any extra attribute\.<br />|


