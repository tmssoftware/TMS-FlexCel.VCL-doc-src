---
uid: TXlsFile.GetWhatIfTable
description: TXlsFile.GetWhatIfTable
---

# TXlsFile\.GetWhatIfTable Method

Returns the range of cells that make the what\-if table that starts at aRow and aCol\.
If there is no What\-if table at aRow, aCol, this method returns null\.

If both the returned rowInputCell and colInputCell are null, this means this table points to deleted references\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetWhatIfTable(const sheet: Integer; const row: Integer; const col: Integer; out rowInputCell: <a href="../../FlexCel.Core/TCellAddress/index.md">TCellAddress</a>; out colInputCell: <a href="../../FlexCel.Core/TCellAddress/index.md">TCellAddress</a>): <a href="../../FlexCel.Core/TXlsCellRange/index.md">TXlsCellRange</a>; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet where the table is\.|
|const|**row**|Integer|First cell from where we want to get a what\-if table\.|
|const|**col**|Integer|First cell from where we want to get a what\-if table\.|
|out|**rowInputCell**|[TCellAddress](../../FlexCel.Core/TCellAddress/index.md)|Returns the row input cell for this table\. If the table doesn't have a row input cell, this value is null\.|
|out|**colInputCell**|[TCellAddress](../../FlexCel.Core/TCellAddress/index.md)|Returns the column input cell for this table\. If the table doesn't have a column input cell, this value is null\.|


## Returns

The full range of the table, not including the formula headers\. Only the cells where \{=Table\(\)\} formulas are\.\.

## See also

* [TXlsFile](../TXlsFile/index.md)

