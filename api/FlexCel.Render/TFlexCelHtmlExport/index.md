---
uid: TFlexCelHtmlExport
description: TFlexCelHtmlExport
---

# TFlexCelHtmlExport Class

A component for exporting an Excel file to HTML\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">TFlexCelHtmlExport = class(TCoreFlexCelHtmlExport, <a href="../../FlexCel.Core/IHtmlFontEvent/index.md">IHtmlFontEvent</a>);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create](Create.md#tflexcelhtmlexportcreate)<br />  [Create\(TExcelFile\)](Create.md#tflexcelhtmlexportcreatetexcelfile)<br />  [Create\(TExcelFile, Boolean\)](Create.md#tflexcelhtmlexportcreatetexcelfile-boolean)<br />|


## Methods

|Name|Description|
|---|---|
|[OnGetImageInformation](OnGetImageInformation.md)|Replace this event when creating a custom descendant of FlexCelHtmlExport\.<br />|
|[OnSaveImage](OnSaveImage.md)|Replace this event when creating a custom descendant of FlexCelHtmlExport\.<br />|
|[OnHtmlFont](OnHtmlFont.md)|Replace this event when creating a custom descendant of FlexCelHtmlExport\.<br />|
|[OnNamedRangeExport](OnNamedRangeExport.md)|Replace this event when creating a custom descendant of FlexCelHtmlExport\.<br />|
|[Cancel](Cancel.md)|Cancels a running export\. This method is equivalent to setting [Canceled](Canceled.md) = true\.<br />**Note:** Please note that when you set a thread to Terminated, the exporting will be canceled too\. So normally you don't need this method, just Terminate the thread\.<br />|
|[Export](Export.md)|**Overloaded<br />**  [Export\(string, string\)](Export.md#tflexcelhtmlexportexportstring-string)<br />  [Export\(TFlexCelWriter, string, ICssInformation\)](Export.md#tflexcelhtmlexportexporttflexcelwriter-string-icssinformation)<br />  [Export\(string, string, ICssInformation\)](Export.md#tflexcelhtmlexportexportstring-string-icssinformation)<br />  [Export\(string, string, string\)](Export.md#tflexcelhtmlexportexportstring-string-string)<br />|
|[ExportToClipboard&#8203;Format](ExportToClipboardFormat.md)|Exports the file in the format expacted by the CT\_HTML clipboard format: https:&#8203;//&#8203;msdn\.&#8203;microsoft\.&#8203;com/&#8203;en\-&#8203;us/&#8203;library/&#8203;windows/&#8203;desktop/&#8203;ms649015\(&#8203;v=&#8203;vs\.&#8203;85\)&#8203;\.&#8203;aspx|
|[ExportAllVisible&#8203;Sheets&#8203;AsTabs](ExportAllVisibleSheetsAsTabs.md)|This method will export all the visible sheets on an xls file to an html file, writing each sheet in a different file\.<br />This is equivalent to calling Export on every sheet\.<br />|
|[ExportAllVisible&#8203;Sheets&#8203;AsOne&#8203;Html&#8203;File](ExportAllVisibleSheetsAsOneHtmlFile.md)|**Overloaded<br />**  [ExportAllVisibleSheetsAsOneHtmlFile\(string, string, string, string\)](ExportAllVisibleSheetsAsOneHtmlFile.md#tflexcelhtmlexportexportallvisiblesheetsasonehtmlfilestring-string-string-string)<br />  [ExportAllVisibleSheetsAsOneHtmlFile\(TFlexCelWriter, string, string, string, string\)](ExportAllVisibleSheetsAsOneHtmlFile.md#tflexcelhtmlexportexportallvisiblesheetsasonehtmlfiletflexcelwriter-string-string-string-string)<br />|
|[ReplaceSeparator&#8203;Macros](ReplaceSeparatorMacros.md)|This method is for internal use\. It will replace the sheet name, pos and count macros in a sheet separator\.<br />|
|[PartialExportAdd](PartialExportAdd.md)|**Overloaded<br />**  [PartialExportAdd\(TPartialExportState, string, string\)](PartialExportAdd.md#tflexcelhtmlexportpartialexportaddtpartialexportstate-string-string)<br />  [PartialExportAdd\(TPartialExportState, string, string, Boolean\)](PartialExportAdd.md#tflexcelhtmlexportpartialexportaddtpartialexportstate-string-string-boolean)<br />|
|[DoHtmlFont](DoHtmlFont.md)|This method is for internal use\.<br />|


## Properties

|Name|Description|
|---|---|
|[Canceled](Canceled.md)|If true the export has been canceled with [Cancel](Cancel.md) method\.<br />You can't set this variable to false, and setting it true is the same as calling [Cancel](Cancel.md)\.<br />**Note:** Please note that when you set a thread to Terminated, the exporting will be canceled too\. So normally you don't need this method, just Terminate the thread\.<br />|
|[Progress](Progress.md)|Progress of the export\. This variable can be accessed from other thread or from the OnProgress event\.<br />|
|[Workbook](Workbook.md)|The ExcelFile to export\.<br />|
|[HidePrintObjects](HidePrintObjects.md)|Select which kind of objects should not be exported to html\. By default we do \*not\* export headers and footers, since they are normally not what you want when exporting to HTML\.<br />|
|[HtmlVersion](HtmlVersion.md)|Version of the HTML generated\.<br />|
|[HtmlFileFormat](HtmlFileFormat.md)|Format of the HTML file to be generated\.<br />|
|[ClassPrefix](ClassPrefix.md)|Prefix to be appended to all CSS classes\. For example, if you set it to "test", CSS classes will be named like "\.test1234"\. Normally you do not need to change this property, but if you need to insert multiple Excel files in the same HTML page, you need to ensure all classes have a unique ClassPrefix\.<br />|
|[FixIE6Transparent&#8203;PngSupport](FixIE6TransparentPngSupport.md)|By default, Internet explorer does not support transparent PNGs\. Normally this is not an issue, since Excel uses  little transparency\. But if you rely on transparent images and don't want to use gif images instead of png, you can set this property to true\. It will add special code to the HTML file to support transparent images in IE6\.<br />**Note:** If setting this property to false, you might want to set [ImageBackground](ImageBackground.md) to Colors\.White instead of TUIColor\.Empty to ensure images have no transparent background\.<br />|
|[FixOutlook2007Css&#8203;Support](FixOutlook2007CssSupport.md)|Outlook 2007 renders HTML worse than previous versions, since it switched to the Word 2007 rendering engine instead of Internet Explorer to show HTML emails\. If you apply this fix, some code will be added to the generated HTML file to improve the display in Outlook 2007\. Other browsers will not be affected and will still render the original file\. Turn this option on if you plan to email the generated file as an HTML email or to edit them in Word 2007\. Note that the pages will not validate with the w3c validator if this option is on\.<br />|
|[FixIE6WordWrap&#8203;Support](FixIE6WordWrapSupport.md)|Some older browsers \(and Word 2007\) might not support the CSS white\-space tag\. In this case, if a line longer than a cell cannot be expanded to the right \(because there is data in the next cell\) it will wrap down instead of being cropped\. This fix will cut the text on this cell to the displayable characters\. If a letter was displayed by the half on the right, after applying this fix it will not display\.<br />This fix is automatically applied when [FixOutlook2007Css&#8203;Support](FixOutlook2007CssSupport.md)[...[more]](FixIE6WordWrapSupport.md)|
|[UseContentId](UseContentId.md)|When exporting to **MHTML**, some mail clients might have problems understanding the newer "Content\-Location" header to show the images\.<br />When this property is true, we will use the older "Content\-Id" header that is better supported than Content Location in the mime headers to reference the images\. You are strongly encouraged to keep this property true in order to maximize the number of mail readers compatible\. When Exporting to HTML \(not MHTML\), this property has no effect\.<br />|
|[HeadingWidth](HeadingWidth.md)|Width in points of the left gutter when printing row numbers and column names\.<br />|
|[HeadingStyle](HeadingStyle.md)|Style definition for the gutter cells when printing row numbers or column names\. This text must be  a valid CSS style definition, without including the braces \("\{\}"\)\.<br />|
|[PrintRangeLeft](PrintRangeLeft.md)|First column to print \(1 based\)\. if this or any other PrintRange property is 0, the range will be automatically calculated\.<br />|
|[PrintRangeTop](PrintRangeTop.md)|First row to print \(1 based\)\. if this or any other PrintRange property is 0, the range will be automatically calculated\.<br />|
|[PrintRangeRight](PrintRangeRight.md)|Last column to print \(1 based\)\. if this or any other PrintRange property is 0, the range will be automatically calculated\.<br />|
|[PrintRangeBottom](PrintRangeBottom.md)|Last row to print \(1 based\)\. if this or any other PrintRange property is 0, the range will be automatically calculated\.<br />|
|[AllowOverwriting&#8203;Files](AllowOverwritingFiles.md)|Determines if FlexCel will automatically delete existing HTML and image files or not\.<br />|
|[IgnoreSharing&#8203;Violations](IgnoreSharingViolations.md)|When this property is true and the component tries to write any file that is locked by other thread, it will not raise an error and just assume the other thread will write the correct image\. You will normally want to have this true, so you can have many threads writing to the same file without issues\. Note that when [AllowOverwriting&#8203;Files](AllowOverwritingFiles.md) is false, this property has no effect\.<br />|
|[VerticalTextAsImages](VerticalTextAsImages.md)|When true and text is vertical, FlexCel will replace the text with an image in order to show it correctly in HTML\.<br />When false, text will be rendered normally without rotation\.<br />Note that when using HTML5 this property is ignored, since HTML5 allows text rotation\.<br />|
|[ExportNamedRanges](ExportNamedRanges.md)|When true FlexCel will insert a span in the first cell of every named range with "id" = the name of the range\.<br />You can access then this with javascript\.<br />For a fine grain control of how names are exported, you can use [NamedRangeExport](NamedRangeExport.md) event\.<br />|
|[LinksInNewWindow](LinksInNewWindow.md)|If true, the links will be exported with a target=\_blank attribute so they open in a new window\.<br />|
|[BackgroundColor](BackgroundColor.md)|Background color for empty cells\. This is White by default, but you migth want to make it TUIColor\.Empty if you want the cells to not cover the background\.<br />|
|[BaseUrl](BaseUrl.md)|If this property is not null, all hyperlinks stating with this value will be converted to relative links, by removing this string from them\.<br /><br />Hyperlinks in Excel must be absolute by default, so this property is a way to get relative hyperlinks\.<br /><br />For example, if BaseUrl is "https:&#8203;//&#8203;www\.&#8203;tmssoftware\.&#8203;com/&#8203;" and an Excel file has a link "https:&#8203;//&#8203;www\.&#8203;tmssoftware\.&#8203;com/&#8203;test\.&#8203;html" the link in the generated HTML file will be "test\.html"|
|[UsePrintScale](UsePrintScale.md)|If false \(the default\) the print scale of the sheet will be ignored when exporting to html\. If true, sheets will be exported honoring the zoom of the page\.Note that if PrintToFit is true, then this value  will be ignored and zoom will be 100%%\.<br />|
|[ImageResolution](ImageResolution.md)|Resolution for the exported images\. The bigger the resolution, the bigger the image size and quality\. Use 96 for standard screen resolution\.<br />|
|[SavedImagesFormat](SavedImagesFormat.md)|File format in which the images will be saved\. Note that Ie6 does not support transparency in PNGs by default, so if you have transparent images and you want to make you page compatible with IE6, you should save as gif or use [FixIE6Transparent&#8203;PngSupport](FixIE6TransparentPngSupport.md)|
|[SmoothingMode](SmoothingMode.md)|This affects how the images, charts, etc are rendered for the image file\. Some modes will look a little blurred but with better quality\.<br />Consult the \.NET framework documentation on SmoothingMode for more information|
|[InterpolationMode](InterpolationMode.md)|This affects how the images, charts, etc are rendered for the image file\. Some modes will look a little blurred but with better quality\.<br />Consult the \.NET framework documentation on SmoothingMode for more information|
|[AntiAliased](AntiAliased.md)|This affects how the text is rendered for example when exporting a chart\. Some modes will look a little blurred but with better quality\.<br />Consult the \.NET framework documentation on SmoothingMode for more information|
|[ImageBackground](ImageBackground.md)|When this property is set to TUIColor\.Empty \(the default\), images will be rendered with a transparent background\.<br />While this is the normal behavior, sometimes you might not want transparent images \(for example to support Internet Explorer 6 without setting [FixIE6Transparent&#8203;PngSupport](FixIE6TransparentPngSupport.md) to true\), and then you could use Colors\.White here\.<br />|
|[RasterizeSVGImages](RasterizeSVGImages.md)|If false \(the default\) then FlexCel will export SVG images inside the Excel file as SVG images inside the generated HTML\.<br />If true, FlexCel will convert the SVG images to PNG and embed the PNG inside the HTML\. This might be more accurate specially if the embedded SVG uses fonts that might not be present in the client machine\. See [S V G Files Inside Xlsx Files](xref:SVGFilesInsideXlsxFiles) for more information\.<br />|
|[ImageNaming](ImageNaming.md)|This property defines how the images will be named by FlexCel\. You can always override the name using the [GetImageInformation](GetImageInformation.md) event\.<br />|
|[EmbedImages](EmbedImages.md)|If true, images will be embedded in the HTML file using base64 encoded data uris as defined in http:&#8203;//&#8203;tools\.&#8203;ietf\.&#8203;org/&#8203;html/&#8203;rfc2397|
|[ExtraInfo](ExtraInfo.md)|Extra information to be added to the HTML file\.<br />|
|[SpreadView](SpreadView.md)|The properties here make the generated file look more like when you view a Spreadsheet in Excel, and less like a printed page\. By default, FlexCel tries to mimic the printed\-page output, not the interactive view\.<br />|
|[GeneratedFiles](GeneratedFiles.md)|Contains all the generated files by the component\. Note that it might contain files not actually generated, if an error happened while trying to create them\.<br />|
|[HasSaveImageEvent](HasSaveImageEvent.md)|Override this property when creating your own [OnSaveImage](OnSaveImage.md) descendant\. This method should return true if there is any event attached to it\.<br />|


## Events

|Name|Description|
|---|---|
|[GetImageInformation](GetImageInformation.md)|Use this event to customize where to save the images when exporting to HTML\.<br />|
|[SaveImage](SaveImage.md)|Use this event to save the images into other place\. Note that this event only fires when saving HTML, not MTHML\.<br />|
|[HtmlFont](HtmlFont.md)|Use this event to customize the fonts used in the exported file\.<br />|
|[NamedRangeExport](NamedRangeExport.md)|Use this event to customize how a named range if exported to the HTML file\. Note that for this event to be called, you first need to set [ExportNamedRanges](ExportNamedRanges.md) = true\. If you want to change the id that will be exported or exclude certain named from being exported, you can do so here\.<br />|


