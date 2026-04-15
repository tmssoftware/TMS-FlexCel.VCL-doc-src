---
uid: TUserDefinedFunction.TryGetDate
description: TUserDefinedFunction.TryGetDate
---

# TUserDefinedFunction\.TryGetDate Method

Tries to retrieve a date/time from a parameter, and return it if it can be converted or an error if not\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TUserDefinedFunction/index.md">TUserDefinedFunction</a>.TryGetDate(const xls: <a href="../TExcelFile/index.md">TExcelFile</a>; const param: <a href="../TFormulaValue/index.md">TFormulaValue</a>; const SuppressTime: Boolean; out ResultValue: TDateTime; out ResultError: <a href="../TFlxFormulaErrorValue.md">TFlxFormulaErrorValue</a>): Boolean; static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**xls**|[TExcelFile](../TExcelFile/index.md)|ExcelFile used to read the parameter when it is a cell reference\.|
|const|**param**|[TFormulaValue](../TFormulaValue/index.md)|One of the parameters passed to [Evaluate](Evaluate.md)|
|const|**SuppressTime**|Boolean|If true, the date returned will have the time set to 0:00 no matter the real value\.|
|out|**ResultValue**|TDateTime|Value of the parameter as double\. If TryGetDate returns false, this value is undefined\.|
|out|**ResultError**|[TFlxFormulaError&#8203;Value](../TFlxFormulaErrorValue.md)|Value of the error when converting the parameter\. If TryGetDate returns true \(there was no error\), this value is undefined\.|


## Returns

True if the parameter can be converted to a datetime, false if there was an error\.

## See also

* [TUserDefinedFunction](../TUserDefinedFunction/index.md)

