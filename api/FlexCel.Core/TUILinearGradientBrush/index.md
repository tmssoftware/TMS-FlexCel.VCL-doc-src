---
uid: TUILinearGradientBrush
description: TUILinearGradientBrush
---

# TUILinearGradientBrush Class

Represents a platform independent linear gradient\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TUILinearGradientBrush = class(<a href="../TUIBrush/index.md">TUIBrush</a>);</code></pre>

## Methods

|Name|Description|
|---|---|
|[CalculateTransform&#8203;Elements](CalculateTransformElements.md)|Calculates the transform elements given a rotation and a rectangle, for platforms that can't calculate it\.<br />|
|[CreateNew](CreateNew.md)|This method will return the appropriate Brush depending in the Graphics framework you are using to render images\.<br />|
|[CalcRotatedCoords](CalcRotatedCoords.md)|Returns the rotated coordinates for the gradient, needed to define in platforms like PDF or OSX\.<br />|
|[InvertBlend](InvertBlend.md)|Inverts the colors of the gradient\.<br />|


## Properties

|Name|Description|
|---|---|
|[Rectangle](Rectangle.md)|Rectangle that defines the gradient\.<br />|
|[TransformElements](TransformElements.md)|Transform matrix\.<br />|
|[InterpolationColors](InterpolationColors.md)|Colors that define the gradient\.<br />|


