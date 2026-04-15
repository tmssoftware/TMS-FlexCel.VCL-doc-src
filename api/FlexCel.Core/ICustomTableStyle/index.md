---
uid: ICustomTableStyle
description: ICustomTableStyle
---

# ICustomTableStyle Interface

Represents a custom table style\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">ICustomTableStyle = interface(IInterface);</code></pre>

## Methods

|Name|Description|
|---|---|
|[CreateSection](CreateSection.md)|Initializes a section to all empty values\. You need to call this method before setting element values\.<br />IF the section already existed, this method will clear all values on it\.<br />|
|[DeleteSection](DeleteSection.md)|Deletes a section and sets it to nulls\.<br />|
|[Clone](Clone.md)|Returns a deep copy of this object\.<br />|


## Properties

|Name|Description|
|---|---|
|[Name](Name.md)|Name of the custom table style\.<br />|
|[CanBeUsedAsPivot&#8203;Table](CanBeUsedAsPivotTable.md)|If true, then this table style can be used in pivot tables\.<br />|
|[CanBeUsedAsTable](CanBeUsedAsTable.md)|If true, then this table style can be used in normal tables\.<br />|
|[SectionCount](SectionCount.md)|This returns the number of sections possible, and it is the same as the highest value of [TTableStyleType](../TTableStyleType.md)\.<br />Note that many of the sections can be null, meaning there is no format applied to them\.<br />|
|[Item\[const section\]](Itemconst-section.md)|Returns the format for a given section of the table\.<br />If the value is null, this means no format is applied to that section\.<br />|


