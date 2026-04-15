---
uid: THSLColor
description: THSLColor
---

# THSLColor Record

Implements a simple representation of a color in Hue/Saturation/Lum colorspace\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">THSLColor = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create\(TUIColor\)](Create.md#thslcolorcreatetuicolor)<br />  [Create\(TColor\)](Create.md#thslcolorcreatetcolor)<br />  [Create\(Double, Double, Double\)](Create.md#thslcolorcreatedouble-double-double)<br />|
|[ToColor](ToColor.md)|Returns a system color from this instance\. This method is only needed in C\+\+, in Delphi you can just assign the HslColor to the Color:[...[more]](ToColor.md)|
|[ApplyTint](ApplyTint.md)|This method returns the brightness that results from applying tint to brightness\.<br />|
|[GetTint](GetTint.md)|Returns the tint needed to go from originalBrightness to newBrightness\.<br />A tint of 0 means no change \(OriginalBrightness == NewBrightness\), a tint of \-1 means NewBrightness = 0, and a tint of 1 means NewBrightness = 1\. So this method just does a simple interpolation to find out the needed tint\.<br /><br /><br /><br /><br />This method is the inverse of [ApplyTint](ApplyTint.md)|
|[DistanceSquared](DistanceSquared.md)|Returns the distance between 2 colors\. Not that this is not the euclidean distance, but a distance calculated to improve Hue matching\.<br />When converting cell colors, we try to preserve hues, so even a very pale red cell will be converted to bright red and not white or a very pale blue\.<br />This make it different from standard color matching as is done when adjusting images to a color palette, and where hue is not as important as here\.<br />|
|[Equals](Equals.md)|Returns true if both colors are the same\.<br />|
|[GetHashCode](GetHashCode.md)|Returns a hashcode for the color\.<br />|
|[CompareTo](CompareTo.md)|Returns \-1 if obj is more than color, 0 if both colors are the same, and 1 if obj is less than color\.<br />|


## Operators

|Name|Description|
|---|---|
|[Implicit Conversion](op_Implicit.md)|**Overloaded<br />**  [Implicit conversion from TUIColor to THSLColor](op_Implicit.md#implicit-conversion-from-tuicolor-to-thslcolor)<br />  [Implicit conversion from THSLColor to TUIColor](op_Implicit.md#implicit-conversion-from-thslcolor-to-tuicolor)<br />  [Implicit conversion from TColor to THSLColor](op_Implicit.md#implicit-conversion-from-tcolor-to-thslcolor)<br />  [Implicit conversion from THSLColor to TColor](op_Implicit.md#implicit-conversion-from-thslcolor-to-tcolor)<br />|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|
|[GreaterThan](op_GreaterThan.md)|Adapts the > operator so it returns true when the first parameter is bigger than the second\.|
|[LessThan](op_LessThan.md)|Adapts the \< operator so it returns true when the first parameter is smaller than the second\.|


## Properties

|Name|Description|
|---|---|
|[Hue](Hue.md)|Color hue\. \(between 0 and 360\)|
|[Sat](Sat.md)|Color Saturation\. \(between 0 and 1\)|
|[Lum](Lum.md)|Color brightness\. \(between 0 and 1\)|
|[R](R.md)|Red component in the RGB space\.<br />|
|[G](G.md)|Green component in the RGB space\.<br />|
|[B](B.md)|Blue component in the RGB space\.<br />|
|[Empty](Empty.md)|Returns an empty color\.<br />|


