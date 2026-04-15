---
uid: TXlsFile.GetSheetBackground
description: TXlsFile.GetSheetBackground
---

# TXlsFile\.GetSheetBackground Method

Gets the sheet background for the active sheet\. It will return null if there isn't any background in the sheet\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetSheetBackground(out imageType: <a href="../../FlexCel.Core/TXlsImgType.md">TXlsImgType</a>): TBytes; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|out|**imageType**|[TXlsImgType](../../FlexCel.Core/TXlsImgType.md)|Returns the image type of the bytes returned\.|


## Returns

The image data as a byte array\.

## See also

* [TXlsFile](../TXlsFile/index.md)

