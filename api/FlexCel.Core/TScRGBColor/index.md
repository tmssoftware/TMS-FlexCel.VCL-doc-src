---
uid: TScRGBColor
description: TScRGBColor
---

# TScRGBColor Record

Implements a simple representation of a color in scRGB colorspace\. Components are doubles going from 0 to 1\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TScRGBColor = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create\(TUIColor\)](Create.md#tscrgbcolorcreatetuicolor)<br />  [Create\(TColor\)](Create.md#tscrgbcolorcreatetcolor)<br />  [Create\(Double, Double, Double\)](Create.md#tscrgbcolorcreatedouble-double-double)<br />|
|[RGBtoSRGB](RGBtoSRGB.md)|Converts a RGB value to sRGB using a gamma of 2\.2|
|[SRGBtoRGB](SRGBtoRGB.md)|Converts a sRGB value to RGB using a gamma of 2\.2|
|[Equals](Equals.md)|Returns true if both colors are the same\.<br />|
|[GetHashCode](GetHashCode.md)|Returns a hashcode for the color\.<br />|
|[CompareTo](CompareTo.md)|Returns \-1 if obj is more than color, 0 if both colors are the same, and 1 if obj is less than color\.<br />|


## Operators

|Name|Description|
|---|---|
|[Implicit Conversion](op_Implicit.md)|**Overloaded<br />**  [Implicit conversion from TUIColor to TScRGBColor](op_Implicit.md#implicit-conversion-from-tuicolor-to-tscrgbcolor)<br />  [Implicit conversion from TScRGBColor to TUIColor](op_Implicit.md#implicit-conversion-from-tscrgbcolor-to-tuicolor)<br />  [Implicit conversion from TColor to TScRGBColor](op_Implicit.md#implicit-conversion-from-tcolor-to-tscrgbcolor)<br />  [Implicit conversion from TScRGBColor to TColor](op_Implicit.md#implicit-conversion-from-tscrgbcolor-to-tcolor)<br />|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|
|[GreaterThan](op_GreaterThan.md)|Adapts the > operator so it returns true when the first parameter is bigger than the second\.|
|[LessThan](op_LessThan.md)|Adapts the \< operator so it returns true when the first parameter is smaller than the second\.|


## Properties

|Name|Description|
|---|---|
|[ScR](ScR.md)|ScRed component\. \(between 0 and 1\)|
|[ScG](ScG.md)|ScGreen component\. \(between 0 and 1\)|
|[ScB](ScB.md)|ScBlue component\. \(between 0 and 1\)|
|[R](R.md)|Red component in the RGB space\. \(0\-255\)|
|[G](G.md)|Green component in the RGB space\. \(0\-255\)|
|[B](B.md)|Blue component in the RGB space\. \(0\-255\)|
|[Empty](Empty.md)|Returns an empty color\.<br />|


