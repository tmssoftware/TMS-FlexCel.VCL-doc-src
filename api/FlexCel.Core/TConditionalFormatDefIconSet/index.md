---
uid: TConditionalFormatDefIconSet
description: TConditionalFormatDefIconSet
---

# TConditionalFormatDefIconSet Class

Defines a format of the color scales in a conditional format\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TConditionalFormatDefIconSet = class(<a href="../TConditionalFormatDef/index.md">TConditionalFormatDef</a>);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates an empty instance, where no format applies\.<br />|


## Methods

|Name|Description|
|---|---|
|[CheckIsValid](CheckIsValid.md)|Checks if the format definition is valid\. This check will be applied automatically when you try to add a conditional format to a sheet, so there is no need to call this method directly\. But you can use it to know if a conditional format will be rejected when you try to  add it\.<br />|
|[GetIconCount](GetIconCount.md)|Returns the number of icons for a given iconset\.<br />|
|[Clone](Clone.md)|Returns a deep copy of the object\.<br />|
|[Equals](Equals.md)|Returns true if this object is equal to obj\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode for this object\.<br />|


## Properties

|Name|Description|
|---|---|
|[Values](Values.md)|A list of definitions and colors for the Icon Set\. It must have the same number of values as the count of the icons in the set \- 1\.<br />[...[more]](Values.md)|
|[IconSet](IconSet.md)|The set of icons used in the conditional format\.<br />|
|[Reverse](Reverse.md)|If true the icons will be reversed\.<br />|
|[ShowValues](ShowValues.md)|If false the cell values will not be shown\.<br />|
|[CustomIcons](CustomIcons.md)|Use this property to mix and match icons from different iconsets\. If null, then only the standard icons from the set will be used\.<br />|
|[IsCustom](IsCustom.md)|Returns true if [CustomIcons](CustomIcons.md) is not empty\.<br />|


