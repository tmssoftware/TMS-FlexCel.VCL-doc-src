---
uid: TExcelFile.CollapseOutlineNodeRow
description: TExcelFile.CollapseOutlineNodeRow
---

# TExcelFile\.CollapseOutlineNodeRow Method

Use this method to collapse a node of the outline\. If the row is not a node \([IsOutlineNodeRow](IsOutlineNodeRow.md) is false\) this method does nothing\.
While this method allows a better control of the rows expanded and collapsed, you will normally use [CollapseOutlineRows\(Integer, TCollapseChildrenMode\)](CollapseOutlineRows.md#texcelfilecollapseoutlinerowsinteger-tcollapsechildrenmode) to collapse or expand all rows in a sheet\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.CollapseOutlineNodeRow(const row: Integer; const collapse: Boolean); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row to expand or collapse \(1 based\)|
|const|**collapse**|Boolean|If true, the node will be collapsed, else it will be expanded\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

