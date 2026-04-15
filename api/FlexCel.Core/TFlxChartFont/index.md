---
uid: TFlxChartFont
description: TFlxChartFont
---

# TFlxChartFont Record

A TFlxFont with Scaling factor\. Scaling factor might be different than 1 if the chart has Autosize Fonts\. To get the real value of the font, you need to multiply by the factor\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TFlxChartFont = record;</code></pre>

## Fields

|Name|Description|
|---|---|
|[Font](Font.md)|Actual information for the font\.<br />|


## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create](Create.md#tflxchartfontcreate)<br />  [Create\(TFlxFont\)](Create.md#tflxchartfontcreatetflxfont)<br />  [Create\(string, Integer\)](Create.md#tflxchartfontcreatestring-integer)<br />  [Create\(string, Integer, Boolean\)](Create.md#tflxchartfontcreatestring-integer-boolean)<br />  [Create\(string, Integer, TExcelColor, TFlxFontStyleSet, TFlxUnderline, TFontScheme\)](Create.md#tflxchartfontcreatestring-integer-texcelcolor-tflxfontstyleset-tflxunderline-tfontscheme)<br />|
|[Null](Null.md)|Constructs a null instance\.<br />|
|[Clone](Clone.md)|Return a deep copy of the copy\.<br />|
|[IsNull](IsNull.md)|Returns true if the record doesn't have a defined value\.<br />|
|[HasValue](HasValue.md)|Returns true if the record has a defined value\. This is the inverse of [IsNull](IsNull.md)|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[Scale](Scale.md)|Scale for the font\. Multiply by this value to get the real size in points\.<br />|
|[IsCalculated](IsCalculated.md)|If true, this font was calculated from defaults, and didn't had a real value in the file\.<br />If the font is calculated, then you shouldn't set it when setting a font\.<br />|


