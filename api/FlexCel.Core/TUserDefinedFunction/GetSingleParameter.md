---
uid: TUserDefinedFunction.GetSingleParameter
description: TUserDefinedFunction.GetSingleParameter
---

# TUserDefinedFunction\.GetSingleParameter Method

Returns a single value from a parameter\.
If the parameter is a cell range and the cell range has only one cell, this method will return the value of the cell, else it will return an error\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TUserDefinedFunction/index.md">TUserDefinedFunction</a>.GetSingleParameter(const xls: <a href="../TExcelFile/index.md">TExcelFile</a>; const param: <a href="../TFormulaValue/index.md">TFormulaValue</a>): <a href="../TFormulaValue/index.md">TFormulaValue</a>; static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**xls**|[TExcelFile](../TExcelFile/index.md)|ExcelFile that will be used to read the value if param is a cell reference\.|
|const|**param**|[TFormulaValue](../TFormulaValue/index.md)|One of the parameters passed to [Evaluate](Evaluate.md)|


## See also

* [TUserDefinedFunction](../TUserDefinedFunction/index.md)

