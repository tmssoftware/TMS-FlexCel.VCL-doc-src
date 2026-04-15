---
uid: TConditionalFormatDefStandard
description: TConditionalFormatDefStandard
---

# TConditionalFormatDefStandard Class

Defines a format to apply for cells when a rule evaluates to true\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TConditionalFormatDefStandard = class(<a href="../TConditionalFormatDef/index.md">TConditionalFormatDef</a>);</code></pre>

## Fields

|Name|Description|
|---|---|
|[ApplyFont](ApplyFont.md)|Specifies which properties of [TUIFont](../TUIFont/index.md) will be applied in the final format\.<br />|
|[Font](Font.md)|The definition of the font\. Only those properties true in [ApplyFont](ApplyFont.md) will be used\.<br />|
|[ApplyFill](ApplyFill.md)|Specifies which properties of [Fill](Fill.md) will be applied in the final format\.<br />|
|[Fill](Fill.md)|Fill properties that will be applied\. Only those in [ApplyFill](ApplyFill.md) will be used\.<br />|
|[ApplyBorders](ApplyBorders.md)|Defines which borders will be applied to the final format\.<br />|
|[Borders](Borders.md)|Defines the borders\. Only those borders where ApplyBorders is true will be used\.<br />|


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
|[NumericFormat](NumericFormat.md)|Numeric format for the cell, when [ApplyNumericFormat](ApplyNumericFormat.md) is true\.<br />|
|[ApplyNumericFormat](ApplyNumericFormat.md)|When true the format specified in [NumericFormat](NumericFormat.md) will be applied, else it will be ignored\.<br />|
|[HasFontBlock](HasFontBlock.md)|Returns true if any font formatting is applied|
|[HasBorderBlock](HasBorderBlock.md)|Returns true if any border formatting is applied\.<br />|
|[HasFillBlock](HasFillBlock.md)|Returns true if any pattern formatting is applied\.<br />|
|[HasNumericFormat&#8203;Block](HasNumericFormatBlock.md)|Returns true if the numeric format is applied\.<br />|
|[HasFormat](HasFormat.md)|Returns true if any format is applied\.<br />|


