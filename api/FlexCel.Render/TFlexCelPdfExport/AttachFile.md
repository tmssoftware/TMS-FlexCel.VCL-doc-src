---
uid: TFlexCelPdfExport.AttachFile
description: TFlexCelPdfExport.AttachFile
---

# TFlexCelPdfExport\.AttachFile Method

## Overloads

* [TFlexCelPdfExport\.AttachFile\(string, string, string, TPdfAttachmentKind\)](#tflexcelpdfexportattachfilestring-string-string-tpdfattachmentkind)
* [TFlexCelPdfExport\.AttachFile\(string, string, string, TDateTime, TPdfAttachmentKind, TPdfAttachmentDataProviderDelegate\)](#tflexcelpdfexportattachfilestring-string-string-tdatetime-tpdfattachmentkind-tpdfattachmentdataproviderdelegate)

# TFlexCelPdfExport\.AttachFile\(string, string, string, TPdfAttachmentKind\)
Attachs a file to the pdf file\. You can attach files at any time while creating the pdf, but the file will be read only when you call [EndExport](EndExport.md)\. The files that are in the list at the moment of calling EndExport are the ones that will be saved, and they contents of the files will be read then\.

You can remove all the attachments in the file by calling [ClearAttachments](ClearAttachments.md)\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelPdfExport/index.md">TFlexCelPdfExport</a>.AttachFile(const fileName: string; const mimeType: string; const description: string; const attachmentKind: <a href="../../FlexCel.Pdf/TPdfAttachmentKind.md">TPdfAttachmentKind</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**fileName**|string|Name on disk of the file to attach\. This will also be the name of the file in  the pdf\. If you want to specify a different name in the pdf than the name on disk, use [AttachFile\(string, string, string, TDateTime, TPdfAttachmentKind, TPdfAttachmentDataProviderDelegate\)](AttachFile.md#tflexcelpdfexportattachfilestring-string-string-tdatetime-tpdfattachmentkind-tpdfattachmentdataproviderdelegate)|
|const|**mimeType**|string|Mime type of the file being attached\.<br />You can use [TStandardMimeType](../../FlexCel.Core/TStandardMimeType/index.md) for predefined types\.<br />Note that while this might be null or Empty for standard pdf files, for PDF/A3 mime type is required\.<br />If you don't know the mime type, you must specify StandardMimeType\.OctectStream\.<br />|
|const|**description**|string|Description of the file that the pdf reader will show in the attachment pane\.<br />While not required by PDF/A\-3, it is recommended to provide a description for the file\.|
|const|**attachmentKind**|[TPdfAttachmentKind](../../FlexCel.Pdf/TPdfAttachmentKind.md)|How the attachment relates to the pdf file\. This is required by PDF/A\-3\.|


## See also

* [TFlexCelPdfExport](../TFlexCelPdfExport/index.md)

# TFlexCelPdfExport\.AttachFile\(string, string, string, TDateTime, TPdfAttachmentKind, TPdfAttachmentDataProviderDelegate\)
Attachs a file to the pdf file\. You can attach files at any time while creating the pdf, but the file will be read only when you call [EndExport](EndExport.md)\. The files that are in the list at the moment of calling EndExport are the ones that will be saved, and they contents of the files will be read then\.

You can remove all the attachments in the file by calling [ClearAttachments](ClearAttachments.md)\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelPdfExport/index.md">TFlexCelPdfExport</a>.AttachFile(const fileName: string; const mimeType: string; const description: string; const modificationTimeLocalTimeZone: TDateTime; const attachmentKind: <a href="../../FlexCel.Pdf/TPdfAttachmentKind.md">TPdfAttachmentKind</a>; const dataProvider: <a href="../../FlexCel.Pdf/TPdfAttachmentDataProviderDelegate.md">TPdfAttachmentDataProviderDelegate</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**fileName**|string|Name that will be used for the file in the pdf\.|
|const|**mimeType**|string|Mime type of the file being attached\.<br />You can use [TStandardMimeType](../../FlexCel.Core/TStandardMimeType/index.md) for predefined types\.<br />Note that while this might be null or Empty for standard pdf files, for PDF/A3 mime type is required\.<br />If you don't know the mime type, you must specify StandardMimeType\.OctectStream\.<br />|
|const|**description**|string|Description of the file that the pdf reader will show in the attachment pane\.<br />While not required by PDF/A\-3, it is recommended to provide a description for the file\.|
|const|**modificationTimeLocalTimeZone**|TDateTime|Modification date of the attachment file in the local time zone\.<br />Use DateTime\.MinValue to not write a modification date for the file\.|
|const|**attachmentKind**|[TPdfAttachmentKind](../../FlexCel.Pdf/TPdfAttachmentKind.md)|How the attachment relates to the pdf file\. This is required by PDF/A\-3\.|
|const|**dataProvider**|[TPdfAttachment&#8203;Data&#8203;Provider&#8203;Delegate](../../FlexCel.Pdf/TPdfAttachmentDataProviderDelegate.md)|This can be a delegate or lambda expression that will load the data for the file when actually embedding it\. This action will be called at the moment of embedding and must provide the data for the file\.|


## See also

* [TFlexCelPdfExport](../TFlexCelPdfExport/index.md)

