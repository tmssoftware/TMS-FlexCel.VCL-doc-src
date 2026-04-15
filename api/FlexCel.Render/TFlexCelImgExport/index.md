---
uid: TFlexCelImgExport
description: TFlexCelImgExport
---

# TFlexCelImgExport Class

A component for exporting an Excel file to an image\. It can return an image object, or the actual bytes of a specific file format\. \(like gif, tiff or png\)

## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">TFlexCelImgExport = class(TFlexCelObject);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create](Create.md#tflexcelimgexportcreate)<br />  [Create\(TExcelFile\)](Create.md#tflexcelimgexportcreatetexcelfile)<br />  [Create\(TExcelFile, Boolean\)](Create.md#tflexcelimgexportcreatetexcelfile-boolean)<br />|


## Methods

|Name|Description|
|---|---|
|[OnBeforePaint](OnBeforePaint.md)|Replace this event when creating a custom descendant of FlexCelImgExport\.<br />|
|[OnAfterPaint](OnAfterPaint.md)|Replace this event when creating a custom descendant of FlexCelImgExport\.<br />|
|[ExportNext](ExportNext.md)|**Overloaded<br />**  [ExportNext\(TUIGraphics, IImgExportInfo\)](ExportNext.md#tflexcelimgexportexportnexttuigraphics-iimgexportinfo)<br />  [ExportNext\(TStream, TImageColorDepth, TXlsImgType, IImgExportInfo\)](ExportNext.md#tflexcelimgexportexportnexttstream-timagecolordepth-txlsimgtype-iimgexportinfo)<br />  [ExportNext\(string, TImageColorDepth, TXlsImgType, IImgExportInfo\)](ExportNext.md#tflexcelimgexportexportnextstring-timagecolordepth-txlsimgtype-iimgexportinfo)<br />|
|[TotalPages](TotalPages.md)|Return the pages to print\. This is a costly operation, so cache the results\.<br />|
|[GetRealPageSize](GetRealPageSize.md)|**Overloaded<br />**  [GetRealPageSize](GetRealPageSize.md#tflexcelimgexportgetrealpagesize)<br />  [GetRealPageSize\(Integer\)](GetRealPageSize.md#tflexcelimgexportgetrealpagesizeinteger)<br />|
|[GetFirstPage&#8203;Export&#8203;Info](GetFirstPageExportInfo.md)|Returns information needed for exporting multiple pages on one sheet\. You normally  don't need to use this method, but you can use it to speed up multiple displays\.<br />|
|[SaveAsImage](SaveAsImage.md)|**Overloaded<br />**  [SaveAsImage\(string, TImageExportType, TImageColorDepth\)](SaveAsImage.md#tflexcelimgexportsaveasimagestring-timageexporttype-timagecolordepth)<br />  [SaveAsImage\(TStream, TImageExportType, TImageColorDepth\)](SaveAsImage.md#tflexcelimgexportsaveasimagetstream-timageexporttype-timagecolordepth)<br />|


## Properties

|Name|Description|
|---|---|
|[Workbook](Workbook.md)|The ExcelFile to print\.<br />|
|[HidePrintObjects](HidePrintObjects.md)|Select which kind of objects should not be printed or exported to the image\.<br />|
|[ExportSheetBackground&#8203;Images](ExportSheetBackgroundImages.md)|If false \(the default\) then the background images in the sheet won't be exported\. Note that Excel doesn't print or export background images, and when it shows them on the screen they look the same no matter the sheet zoom\.<br />When you set this to true we will try to export the image, but it will grow and shrink when you zoom, making it look different from what Excel shows\.<br />|
|[PrintRangeLeft](PrintRangeLeft.md)|First column to print \(1 based\)\. if this or any other PrintRange property is 0, the range will be automatically calculated\.<br />|
|[PrintRangeTop](PrintRangeTop.md)|First row to print \(1 based\)\. if this or any other PrintRange property is 0, the range will be automatically calculated\.<br />|
|[PrintRangeRight](PrintRangeRight.md)|Last column to print \(1 based\)\. if this or any other PrintRange property is 0, the range will be automatically calculated\.<br />|
|[PrintRangeBottom](PrintRangeBottom.md)|Last row to print \(1 based\)\. if this or any other PrintRange property is 0, the range will be automatically calculated\.<br />|
|[PageSize](PageSize.md)|Image page size\. Set it to null to use the paper size on the xls file\.<br />|
|[AllowOverwriting&#8203;Files](AllowOverwritingFiles.md)|Determines if FlexCel will automatically delete existing image files or not\.<br />|
|[Resolution](Resolution.md)|"The default resolution on pixels per inch for the rendered images\. For the screen, this is 96\."|
|[AllVisibleSheets](AllVisibleSheets.md)|If true, All visible sheets on the workbook will be printed\. See [ResetPageNumber&#8203;OnEach&#8203;Sheet](ResetPageNumberOnEachSheet.md) for behavior of the page number when printing multiple sheets\.<br />|
|[ResetPageNumber&#8203;OnEach&#8203;Sheet](ResetPageNumberOnEachSheet.md)|This property only makes sense when [AllVisibleSheets](AllVisibleSheets.md) is true\. On that case, if this property is true each sheet of the workbook will have the page number reset\. For example if the xls file has 2 sheets and each has 3 pages:  When ResetPageNumber&#8203;OnEach&#8203;Sheet = true then footers will look like "Page 1 of 3"\. If false, they will look like "Page 5 of 6"|


## Events

|Name|Description|
|---|---|
|[BeforePaint](BeforePaint.md)|Fires before drawing the image, allowing to modify it or to modify the XlsFile associated\.<br />|
|[AfterPaint](AfterPaint.md)|Fires after the image has been drawn, allowing to modify it\.<br />|


