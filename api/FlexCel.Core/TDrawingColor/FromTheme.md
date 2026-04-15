---
uid: TDrawingColor.FromTheme
description: TDrawingColor.FromTheme
---

# TDrawingColor\.FromTheme Method

## Overloads

* [TDrawingColor\.FromTheme\(TThemeColor\)](#tdrawingcolorfromthemetthemecolor)
* [TDrawingColor\.FromTheme\(TThemeColor, TColorTransformArray\)](#tdrawingcolorfromthemetthemecolor-tcolortransformarray)

# TDrawingColor\.FromTheme\(TThemeColor\)
Returns a color class with a specified themed color\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TDrawingColor/index.md">TDrawingColor</a>.FromTheme(const aColor: <a href="../TThemeColor.md">TThemeColor</a>): <a href="../TDrawingColor/index.md">TDrawingColor</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aColor**|[TThemeColor](../TThemeColor.md)|Color that we want to set\.|


## Returns

The corresponding system color\.

## See also

* [TDrawingColor](../TDrawingColor/index.md)

# TDrawingColor\.FromTheme\(TThemeColor, TColorTransformArray\)
Returns a color class with an specified themed color\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TDrawingColor/index.md">TDrawingColor</a>.FromTheme(const aColor: <a href="../TThemeColor.md">TThemeColor</a>; const aTransforms: <a href="../TColorTransform/index.md">TArray&lt;TColorTransform></a>): <a href="../TDrawingColor/index.md">TDrawingColor</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aColor**|[TThemeColor](../TThemeColor.md)|Color that we want to set\.|
|const|**aTransforms**|[TArray\<&#8203;TColor&#8203;Transform>](../TColorTransform/index.md)|Transformations you want to apply\.|


## Returns

The corresponding system color\.

## See also

* [TDrawingColor](../TDrawingColor/index.md)

