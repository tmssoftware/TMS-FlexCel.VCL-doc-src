---
uid: TLabColor
description: TLabColor
---

# TLabColor Record

Implements a simple representation of a color in CIE\-L\*a\*b\* colorspace\. This colorspace is mostly used for finding distances between colors\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TLabColor = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create\(TUIColor\)](Create.md#tlabcolorcreatetuicolor)<br />  [Create\(TColor\)](Create.md#tlabcolorcreatetcolor)<br />|
|[ToColor](ToColor.md)|Returns a system color from this instance\. This method is only needed in C\+\+, in Delphi you can just assign the LabColor to the Color:[...[more]](ToColor.md)|
|[DistanceSquared](DistanceSquared.md)|Returns the euclidean distance squared \(DeltaE CIE 1976 squared\) between this color and other color\.<br />|
|[CMCSquared](CMCSquared.md)|Returns the CMC color distance between this color and color2 \(distance returned is squared, so you need to get the sqrt if you want the real CMC value\)\. Note that CMC is not symmetric \(&#8203;Color1\.&#8203;CMC\(&#8203;Color2\) \!= Color2\.&#8203;CMC\(&#8203;Color1\)&#8203;, so this color is the one used as reference\.<br />|
|[Equals](Equals.md)|Returns true if both colors are the same\.<br />|
|[GetHashCode](GetHashCode.md)|Returns a hashcode for the color\.<br />|
|[CompareTo](CompareTo.md)|Returns \-1 if obj is more than color, 0 if both colors are the same, and 1 if obj is less than color\.<br />|


## Operators

|Name|Description|
|---|---|
|[Implicit Conversion](op_Implicit.md)|**Overloaded<br />**  [Implicit conversion from TUIColor to TLabColor](op_Implicit.md#implicit-conversion-from-tuicolor-to-tlabcolor)<br />  [Implicit conversion from TLabColor to TUIColor](op_Implicit.md#implicit-conversion-from-tlabcolor-to-tuicolor)<br />  [Implicit conversion from TColor to TLabColor](op_Implicit.md#implicit-conversion-from-tcolor-to-tlabcolor)<br />  [Implicit conversion from TLabColor to TColor](op_Implicit.md#implicit-conversion-from-tlabcolor-to-tcolor)<br />|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|
|[GreaterThan](op_GreaterThan.md)|Adapts the > operator so it returns true when the first parameter is bigger than the second\.|
|[LessThan](op_LessThan.md)|Adapts the \< operator so it returns true when the first parameter is smaller than the second\.|


## Properties

|Name|Description|
|---|---|
|[L0](L0.md)|L\* \(Lightness\) \(Between 0 and 100\)|
|[a0](a0.md)|a\* component\.<br />|
|[b0](b0.md)|b\* component\.<br />|
|[R](R.md)|Red component in the RGB space\.<br />|
|[G](G.md)|Green component in the RGB space\.<br />|
|[B](B.md)|Blue component in the RGB space\.<br />|


