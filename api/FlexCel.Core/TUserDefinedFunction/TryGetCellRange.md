---
uid: TUserDefinedFunction.TryGetCellRange
description: TUserDefinedFunction.TryGetCellRange
---

# TUserDefinedFunction\.TryGetCellRange Method

Tries to retrieve a cell range from a parameter, and return it if it can be converted or an error if not\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TUserDefinedFunction/index.md">TUserDefinedFunction</a>.TryGetCellRange(const param: <a href="../TFormulaValue/index.md">TFormulaValue</a>; out ResultValue: <a href="../TXls3DRange/index.md">TXls3DRange</a>; out ResultError: <a href="../TFlxFormulaErrorValue.md">TFlxFormulaErrorValue</a>): Boolean; static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**param**|[TFormulaValue](../TFormulaValue/index.md)|One of the parameters passed to [Evaluate](Evaluate.md)|
|out|**ResultValue**|[TXls3DRange](../TXls3DRange/index.md)|Value of the parameter as a TXls3DRange\. If TryGetRange returns false, this value is undefined\.|
|out|**ResultError**|[TFlxFormulaError&#8203;Value](../TFlxFormulaErrorValue.md)|Value of the error when converting the parameter\. If TryGetCellRange returns true \(there was no error\), this value is undefined\.|


## Returns

True if the parameter can be converted to a cell range, false if there was an error\.

## See also

* [TUserDefinedFunction](../TUserDefinedFunction/index.md)

