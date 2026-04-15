---
uid: TColorTransform
description: TColorTransform
---

# TColorTransform Record

Specifies a color transformation to be applied to a color\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TColorTransform = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new TColorTransform with the corresponding parameters\.<br />|
|[Equals](Equals.md)|Returns true if both color transforms are the same\.<br />|
|[GetHashCode](GetHashCode.md)|Hashcode for the color transform\.<br />|
|[Transform](Transform.md)|Applies the transform for a given color\.<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[ColorTransformType](ColorTransformType.md)|Type of transformation to be applied\.<br />|
|[Value](Value.md)|Value of the transform\. The meaning of this field depends in the [ColorTransformType](ColorTransformType.md) value\.<br />|


