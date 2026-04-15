---
uid: TDrawingColor.FromHSL
description: TDrawingColor.FromHSL
---

# TDrawingColor\.FromHSL Method

## Overloads

* [TDrawingColor\.FromHSL\(THSLColor\)](#tdrawingcolorfromhslthslcolor)
* [TDrawingColor\.FromHSL\(THSLColor, TColorTransformArray\)](#tdrawingcolorfromhslthslcolor-tcolortransformarray)

# TDrawingColor\.FromHSL\(THSLColor\)
Returns a color class with a specified HSL color\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TDrawingColor/index.md">TDrawingColor</a>.FromHSL(const aColor: <a href="../THSLColor/index.md">THSLColor</a>): <a href="../TDrawingColor/index.md">TDrawingColor</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aColor**|[THSLColor](../THSLColor/index.md)|Color that we want to set\.|


## Returns

The corresponding system color\.

## See also

* [TDrawingColor](../TDrawingColor/index.md)

# TDrawingColor\.FromHSL\(THSLColor, TColorTransformArray\)
Returns a color class with an specified HSL color\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TDrawingColor/index.md">TDrawingColor</a>.FromHSL(const aColor: <a href="../THSLColor/index.md">THSLColor</a>; const aTransforms: <a href="../TColorTransform/index.md">TArray&lt;TColorTransform></a>): <a href="../TDrawingColor/index.md">TDrawingColor</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aColor**|[THSLColor](../THSLColor/index.md)|Color that we want to set\.|
|const|**aTransforms**|[TArray\<&#8203;TColor&#8203;Transform>](../TColorTransform/index.md)|Transformations you want to apply\.|


## Returns

The corresponding system color\.

## See also

* [TDrawingColor](../TDrawingColor/index.md)

