---
uid: TDrawingColor.FromScRgb
description: TDrawingColor.FromScRgb
---

# TDrawingColor\.FromScRgb Method

## Overloads

* [TDrawingColor\.FromScRgb\(TScRGBColor\)](#tdrawingcolorfromscrgbtscrgbcolor)
* [TDrawingColor\.FromScRgb\(TScRGBColor, TColorTransformArray\)](#tdrawingcolorfromscrgbtscrgbcolor-tcolortransformarray)

# TDrawingColor\.FromScRgb\(TScRGBColor\)
Returns a color class with a specified scRGB color\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TDrawingColor/index.md">TDrawingColor</a>.FromScRgb(const aColor: <a href="../TScRGBColor/index.md">TScRGBColor</a>): <a href="../TDrawingColor/index.md">TDrawingColor</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aColor**|[TScRGBColor](../TScRGBColor/index.md)|Color that we want to set\.|


## Returns

The corresponding system color\.

## See also

* [TDrawingColor](../TDrawingColor/index.md)

# TDrawingColor\.FromScRgb\(TScRGBColor, TColorTransformArray\)
Returns a color class with an specified scRGB color\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TDrawingColor/index.md">TDrawingColor</a>.FromScRgb(const aColor: <a href="../TScRGBColor/index.md">TScRGBColor</a>; const aTransforms: <a href="../TColorTransform/index.md">TArray&lt;TColorTransform></a>): <a href="../TDrawingColor/index.md">TDrawingColor</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aColor**|[TScRGBColor](../TScRGBColor/index.md)|Color that we want to set\.|
|const|**aTransforms**|[TArray\<&#8203;TColor&#8203;Transform>](../TColorTransform/index.md)|Transformations you want to apply\.|


## Returns

The corresponding system color\.

## See also

* [TDrawingColor](../TDrawingColor/index.md)

