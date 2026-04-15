---
uid: TUserDefinedFunction.TryGetDoubleList
description: TUserDefinedFunction.TryGetDoubleList
---

# TUserDefinedFunction\.TryGetDoubleList Method

Tries to retrieve a list of double arguments from the parameters, starting at parameter startParam\.
Use this method for functions that accept a range of numeric values as an entry\. \(for example =Sum\(a1:a10\)\)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TUserDefinedFunction/index.md">TUserDefinedFunction</a>.TryGetDoubleList(const Xls: <a href="../TExcelFile/index.md">TExcelFile</a>; const parameters: <a href="../TFormulaValue/index.md">TArray&lt;TFormulaValue></a>; startParam: Integer; endParam: Integer; const agg: <a href="../IUserDefinedFunctionAggregator/index.md">IUserDefinedFunctionAggregator</a>; out Err: <a href="../TFlxFormulaErrorValue.md">TFlxFormulaErrorValue</a>): Boolean;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Xls**|[TExcelFile](../TExcelFile/index.md)|ExcelFile used to read the parameter when it is a cell reference\.|
|const|**parameters**|[TArray\<&#8203;TFormula&#8203;Value>](../TFormulaValue/index.md)|The parameters passed to the function\.|
||**startParam**|Integer|First parameter we want to evaluate\.|
||**endParam**|Integer|Last parameter we want to evaluate\. If \< 0, it will evaluate all parameters from startParam to parameters\.Length|
|const|**agg**|[IUserDefined&#8203;Function&#8203;Aggregator](../IUserDefinedFunctionAggregator/index.md)|A class descending from TUserDefinedFunctionAggregator that will process the values for every entry in the range\.|
|out|**Err**|[TFlxFormulaError&#8203;Value](../TFlxFormulaErrorValue.md)|Value of the error when converting the parameter\. If TryGetDouble returns true \(there was no error\), this value is undefined\.|


## See also

* [TUserDefinedFunction](../TUserDefinedFunction/index.md)

