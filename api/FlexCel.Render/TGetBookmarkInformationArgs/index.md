---
uid: TGetBookmarkInformationArgs
description: TGetBookmarkInformationArgs
---

# TGetBookmarkInformationArgs Class

Arguments passed on [TFlexCelPdfExport.GetBookmarkInformation](../TFlexCelPdfExport/GetBookmarkInformation.md),

## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">TGetBookmarkInformationArgs = class(EventArgs);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new Argument\.<br />|


## Properties

|Name|Description|
|---|---|
|[DataFile](DataFile.md)|The file with the pdf data\.<br />|
|[CurrentPage](CurrentPage.md)|Page currently printing\. 0 means the global bookmark parent of all the sheets\.<br />|
|[CurrentPageInSheet](CurrentPageInSheet.md)|Page currently printing, relative to the active sheet\.<br />|
|[Bookmark](Bookmark.md)|Bookmark that we are about to include\.<br />|


