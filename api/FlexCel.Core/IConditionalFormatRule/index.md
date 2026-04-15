---
uid: IConditionalFormatRule
description: IConditionalFormatRule
---

# IConditionalFormatRule Interface

A rule specifying a conditional format\. You cannot create instances of this class, only of their children\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IConditionalFormatRule = interface(IInterface);</code></pre>

## Methods

|Name|Description|
|---|---|
|[Clone](Clone.md)|Returns a deep copy of the object\.<br />|
|[CheckIsValid](CheckIsValid.md)|Checks if the rule is valid\. This check will be applied automatically when you try to add a conditional format to a sheet, so there is no need to call this method directly\. But you can use it to know if a conditional format will be rejected when you try to  add it\.<br />|


## Properties

|Name|Description|
|---|---|
|[Kind](Kind.md)|Defines which kind of conditional rule this object contains\. FormatDef will contain a subclass that must match the kind here\.<br />|
|[Priority](Priority.md)|Priority for the rule\. 1 means the highest priority and higher number mean that the rule will be evaluated later\.<br />Note that priorities of all conditional rules **must be unique on the sheet**\. If you specify a duplicated priority, all other priorities might be shifted when you save the file so they keep being unique\.<br />|
|[StopIfTrue](StopIfTrue.md)|When true, rules after this one will not evaluate if this one applies\. Only Applies to Excel 2007 or newer, and it doesn't apply to DataBars, IconSets or ColorScales\.<br />|


