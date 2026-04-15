---
uid: TUITextureBrush.CreateNew
description: TUITextureBrush.CreateNew
---

# TUITextureBrush\.CreateNew Method

## Overloads

* [TUITextureBrush\.CreateNew\(TUIImage\)](#tuitexturebrushcreatenewtuiimage)
* [TUITextureBrush\.CreateNew\(TUIImage, TArray\<Double>, TArray\<Double>\)](#tuitexturebrushcreatenewtuiimage-tarraydouble-tarraydouble)

# TUITextureBrush\.CreateNew\(TUIImage\)
This method will return the appropriate Brush depending in the Graphics framework you are using to render images\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TUITextureBrush/index.md">TUITextureBrush</a>.CreateNew(const img: <a href="../TUIImage/index.md">TUIImage</a>): <a href="../TUITextureBrush/index.md">TUITextureBrush</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**img**|[TUIImage](../TUIImage/index.md)|Image for the brush\.|


## See also

* [TUITextureBrush](../TUITextureBrush/index.md)

# TUITextureBrush\.CreateNew\(TUIImage, TArray\<Double>, TArray\<Double>\)
This method will return the appropriate Brush depending in the Graphics framework you are using to render images\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TUITextureBrush/index.md">TUITextureBrush</a>.CreateNew(const img: <a href="../TUIImage/index.md">TUIImage</a>; const atm: TArray&lt;Double&gt;; const canvasMatrix: TArray&lt;Double&gt;): <a href="../TUITextureBrush/index.md">TUITextureBrush</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**img**|[TUIImage](../TUIImage/index.md)|Image for the brush\.|
|const|**atm**|TArray\<Double>|Transform Matrix for the pattern\.|
|const|**canvasMatrix**|TArray\<Double>|Transform matrix for the graphics context\.|


## See also

* [TUITextureBrush](../TUITextureBrush/index.md)

