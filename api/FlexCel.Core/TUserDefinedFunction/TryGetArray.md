---
uid: TUserDefinedFunction.TryGetArray
description: TUserDefinedFunction.TryGetArray
---

# TUserDefinedFunction\.TryGetArray Method

Tries to retrieve an array from a parameter, and return it if it can be converted or an error if not\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TUserDefinedFunction/index.md">TUserDefinedFunction</a>.TryGetArray(const xls: <a href="../TExcelFile/index.md">TExcelFile</a>; const param: <a href="../TFormulaValue/index.md">TFormulaValue</a>; out ResultValue: <a href="../TFormulaValue/index.md">TArray&lt;TArray&lt;TFormulaValue>></a>; out ResultError: <a href="../TFlxFormulaErrorValue.md">TFlxFormulaErrorValue</a>): Boolean; static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**xls**|[TExcelFile](../TExcelFile/index.md)|ExcelFile used to read the parameter when it is a cell reference\.|
|const|**param**|[TFormulaValue](../TFormulaValue/index.md)|One of the parameters passed to [Evaluate](Evaluate.md)|
|out|**ResultValue**|[TArray\<&#8203;TArray\<&#8203;TFormula&#8203;Value>&#8203;>](../TFormulaValue/index.md)|Value of the parameter as an array\. If TryGetArray returns false, this value is undefined\.|
|out|**ResultError**|[TFlxFormulaError&#8203;Value](../TFlxFormulaErrorValue.md)|Value of the error when converting the parameter\. If TryGetArray returns true \(there was no error\), this value is undefined\.|


## Returns

True if the parameter can be converted to an array, false if there was an error\.

## See also

* [TUserDefinedFunction](../TUserDefinedFunction/index.md)

