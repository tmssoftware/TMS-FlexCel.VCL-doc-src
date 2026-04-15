---
uid: TPdfWriter
description: TPdfWriter
---

# TPdfWriter Class

A simple class for creating PDF files\. It will not hold contents into memory, so it can be used with little memory\.


## Remarks

This class is not intended for providing a complete API for writing PDFs, only what is necessary to create them from xls files\.
Even when this class could be used standalone, on most cases [FlexCel.Render.TFlexCelPdfExport](../../FlexCel.Render/TFlexCelPdfExport/index.md) should be used\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">TPdfWriter = class(TFlexCelObject);</code></pre>

## Fields

|Name|Description|
|---|---|
|[Properties](Properties.md)|Properties of the PDF file\.<br />|


## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new PDF file instance\.<br />|


## Methods

|Name|Description|
|---|---|
|[BeginDoc](BeginDoc.md)|Call this method before starting the output\.<br />It will initialize a new page\. After this you can call [DrawString\(&#8203;&#8203;string, TUIFont, TUIBrush, Double, Double\)](DrawString.md#tpdfwriterdrawstringstring-tuifont-tuibrush-double-double), [NewPage](NewPage.md), etc\.<br />Always end the document with a call to [EndDoc](EndDoc.md) and then remember to close the stream\.<br />|
|[EndDoc](EndDoc.md)|Always call this method to write the final part of a pdf file\.<br />|
|[NewPage](NewPage.md)|Closes the active page and creates a new one\. All following commands will go to the new page\.<br />|
|[DrawString](DrawString.md)|**Overloaded<br />**  [DrawString\(string, TUIFont, TUIBrush, Double, Double\)](DrawString.md#tpdfwriterdrawstringstring-tuifont-tuibrush-double-double)<br />  [DrawString\(string, TUIFont, TUITextDecoration, TUIBrush, Double, Double\)](DrawString.md#tpdfwriterdrawstringstring-tuifont-tuitextdecoration-tuibrush-double-double)<br />  [DrawString\(string, TUIFont, TUIPen, TUIBrush, Double, Double\)](DrawString.md#tpdfwriterdrawstringstring-tuifont-tuipen-tuibrush-double-double)<br />  [DrawString\(string, TUIFont, TUITextDecoration, TUIPen, TUIBrush, Double, Double\)](DrawString.md#tpdfwriterdrawstringstring-tuifont-tuitextdecoration-tuipen-tuibrush-double-double)<br />|
|[Hyperlink](Hyperlink.md)|**Overloaded<br />**  [Hyperlink\(Double, Double, Double, Double, string\)](Hyperlink.md#tpdfwriterhyperlinkdouble-double-double-double-string)<br />  [Hyperlink\(Double, Double, Double, Double, TUri\)](Hyperlink.md#tpdfwriterhyperlinkdouble-double-double-double-turi)<br />  [Hyperlink\(Double, Double, Double, Double, Integer, Double, Double\)](Hyperlink.md#tpdfwriterhyperlinkdouble-double-double-double-integer-double-double)<br />|
|[Comment](Comment.md)|Creates a comment on the pdf file\.<br />|
|[GetBookmarks](GetBookmarks.md)|Returns all the bookmarks on the file\. Note that this will return a COPY of the bookmarks, so changing them will not change them in the file\. You need to use [SetBookmarks](SetBookmarks.md) to replace the new list\.<br />|
|[SetBookmarks](SetBookmarks.md)|Replaces the bookmarks on the file with other list\. The new list will be copied, so you can change the old list after setting it and it will not affect the file\.<br />|
|[AddBookmark](AddBookmark.md)|Adds a new bookmark to the document\.<br />|
|[MeasureString](MeasureString.md)|Returns the size of a string in points \* Scale\. \(1/72 of an inch \* Scale\)|
|[FontHeight](FontHeight.md)|Returns the font height on points \* Scale\. \(1/72 of an inch \* Scale\)|
|[FontLinespacing](FontLinespacing.md)|Returns the font white space on points \* Scale\. \(1/72 of an inch \* Scale\)|
|[FontDescent](FontDescent.md)|Returns the font height on points \* Scale\. \(1/72 of an inch \* Scale\)|
|[DrawLine](DrawLine.md)|Draws a line on the current page\.<br />|
|[DrawLines](DrawLines.md)|Draws an array of line connecting pairs of points\.<br />|
|[FillRectangle](FillRectangle.md)|Fills the interior of a rectangle specified by a pair of coordinates, a width, and a height\.<br />No line is drawn around the rectangle\.<br />|
|[DrawRectangle](DrawRectangle.md)|Draws a rectangle specified by a coordinate pair, a width, and a height\.<br />|
|[DrawAndFillRectangle](DrawAndFillRectangle.md)|Draws and fills a rectangle specified by a coordinate pair, a width, and a height\.<br />|
|[DrawAndFillBeziers](DrawAndFillBeziers.md)|Draws and/or fills a bezier path\. If Brush is not null, the shape will be closed for filling\.<br />|
|[DrawAndFillMulti&#8203;Beziers](DrawAndFillMultiBeziers.md)|Draws and/or fills a bezier path\.<br />|
|[DrawAndFillPolygon](DrawAndFillPolygon.md)|Draws and/or fills a polygon\. The shape will be closed\.<br />|
|[IntersectClipRegion](IntersectClipRegion.md)|Intersects the current clipping region with the new one\.<br />There is no command to reset or expand a clipping region, you need to use [SaveState](SaveState.md) and [RestoreState](RestoreState.md)|
|[ClipRectangle](ClipRectangle.md)|Intersect the clip region with a rectangle specified by a pair of coordinates, a width, and a height\.<br />|
|[ClipPolygon](ClipPolygon.md)|Intersects the clipping area with a polygon\.<br />|
|[ClipBeziers](ClipBeziers.md)|Intersects the clipping area with a bezier region\.<br />|
|[ClipMultiBeziers](ClipMultiBeziers.md)|Intersects the clipping area with multiple bezier regions\.<br />|
|[DrawImage](DrawImage.md)|**Overloaded<br />**  [DrawImage\(TUIImage, TUIRectangle, TStream\)](DrawImage.md#tpdfwriterdrawimagetuiimage-tuirectangle-tstream)<br />  [DrawImage\(TUIImage, TUIRectangle, TStream, Int64, Boolean\)](DrawImage.md#tpdfwriterdrawimagetuiimage-tuirectangle-tstream-int64-boolean)<br />|
|[Rotate](Rotate.md)|Rotates the canvas around point \(x,y\)\.<br />|
|[ScaleBy](ScaleBy.md)|**Overloaded<br />**  [ScaleBy\(Double, Double\)](ScaleBy.md#tpdfwriterscalebydouble-double)<br />  [ScaleBy\(Double, Double, Double, Double\)](ScaleBy.md#tpdfwriterscalebydouble-double-double-double)<br />|
|[GetMatrix](GetMatrix.md)|Returns the drawing matrix in use\. The elements in this matrix are similar to the ones returned by "System\.&#8203;Drawing\.&#8203;Drawing2D\.&#8203;Matrix\.&#8203;Elements" and have the same meaning\.<br />**Important remark\. This matrix is the real one, and does not consider things like [YAxisGrowsDown](YAxisGrowsDown.md) or [Scale](Scale.md)\.** You will probably want to use [Transform\(&#8203;&#8203;TUIPointF\)](Transform.md#tpdfwritertransformtuipointf) to find out the coordinates of a point\.<br />|
|[Transform](Transform.md)|**Overloaded<br />**  [Transform\(TUIPointF\)](Transform.md#tpdfwritertransformtuipointf)<br />  [Transform\(TUIPointF, TArray\<Double>\)](Transform.md#tpdfwritertransformtuipointf-tarraydouble)<br />|
|[SaveState](SaveState.md)|Saves the current graphic state\. Be sure to always call [RestoreState](RestoreState.md) each time you call this method\.<br />|
|[RestoreState](RestoreState.md)|Restores the graphic state saved by a [SaveState](SaveState.md) call\.<br />|
|[Sign](Sign.md)|Signs the pdf documents with the specified [TPdfSignature](../TPdfSignature/index.md) or [TPdfVisibleSignature](../TPdfVisibleSignature/index.md)\.<br /><br />**Important:** This method will take ownership of the signature and free it when it ends\. Don't reuse the signature twice, and don't free it yourself\.<br />**Note:** This method must be called **before** calling [BeginDoc](BeginDoc.md)|
|[TagContentBegin](TagContentBegin.md)|Marks the start of a content tag inside a stream\. Must be finished with a call to [TagContentEnd](TagContentEnd.md)|
|[TagContentEnd](TagContentEnd.md)|Ends marking content which started with [TagContentBegin](TagContentBegin.md)|
|[AttachFile](AttachFile.md)|**Overloaded<br />**  [AttachFile\(string, string, string, TPdfAttachmentKind\)](AttachFile.md#tpdfwriterattachfilestring-string-string-tpdfattachmentkind)<br />  [AttachFile\(string, string, string, TDateTime, TPdfAttachmentKind, TPdfAttachmentDataProviderDelegate\)](AttachFile.md#tpdfwriterattachfilestring-string-string-tdatetime-tpdfattachmentkind-tpdfattachmentdataproviderdelegate)<br />|
|[ClearAttachments](ClearAttachments.md)|Removes all existing attachments in the writer\.<br />|


## Properties

|Name|Description|
|---|---|
|[Compress](Compress.md)|Set it to true to compress the text on the generated pdf file\.<br />|
|[PageSize](PageSize.md)|Page size of the active page\. You can change it \*before\* calling NewPage\(\) and it will change for the new sheets\.<br />Note that once NewPage\(\) \(or BeginDoc\(\) for the first page\) is called, the page size will remain constant for that page\.<br />This property must be changed before\.<br />|
|[YAxisGrowsDown](YAxisGrowsDown.md)|When true, the y axis origin corresponds to the upper corner of a sheet and bigger Y coordinates will  move down on the paper\. This is the standard GDI\+ behavior\.<br />When false, the Y origin is at the bottom and it grows up into the page\. This is the standard PDF behavior\.<br />|
|[AddFontDescent](AddFontDescent.md)|When false, \(the default\) text base will be at the y coordinate\. For example, DrawString\(\.\.\., y=100,\.\.\.\) will draw a string with its base at 100\. Font descent \(for example the lower part of a "p"\) will be below 100, and the ascent \(the upper part\) will be above\. This is the standard PDF behavior\.<br />When true, all text will be drawn above the y coordinate\. \(both ascent and descent\)\.<br />This is the standard GDI\+ behavior, when StringFormat\.&#8203;Line&#8203;Alignment=&#8203;String&#8203;Alignment\.&#8203;Far\.&#8203;<br />|
|[Scale](Scale.md)|A scale factor to change X and Y coordinates\. When Scale=1, the using is the point \(1/72 of an inch\)\.<br />Font size is not affected by scale, it is always in points\.<br />|
|[PdfType](PdfType.md)|Defines the type of pdf being created\. Note that if you set this property to other value than standard, other properties might be ignored\. For example, when creating a PDF/A file all fonts must be embedded so  the value of the FontEmbed property will be ignored\.<br />|
|[UnlicensedFontAction](UnlicensedFontAction.md)|Defines what to do when a font has a license that doesn't allow embedding, and you are trying to embed the font\.<br />FlexCel will default to throw an Exception in those cases, but if you for example have a license to embed the font, you can change this property to ignore the error\. You can also set a replacement font to be used for fonts that don't allow embedding inside PDF docs\. For more information, see [https:&#8203;//&#8203;www.&#8203;microsoft.&#8203;com/&#8203;en-&#8203;us/&#8203;microsoft-&#8203;365/&#8203;blog/&#8203;2015/&#8203;07/&#8203;06/&#8203;document-&#8203;font-&#8203;embedding-&#8203;demystified/](https://www.microsoft.com/en-us/microsoft-365/blog/2015/07/06/document-font-embedding-demystified/)|
|[UnlicensedReplacement&#8203;Font](UnlicensedReplacementFont.md)|When trying to embed a font that isn't licensed for embedding, and [UnlicensedFontAction](UnlicensedFontAction.md) is TUnlicensedFont&#8203;Action\.&#8203;Replace this property specifies the font that will be used to replace it\. If null or empty, Arial will be used\.<br />|
|[PdfVersion](PdfVersion.md)|Defines the version of pdf being created\. For maximum compatibility you can choose PDF 1\.4\. \(Acrobat 5\.0, but can be opened by any version of Acrobat, even if version less than 1\.4 won't have all the features\)\.<br />Choosing PDF 1\.6 \(Acrobat 7\) allows for more compression and smaller files, but you'll need Acrobat 7 or newer  to see the files\. Older versions won't be able to open it at all\.<br /><br /><br />Note that this value will be ignored if you are creating PDFA\-1 \(as it requires PDF1\-4\)\. Also for signing, FlexCel requires PDF1\-6\.<br />|
|[EmbedColorProfile](EmbedColorProfile.md)|If true, a color profile will be embedded in the generated pdf files\. An embedded color profile can increase the size of the generated file in some kilobytes, and it isn't required or needed, so you'll normally want to  keep this property false\. For PDF/A, it is required, but when you set the PdfType to PDF/A the color profile will always be included anyway, and this property will be ignored\.<br />|
|[FontEmbed](FontEmbed.md)|Determines what fonts will be embedded on the generated pdf\.<br />Note that when using UNICODE fonts WILL BE EMBEDDED no matter the value of this property\. Also if creating PDF/A files\.<br />|
|[FontSubset](FontSubset.md)|When [FontEmbed](FontEmbed.md) is set to embed the fonts, this setting determines if the full font will be embedded, or only the characters used in the document\. If the full font is embedded the resulting file will be larger, but  it will be possible to edit it with a third party tool once it has been generated\.<br />|
|[FontMapping](FontMapping.md)|Determines how fonts will be replaced on the generated pdf\. Pdf comes with 4 standard font families, Serif, Sans\-Serif, Monospace and Symbol\. You can use for example the standard Helvetica instead of Arial and do not worry about embedding the font\.<br />|
|[Kerning](Kerning.md)|By default, pdf does not do any kerning with the fonts\. This is, on the string "AVANT", it won't compensate the spaces between "A" and "V"\. \(they should be smaller\)  If you turn this property on, FlexCel will calculate the kerning and add it to the generated file\.<br />The result file will be a little bigger because of the kerning info on all strings, but it will also look a little better\.<br />|
|[UseFauxStyles](UseFauxStyles.md)|When a font doesn't have a bold, italic or bold\-italic variant, FlexCel can't export bold, italic or bold\-italic characters to the pdf respectively\. When this property is true \(the default\), FlexCel will try to "fake" those missing styles by using a wider pen width for the characters to simulate bold, or doing a slant transform to simulate italics\.<br /><br />The results of a simulated bold or italic can be not great, so if you prefer that FlexCel doesn't try to simulate bold or italics, then you can set this property to false\. If this property is false and the font you are using doesn't have bold or italics variants, then the pdf won't show bold or italics for that font\.<br />[...[more]](UseFauxStyles.md)|
|[FallbackFonts](FallbackFonts.md)|A semicolon \(;\) separated list of font names to try when a character is not found in the used font\.<br /><br />When a character is not found in a font, it will display as an empty square by default\. By setting this property, FlexCel will try to find a font that supports this character in this list, and if found, use that font to render the character\.<br />|
|[FallbackFontsBold](FallbackFontsBold.md)|A semicolon \(;\) separated list of font names similar to [FallbackFonts](FallbackFonts.md) that will be used only for bold fonts\.<br /><br />If you fallback fonts already contain bold variants, you don't need to set this property\.<br />This property is only if you want to use different font fallbacks for bold fonts and regular fonts\.<br />|
|[FallbackFontsItalic](FallbackFontsItalic.md)|A semicolon \(;\) separated list of font names similar to [FallbackFonts](FallbackFonts.md) that will be used only for italic fonts\.<br /><br />If you fallback fonts already contain italic variants, you don't need to set this property\.<br />This property is only if you want to use different font fallbacks for italic fonts and regular fonts\.<br />|
|[FallbackFonts&#8203;Bold&#8203;Italic](FallbackFontsBoldItalic.md)|A semicolon \(;\) separated list of font names similar to [FallbackFonts](FallbackFonts.md) that will be used only for fonts which are both bold and italic\.<br /><br />If you fallback fonts already contain bold\-italic variants, you don't need to set this property\.<br />This property is only if you want to use different font fallbacks for bold\-italic fonts and regular fonts\.<br />|
|[OnFontFolderNotFound](OnFontFolderNotFound.md)|This property determines how FlexCel behaves when one of the folders you specify in [GetFontFolder](GetFontFolder.md) doesn't exist\.<br />Note that this applies for a single PdfWriter instance, to set it for the full application, use [OnFontFolder&#8203;NotFound&#8203;Global](OnFontFolderNotFoundGlobal.md)|
|[OnFontFolder&#8203;NotFound&#8203;Global](OnFontFolderNotFoundGlobal.md)|This property determines how FlexCel behaves when one of the folders you specify in [GetFontFolder](GetFontFolder.md) doesn't exist\.<br />**Important:** This event isn't thread safe or guarded by any lock\. You should set it once when your application starts and never modify it\. For changing a particular instance, use [OnFontFolderNotFound](OnFontFolderNotFound.md) instead\. If you aren't sure, use [OnFontFolderNotFound](OnFontFolderNotFound.md)|
|[UseLocalFontList](UseLocalFontList.md)|**This is a setting mostly for testing, do not change unless you have a good reason,**<br />By default, FlexCel uses a global font list for exporting to PDF, because populating the font list is slow, and keeping it in a cache makes everything faster\. But when testing, we sometimes need to validate specific behaviors in a test, and a shared global font list can make it difficult\.<br />Setting this property to true will make FlexCel use a local font list for this instance of PdfWriter, so it won't interfere with other tests that might be running at the same time\.<br />It will also make the exporting slower\.<br />|
|[PageLayout](PageLayout.md)|Sets the default page layout when opening the document\.<br />|
|[PageLayoutDisplay](PageLayoutDisplay.md)|Sets the default page display layout when opening the document\.<br />|
|[InitialZoomAndPage](InitialZoomAndPage.md)|Sets the default zoom and initial page when opening the document\.<br />|
|[TagActions](TagActions.md)|Implement this interface in order to define the tags\.<br />|


## Events

|Name|Description|
|---|---|
|[GetFontData](GetFontData.md)|Use this event if you want to provide your own font information for embedding for a particular instance\.<br />Note that if you don't assign this event, [GetFontDataGlobal](GetFontDataGlobal.md) will be used instead\.<br />If GetFontData and GetFontDataGlobal are not assigned the default method will be used, and this  will try to find the font on the Fonts folder\. To change the font folder, use [GetFontFolder](GetFontFolder.md) event|
|[GetFontDataGlobal](GetFontDataGlobal.md)|Use this event if you want to provide your own font information for embedding for the full application\.<br />Note that if you assign [GetFontData](GetFontData.md) for a particular object instance it will be used instead\.<br />**Important:** This event isn't thread safe or guarded by any lock\. You should set it once when your application starts and never modify it\. For changing a particular instance, use [GetFontData](GetFontData.md) instead\. If you aren't sure, use [GetFontData](GetFontData.md)|
|[GetFontFolder](GetFontFolder.md)|Use this event if you want to provide your own font information for embedding for a particular object instance\.<br /><br />For changing the font folder for the full application, use [GetFontFolderGlobal](GetFontFolderGlobal.md) instead\.<br />Normally FlexCel will search for fonts on \[System\]\\Fonts folder and %%&#8203;localappdata%&#8203;%\\Microsoft\\Windows\\Fonts\. If your fonts are in  other location, you can tell FlexCel where they are here\. If you prefer just to give FlexCel the full data on the font, you can use[...[more]](GetFontFolder.md)|
|[GetFontFolderGlobal](GetFontFolderGlobal.md)|Use this event if you want to provide your own font folder for the full application\.<br />Note that if you assign [GetFontFolder](GetFontFolder.md) for a particular object instance it will be used instead\.<br />**Important:** This event isn't thread safe or guarded by any lock\. You should set it once when your application starts and never modify it\. For changing a particular instance, use [GetFontFolder](GetFontFolder.md) instead\. If you aren't sure, use [GetFontFolder](GetFontFolder.md)<br />Note that you can return more than one path by separating them with semicolons\. For example if you return "c:&#8203;\\fonts1;&#8203;c:&#8203;\\fonts2" FlexCel will search both in fonts1 and fonts2\. Every folder you specify here must have at least one font\.<br />[...[more]](GetFontFolderGlobal.md)|
|[OnFontEmbed](OnFontEmbed.md)|Use this event if you want to manually specify which fonts to embed into the pdf document\.<br />Note that this applies for a single PdfWriter instance, to set it for the full application, use [OnFontEmbedGlobal](OnFontEmbedGlobal.md)|
|[OnFontEmbedGlobal](OnFontEmbedGlobal.md)|Use this event if you want to manually specify which fonts to embed into the pdf document for the full application\.<br />Note that if you assign [OnFontEmbed](OnFontEmbed.md) for a particular object instance it will be used instead\.<br />**Important:** This event isn't thread safe or guarded by any lock\. You should set it once when your application starts and never modify it\. For changing a particular instance, use [OnFontEmbed](OnFontEmbed.md) instead\. If you aren't sure, use [OnFontEmbed](OnFontEmbed.md)|


