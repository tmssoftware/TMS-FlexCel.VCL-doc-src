---
uid: FlexCel.Pdf
description: FlexCel.Pdf
---

# FlexCel.Pdf Namespace

This is a low level PDF engine\. It provides an API similar to GDI\+ to generate pdf files\. isn't Excel related and you can use it on its own\. It is used by FlexCel\.Render to convert xls/x files into PDF\.


## Classes

|Name|Description|
|---|---|
|[EFlexCelPdfException](EFlexCelPdfException/index.md)|Exception thrown when an exception on the PDF engine happens\.<br />|
|[TBookmark](TBookmark/index.md)|An entry on the Bookmark list for a PDF file\.<br />|
|[TBookmarkList](TBookmarkList/index.md)|A list of bookmarks\.<br />|
|[TBuiltInSigner&#8203;Factory](TBuiltInSignerFactory/index.md)|This class will create instances of the Built\-in signer\. It will take ownership of the signer you assign to it\.<br />|
|[TFontEmbedEventArgs](TFontEmbedEventArgs/index.md)|Arguments passed on [TFlexCelPdfExport.&#8203;OnFont&#8203;Embed](../FlexCel.Render/TFlexCelPdfExport/OnFontEmbed.md)\.<br />Use this event to specify which fonts to embed and which fonts to ignore\. Note that unicode fonts will be  embedded no matter what you say here\.<br />|
|[TGetFontData&#8203;Event&#8203;Args](TGetFontDataEventArgs/index.md)|Arguments passed on [TFlexCelPdfExport.&#8203;Get&#8203;Font&#8203;Data](../FlexCel.Render/TFlexCelPdfExport/GetFontData.md)\.<br />Use this event to provide font information for embedding\.<br />|
|[TGetFontFolder&#8203;Event&#8203;Args](TGetFontFolderEventArgs/index.md)|Arguments passed on [TFlexCelPdfExport.&#8203;Get&#8203;Font&#8203;Folder](../FlexCel.Render/TFlexCelPdfExport/GetFontFolder.md)\.<br />Use this event to provide font information for embedding\.<br />|
|[TPdfAttachmentWriter](TPdfAttachmentWriter/index.md)|Class used to write the file contents of one attachment into a PDF file\.<br />|
|[TPdfSignature](TPdfSignature/index.md)|Describes a non visible signature for a PDF file\.<br />For a visible signature, use [TPdfVisibleSignature](TPdfVisibleSignature/index.md)<br />**NOTE:** This class will take ownership of the signer factory and will free it once it is used\.<br />|
|[TPdfSigner](TPdfSigner/index.md)|Represents an abstract class to create a pdf PKCS7 DER encoded signature\.<br />Descend from this class to create your own SignerFactory implementations\.<br />|
|[TPdfSignerFactory](TPdfSignerFactory/index.md)|Override this factory when creating your own [TPdfSigner](TPdfSigner/index.md) class, so it is returned here\.<br />|
|[TPdfVisibleSignature](TPdfVisibleSignature/index.md)|Describes a visible signature in a PDF file\. For an invisible signature, see [TPdfSignature](TPdfSignature/index.md)\.<br />|
|[TPdfWriter](TPdfWriter/index.md)|A simple class for creating PDF files\. It will not hold contents into memory, so it can be used with little memory\.<br />|
|[TPngInformation](TPngInformation/index.md)|Basic information about a PNG file\.<br />|


## Records

|Name|Description|
|---|---|
|[TPdfCommentProperties](TPdfCommentProperties/index.md)|Properties for a PDF comment\.<br />|
|[TPdfDestination](TPdfDestination/index.md)|Represents a destination inside a PDF document\.<br />|
|[TPdfMessages](TPdfMessages/index.md)|FlexCel Native PDF Constants\. It reads the resources from the active locale, and returns the correct string\.<br />If your language is not supported and you feel like translating the messages, please send us a copy\. We will include it on the next FlexCel version\.<br /><br /><br />To add a new language:[...[more]](TPdfMessages/index.md)<br /><br />|
|[TPdfPng](TPdfPng/index.md)|A class for reading a PNG image\. Mostly for internal use, but it can return some very basic information on a PNG file too\.<br />|
|[TPdfProperties](TPdfProperties/index.md)|Encapsulates the document properties for the PDF file\.<br />|


## Interfaces

|Name|Description|
|---|---|
|[IPdfPageTagger](IPdfPageTagger/index.md)|Implement this interface in order to tag a pdf file created by TPdfWriter\. This interface will be called after every page is generated\. Note that FlexCelPdfExport already implements it so there is no need to define it again\.<br />|
|[IPdfRoleTag](IPdfRoleTag/index.md)|Implement this interface in order to add roles to the structure tree\.<br />|
|[IPdfTagActions](IPdfTagActions/index.md)|Events that allow you to tag a pdf document\.<br />|
|[IPdfTagger](IPdfTagger/index.md)|Base interface for tagging PDF documents\.<br />|
|[IPdfTeardownTagger](IPdfTeardownTagger/index.md)|Implement this interface to tag a PDF file created by TPdfWriter\. This interface will be called after every document is finished and allows you to write global tags\. Note that FlexCelPdfExport already implements it, so there is no need to define it again\.<br />|
|[IPdfTimestamp&#8203;Settings](IPdfTimestampSettings/index.md)|Says how a signature is timestamped, so it is a PAdES B\-T signature instead of a plain B\-B\.<br />|


## Enumerations

|Name|Description|
|---|---|
|[HashAlgorithmName](HashAlgorithmName.md)|Algorithm used to create a hash\.<br />|
|[TBookmarkStyle](TBookmarkStyle.md)|This enum indicates the text style for a bookmark entry\.<br />You can combine the entries by or'ing them together\.<br />|
|[TFontEmbed](TFontEmbed.md)|The way fonts will be embedded on the resulting pdf file\.<br />|
|[TFontMapping](TFontMapping.md)|How fonts will be replaced on the generated PDF file\.<br />|
|[TFontSubset](TFontSubset.md)|Determines if full fonts will be embedded in the generated pdf files, or only the characters being used\.<br />|
|[TPageLayout](TPageLayout.md)|Viewer settings when the document is opened for the first time\.<br />|
|[TPageLayoutDisplay](TPageLayoutDisplay.md)|How the pages will display when the document is opened for the first time\.<br />|
|[TPdfAllowedChanges](TPdfAllowedChanges.md)|Changes allowed in a signed PDF document\.<br />|
|[TPdfAttachmentKind](TPdfAttachmentKind.md)|Specifies how the attached file relates to the pdf file\. It is required by PDF/A3|
|[TPdfCommentIcon](TPdfCommentIcon.md)|Icon for a pdf comment|
|[TPdfCommentType](TPdfCommentType.md)|Different types of comments\.<br />|
|[TPdfErr](TPdfErr.md)|Error Codes\. We use this and not actual strings to make sure all are correctly spelled\.<br />|
|[TPdfFontFolder&#8203;NotFound&#8203;Action](TPdfFontFolderNotFoundAction.md)|Determines what FlexCel should do when a font folder doesn't exist\.<br />|
|[TPdfSignature&#8203;SubFilter](TPdfSignatureSubFilter.md)|Format of the digital signature embedded in a PDF file\. This is the value written to the "SubFilter" entry of the signature dictionary, and it tells the PDF reader how the bytes returned by [TPdfSigner.&#8203;Get&#8203;Signature](TPdfSigner/GetSignature.md) have to be interpreted\.<br />|
|[TPdfSubType](TPdfSubType.md)|Use this enum to specify the subtype of PDF/A files generated by FlexCel, when it cannot be determined automatically\.<br />Don't use this enum unless you need to specify the exact subtype\. Also note that if the type can be determined automatically, FlexCel will use that instead, no matter the value here\.<br />|
|[TPdfToken](TPdfToken.md)|Tokens for creating a PDF file\. Internal use\.<br />|
|[TPdfType](TPdfType.md)|The variant of pdf that will be created\.<br /><br />Look at ['Creating pdfa files' in the Pdf Exporting Guide](xref:PdfExportingGuide#creating-pdfa-files) for more information\.<br />|
|[TPdfVersion](TPdfVersion.md)|Specifies the version of PDF that FlexCel will generate\.<br />|
|[TTagMode](TTagMode.md)|Specifies how the document will be tagged\.<br />|
|[TUnlicensedFont&#8203;Action](TUnlicensedFontAction.md)|Determines what to do when trying to embed a font that isn't licensed for embedding\.<br />|
|[TZoomOptions](TZoomOptions.md)|Zoom options for a PDF destination\.<br />|


## Anonymous methods

|Name|Description|
|---|---|
|[TPdfAttachment&#8203;Data&#8203;Provider&#8203;Delegate](TPdfAttachmentDataProviderDelegate.md)|Delegate used to attach files to a pdf file\.<br />|
|[TPdfTimestampHandler](TPdfTimestampHandler.md)|Sends a timestamp request to a Time Stamping Authority \(TSA\) and returns the answer\. The request is a DER encoded RFC 3161 TimeStampReq, and the answer is a DER encoded TimeStampResp\.<br /><br />**FlexCel never connects to the internet by itself**: So you need to provide the internet access through this method\.<br />|


## Types

|Name|Description|
|---|---|
|[TFontEmbedEvent&#8203;Handler](TFontEmbedEventHandler.md)|Delegate for reading the font data\.<br />|
|[TGetFontData&#8203;Event&#8203;Handler](TGetFontDataEventHandler.md)|Delegate for reading the font data\.<br />|
|[TGetFontFolder&#8203;Event&#8203;Handler](TGetFontFolderEventHandler.md)|Delegate for reading the font data\.<br />|


