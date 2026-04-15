---
uid: TDrawingColor.FromPreset
description: TDrawingColor.FromPreset
---

# TDrawingColor\.FromPreset Method

## Overloads

* [TDrawingColor\.FromPreset\(TPresetColor\)](#tdrawingcolorfrompresettpresetcolor)
* [TDrawingColor\.FromPreset\(TPresetColor, TColorTransformArray\)](#tdrawingcolorfrompresettpresetcolor-tcolortransformarray)

# TDrawingColor\.FromPreset\(TPresetColor\)
Returns a color class with a specified preset color\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TDrawingColor/index.md">TDrawingColor</a>.FromPreset(const aColor: <a href="../TPresetColor.md">TPresetColor</a>): <a href="../TDrawingColor/index.md">TDrawingColor</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aColor**|[TPresetColor](../TPresetColor.md)|Color that we want to set\.|


## Returns

The corresponding preset color\.

## See also

* [TDrawingColor](../TDrawingColor/index.md)

# TDrawingColor\.FromPreset\(TPresetColor, TColorTransformArray\)
Returns a color class with an specified preset color\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TDrawingColor/index.md">TDrawingColor</a>.FromPreset(const aColor: <a href="../TPresetColor.md">TPresetColor</a>; const aTransforms: <a href="../TColorTransform/index.md">TArray&lt;TColorTransform></a>): <a href="../TDrawingColor/index.md">TDrawingColor</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aColor**|[TPresetColor](../TPresetColor.md)|Color that we want to set\.|
|const|**aTransforms**|[TArray\<&#8203;TColor&#8203;Transform>](../TColorTransform/index.md)|Transformations you want to apply\.|


## Returns

The corresponding preset color\.

## See also

* [TDrawingColor](../TDrawingColor/index.md)

