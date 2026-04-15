---
uid: TUIColor
description: TUIColor
---

# TUIColor Record

Represents a color used to draw in a canvas \(gdi\+, wpf, etc\) in a way that is independent of the drawing framework\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TUIColor = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new color with the ARGB components\.<br />|
|[FromArgb](FromArgb.md)|**Overloaded<br />**  [FromArgb\(Integer\)](FromArgb.md#tuicolorfromargbinteger)<br />  [FromArgb\(Integer, TUIColor\)](FromArgb.md#tuicolorfromargbinteger-tuicolor)<br />  [FromArgb\(Integer, Integer, Integer\)](FromArgb.md#tuicolorfromargbinteger-integer-integer)<br />  [FromArgb\(Integer, Integer, Integer, Integer\)](FromArgb.md#tuicolorfromargbinteger-integer-integer-integer)<br />|
|[ToArgb](ToArgb.md)|Gets the 32 bit ARGB color from this structure\.<br />|
|[Equals](Equals.md)|Returns an empty color\. This color isn't valid\.<br />|
|[Empty](Empty.md)|Returns an empty color\. This color isn't valid\.<br />|


## Operators

|Name|Description|
|---|---|
|[Implicit Conversion](op_Implicit.md)|**Overloaded<br />**  [Implicit conversion from TColor to TUIColor](op_Implicit.md#implicit-conversion-from-tcolor-to-tuicolor)<br />  [Implicit conversion from TAlphaColor to TUIColor](op_Implicit.md#implicit-conversion-from-talphacolor-to-tuicolor)<br />  [Implicit conversion from TUIColor to TColor](op_Implicit.md#implicit-conversion-from-tuicolor-to-tcolor)<br />  [Implicit conversion from TUIColor to TAlphaColor](op_Implicit.md#implicit-conversion-from-tuicolor-to-talphacolor)<br />  [Implicit conversion from Integer to TUIColor](op_Implicit.md#implicit-conversion-from-integer-to-tuicolor)<br />  [Implicit conversion from TUIColor to Integer](op_Implicit.md#implicit-conversion-from-tuicolor-to-integer)<br />  [Implicit conversion from Int64 to TUIColor](op_Implicit.md#implicit-conversion-from-int64-to-tuicolor)<br />  [Implicit conversion from TUIColor to Int64](op_Implicit.md#implicit-conversion-from-tuicolor-to-int64)<br />|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[A](A.md)|Alpha component, between 0 and 255\.<br />|
|[R](R.md)|Red component, between 0 and 255\.<br />|
|[G](G.md)|Green component, between 0 and 255|
|[B](B.md)|Blue component, between 0 and 255|
|[IsEmpty](IsEmpty.md)|Returns true if this color is the same as [Empty](Empty.md)|
|[IsNamedColor](IsNamedColor.md)|This method returns always false, TUIColor doesn't support named colors\.<br />|


