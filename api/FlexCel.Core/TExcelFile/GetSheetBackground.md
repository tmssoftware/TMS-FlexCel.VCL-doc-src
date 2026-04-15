---
uid: TExcelFile.GetSheetBackground
description: TExcelFile.GetSheetBackground
---

# TExcelFile\.GetSheetBackground Method

Gets the sheet background for the active sheet\. It will return null if there isn't any background in the sheet\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetSheetBackground(out imageType: <a href="../TXlsImgType.md">TXlsImgType</a>): TBytes; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|out|**imageType**|[TXlsImgType](../TXlsImgType.md)|Returns the image type of the bytes returned\.|


## Returns

The image data as a byte array\.

## See also

* [TExcelFile](../TExcelFile/index.md)

