---
uid: IGradientFill
description: IGradientFill
---

# IGradientFill Interface

Shapes are filled with a gradient\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IGradientFill = interface(<a href="../IFillStyle/index.md">IFillStyle</a>);</code></pre>

## Properties

|Name|Description|
|---|---|
|[RotateWithShape](RotateWithShape.md)|Specifies that the fill should rotate with the shape\.<br />|
|[TileRect](TileRect.md)|This element specifies a rectangular region of the shape to which the gradient is applied\.  This region is then  tiled across the remaining area of the shape to complete the fill\.  The tile rectangle is defined by percentage  offsets from the sides of the shape's bounding box\.<br />|
|[Flip](Flip.md)|Specifies the direction\(s\) in which to flip the gradient while tiling\.<br /><br />Normally a gradient fill encompasses the entire bounding box of the shape which  contains the fill\. However, with the tileRect element, it is possible to define a "tile"  rectangle which is smaller than the bounding box\. In this situation, the gradient fill is  encompassed within the tile rectangle, and the tile rectangle is tiled across the bounding box to fill the entire area|
|[GradientStops](GradientStops.md)|The list of gradient stops that specifies the gradient colors and their relative positions in the color band\.<br />|
|[GradientDef](GradientDef.md)|Definition of the gradient\. This can be a TDrawingLinear&#8203;Gradient class or a TDrawingPathGradient class\.<br />|


