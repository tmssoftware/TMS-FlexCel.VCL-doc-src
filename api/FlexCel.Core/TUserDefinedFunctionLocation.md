---
uid: TUserDefinedFunctionLocation
description: TUserDefinedFunctionLocation
---

# TUserDefinedFunctionLocation Enumeration

Defines where the custom function is located, if inside a macro in the same file, or inside a macro in an external file\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|External|0|The custom function is defined in an external file or addin\. Whenever you add this function to a workbook, references will be created to an external function\.<br />|
|Internal|1|The custom function is defined inside the same file where the formula is\. Whenever you add this function to a workbook, references will be created to a macro in the same file\.<br />|


