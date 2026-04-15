---
uid: TFlxApplyFormat
description: TFlxApplyFormat
---

# TFlxApplyFormat Record

Defines which attributes of a [TFlxFormat](../TFlxFormat/index.md) will be applied for one cell\.
Whatever member is set to false, it will not apply this member property to the cell\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TFlxApplyFormat = record;</code></pre>

## Fields

|Name|Description|
|---|---|
|[FillPattern](FillPattern.md)|Fill pattern\.<br />|
|[Font](Font.md)|Cell Font\.<br />|
|[Borders](Borders.md)|Cell borders\.<br />|


## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|Creates an empty Format class\.<br />|
|[SetAllMembers](SetAllMembers.md)|Sets all members to true or false|
|[Apply](Apply.md)|This method will modify existingFormat with the properties from newFormat that are specified on this class|
|[Clone](Clone.md)|Returns a deep copy of the format\.<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[Format](Format.md)|Format string\.  \(For example, "yyyy\-mm\-dd" for a date format, or "\#\.00" for a numeric 2 decimal format\)<br />This format string is the same you use in Excel under "Custom" format when formatting a cell, and it is documented in Excel documentation\. Under **"Finding out what format string to use in TFlxFormat\.Format"** section in **UsingFlexCelAPI\.pdf** you can find more detailed information on how to create this string\.<br />|
|[HAlignment](HAlignment.md)|Horizontal align on the cell\.<br />|
|[VAlignment](VAlignment.md)|Vertical align on the cell\.<br />|
|[Locked](Locked.md)|Cell is locked\.<br />|
|[Hidden](Hidden.md)|Cell is Hidden\.<br />|
|[ParentStyle](ParentStyle.md)|Parent style\. This is the parent style name and all the properties that are linked to it\.<br />|
|[WrapText](WrapText.md)|Cell wrap\.<br />|
|[ShrinkToFit](ShrinkToFit.md)|Shrink to fit\.<br />|
|[Rotation](Rotation.md)|Text Rotation in degrees\.<br /><br />When this value is from 0 to 90 then this is the rotation degrees in the up direction\.<br /><br />When this value is from 91 to 180 then this is a rotation in the down direction\. 91 means \-1 degree rotation, 92 means \-2 degrees, and so on until 180 which means \-90 degrees\.<br /><br />255 is vertical text\.<br /><br />Other values are invalid\.<br />|
|[Indent](Indent.md)|Indent value\. \(on characters\)|
|[ReadingOrder](ReadingOrder.md)|Reading order\.<br />|
|[Lotus123Prefix](Lotus123Prefix.md)|Lotus 123 compatibility prefixes\.<br />|
|[IsEmpty](IsEmpty.md)|Returns true if the format does not apply any setting\.<br />|
|[HasOnlyBorders](HasOnlyBorders.md)|Returns true if the format definition contains only borders\.<br />|


