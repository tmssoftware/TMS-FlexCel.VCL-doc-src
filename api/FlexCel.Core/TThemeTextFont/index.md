---
uid: TThemeTextFont
description: TThemeTextFont
---

# TThemeTextFont Record

The characteristics that define a font\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TThemeTextFont = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create\(string\)](Create.md#tthemetextfontcreatestring)<br />  [Create\(string, string, TPitchFamily, TFontCharSet\)](Create.md#tthemetextfontcreatestring-string-tpitchfamily-tfontcharset)<br />|
|[TypefaceName](TypefaceName.md)|Returns the actual font name used\. Different from [Typeface](Typeface.md), this property will change the "\+mj" and "\+mn" strings in the actual major and minor fonts\.<br />|
|[CompareTo](CompareTo.md)|Returns \-1, 0 or 1 depending if the objects is smaller, equal or bigger than the other\.<br />|
|[GetHashCode](GetHashCode.md)|Returns a hashcode for the object\.<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|
|[GreaterThan](op_GreaterThan.md)|Adapts the > operator so it returns true when the first parameter is bigger than the second\.|
|[LessThan](op_LessThan.md)|Adapts the \< operator so it returns true when the first parameter is smaller than the second\.|


## Properties

|Name|Description|
|---|---|
|[Typeface](Typeface.md)|Specifies the typeface, or name of the font that is to be used\. The typeface is a string  name of the specific font that should be used in rendering the presentation\. If this font is  not available within the font list of the generating application than font substitution logic  should be utilized in order to select an alternate font\. This string can also be "\+mj\-lt" for the major font, and "\+mn\-lt" for the minor font\. To get the typeface name, use [TypefaceName](TypefaceName.md)|
|[Scheme](Scheme.md)|Returns the scheme for the font, if there is one\.<br />|
|[Panose](Panose.md)|Specifies the Panose\-1 classification number for the current font\.<br />This is a string consisting of 20 hexadecimal digits which defines the Panose\-1 font classification|
|[Pitch](Pitch.md)|Specifies the font pitch as well as the font family for the corresponding font\.<br />|
|[CharSet](CharSet.md)|Specifies the character set which is supported by the parent font\. This information can be used in font substitution logic to locate an appropriate substitute font when this font is not available\. This information is determined by querying the font when present and shall not be modified when the font is not available\.<br />|


