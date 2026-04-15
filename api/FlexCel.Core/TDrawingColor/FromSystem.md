---
uid: TDrawingColor.FromSystem
description: TDrawingColor.FromSystem
---

# TDrawingColor\.FromSystem Method

## Overloads

* [TDrawingColor\.FromSystem\(TSystemColor\)](#tdrawingcolorfromsystemtsystemcolor)
* [TDrawingColor\.FromSystem\(TSystemColor, TColorTransformArray\)](#tdrawingcolorfromsystemtsystemcolor-tcolortransformarray)

# TDrawingColor\.FromSystem\(TSystemColor\)
Returns a color class with a specified system color\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TDrawingColor/index.md">TDrawingColor</a>.FromSystem(const aColor: <a href="../TSystemColor.md">TSystemColor</a>): <a href="../TDrawingColor/index.md">TDrawingColor</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aColor**|[TSystemColor](../TSystemColor.md)|Color that we want to set\.|


## Returns

The corresponding system color\.

## See also

* [TDrawingColor](../TDrawingColor/index.md)

# TDrawingColor\.FromSystem\(TSystemColor, TColorTransformArray\)
Returns a color class with a specified system color\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TDrawingColor/index.md">TDrawingColor</a>.FromSystem(const aColor: <a href="../TSystemColor.md">TSystemColor</a>; const aTransforms: <a href="../TColorTransform/index.md">TArray&lt;TColorTransform></a>): <a href="../TDrawingColor/index.md">TDrawingColor</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aColor**|[TSystemColor](../TSystemColor.md)|Color that we want to set\.|
|const|**aTransforms**|[TArray\<&#8203;TColor&#8203;Transform>](../TColorTransform/index.md)|Transformations you want to apply\.|


## Returns

The corresponding system color\.

## See also

* [TDrawingColor](../TDrawingColor/index.md)

