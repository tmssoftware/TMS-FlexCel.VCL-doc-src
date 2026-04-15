---
uid: IBlipFill
description: IBlipFill
---

# IBlipFill Interface

Shapes are filled with an image\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IBlipFill = interface(<a href="../IFillStyle/index.md">IFillStyle</a>);</code></pre>

## Properties

|Name|Description|
|---|---|
|[Dpi](Dpi.md)|Specifies the DPI \(dots per inch\) used to calculate the size of the blip\. If not present or zero, the DPI in the blip is used\.<br />|
|[RotateWithShape](RotateWithShape.md)|Specifies that the fill should rotate with the shape\.<br />|
|[Blip](Blip.md)|Picture and properties used in the Blip fill\.<br />|
|[SourceRect](SourceRect.md)|This element specifies the portion of the blip used for the fill\.<br />Each edge of the source rectangle is defined by a percentage offset from the corresponding edge of the  bounding box\.  A positive percentage specifies an inset, while a negative percentage specifies an outset\.<br />For example, a left offset of 25%% specifies that the left edge of the source rectangle is located to the right of the  bounding box's left edge by an amount equal to 25%% of the bounding box's width\.<br />|
|[FillMode](FillMode.md)|Specifies how the blip will be applied to the fill, either by stretching it to cover all the surface, of by tiling it\.<br />|


