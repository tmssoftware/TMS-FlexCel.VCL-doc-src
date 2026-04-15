---
uid: FlexCel.Render
description: FlexCel.Render
---

# FlexCel.Render Namespace

This is the rendering engine\. It can render an xls or xlsx file into an image, pdf or html files\.


## Classes

|Name|Description|
|---|---|
|[TFlexCelHtmlExport](TFlexCelHtmlExport/index.md)|A component for exporting an Excel file to HTML\.<br />|
|[TFlexCelHtml&#8203;Export&#8203;Progress](TFlexCelHtmlExportProgress/index.md)|Indicates how much of the report has been generated\.<br />|
|[TFlexCelImgExport](TFlexCelImgExport/index.md)|A component for exporting an Excel file to an image\. It can return an image object, or the actual bytes of a specific file format\. \(like gif, tiff or png\)|
|[TFlexCelPdfExport](TFlexCelPdfExport/index.md)|A component for exporting an Excel file to PDF\.<br />|
|[TFlexCelPdfExport&#8203;Progress](TFlexCelPdfExportProgress/index.md)|Indicates how much of the report has been generated\.<br />|
|[TFlexCelPrint&#8203;Document](TFlexCelPrintDocument/index.md)|Use this class to print an Excel file natively\.<br />|
|[TFlexCelPrinting&#8203;Progress](TFlexCelPrintingProgress/index.md)|Indicates how much of the report has been generated\.<br />|
|[TFlexCelSVGExport](TFlexCelSVGExport/index.md)|A component for exporting an Excel file to an SVG \(Scalable Vector Graphics\) image\.<br />|
|[TGeneratedFiles](TGeneratedFiles/index.md)|An object containing all the files generated in the export\.<br />|
|[TGetBookmark&#8203;Information&#8203;Args](TGetBookmarkInformationArgs/index.md)|Arguments passed on [TFlexCelPdfExport.&#8203;Get&#8203;Bookmark&#8203;Information](TFlexCelPdfExport/GetBookmarkInformation.md),|
|[THtmlExtraInfo](THtmlExtraInfo/index.md)|Stores extra data to write in the HTML file\.<br />|
|[THtmlHotTrack](THtmlHotTrack/index.md)|Defines how and if the cells will be highlighted when the mouse is over them\.<br />|
|[THtmlSpreadView](THtmlSpreadView/index.md)|The properties in this class make the generated file look more like when you view a Spreadsheet in Excel, and less like a printed page\. By default, FlexCel tries to mimic the printed\-page output, not the interactive view\.<br />|
|[TImageInformation&#8203;Event&#8203;Args](TImageInformationEventArgs/index.md)|Arguments passed on [TFlexCelHtml&#8203;Export.&#8203;OnGet&#8203;Image&#8203;Information](TFlexCelHtmlExport/OnGetImageInformation.md),|
|[TImgPaintEventArgs](TImgPaintEventArgs/index.md)|Arguments passed on Paint events\.<br />|
|[TNamedRangeExport&#8203;Event&#8203;Args](TNamedRangeExportEventArgs/index.md)|Arguments passed on [TFlexCelHtml&#8203;Export.&#8203;OnNamed&#8203;Range&#8203;Export](TFlexCelHtmlExport/OnNamedRangeExport.md),|
|[TPageEventArgs](TPageEventArgs/index.md)|Arguments passed on [TFlexCelPdfExport.&#8203;Before&#8203;Generate&#8203;Page](TFlexCelPdfExport/BeforeGeneratePage.md), [TFlexCelPdfExport.&#8203;Before&#8203;NewPage](TFlexCelPdfExport/BeforeNewPage.md) and [TFlexCelPdfExport.&#8203;After&#8203;Generate&#8203;Page](TFlexCelPdfExport/AfterGeneratePage.md)|
|[TPartialExportState](TPartialExportState/index.md)|This class is used to save the necessary information to partially export a file\.<br />|
|[TPrintPageEventArgs](TPrintPageEventArgs/index.md)|Arguments passed on [TFlexCelPrint&#8203;Document.&#8203;Before&#8203;Generate&#8203;Page](TFlexCelPrintDocument/BeforeGeneratePage.md), [TFlexCelPrint&#8203;Document.&#8203;Before&#8203;NewPage](TFlexCelPrintDocument/BeforeNewPage.md) and [TFlexCelPrint&#8203;Document.&#8203;After&#8203;Generate&#8203;Page](TFlexCelPrintDocument/AfterGeneratePage.md)|
|[TSaveImageEventArgs](TSaveImageEventArgs/index.md)|Arguments passed on [TFlexCelHtml&#8203;Export.&#8203;OnSave&#8203;Image](TFlexCelHtmlExport/OnSaveImage.md),|
|[TSheetSelector](TSheetSelector/index.md)|Abstract class to implement a Sheet Selector\. Derive from this class for example to implement tabs with images\. For a standard implementation using CSS Tabs and divs, use [TStandardSheet&#8203;Selector](TStandardSheetSelector/index.md)|
|[TSheetSelector&#8203;Entry&#8203;Event&#8203;Args](TSheetSelectorEntryEventArgs/index.md)|Arguments passed on FlexCel\.&#8203;Render\.&#8203;TStandard&#8203;Sheet&#8203;Selector\.&#8203;OnSheet&#8203;Selector&#8203;Entry\.<br />|
|[TSheetSelectorLink](TSheetSelectorLink/index.md)|Holds the sheet name in Excel and in the file\.<br />|
|[TStandardSheet&#8203;Selector](TStandardSheetSelector/index.md)|Implements a standard sheet selector \(with CSS tabs\) that will allow you to change the page when exporting multiple sheets\.<br />You can customize its default behavior by altering the CSS properties, or by inheriting from it and replacing the virtual methods\.<br />If you want to create a completely new type of sheet selector, derive it from [TSheetSelector](TSheetSelector/index.md) instead of this class\.<br />|
|[TStandardSheet&#8203;Selector&#8203;Styles](TStandardSheetSelectorStyles/index.md)|Holds the styles for one of the positions of a [TStandardSheet&#8203;Selector](TStandardSheetSelector/index.md)\.<br />|
|[TSVGExportParameters](TSVGExportParameters/index.md)|Parameters used when exporting to SVG\.<br />|


## Records

|Name|Description|
|---|---|
|[TLightImgExportInfo](TLightImgExportInfo/index.md)|A class with only the specific data needed, so it can be stored in a cache\.<br />|


## Interfaces

|Name|Description|
|---|---|
|[ICssInformation](ICssInformation/index.md)|Encapsulates the information needed to create external CSS files\.<br />Note that if you use the same TCssInformation instance to create different html files, the CSS file created will be only one\.<br />|
|[IImgExportInfo](IImgExportInfo/index.md)|Holds information needed to export the pages, so it is only calculated once\.<br />|
|[IOneImgExportInfo](IOneImgExportInfo/index.md)|Holds information needed to export one of the workbook sheets, so it is only calculated once\.<br />|


## Enumerations

|Name|Description|
|---|---|
|[THtmlImageFormat](THtmlImageFormat.md)|Possible values in which we can save an image when exporting to HTML\.<br />|
|[TSheetSelector&#8203;Position](TSheetSelectorPosition.md)|Where to place the tabs for selecting a sheet when exporting multiple sheets\.<br />You might combine more than one, for example, to have tabs at the top and bottom: C\#: TSheetSelector&#8203;Position\.&#8203;Top \| TSheetSelector&#8203;Position\.&#8203;Bottom VB\.NET, Delphi\.NET: TSheetSelector&#8203;Position\.&#8203;Top or TSheetSelector&#8203;Position\.&#8203;Bottom|


## Types

|Name|Description|
|---|---|
|[TGetBookmark&#8203;Information&#8203;Event&#8203;Handler](TGetBookmarkInformationEventHandler.md)|This event will happen each time a PDF bookmark is automatically added by FlexCel\. You can use it to customize the bookmark, for example change the font color or style\.<br />|
|[TImageInformation&#8203;Event&#8203;Handler](TImageInformationEventHandler.md)|Delegate used to specify where to store the images on a page\.<br />|
|[TNamedRangeExport&#8203;Event&#8203;Handler](TNamedRangeExportEventHandler.md)|Delegate used to customize exporting of named ranges on a page\.<br />|
|[TPageEventHandler](TPageEventHandler.md)|Generic delegate for After/Before page events\.<br />|
|[TPaintEventHandler](TPaintEventHandler.md)|Delegate for Paint events\.<br />|
|[TSaveImageEvent&#8203;Handler](TSaveImageEventHandler.md)|Delegate used to specify where to store the images on a page\.<br />|
|[TSheetSelector&#8203;Entry&#8203;Event&#8203;Handler](TSheetSelectorEntryEventHandler.md)|Delegate used to specify how the Sheet Selector will be like\.<br />|


