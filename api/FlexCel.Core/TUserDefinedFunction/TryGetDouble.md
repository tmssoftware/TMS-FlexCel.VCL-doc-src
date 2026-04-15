---
uid: TUserDefinedFunction.TryGetDouble
description: TUserDefinedFunction.TryGetDouble
---

# TUserDefinedFunction\.TryGetDouble Method

Tries to retrieve a double from a parameter, and return it if it can be converted or an error if not\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TUserDefinedFunction/index.md">TUserDefinedFunction</a>.TryGetDouble(const xls: <a href="../TExcelFile/index.md">TExcelFile</a>; const param: <a href="../TFormulaValue/index.md">TFormulaValue</a>; out ResultValue: Double; out ResultError: <a href="../TFlxFormulaErrorValue.md">TFlxFormulaErrorValue</a>): Boolean; static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**xls**|[TExcelFile](../TExcelFile/index.md)|ExcelFile used to read the parameter when it is a cell reference\.|
|const|**param**|[TFormulaValue](../TFormulaValue/index.md)|One of the parameters passed to [Evaluate](Evaluate.md)|
|out|**ResultValue**|Double|Value of the parameter as double\. If TryGetDouble returns false, this value is undefined\.|
|out|**ResultError**|[TFlxFormulaError&#8203;Value](../TFlxFormulaErrorValue.md)|Value of the error when converting the parameter\. If TryGetDouble returns true \(there was no error\), this value is undefined\.|


## Returns

True if the parameter can be converted to a double, false if there was an error\.

## See also

* [TUserDefinedFunction](../TUserDefinedFunction/index.md)

