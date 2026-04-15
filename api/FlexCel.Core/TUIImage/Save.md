---
uid: TUIImage.Save
description: TUIImage.Save
---

# TUIImage\.Save Method

## Overloads

* [TUIImage\.Save\(TStream, TXlsImgType\)](#tuiimagesavetstream-txlsimgtype)
* [TUIImage\.Save\(string, TXlsImgType\)](#tuiimagesavestring-txlsimgtype)

# TUIImage\.Save\(TStream, TXlsImgType\)
Saves the image to a stream, in the specified format\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TUIImage/index.md">TUIImage</a>.Save(const outMs: TStream; const ImgType: <a href="../TXlsImgType.md">TXlsImgType</a>): <a href="../TXlsImgType.md">TXlsImgType</a>; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**outMs**|TStream||
|const|**ImgType**|[TXlsImgType](../TXlsImgType.md)||


## Returns

The actual file format in which the file was saved\. It might not be possible to save in the required format, and a different one might be used\.

## See also

* [TUIImage](../TUIImage/index.md)

# TUIImage\.Save\(string, TXlsImgType\)
Saves the image to a file\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TUIImage/index.md">TUIImage</a>.Save(const fname: string; const ImgType: <a href="../TXlsImgType.md">TXlsImgType</a> = TXlsImgType.Unknown): <a href="../TXlsImgType.md">TXlsImgType</a>; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**fname**|string|Name of the file where the image will be saved\.<br />|
|const|**ImgType**|[TXlsImgType](../TXlsImgType.md)|**Optional**: Default value is TXlsImgType.Unknown<br /><br />Image format for the saved image\. If this is unspecified or Unknown, the image will be saved depending on its extension\. If the image type can't be inferred from the filename, it will be saved as png\.<br />|


## Returns

The actual file format in which the file was saved\. It might not be possible to save in the required format, and a different one might be used\.

## See also

* [TUIImage](../TUIImage/index.md)

