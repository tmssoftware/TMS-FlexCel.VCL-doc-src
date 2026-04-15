---
uid: TGradientStop
description: TGradientStop
---

# TGradientStop Record

Represents one of the points in a Gradient definition for an Excel cell\. Note that drawings \(autoshapes, charts, etc\) use a different Gradient definition: [TDrawingGradientStop](../TDrawingGradientStop/index.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TGradientStop = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new Gradient stop\.<br />|
|[CompareTo](CompareTo.md)|Compares 2 instances of this struct\.<br />|
|[Equals](Equals.md)|Returns if this struct has the same values as other one\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode for this struct\.<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|
|[GreaterThan](op_GreaterThan.md)|Adapts the > operator so it returns true when the first parameter is bigger than the second\.|
|[LessThan](op_LessThan.md)|Adapts the \< operator so it returns true when the first parameter is smaller than the second\.|


## Properties

|Name|Description|
|---|---|
|[Position](Position.md)|This value must be between 0 and 1, and represents the position in the gradient where the [Color](Color.md) in this structure is pure\.<br />|
|[Color](Color.md)|Color for this definition\.<br />|


