---
uid: TFlexCelPrintDocument
description: TFlexCelPrintDocument
---

# TFlexCelPrintDocument Class

Use this class to print an Excel file natively\.


## Remarks

This class uses the settings from the standard "Printer" object in Delphi, so to change most settings, you should change the settings for Printer\. You can also use a standard Delphi PrintDialog to allow the user to choose printer and parameters\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">TFlexCelPrintDocument = class(TFlexCelObject);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create](Create.md#tflexcelprintdocumentcreate)<br />  [Create\(TExcelFile\)](Create.md#tflexcelprintdocumentcreatetexcelfile)<br />|


## Methods

|Name|Description|
|---|---|
|[OnBeforeNewPage](OnBeforeNewPage.md)|Replace this event when creating a custom descendant of FlexCelPrint&#8203;Document\. See also [BeforeNewPage](BeforeNewPage.md)|
|[OnBeforeGeneratePage](OnBeforeGeneratePage.md)|Replace this event when creating a custom descendant of FlexCelPrint&#8203;Document\. See also [BeforeGeneratePage](BeforeGeneratePage.md)|
|[OnAfterGeneratePage](OnAfterGeneratePage.md)|Replace this event when creating a custom descendant of FlexCelPrint&#8203;Document\. See also [AfterGeneratePage](AfterGeneratePage.md)|
|[Cancel](Cancel.md)|Cancels a printing process\. This method is equivalent to setting [Canceled](Canceled.md) = true\.<br />**Note:** Please note that when you set a thread to Terminated, the printing will be canceled too\. So normally you don't need this method, just Terminate the thread\.<br />|
|[Print](Print.md)|Prints the active sheet of the associated xls workbook\.<br />|
|[BeginPrint](BeginPrint.md)|Initializes the printing engine\. After calling this method you can call [PrintSheet](PrintSheet.md) to print different xls files, or [PrintAllVisible&#8203;Sheets](PrintAllVisibleSheets.md)\. You should always end printing with a call to [EndPrint](EndPrint.md)|
|[EndPrint](EndPrint.md)|Finishes the printing process\. You should always call this method\.<br />|
|[CalcPrintArea](CalcPrintArea.md)|Calculates the actual spreadsheet range that will be printed\. This is given by: 1\)If you specified non zero values on PrintRange, this will be used\.<br />2\)If any value in PrintRange is zero and there is a Print Area defined on the spreadsheet, the Print Area will be used\.<br />3\)If there is no PrintRange and no Print Area defined, the visible cells on the sheet will be printed\.<br />|
|[TotalPagesInSheet](TotalPagesInSheet.md)|Returns the number of pages that the active sheet will use when printed\.<br />|
|[PrintSheet](PrintSheet.md)|**Overloaded<br />**  [PrintSheet](PrintSheet.md#tflexcelprintdocumentprintsheet)<br />  [PrintSheet\(Integer, Integer, Integer, Integer\)](PrintSheet.md#tflexcelprintdocumentprintsheetinteger-integer-integer-integer)<br />|
|[PrintAllVisible&#8203;Sheets](PrintAllVisibleSheets.md)|This method will print all the visible sheets on an xls file\.<br />Different than calling PrintSheet for each sheet, this method can keep the page number growing on each sheet, without resetting it\.<br />|


## Properties

|Name|Description|
|---|---|
|[Canceled](Canceled.md)|If true the printing has been canceled with [Cancel](Cancel.md) method\.<br />You can't set this variable to false, and setting it true is the same as calling [Cancel](Cancel.md)\.<br />**Note:** Please note that when you set a thread to Terminated, the printing will be canceled too\. So normally you don't need this property, just Terminate the thread\.<br />|
|[Progress](Progress.md)|Progress of the printing\. This variable can be accessed from other thread, or from the [AfterGeneratePage](AfterGeneratePage.md) event\.<br />|
|[Workbook](Workbook.md)|The ExcelFile to print\.<br />|
|[HidePrintObjects](HidePrintObjects.md)|Select which kind of objects should not be printed\.<br />|
|[ExportSheetBackground&#8203;Images](ExportSheetBackgroundImages.md)|If false \(the default\) then the background images in the sheet won't be exported\. Note that Excel doesn't print or export background images, and when it shows them on the screen they look the same no matter the sheet zoom\.<br />When you set this to true we will try to export the image, but it will grow and shrink when you zoom, making it look different from what Excel shows\.<br />|
|[PrintRangeLeft](PrintRangeLeft.md)|First column to print \(1 based\)\. if this or any other PrintRange property is 0, the range will be automatically calculated\.<br />|
|[PrintRangeTop](PrintRangeTop.md)|First row to print \(1 based\)\. if this or any other PrintRange property is 0, the range will be automatically calculated\.<br />|
|[PrintRangeRight](PrintRangeRight.md)|Last column to print \(1 based\)\. if this or any other PrintRange property is 0, the range will be automatically calculated\.<br />|
|[PrintRangeBottom](PrintRangeBottom.md)|Last row to print \(1 based\)\. if this or any other PrintRange property is 0, the range will be automatically calculated\.<br />|
|[PageSize](PageSize.md)|Page size\. Set it to null to use the paper size on the xls file\.<br />|
|[CurrentPage](CurrentPage.md)|Returns the next page that we are going to print\.<br />|
|[CurrentPageInSheet](CurrentPageInSheet.md)|Returns the next page we are going to print, on the current sheet\.<br />When not printing more than one sheet, it is equivalent to [CurrentPage](CurrentPage.md)|
|[PrintAsBitmap](PrintAsBitmap.md)|If true, the file will be rendered to a bitmap and then we will print the bitmap, instead of directly printing the file\.<br />**Use with caution\.** See remarks|
|[BitmapDPI](BitmapDPI.md)|When using a bitmap to print \([PrintAsBitmap](PrintAsBitmap.md) is true\), this property specifies the resolution for the temporary bitmap that will be sent to the printer\. The higher the resolution the better quality of the print, but also the more memory, network time and processing time it will take\.<br />**Important:** A value of 0 means creating bitmaps with the native printer resolution\. This will give the best quality, but the bitmap can be big\. A negative value means no bitmap used, and it is the same as setting[...[more]](BitmapDPI.md)|


## Events

|Name|Description|
|---|---|
|[BeforeNewPage](BeforeNewPage.md)|Fires before each new page is printed\.<br />You can use this event to change the pagesize for the new sheet\.<br />|
|[BeforeGeneratePage](BeforeGeneratePage.md)|Fires after each new page is printed, but before any content is written to the page\. \(The page is blank\) You can use this event to add a watermark or a background image\.<br />|
|[AfterGeneratePage](AfterGeneratePage.md)|Fires after each new page is printed, and after all content is written to the page\. \(The page is written\) You can use this event to add some text or images on top of the page contents\.<br />|


