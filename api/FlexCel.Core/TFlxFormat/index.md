---
uid: TFlxFormat
description: TFlxFormat
---

# TFlxFormat Record

Format for one cell or named style\.
Cell formats are used to format cells, Named styles to create styles\. A Cell format can have a parent style format, even when normally this is null \(parent is normal format\)\.
Named styles will have a non\-null Style property\. Cell formats will have style = null\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TFlxFormat = record;</code></pre>

## Fields

|Name|Description|
|---|---|
|[FillPattern](FillPattern.md)|Fill pattern\.<br />|
|[IsStyle](IsStyle.md)|When true this format is a named style, when false a cell format\.<br />|
|[Font](Font.md)|Cell Font\.<br />|
|[Borders](Borders.md)|Cell borders\.<br />|
|[Format](Format.md)|Format string\.  \(For example, "yyyy\-mm\-dd" for a date format, or "\#\.00" for a numeric 2 decimal format\)<br />This format string is the same you use in Excel under "Custom" format when formatting a cell, and it is documented in Excel documentation\. Under **"Finding out what format string to use in TFlxFormat\.Format"** section in **UsingFlexCelAPI\.pdf** you can find more detailed information on how to create this string\.<br />|
|[HAlignment](HAlignment.md)|Horizontal alignment on the cell\.<br />|
|[VAlignment](VAlignment.md)|Vertical alignment on the cell\.<br />|
|[Locked](Locked.md)|Cell is locked\.<br />|
|[Hidden](Hidden.md)|Cell is Hidden\.<br />|
|[WrapText](WrapText.md)|Cell wrap\.<br />|
|[ShrinkToFit](ShrinkToFit.md)|Shrink to fit\.<br />|
|[Rotation](Rotation.md)|Text Rotation in degrees\.<br /><br />When this value is from 0 to 90 then this is the rotation degrees in the up direction\.<br /><br />When this value is from 91 to 180 then this is a rotation in the down direction\. 91 means \-1 degree rotation, 92 means \-2 degrees, and so on until 180 which means \-90 degrees\.<br /><br />255 is vertical text\.<br /><br />Other values are invalid\.<br />|
|[Indent](Indent.md)|Indent value\. \(in characters\)\. This value can't be bigger than 15 in Excel 2003 or earlier, and no bigger than 250 in Excel 2007 or newer\.<br />|
|[Lotus123Prefix](Lotus123Prefix.md)|If true the prefix for the cell is compatible with Lotus 123\.<br />|
|[ParentStyle](ParentStyle.md)|Name of the Parent style\. Normally you will want to keep it at null \(parent is normal style\), but you can write an existing style here\.<br />If [IsStyle](IsStyle.md) is true this property is not used\.<br />|
|[LinkedStyle](LinkedStyle.md)|If this object holds a Cell format, LinkedStyle specifies which properties of the cell format are linked to its parent style\.<br />If this object holds a Style format, LinkedStyle specifies the default set of properties that will be applied when you use this style from Excel\.<br />|
|[ReadingOrder](ReadingOrder.md)|Reading order for the cell\.<br />|


## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|Creates an empty Format class\. Don't use this to get TFlxFormat instances, use XlsFile\.&#8203;Get&#8203;Default&#8203;Format instead\.<br />|
|[Null](Null.md)|Creates an invalid Format class\.<br />|
|[CreateStandard2007](CreateStandard2007.md)|Returns a standard TFlxFormat for Excel 2007\. \(Font name is Calibri, etc\)\. You will normally want to use [TExcelFile.&#8203;Get&#8203;Default&#8203;Format](../TExcelFile/GetDefaultFormat.md) instead of this, since it returns the default format for an specific file, and not a generic format like this\.<br />|
|[Clone](Clone.md)|Returns a deep copy of the format\.<br />|
|[Equals](Equals.md)|Returns true if 2 instances have the same values\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode of the object\.<br />|
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
|[NotNullParentStyle](NotNullParentStyle.md)|This is similar to [ParentStyle](ParentStyle.md) but will return "Normal" when the parent is null\.<br />|
|[WillWrap](WillWrap.md)|Returns true if the text will wrap in the cell\. This might be because [WrapText](WrapText.md) is true, of because the alignment is justify or distributed\.<br />|


