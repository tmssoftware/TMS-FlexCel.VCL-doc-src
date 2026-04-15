---
uid: TUserDefinedFunctionScope
description: TUserDefinedFunctionScope
---

# TUserDefinedFunctionScope Enumeration

Defines how custom functions are added to the recalculation engine\.
If a function is defined in both Global and Local scope, Local scope will be used\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|Global|0|Function will be added for all instances of FlexCel\. You will normally use this setting only once at the beginning of your application\.<br />|
|Local|1|Functions will be available only for the instance where they were added\. Use this option if you might have different custom functions with the same name in different  spreadsheets, and adding the function globally would clash\. You will normally use this setting when adding the formulas after creating the ExcelFile instances\.<br />|


