---
uid: TBlipFillTile
description: TBlipFillTile
---

# TBlipFillTile Class

This element specifies that a BLIP should be tiled to fill the available space\.  This element defines a "tile"  rectangle within the bounding box\.  The image is encompassed within the tile rectangle, and the tile rectangle is  tiled across the bounding box to fill the entire area\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TBlipFillTile = class(<a href="../TBlipFillMode/index.md">TBlipFillMode</a>);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new Blip fill tile instance\.<br />|


## Methods

|Name|Description|
|---|---|
|[Equals](Equals.md)|Returns true if this instance has the same data as the object obj\.<br />|
|[CompareTo](CompareTo.md)|Returns \-1 if obj is bigger than this, 0 if both objects are the same, and 1 if obj is smaller than this\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode for this object|
|[Clone](Clone.md)|Return a deep copy of the object\.<br />|


## Properties

|Name|Description|
|---|---|
|[Align](Align.md)|Specifies where to align the first tile with respect to the shape\.  Alignment happens after the scaling, but before the additional offset\.<br />|
|[Flip](Flip.md)|Specifies the direction\(s\) in which to flip the source image while tiling\.  Images can be flipped horizontally, vertically, or in both directions to fill the entire region\.<br />|
|[Tx](Tx.md)|Specifies an extra horizontal offset after alignment\.<br />|
|[Ty](Ty.md)|Specifies an extra vertical offset after alignment\.<br />|
|[ScaleX](ScaleX.md)|Indicates the amount to horizontally scale the source rectangle\.<br />|
|[ScaleY](ScaleY.md)|Indicates the amount to vertically scale the source rectangle\.<br />|


