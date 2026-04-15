---
uid: TXlsFile.CollapseOutlineNodeRow
description: TXlsFile.CollapseOutlineNodeRow
---

# TXlsFile\.CollapseOutlineNodeRow Method

Use this method to collapse a node of the outline\. If the row is not a node \([TExcelFile.IsOutlineNodeRow](../../FlexCel.Core/TExcelFile/IsOutlineNodeRow.md) is false\) this method does nothing\.
While this method allows a better control of the rows expanded and collapsed, you will normally use [TExcelFile.CollapseOutlineRows\(Integer, TCollapseChildrenMode\)](../../FlexCel.Core/TExcelFile/CollapseOutlineRows.md#texcelfilecollapseoutlinerowsinteger-tcollapsechildrenmode) to collapse or expand all rows in a sheet\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.CollapseOutlineNodeRow(const row: Integer; const collapse: Boolean); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row to expand or collapse \(1 based\)|
|const|**collapse**|Boolean|If true, the node will be collapsed, else it will be expanded\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

