---
uid: TFlxFont
description: TFlxFont
---

# TFlxFont Record

Encapsulation of an Excel Font\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TFlxFont = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create](Create.md#tflxfontcreate)<br />  [Create\(string, Integer\)](Create.md#tflxfontcreatestring-integer)<br />|
|[Null](Null.md)|Returns a font without defined value\.<br />|
|[CopyTo](CopyTo.md)|Copies this font information to other font object\.<br />|
|[Equals](Equals.md)|Returns true if a font has is the same as the current\.<br />|
|[GetHashCode](GetHashCode.md)|Hash code of the font\.<br />|
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
|[Name](Name.md)|Font name\. \(For example, "Arial"\)\. **Important:** When using Excel 2007, if [Scheme](Scheme.md) is different from "None", the font scheme takes precedence over the name\. If for example Name = "Arial" but Scheme is Major and the major font is Calibri, the font will use Calibri\.<br />|
|[Size20](Size20.md)|Height of the font \(in units of 1/20th of a point\)\. A Size20 = 200 means 10 points\.<br />|
|[Color](Color.md)|Color of the font\.<br />|
|[Style](Style.md)|Style of the font, such as bold or italics\. Underline is a different option\.<br />|
|[Underline](Underline.md)|Underline type\.<br />|
|[Family](Family.md)|Font family, \(see Windows API LOGFONT structure\)\.<br />|
|[CharSet](CharSet.md)|Character set\. \(see Windows API LOGFONT structure\)|
|[Scheme](Scheme.md)|Font scheme\. This only applies to Excel 2007\. Note that this property takes over other properties like font name: If the scheme is for example "Major" and the theme has a Major font defined as calibri, then the font will be Calibri no matter if you change the font name\.<br /><br />To manually change the font name, make sure to set `Scheme = TFontScheme.None`|


