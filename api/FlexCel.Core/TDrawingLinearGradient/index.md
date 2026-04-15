---
uid: TDrawingLinearGradient
description: TDrawingLinearGradient
---

# TDrawingLinearGradient Class

This class holds a linear gradient definition\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TDrawingLinearGradient = class(<a href="../TDrawingGradientDef/index.md">TDrawingGradientDef</a>);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new Linear gradient definition\.<br />|


## Methods

|Name|Description|
|---|---|
|[Equals](Equals.md)|Returns true if this instance has the same data as the object obj\.<br />|
|[CompareTo](CompareTo.md)|Returns \-1 if obj is bigger than this, 0 if both objects are the same, and 1 if obj is smaller than this\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode for this object|


## Properties

|Name|Description|
|---|---|
|[Angle](Angle.md)|Specifies the direction of color change for the gradient\. To define this angle, let its value  be x measured clockwise\. Then \( \-sin x, cos x \) is a vector parallel to the line of constant  color in the gradient fill\.<br />|
|[Scaled](Scaled.md)|Whether the gradient angle scales with the fill region\. Mathematically, if this flag is true,  then the gradient vector \( cos x , sin x \) is scaled by the width \(w\) and height \(h\) of the fill  region, so that the vector becomes \( w cos x, h sin x \) \(before normalization\)\.<br />|


