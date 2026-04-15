---
uid: TPdfWriter.DrawImage
description: TPdfWriter.DrawImage
---

# TPdfWriter\.DrawImage Method

## Overloads

* [TPdfWriter\.DrawImage\(TUIImage, TUIRectangle, TStream\)](#tpdfwriterdrawimagetuiimage-tuirectangle-tstream)
* [TPdfWriter\.DrawImage\(TUIImage, TUIRectangle, TStream, Int64, Boolean\)](#tpdfwriterdrawimagetuiimage-tuirectangle-tstream-int64-boolean)

# TPdfWriter\.DrawImage\(TUIImage, TUIRectangle, TStream\)
Draws an image on the canvas\. Image can be any type, but all except jpeg will be converted to PNG\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TPdfWriter/index.md">TPdfWriter</a>.DrawImage(const image: <a href="../../FlexCel.Core/TUIImage/index.md">TUIImage</a>; const rect: <a href="../../FlexCel.Core/TUIRectangle/index.md">TUIRectangle</a>; const imageData: TStream); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**image**|[TUIImage](../../FlexCel.Core/TUIImage/index.md)|Image to insert\. If it is not JPEG or PNG, it will be converted to PNG\.|
|const|**rect**|[TUIRectangle](../../FlexCel.Core/TUIRectangle/index.md)|Rectangle where the image will be\.|
|const|**imageData**|TStream|Stream with the raw image data\. Not required, might be null\.|


## See also

* [TPdfWriter](../TPdfWriter/index.md)

# TPdfWriter\.DrawImage\(TUIImage, TUIRectangle, TStream, Int64, Boolean\)
Draws an image on the canvas\. Image can be any type, but all except jpeg will be converted to PNG\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TPdfWriter/index.md">TPdfWriter</a>.DrawImage(const image: <a href="../../FlexCel.Core/TUIImage/index.md">TUIImage</a>; const rect: <a href="../../FlexCel.Core/TUIRectangle/index.md">TUIRectangle</a>; const imageData: TStream; const transparentColor: Int64; const defaultToJpg: Boolean); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**image**|[TUIImage](../../FlexCel.Core/TUIImage/index.md)|Image to insert\. If it is not JPEG or PNG, it will be converted to PNG\.|
|const|**rect**|[TUIRectangle](../../FlexCel.Core/TUIRectangle/index.md)|Rectangle where the image will be\.|
|const|**imageData**|TStream|Stream with the raw image data\. Not required, might be null\.|
|const|**transparentColor**|Int64|Color to make transparent\. To specify no transparent color use [TFlxConsts.NoTransparentColor](../../FlexCel.Core/TFlxConsts/NoTransparentColor.md)|
|const|**defaultToJpg**|Boolean|When true and the image is not on a supported format \(or imageData==null\) the image will be converted to JPG\. If false, the image will be converted to PNG\.|


## See also

* [TPdfWriter](../TPdfWriter/index.md)

