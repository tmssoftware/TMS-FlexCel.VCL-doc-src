---
uid: TUnsupportedFormulaErrorType
description: TUnsupportedFormulaErrorType
---

# TUnsupportedFormulaErrorType Enumeration

Types of error that might happen while recalculating\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|FormulaTooComplex|0|FlexCel was not able to parse the formula\.<br />|
|MissingFunction|1|There is a function on the formula that is not implemented by FlexCel\.<br />|
|FunctionalityNotImplemented|2|The function is supported, but not with those arguments\.<br />|
|CircularReference|3|There is a circular reference on this cell\.<br />|
|ExternalReference|4|The file in the external reference was not found\.<br />|


