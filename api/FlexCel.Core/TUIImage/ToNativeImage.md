---
uid: TUIImage.ToNativeImage
description: TUIImage.ToNativeImage
---

# TUIImage\.ToNativeImage Method

## Overloads

* [TUIImage\.ToNativeImage\(Pointer, Double\)](#tuiimagetonativeimagepointer-double)
* [TUIImage\.ToNativeImage\(Double, Double, Pointer, Double\)](#tuiimagetonativeimagedouble-double-pointer-double)

# TUIImage\.ToNativeImage\(Pointer, Double\)
Draws the image into a native bitmap\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TUIImage/index.md">TUIImage</a>.ToNativeImage(const NativeImageHandle: Pointer; const Scale: Double); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**NativeImageHandle**|Pointer|For VCL, this is a Canvas\.Handle\. For Firemonkey, this is a TCanvas object\.<br />|
|const|**Scale**|Double||


## See also

* [TUIImage](../TUIImage/index.md)

# TUIImage\.ToNativeImage\(Double, Double, Pointer, Double\)
Draws the image into a native bitmap\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TUIImage/index.md">TUIImage</a>.ToNativeImage(const x: Double; const y: Double; const NativeImageHandle: Pointer; const Scale: Double); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**x**|Double|X position where the image will be rendered\.|
|const|**y**|Double|Y position where the image will be rendered\.|
|const|**NativeImageHandle**|Pointer|For VCL, this is a Canvas\.Handle\. For Firemonkey, this is a TCanvas object\.<br />|
|const|**Scale**|Double||


## See also

* [TUIImage](../TUIImage/index.md)

