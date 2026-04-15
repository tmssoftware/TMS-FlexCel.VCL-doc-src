---
uid: TUserDefinedFunction.TryGetBoolean
description: TUserDefinedFunction.TryGetBoolean
---

# TUserDefinedFunction\.TryGetBoolean Method

Tries to retrieve a boolean from a parameter, and return it if it can be converted or an error if not\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TUserDefinedFunction/index.md">TUserDefinedFunction</a>.TryGetBoolean(const xls: <a href="../TExcelFile/index.md">TExcelFile</a>; const param: <a href="../TFormulaValue/index.md">TFormulaValue</a>; out ResultValue: Boolean; out ResultError: <a href="../TFlxFormulaErrorValue.md">TFlxFormulaErrorValue</a>): Boolean; static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**xls**|[TExcelFile](../TExcelFile/index.md)|ExcelFile used to read the parameter when it is a cell reference\.|
|const|**param**|[TFormulaValue](../TFormulaValue/index.md)|One of the parameters passed to [Evaluate](Evaluate.md)|
|out|**ResultValue**|Boolean|Value of the parameter as a boolean\. If TryGetBoolean returns false, this value is undefined\.|
|out|**ResultError**|[TFlxFormulaError&#8203;Value](../TFlxFormulaErrorValue.md)|Value of the error when converting the parameter\. If TryGetBoolean returns true \(there was no error\), this value is undefined\.|


## Returns

True if the parameter can be converted to a boolean, false if there was an error\.

## See also

* [TUserDefinedFunction](../TUserDefinedFunction/index.md)

