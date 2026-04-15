---
uid: TExcelFile.SetWhatIfTable
description: TExcelFile.SetWhatIfTable
---

# TExcelFile\.SetWhatIfTable Method

Creates an Excel What\-if table in the range of cells specified by Range\. Calling this method is the same as setting a cell value with a TFormula where TFormula\.Span has more than one cell, and TFormula\.Text is something like "\{=TABLE\(,A4\)\}"\. The parameters for the =TABLE function are rowInputCell and colInputCell, and they look the same a Excel will show them\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetWhatIfTable(const range: <a href="../TXlsCellRange/index.md">TXlsCellRange</a>; const rowInputCell: <a href="../TCellAddress/index.md">TCellAddress</a>; const colInputCell: <a href="../TCellAddress/index.md">TCellAddress</a>); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**range**|[TXlsCellRange](../TXlsCellRange/index.md)|Range for the table\. This is the range of cells that will have "=\{TABLE\(\)\}" formulas\.|
|const|**rowInputCell**|[TCellAddress](../TCellAddress/index.md)|Row input cell for the table\. Make it null if you don't want a row input cell\. If both rowInputCell and colInputCell are null, a table with deleted references will be added\.<br /><br />Note that the sheet here is ignored, What\-if tables need the input cells to be in the same sheet as the table\.|
|const|**colInputCell**|[TCellAddress](../TCellAddress/index.md)|Column input cell for the table\. Make it null if you don't want a column input cell\.  If both rowInputCell and colInputCell are null, a table with deleted references will be added\.<br /><br />Note that the sheet here is ignored, What\-if tables need the input cells to be in the same sheet as the table\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

