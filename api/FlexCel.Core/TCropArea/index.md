---
uid: TCropArea
description: TCropArea
---

# TCropArea Record

Defines a cropping area for an image\. If the values are not zero, only a part of the image will display on Excel\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TCropArea = record;</code></pre>

## Fields

|Name|Description|
|---|---|
|[CropFromTop](CropFromTop.md)|How much to crop the image, in fractions of 65536 of the total image height\.<br />|
|[CropFromBottom](CropFromBottom.md)|How much to crop the image, in fractions of 65536 of the total image height\.<br />|
|[CropFromLeft](CropFromLeft.md)|How much to crop the image, in fractions of 65536 of the total image width\.<br />|
|[CropFromRight](CropFromRight.md)|How much to crop the image, in fractions of 65536 of the total image width\.<br />|


## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create](Create.md#tcropareacreate)<br />  [Create\(Integer, Integer, Integer, Integer\)](Create.md#tcropareacreateinteger-integer-integer-integer)<br />|
|[Null](Null.md)|Returns a null crop area\.<br />|
|[Clone](Clone.md)|Returns a deep copy of this object|
|[IsEmpty](IsEmpty.md)|Returns true if all the coordinates are 0\.<br />|
|[EqualValues](EqualValues.md)|Returns true if both instances of the objects contain the same values\. Instances might be different, this method will return if their values are equal\. Instances can be null\.<br />|
|[IsNull](IsNull.md)|Returns true if the record doesn't have a defined value\.<br />|
|[HasValue](HasValue.md)|Returns true if the record has a defined value\. This is the inverse of [IsNull](IsNull.md)|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


