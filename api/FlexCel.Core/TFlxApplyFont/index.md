---
uid: TFlxApplyFont
description: TFlxApplyFont
---

# TFlxApplyFont Record

Encapsulation of an Excel Font\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TFlxApplyFont = record;</code></pre>

## Fields

|Name|Description|
|---|---|
|[Name](Name.md)|Font name\. \(For example, "Arial"\)|
|[Size20](Size20.md)|Height of the font \(in units of 1/20th of a point\)\. A Size20=200 means 10 points\.<br />|
|[Color](Color.md)|Color of the font\.<br />|
|[StyleEx](StyleEx.md)|Allows to control which styles are applied one by one, different from [Style](Style.md) which applies all the styles at once\.<br />Setting [Style](Style.md) will change all the StyleEx at once\.<br />|
|[Underline](Underline.md)|Underline type\.<br />|
|[Family](Family.md)|Font family, \(see Windows API LOGFONT structure\)\.<br />|
|[CharSet](CharSet.md)|Character set\. \(see Windows API LOGFONT structure\)|
|[Scheme](Scheme.md)|Scheme of the font, when using themes\. \(Excel 2007\)\.<br />|


## Methods

|Name|Description|
|---|---|
|[HasStyleBold&#8203;AndItalic](HasStyleBoldAndItalic.md)|Returns true if this struct applies either italic or bold styles\. This is the same as checking if StyleEx contains bold or italic\.<br />|
|[HasStyleSubSuperscript](HasStyleSubSuperscript.md)|Returns true if this struct applies either subscript or superscript styles\. This is the same as checking if StyleEx contains subscript or superscript\.<br />|
|[SetAllMembers](SetAllMembers.md)|Sets all members to true or false|
|[Apply](Apply.md)|This method will modify existingFormat with the properties from newFormat that are specified on this class|
|[Clone](Clone.md)|Returns a deep copy of the font\.<br />|
|[Equals](Equals.md)|Returns true if both objects are the same\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hash code of the object\.<br />|
|[HasStyleStrikeout](HasStyleStrikeout.md)|Returns true if this struct applies a strikeout\. This is the same as checking if StyleEx contains Strikeout\.<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[Style](Style.md)|Style of the font, such as bold or italics\. Underline is a different option\.<br />Note that when true this applies the full style, and sets all values of [StyleEx](StyleEx.md) to true\. [StyleEx](StyleEx.md) can be used for more fine control over what styles are applied\.<br />|
|[IsEmpty](IsEmpty.md)|Returns true if the format definition does not apply any setting\.<br />|


