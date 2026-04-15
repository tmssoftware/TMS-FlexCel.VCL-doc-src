---
uid: TExcelFile.GetCellValueAndRecalc
description: TExcelFile.GetCellValueAndRecalc
---

# TExcelFile\.GetCellValueAndRecalc Method

This is used internally to get the value of another part of the workbook\.
No checks are made, and we try to recalculate the value before sending it\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetCellValueAndRecalc(const sheet: Integer; const row: Integer; const col: Integer; const cIndex: Integer; const CalcState: TCalcState; const CalcStack: TCalcStack): <a href="../TCellValue/index.md">TCellValue</a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer||
|const|**row**|Integer||
|const|**col**|Integer||
|const|**cIndex**|Integer||
|const|**CalcState**|TCalcState||
|const|**CalcStack**|TCalcStack||


## See also

* [TExcelFile](../TExcelFile/index.md)

