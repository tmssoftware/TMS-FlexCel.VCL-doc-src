---
uid: TExcelFile.GetCellValueNumericAndRecalc
description: TExcelFile.GetCellValueNumericAndRecalc
---

# TExcelFile\.GetCellValueNumericAndRecalc Method

This is used internally to get the value of another part of the workbook\.
No checks are made, and we try to recalculate the value before sending it\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetCellValueNumericAndRecalc(const sheet: Integer; const row: Integer; const col: Integer; const cIndex: Integer; const CalcState: TCalcState; const CalcStack: TCalcStack; out CellType: <a href="../TCellValueType.md">TCellValueType</a>; out Err: <a href="../TFlxFormulaErrorValue.md">TFlxFormulaErrorValue</a>): Double; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer||
|const|**row**|Integer||
|const|**col**|Integer||
|const|**cIndex**|Integer||
|const|**CalcState**|TCalcState||
|const|**CalcStack**|TCalcStack||
|out|**CellType**|[TCellValueType](../TCellValueType.md)||
|out|**Err**|[TFlxFormulaError&#8203;Value](../TFlxFormulaErrorValue.md)||


## See also

* [TExcelFile](../TExcelFile/index.md)

