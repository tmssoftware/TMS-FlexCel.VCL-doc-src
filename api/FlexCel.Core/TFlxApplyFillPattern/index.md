---
uid: TFlxApplyFillPattern
description: TFlxApplyFillPattern
---

# TFlxApplyFillPattern Record

Fill pattern and color for the background of a cell\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TFlxApplyFillPattern = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|Creates the record setting all members to true or false\.<br />|
|[SetAllMembers](SetAllMembers.md)|Sets all members to true or false|
|[Apply](Apply.md)|This method will modify existingFormat with the properties from newFormat that are specified on this class|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[Pattern](Pattern.md)|Fill style\.<br />|
|[FgColor](FgColor.md)|Color for the foreground of the pattern\.<br />|
|[BgColor](BgColor.md)|Color for the background of the pattern\.  If the pattern is solid, has no effect\.<br />|
|[Gradient](Gradient.md)|Defines if to apply a gradient to a cell\. Only valid in Excel 2007 or newer\.<br />|
|[IsEmpty](IsEmpty.md)|Returns true if the format does not apply any setting\.<br />|


