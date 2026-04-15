---
uid: TExcelColor
description: TExcelColor
---

# TExcelColor Record

Represents an Excel color\. Colors in Excel can be defined in four ways: Automatic Colors, Indexed Colors \(for compatibility with Excel 2003 or older\), Palette colors, and RGB colors\. This Structure is immutable, once you create it you cannot change its members\. You need to create a new struct to modify it\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TExcelColor = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[EqualsAutomatic&#8203;IsSame](EqualsAutomaticIsSame.md)|Returns true if both colors are the same, considering all types of automatic as equal\.<br />|
|[GetHashCodeAutomatic&#8203;IsSame](GetHashCodeAutomaticIsSame.md)|Returns a hashcode that is the same for all automatic types\. Designed to be used together with [EqualsAutomatic&#8203;IsSame](EqualsAutomaticIsSame.md)|
|[CompareTo](CompareTo.md)|Returns \-1 if obj is more than color, 0 if both colors are the same, and 1 if obj is less than color\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode of the object\.<br />|
|[Equals](Equals.md)|Returns true if both instances have the same color\.<br />|
|[FromArgb](FromArgb.md)|**Overloaded<br />**  [FromArgb\(Integer\)](FromArgb.md#texcelcolorfromargbinteger)<br />  [FromArgb\(Integer, Double\)](FromArgb.md#texcelcolorfromargbinteger-double)<br />  [FromArgb\(Byte, Byte, Byte\)](FromArgb.md#texcelcolorfromargbbyte-byte-byte)<br />  [FromArgb\(Byte, Byte, Byte, Double\)](FromArgb.md#texcelcolorfromargbbyte-byte-byte-double)<br />|
|[FromIndex](FromIndex.md)|**Overloaded<br />**  [FromIndex\(Integer\)](FromIndex.md#texcelcolorfromindexinteger)<br />  [FromIndex\(Integer, Double\)](FromIndex.md#texcelcolorfromindexinteger-double)<br />|
|[FromTheme](FromTheme.md)|**Overloaded<br />**  [FromTheme\(TThemeColor\)](FromTheme.md#texcelcolorfromthemetthemecolor)<br />  [FromTheme\(TThemeColor, Double\)](FromTheme.md#texcelcolorfromthemetthemecolor-double)<br />|
|[FromAutomatic](FromAutomatic.md)|Returns an standard Automatic color\.<br />|
|[ToColor](ToColor.md)|**Overloaded<br />**  [ToColor\(TCoreExcelFile\)](ToColor.md#texcelcolortocolortcoreexcelfile)<br />  [ToColor\(TCoreExcelFile, TUIColor\)](ToColor.md#texcelcolortocolortcoreexcelfile-tuicolor)<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|
|[LessThan](op_LessThan.md)|Adapts the \< operator so it returns true when the first parameter is smaller than the second\.|
|[GreaterThan](op_GreaterThan.md)|Adapts the > operator so it returns true when the first parameter is bigger than the second\.|
|[Implicit Conversion](op_Implicit.md)|**Overloaded<br />**  [Implicit conversion from TUIColor to TExcelColor](op_Implicit.md#implicit-conversion-from-tuicolor-to-texcelcolor)<br />  [Implicit conversion from TColor to TExcelColor](op_Implicit.md#implicit-conversion-from-tcolor-to-texcelcolor)<br />  [Implicit conversion from TAlphaColor to TExcelColor](op_Implicit.md#implicit-conversion-from-talphacolor-to-texcelcolor)<br />|


## Properties

|Name|Description|
|---|---|
|[ColorType](ColorType.md)|Identifies which kind of color is the one to apply in this structure\.<br />|
|[RGB](RGB.md)|Returns the color when this structure has an RGB color, as a 0xRRGGBB integer\. This property is fully functional with Excel 2007 or newer, older versions will be converted to Indexed color before saving as xls\.<br /><br /><br /><br /><br />**Note:** When reading a color, the value here might not be the final one, since [Tint](Tint.md) is applied to get the final color\. Use  [ToColor\(&#8203;&#8203;TCore&#8203;Excel&#8203;File\)](ToColor.md#texcelcolortocolortcoreexcelfile) method to find out the RGB color stored in this struct\.<br />[...[more]](RGB.md)|
|[AutomaticFillType](AutomaticFillType.md)|Returns the type of automatic color, if this structure contains an automatic color\.<br />|
|[Index](_Index.md)|Returns the color when this structure contains an indexed color \(1 based\)\. This property is for compatibility with xls files \(Excel 2003 or older\), but if you are not changing the color palette, even for older files, it is preferred to use [RGB](RGB.md) or [Theme](Theme.md) instead\.<br /><br /><br />If you try to read the value of this property and [ColorType](ColorType.md) is not the right kind, an Exception will be raised\.<br />|
|[Theme](Theme.md)|Returns the color if it is one of the entries in the theme palette \(1 based\)\.<br /><br /><br />If you try to read the value of this property and [ColorType](ColorType.md) is not the right kind, an Exception will be raised\.<br />|
|[Tint](Tint.md)|Returns the tint value applied to the color\.<br /><br />If tint is supplied, then it is applied to the RGB value of the color to determine the final color applied\.<br /><br />The tint value is stored as a double from \-1\.0 \.\. 1\.0, where \-1\.0 means 100%% darken and 1\.0 means 100%% lighten\. Also, 0\.0 means no change\.<br />|
|[Automatic](Automatic.md)|Returns an standard Automatic color\.<br />|
|[IsAutomatic](IsAutomatic.md)|Returns true if this instance has an automatic color\.<br />|


