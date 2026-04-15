---
uid: TXlsFile.CollapseOutlineNodeCol
description: TXlsFile.CollapseOutlineNodeCol
---

# TXlsFile\.CollapseOutlineNodeCol Method

Use this method to collapse a node of the outline\. If the column is not a node \([TExcelFile.IsOutlineNodeCol](../../FlexCel.Core/TExcelFile/IsOutlineNodeCol.md) is false\) this method does nothing\.
While this method allows a better control of the columns expanded and collapsed, you will normally use [TExcelFile.CollapseOutlineCols\(Integer, TCollapseChildrenMode\)](../../FlexCel.Core/TExcelFile/CollapseOutlineCols.md#texcelfilecollapseoutlinecolsinteger-tcollapsechildrenmode) to collapse or expand all columns in a sheet\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.CollapseOutlineNodeCol(const col: Integer; const collapse: Boolean); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col**|Integer|Column to expand or collapse\. \(1 based\)|
|const|**collapse**|Boolean|If true, the node will be collapsed, else it will be expanded\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

