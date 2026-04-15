---
uid: TFlexCelSVGExport
description: TFlexCelSVGExport
---

# TFlexCelSVGExport Class

A component for exporting an Excel file to an SVG \(Scalable Vector Graphics\) image\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">TFlexCelSVGExport = class(TFlexCelObject);</code></pre>

## Fields

|Name|Description|
|---|---|
|[FCompress](FCompress.md)|If true, the file will be compressed\. This property is just for derived classes, for normal cases use [Compress](Compress.md)|


## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create](Create.md#tflexcelsvgexportcreate)<br />  [Create\(TExcelFile\)](Create.md#tflexcelsvgexportcreatetexcelfile)<br />  [Create\(TExcelFile, Boolean\)](Create.md#tflexcelsvgexportcreatetexcelfile-boolean)<br />|


## Methods

|Name|Description|
|---|---|
|[TotalPagesInSheet](TotalPagesInSheet.md)|Returns the number of pages that the active sheet will use when exported to SVG\.<br />|
|[SaveAsImage](SaveAsImage.md)|Saves the current Excel file on an SVG image stream\.<br />|


## Properties

|Name|Description|
|---|---|
|[Workbook](Workbook.md)|The ExcelFile to print\.<br />|
|[Compress](Compress.md)|When true, the pdf file will be compressed\.<br />|
|[HidePrintObjects](HidePrintObjects.md)|Select which kind of objects should not be printed or exported to the image\.<br />|
|[ExportSheetBackground&#8203;Images](ExportSheetBackgroundImages.md)|If false \(the default\) then the background images in the sheet won't be exported\. Note that Excel doesn't print or export background images, and when it shows them on the screen they look the same no matter the sheet zoom\.<br />When you set this to true we will try to export the image, but it will grow and shrink when you zoom, making it look different from what Excel shows\.<br />|
|[RasterizeSVGImages](RasterizeSVGImages.md)|If false \(the default\) then FlexCel will export SVG images inside the Excel file as SVG images inside the generated SVG\.<br />If true, FlexCel will convert the SVG images to PNG and embed the PNG inside the SVG\. This might be more accurate specially if the embedded SVG uses fonts that might not be present in the client machine\. See [S V G Files Inside Xlsx Files](xref:SVGFilesInsideXlsxFiles) for more information\.<br />|
|[PrintRangeLeft](PrintRangeLeft.md)|First column to print \(1 based\)\. if this or any other PrintRange property is 0, the range will be automatically calculated\.<br />|
|[PrintRangeTop](PrintRangeTop.md)|First row to print \(1 based\)\. if this or any other PrintRange property is 0, the range will be automatically calculated\.<br />|
|[PrintRangeRight](PrintRangeRight.md)|Last column to print \(1 based\)\. if this or any other PrintRange property is 0, the range will be automatically calculated\.<br />|
|[PrintRangeBottom](PrintRangeBottom.md)|Last row to print \(1 based\)\. if this or any other PrintRange property is 0, the range will be automatically calculated\.<br />|
|[PageSize](PageSize.md)|Image page size\. Set it to null to use the paper size on the xls file\.<br />|
|[AllowOverwriting&#8203;Files](AllowOverwritingFiles.md)|Determines if FlexCel will automatically delete existing image files or not\.<br />|
|[AllVisibleSheets](AllVisibleSheets.md)|If true, all visible sheets on the workbook will be printed\. See [ResetPageNumber&#8203;OnEach&#8203;Sheet](ResetPageNumberOnEachSheet.md) for behavior of the page number when printing multiple sheets\.<br />|
|[ResetPageNumber&#8203;OnEach&#8203;Sheet](ResetPageNumberOnEachSheet.md)|This property only makes sense when [AllVisibleSheets](AllVisibleSheets.md) is true\. On that case, if this property is true each sheet of the workbook will have the page number reset\. For example if the xls file has 2 sheets and each has 3 pages:  When ResetPageNumber&#8203;OnEach&#8203;Sheet = true then footers will look like "Page 1 of 3"\. If false, they will look like "Page 5 of 6"|
|[ExportType](ExportType.md)|How much of the svg will be exported\.<br />|
|[Encoding](Encoding.md)|Encoding used to generate the SVG file\. If null, UTF8 without BOM will be used\.<br />|
|[IdPrefix](IdPrefix.md)|Prefix to be used in all definitions inside the svg file\. For normal SVG files you can leave this null, but if you are embedding the files inside an html file, you need to ensure every image has unique identifiers\.<br />All SVG identifiers from different images inside an html file must be unique\.<br />|
|[LinksInNewWindow](LinksInNewWindow.md)|IF true, links will be exported to open in a new window\. \(using the show=new attribute in svg links\)|


