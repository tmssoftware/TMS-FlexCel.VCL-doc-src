---
uid: TFlexCelPdfExport
description: TFlexCelPdfExport
---

# TFlexCelPdfExport Class

A component for exporting an Excel file to PDF\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">TFlexCelPdfExport = class(TFlexCelObject);</code></pre>

## Fields

|Name|Description|
|---|---|
|[FPdfStream](FPdfStream.md)|Stream where the file will be saved\. You can use this in a derived class to write your own data to the stream\.<br />|
|[FCompress](FCompress.md)|If true, the file will be compressed\. This property is just for derived classes, for normal cases use [Compress](Compress.md)|
|[Properties](Properties.md)|Pdf file properties\. Note that if [UseExcelProperties](UseExcelProperties.md) is true and the values are null or empty, the properties from the exported workbook will be used\.<br />|
|[PdfCanvas](PdfCanvas.md)|Writer where the pdf commands will be sent\. Only for use in derived classes\.<br />|
|[FPrintRange](FPrintRange.md)|Only for use in derived classes\. Use "PrintRangeLeft/&#8203;Top/&#8203;Right/&#8203;Bottom" instead\.<br />|
|[FPageSize](FPageSize.md)|Only for use in derived classes\. Use [PageSize](PageSize.md) instead\.<br />|
|[FFontEmbed](FFontEmbed.md)|Only for use in derived classes\. Use [FontEmbed](FontEmbed.md) instead\.<br />|
|[FFontSubset](FFontSubset.md)|Only for use in derived classes\. Use [FontSubset](FontSubset.md) instead\.<br />|
|[FFontMapping](FFontMapping.md)|Only for use in derived classes\. Use [FontMapping](FontMapping.md) instead\.<br />|
|[FFallbackFonts](FFallbackFonts.md)|Only for use in derived classes\. Use [FallbackFonts](FallbackFonts.md) instead\.<br />|
|[FFallbackFontsBold](FFallbackFontsBold.md)|Only for use in derived classes\. Use [FallbackFontsBold](FallbackFontsBold.md) instead\.<br />|
|[FFallbackFontsItalic](FFallbackFontsItalic.md)|Only for use in derived classes\. Use [FallbackFontsItalic](FallbackFontsItalic.md) instead\.<br />|
|[FFallbackFonts&#8203;Bold&#8203;Italic](FFallbackFontsBoldItalic.md)|Only for use in derived classes\. Use [FallbackFonts&#8203;Bold&#8203;Italic](FallbackFontsBoldItalic.md) instead\.<br />|
|[OnFontFolderNotFound](OnFontFolderNotFound.md)|This property determines how FlexCel behaves when one of the folders you specify in [GetFontFolder](GetFontFolder.md) doesn't exist\.<br />Note that this property applies only to this object\. To change the property for the full application, use [TPdfWriter.&#8203;OnFont&#8203;Folder&#8203;NotFound&#8203;Global](../../FlexCel.Pdf/TPdfWriter/OnFontFolderNotFoundGlobal.md)|


## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create](Create.md#tflexcelpdfexportcreate)<br />  [Create\(TExcelFile\)](Create.md#tflexcelpdfexportcreatetexcelfile)<br />  [Create\(TExcelFile, Boolean\)](Create.md#tflexcelpdfexportcreatetexcelfile-boolean)<br />|


## Methods

|Name|Description|
|---|---|
|[OnBeforeNewPage](OnBeforeNewPage.md)|Replace this event when creating a custom descendant of FlexCelPdfExport\. See also [BeforeNewPage](BeforeNewPage.md)|
|[OnBeforeGeneratePage](OnBeforeGeneratePage.md)|Replace this event when creating a custom descendant of FlexCelPdfExport\. See also [BeforeGeneratePage](BeforeGeneratePage.md)|
|[OnAfterGeneratePage](OnAfterGeneratePage.md)|Replace this event when creating a custom descendant of FlexCelPdfExport\. See also [AfterGeneratePage](AfterGeneratePage.md)|
|[OnGetBookmark&#8203;Information](OnGetBookmarkInformation.md)|Replace this event when creating a custom descendant of FlexCelPdfExport\.<br />|
|[Cancel](Cancel.md)|Cancels a running export\. This method is equivalent to setting [Canceled](Canceled.md) = true\.<br />**Note:** Please note that when you set a thread to Terminated, the exporting will be canceled too\. So normally you don't need this method, just Terminate the thread\.<br />|
|[Export](Export.md)|**Overloaded<br />**  [Export\(TStream\)](Export.md#tflexcelpdfexportexporttstream)<br />  [Export\(string\)](Export.md#tflexcelpdfexportexportstring)<br />|
|[BeginExport](BeginExport.md)|Initializes the PDF exporting to a new file\. After calling this method you can call [ExportSheet](ExportSheet.md) to export different xls files to the same pdf, or [ExportAllVisible&#8203;Sheets\(&#8203;&#8203;Boolean, string\)](ExportAllVisibleSheets.md#tflexcelpdfexportexportallvisiblesheetsboolean-string)\.<br />You should always end the document with a call to [EndExport](EndExport.md)|
|[EndExport](EndExport.md)|Writes the trailer information on a PDF file\. Always call this method after calling [BeginExport](BeginExport.md)|
|[CalcPrintArea](CalcPrintArea.md)|Calculates the actual spreadsheet range that will be printed\. This is given by: 1\)If you specified non zero values on PrintRange, this will be used\.<br />2\)If any value in PrintRange is zero and there is a Print Area defined on the spreadsheet, the Print Area will be used\.<br />3\)If there is no PrintRange and no Print Area defined, the visible cells on the sheet will be printed\.<br />|
|[TotalPagesInSheet](TotalPagesInSheet.md)|Returns the number of pages that the active sheet will use when exported to pdf\.<br />|
|[ExportSheet](ExportSheet.md)|**Overloaded<br />**  [ExportSheet](ExportSheet.md#tflexcelpdfexportexportsheet)<br />  [ExportSheet\(Integer, Integer\)](ExportSheet.md#tflexcelpdfexportexportsheetinteger-integer)<br />  [ExportSheet\(Integer, Integer, Integer, Integer\)](ExportSheet.md#tflexcelpdfexportexportsheetinteger-integer-integer-integer)<br />|
|[ExportAllVisible&#8203;Sheets](ExportAllVisibleSheets.md)|**Overloaded<br />**  [ExportAllVisibleSheets\(Boolean, string\)](ExportAllVisibleSheets.md#tflexcelpdfexportexportallvisiblesheetsboolean-string)<br />  [ExportAllVisibleSheets\(string, Boolean, string\)](ExportAllVisibleSheets.md#tflexcelpdfexportexportallvisiblesheetsstring-boolean-string)<br />|
|[Sign](Sign.md)|Signs the pdf documents with the specified [TPdfSignature](../../FlexCel.Pdf/TPdfSignature/index.md) or [TPdfVisibleSignature](../../FlexCel.Pdf/TPdfVisibleSignature/index.md)\.<br />**Note:** This method must be called **before** calling [BeginExport](BeginExport.md)|
|[AttachFile](AttachFile.md)|**Overloaded<br />**  [AttachFile\(string, string, string, TPdfAttachmentKind\)](AttachFile.md#tflexcelpdfexportattachfilestring-string-string-tpdfattachmentkind)<br />  [AttachFile\(string, string, string, TDateTime, TPdfAttachmentKind, TPdfAttachmentDataProviderDelegate\)](AttachFile.md#tflexcelpdfexportattachfilestring-string-string-tdatetime-tpdfattachmentkind-tpdfattachmentdataproviderdelegate)<br />|
|[ClearAttachments](ClearAttachments.md)|Removes all existing attachments in the writer\.<br />|


## Properties

|Name|Description|
|---|---|
|[Canceled](Canceled.md)|If true the export has been canceled with [Cancel](Cancel.md) method\.<br />You can't set this variable to false, and setting it true is the same as calling [Cancel](Cancel.md)\.<br />**Note:** Please note that when you set a thread to Terminated, the exporting will be canceled too\. So normally you don't need this property, just Terminate the thread\.<br />|
|[Progress](Progress.md)|Progress of the export\. This variable can be accessed from other thread, or from the [AfterGeneratePage](AfterGeneratePage.md) event\.<br />|
|[Workbook](Workbook.md)|The ExcelFile to print\.<br />|
|[TagMode](TagMode.md)|If TagMode is full \(the default\), the generated file will be tagged\. Tagged pdfs provide better accesibility support, but the files can be significantly bigger and take a little longer to create\. If you prefer smaller files even if not accessible, turn this option off\. Note that when creating PDF/A files with [PdfType](PdfType.md)  this property defines if the file is PDF/A\-na or PDF/A\-nb\.<br />This is because PDF/A\-1a and PDF/A\-2a require tagged files, so if this option is true the geneated files will be "a"\.<br />If this option is false, then the generated files will be "b" which is a less strict standard and doesn't require tagging\.<br />To reduce file size, you might want to set[...[more]](TagMode.md)|
|[PdfType](PdfType.md)|Defines the type of pdf being created\. Note that if you set this property to other value than standard, other properties might be ignored\. For example, when creating a PDF/A file all fonts must be embedded so  the value of the FontEmbed property will be ignored\.<br />See the [TagMode](TagMode.md) property to determine if the file will be PDF/A\-na or PDF/A\-nb\. If tagging is true \(the default\) the generated files will be "a"\. If not, they will be "b", since b doesn't require tagging\.<br />|
|[PdfVersion](PdfVersion.md)|Defines the version of pdf being created\. For maximum compatibility you can choose PDF 1\.4\. \(Acrobat 5\.0, but can be opened by any version of Acrobat, even if version less than 1\.4 won't have all the features\)\.<br />Choosing PDF 1\.6 \(Acrobat 7\) allows for more compression and smaller files, but you'll need Acrobat 7 or newer  to see the files\. Older versions won't be able to open it at all\.<br /><br /><br />Note that this value might be ignored if you are creating PDFA\-1 \(as it requires PDF1\-4\)\. Also for signing, FlexCel requires PDF 1\.7\.<br />|
|[UnlicensedFontAction](UnlicensedFontAction.md)|Defines what to do when a font has a license that doesn't allow embedding, and you are trying to embed the font\.<br />|
|[UnlicensedReplacement&#8203;Font](UnlicensedReplacementFont.md)|When trying to embed a font that isn't licensed for embedding, and [UnlicensedFontAction](UnlicensedFontAction.md) is TUnlicensedFont&#8203;Action\.&#8203;Replace this property specifies the font that will be used to replace it\. If null or empty, Arial will be used\.<br />|
|[HidePrintObjects](HidePrintObjects.md)|Select which kind of objects should not be printed or exported to pdf\.<br />|
|[ExportSheetBackground&#8203;Images](ExportSheetBackgroundImages.md)|If false \(the default\) then the background images in the sheet won't be exported\. Note that Excel doesn't print or export background images, and when it shows them on the screen they look the same no matter the sheet zoom\.<br />When you set this to true we will try to export the image, but it will grow and shrink when you zoom, making it look different from what Excel shows\.<br />|
|[Compress](Compress.md)|When true, the pdf file will be compressed\.<br />|
|[Kerning](Kerning.md)|By default, pdf does not do any kerning with the fonts\. This is, on the string "AVANT", it won't compensate the spaces between "A" and "V"\. \(they should be smaller\)  If you turn this property on, FlexCel will calculate the kerning and add it to the generated file\.<br />The result file will be a little bigger because of the kerning info on all strings, but it will also look a little better\.<br />|
|[UseFauxStyles](UseFauxStyles.md)|When a font doesn't have a bold, italic or bold\-italic variant, FlexCel can't export bold, italic or bold\-italic characters to the pdf respectively\. When this property is true \(the default\), FlexCel will try to "fake" those missing styles by using a wider pen width for the characters to simulate bold, or doing a slant transform to simulate italics\.<br /><br /><br />The results of a simulated bold or italic can be not great, so if you prefer that FlexCel doesn't try to simulate bold or italics, then you can set this property to false\. If this property is false and the font you are using doesn't have bold or italics variants, then the pdf won't show bold or italics for that font\.<br />[...[more]](UseFauxStyles.md)|
|[UseExcelProperties](UseExcelProperties.md)|When this property is true, the properties of the Excel file will be used when the property is null or empty\.<br />|
|[PrintRangeLeft](PrintRangeLeft.md)|First column to print \(1 based\)\. if this or any other PrintRange property is 0, the range will be automatically calculated\.<br />|
|[PrintRangeTop](PrintRangeTop.md)|First row to print \(1 based\)\. if this or any other PrintRange property is 0, the range will be automatically calculated\.<br />|
|[PrintRangeRight](PrintRangeRight.md)|Last column to print \(1 based\)\. if this or any other PrintRange property is 0, the range will be automatically calculated\.<br />|
|[PrintRangeBottom](PrintRangeBottom.md)|Last row to print \(1 based\)\. if this or any other PrintRange property is 0, the range will be automatically calculated\.<br />|
|[PageSize](PageSize.md)|Pdf page size\. Set it to null to use the paper size on the xls file\.<br />|
|[UseLocalFontList](UseLocalFontList.md)|**This is a setting mostly for testing, do not change unless you have a good reason,**<br />By default, FlexCel uses a global font list for exporting to PDF, because populating the font list is slow, and keeping it in a cache makes everything faster\. But when testing, we sometimes need to validate specific behaviors in a test, and a shared global font list can make it difficult\.<br />Setting this property to true will make FlexCel use a local font list for this instance of PdfWriter, so it won't interfere with other tests that might be running at the same time\.<br />It will also make the exporting slower\.<br />|
|[AllowOverwriting&#8203;Files](AllowOverwritingFiles.md)|Determines if FlexCel will automatically delete existing pdf files or not\.<br />|
|[FontEmbed](FontEmbed.md)|Determines what fonts will be embedded on the generated pdf\. Note that when using UNICODE, fonts will be embedded anyway, no matter what this setting is\.<br />|
|[FontSubset](FontSubset.md)|Determines if the full font will be embedded or only the characters used, when embedding fonts\.<br />|
|[FontMapping](FontMapping.md)|Determines how fonts will be replaced on the generated pdf\. Pdf comes with 4 standard font families, Serif, Sans\-Serif, Monospace and Symbol\. You can use for example the standard Helvetica instead of Arial and do not worry about embedding the font\.<br />|
|[FallbackFonts](FallbackFonts.md)|A semicolon \(;\) separated list of font names to try when a character is not found in the used font\.<br /><br />When a character is not found in a font, it will display as an empty square by default\. By setting this property, FlexCel will try to find a font that supports this character in this list, and if found, use that font to render the character\.<br />|
|[FallbackFontsBold](FallbackFontsBold.md)|A semicolon \(;\) separated list of font names to try when a character is not found in the used font and the font is bold\.<br /><br />This property is only used for **bold** fonts, and has higher priority than [FallbackFonts](FallbackFonts.md) for bold fonts\.<br />It allows you to specify different fallback fonts for bold and not bold characters\.<br /><br />**Important:** This property is only needed if the fonts in [FallbackFonts](FallbackFonts.md) don't have bold variants\.<br />If your fallback fonts come with bold variants, there is not need to set this property\.<br />|
|[FallbackFontsItalic](FallbackFontsItalic.md)|A semicolon \(;\) separated list of font names to try when a character is not found in the used font and the font is italic\.<br /><br />This property is only used for *italic* fonts, and has higher priority than [FallbackFonts](FallbackFonts.md) for italic fonts\.<br />It allows you to specify different fallback fonts for italic and not italic characters\.<br /><br />**Important:** This property is only needed if the fonts in [FallbackFonts](FallbackFonts.md) don't have italic variants\.<br />If your fallback fonts come with italic variants, there is not need to set this property\.<br />|
|[FallbackFonts&#8203;Bold&#8203;Italic](FallbackFontsBoldItalic.md)|A semicolon \(;\) separated list of font names to try when a character is not found in the used font and the font is bold and italic\.<br /><br />This property is only used for fonts which are both **bold and***italic*, and has higher priority  than [FallbackFonts](FallbackFonts.md), [FallbackFontsBold](FallbackFontsBold.md) and [FallbackFontsItalic](FallbackFontsItalic.md) for bold\-italic fonts\.<br />It allows you to specify different fallback fonts for bold\-italic and not bold\-italic characters\.<br /><br />**Important:**[...[more]](FallbackFontsBoldItalic.md)|
|[PageLayout](PageLayout.md)|Sets the default page layout when opening the document\.<br />|
|[PageLayoutDisplay](PageLayoutDisplay.md)|Sets the default page display layout when opening the document\.<br />|
|[InitialZoomAndPage](InitialZoomAndPage.md)|Sets the default zoom and initial page when opening the document\.<br />|
|[CurrentPage](CurrentPage.md)|Returns the next page that we are going to print\.<br />|
|[CurrentPageInSheet](CurrentPageInSheet.md)|Returns the next page we are going to print, on the current sheet\.<br />When not printing more than one sheet, it is equivalent to [CurrentPage](CurrentPage.md)|


## Events

|Name|Description|
|---|---|
|[BeforeNewPage](BeforeNewPage.md)|Fires before each new page is generated on the pdf\.<br />You can use this event to change the pagesize for the new sheet\.<br />|
|[BeforeGeneratePage](BeforeGeneratePage.md)|Fires after each new page is generated on the pdf, but before any content is written to the page\. \(The page is blank\) You can use this event to add a watermark or a background image\.<br />|
|[AfterGeneratePage](AfterGeneratePage.md)|Fires after each new page is generated on the pdf, and after all content is written to the page\. \(The page is written\) You can use this event to add some text or images on top of the page contents\.<br />|
|[GetFontData](GetFontData.md)|Use this event if you want to provide your own font information for embedding\.<br />Note that if you don't assign this event, the default method will be used, and this  will try to find the font on the Fonts folder\. To change the font folder, use [GetFontFolder](GetFontFolder.md) event<br /><br />Note that this property applies only to this object\. To change the property for the full application, use [TPdfWriter.&#8203;Get&#8203;Font&#8203;Data&#8203;Global](../../FlexCel.Pdf/TPdfWriter/GetFontDataGlobal.md)|
|[GetFontFolder](GetFontFolder.md)|Use this event if you want to provide your own font information for embedding\.<br />Normally FlexCel will search for fonts on \[System\]\\Fonts folder and %%&#8203;localappdata%&#8203;%\\Microsoft\\Windows\\Fonts\. If your fonts are in  other location, you can tell FlexCel where they are here\. If you prefer just to give FlexCel the full data on the font, you can use [GetFontData](GetFontData.md) event instead\.<br /><br /><br /><br />Note that this property applies only to this object\. To change the property for the full application, use[...[more]](GetFontFolder.md)|
|[OnFontEmbed](OnFontEmbed.md)|Use this event if you want to manually specify which fonts to embed into the pdf document\.<br /><br /><br /><br />Note that this property applies only to this object\. To change the property for the full application, use [TPdfWriter.&#8203;OnFont&#8203;Embed&#8203;Global](../../FlexCel.Pdf/TPdfWriter/OnFontEmbedGlobal.md)|
|[GetBookmarkInformation](GetBookmarkInformation.md)|Use this event to customize what goes inside the bookmarks when exporting multiple sheets of an xls file\.<br />|


