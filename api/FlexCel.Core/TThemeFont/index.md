---
uid: TThemeFont
description: TThemeFont
---

# TThemeFont Class

Represents either a major or a minor font for the theme\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TThemeFont = class(TCoreThemeFont);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create](Create.md#tthemefontcreate)<br />  [Create\(TThemeTextFont, TThemeTextFont, TThemeTextFont\)](Create.md#tthemefontcreatetthemetextfont-tthemetextfont-tthemetextfont)<br />|


## Methods

|Name|Description|
|---|---|
|[AddFont](AddFont.md)|Adds a new font to the font collection\.<br />|
|[GetFont](GetFont.md)|Returns the typeface associated with a script\.<br />|
|[ClearFonts](ClearFonts.md)|Clears all font associations\.<br />|
|[GetFontScripts](GetFontScripts.md)|Returns all scripts that have a current association\. You can use the values in this array as keys for [GetFont](GetFont.md)|
|[Clone](Clone.md)|Returns a deep copy of this object\.<br />|
|[Equals](Equals.md)|Returns true if both objects are the same\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode for the object\.<br />|


## Properties

|Name|Description|
|---|---|
|[Latin](Latin.md)|**NORMALLY THIS IS ALL YOU HAVE TO CHANGE TO CHANGE A TYPEFACE\.** Check with APIMate if unsure\.<br />This element specifies that a Latin font be used for a specific run of text\. This font is specified with a typeface  attribute much like the others but is specifically classified as a Latin font\.<br />|
|[EastAsian](EastAsian.md)|This element specifies that an East Asian font be used for a specific run of text\. This font is specified with a  typeface attribute much like the others but is specifically classified as an East Asian font\.<br />|
|[ComplexScript](ComplexScript.md)|This element specifies that a complex script font be used for a specific run of text\. This font is specified with a  typeface attribute much like the others but is specifically classified as a complex script font\.<br />|


