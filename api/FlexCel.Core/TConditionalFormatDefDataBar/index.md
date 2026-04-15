---
uid: TConditionalFormatDefDataBar
description: TConditionalFormatDefDataBar
---

# TConditionalFormatDefDataBar Class

Defines a format of the databars in a conditional format\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TConditionalFormatDefDataBar = class(<a href="../TConditionalFormatDef/index.md">TConditionalFormatDef</a>);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates an empty instance, where no format applies\.<br />|


## Methods

|Name|Description|
|---|---|
|[CheckIsValid](CheckIsValid.md)|Checks if the format definition is valid\. This check will be applied automatically when you try to add a conditional format to a sheet, so there is no need to call this method directly\. But you can use it to know if a conditional format will be rejected when you try to  add it\.<br />|
|[Clone](Clone.md)|Returns a deep copy of the object\.<br />|
|[Equals](Equals.md)|Returns true if this object is equal to obj\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode for this object\.<br />|


## Properties

|Name|Description|
|---|---|
|[MinLengthValue](MinLengthValue.md)|A condition that specifies the value that corresponds with the minimum length of the databar\.<br />|
|[MaxLengthValue](MaxLengthValue.md)|A condition that specifies the value that corresponds with the maximum length of the databar\.<br />|
|[Colors](Colors.md)|Colors that define the databar\.<br />|
|[MinBarWidth](MinBarWidth.md)|The minimum length of the data bar, as a percentage of the cell width\.<br />|
|[MaxBarWidth](MaxBarWidth.md)|The maximum length of the data bar, as a percentage of the cell width\.<br />|
|[ShowValues](ShowValues.md)|If true, we will show the values in the cell where the databar is\.<br />|
|[HasBorders](HasBorders.md)|If true the databar has a border\.<br />|
|[IsGradient](IsGradient.md)|If true the fill will be a gradient, otherwise it will be a solid color\.<br />|
|[Direction](Direction.md)|Direction of the databar\.<br />|
|[IsNegativeBar&#8203;Color&#8203;Same&#8203;AsPositive](IsNegativeBarColorSameAsPositive.md)|If true, the negative bars have the same color as the positives\.<br />|
|[IsNegativeBar&#8203;Border&#8203;Color&#8203;Same&#8203;AsPositive](IsNegativeBarBorderColorSameAsPositive.md)|If true, the borders of the negative bars are the same color as the positives\.<br />|
|[AxisPosition](AxisPosition.md)|Position for the axis\.<br />|


