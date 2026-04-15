---
uid: TFlexCelError
description: TFlexCelError
---

# TFlexCelError Enumeration

An enumeration of all possible FlexCel non fatal errors that can be logged\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|Undefined|0|This error should never happen\.<br />|
|XlsTooManyPageBreaks|256|There are more page breaks in this page than the maximum allowed, and page breaks over this maximum are being ignored\.<br />You can control if you want a "real" exception here with the [TExcelFile.ErrorActions](TExcelFile/ErrorActions.md) and [TFlexCelReport.ErrorActions](../FlexCel.Report/TFlexCelReport/ErrorActions.md) properties\.<br />|
|RowHeightTooBig|257||
|XlsxInvalidName|258|A corrupt xlsx file can have invalid names\. If [TExcelFile.ErrorActions](TExcelFile/ErrorActions.md) is set to the  correct value, those names will be imported as \#REF\! instead of rising an Exception\.<br />|
|XlsxMissingPart|259|The file has references to other parts that don't exist\. For example, an image might be referenced in a sheet,  but the actual image data missing from the file\. If [TExcelFile.ErrorActions](TExcelFile/ErrorActions.md) is set to the  correct value, those parts will be ignored\.<br />|
|RenderMetafile|512|There was a GDI\+ error trying to draw or print a metafile\. It will be rendered as a bitmap\.<br />|
|RenderCorruptImage|513|The image could not be rendered by GDI\+\.<br />|
|RenderErrorDrawingImage|514|An image could not be drawn\. This error normally happens in \.NET 1\.1 if vj\# is not installed\.<br />|
|RenderGenericPreview|515|A generic error when drawing the preview\.<br />|
|PdfFontNotFound|768|The font was not found in the system\. A substitute font will be used for the rendering, and it might not look the same\.<br /><br />If you are seeing this message in a server, make sure the server has the same fonts installed as the machine where you developed the application\.<br />|
|PdfGlyphNotInFont|769|FlexCel is trying to render a character that is not in the font or the fallback fonts\. This character will show as an empty square in the generated PDF file\.<br />Normally this means that Excel is replacing fonts, for example Arial with MS Mincho, and to fix this error you should provide a  suitable list of Fallback fonts\. Look at ['Dealing with missing fonts and glyphs' in the Pdf Exporting Guide](xref:PdfExportingGuide#dealing-with-missing-fonts-and-glyphs) for more information\.<br />|
|PdfUsedFallbackFont|770|FlexCel is trying to render a character that is not in the font, but it is in the fallback font list\. This character will be drawn with the fallback font\.<br />Normally this means that Excel is replacing fonts, for example Arial with MS Mincho\. Look at ['Dealing with missing fonts and glyphs' in the Pdf Exporting Guide](xref:PdfExportingGuide#dealing-with-missing-fonts-and-glyphs) for more information\.<br />|
|PdfFauxBoldOrItalics|771|The font you are trying to use does not have a "bold" or "italic" variation, and we will use "faux" font created by making the normal font heavier or slanting it to the right\. This normally results in lower quality text that might not look good\. We recommend that you use fonts that have italics and bold variations\.<br /><br /><br />If you want to avoid FlexCel creating faux bold or italic, you can set FlexCelPdfExport\.UseFauxStyles = false\. But even if you set that property off, this warning will still appear in FlexCelTrace\.<br /><br /><br />Look at ['Dealing with missing fonts and glyphs' in the Pdf Exporting Guide](xref:PdfExportingGuide#dealing-with-missing-fonts-and-glyphs) for more information\.<br />|
|PdfCorruptFontInFontFolder|772|The "Fonts" folder in this machine has a file that could not be parsed by FlexCel and is probably corrupt\. While this will not affect FlexCel in any way, you might want to look at the "Font" folder and remove this font, since it can make windows slower\.<br />|
|PdfFontLicenseDoesntAllowEmbedding|773|Trying to embed a font which is not licensed to be embedded\.<br />|
|HtmlSaveSharingViolation|1024|There was a sharing violation when trying to save an html file, and [TFlexCelHtmlExport.IgnoreSharingViolations](../FlexCel.Render/TFlexCelHtmlExport/IgnoreSharingViolations.md) is true\.<br />Normally this just means two parallel threads trying to write the same file and can be safely ignored\.<br />|
|MalformedUrl|1280|A malformed Url was detected in the xls file and was not exported\. An example of this might be: "mailto:test@test@test"\.<br />|
|RecoveryInvalidName|1536|A name couldn't be loaded\.<br />|
|RecoveryInvalidFormulaTokens|1537|A formula can't be read\.<br />|
|RecoveryInvalidFormat|1538|The format is invalid\.<br />|


