---
uid: TConditionalFormat
description: TConditionalFormat
---

# TConditionalFormat Record

This class encapsulates a list of conditional formats for a range of cells\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TConditionalFormat = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new conditional format\.<br />|
|[CheckIsValid](CheckIsValid.md)|Checks if the format is valid\. This check will be applied automatically when you try to add a conditional format to a sheet, so there is no need to call this method directly\. But you can use it to know if a conditional format will be rejected when you try to  add it\.<br />|
|[Equals](Equals.md)|Returns true if both conditional formats are the same\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode of the object|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[Rules](Rules.md)|List of rules that will be applied to the cells\.<br />|
|[Ranges](Ranges.md)|List of cell ranges where this conditional format applies\.<br />|
|[IsPivot](IsPivot.md)|If true, then this is a conditional format for a pivot table\.<br />|


