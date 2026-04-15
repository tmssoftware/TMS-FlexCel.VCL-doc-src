---
uid: TExcelFile.CollapseOutlineNodeCol
description: TExcelFile.CollapseOutlineNodeCol
---

# TExcelFile\.CollapseOutlineNodeCol Method

Use this method to collapse a node of the outline\. If the column is not a node \([IsOutlineNodeCol](IsOutlineNodeCol.md) is false\) this method does nothing\.
While this method allows a better control of the columns expanded and collapsed, you will normally use [CollapseOutlineCols\(Integer, TCollapseChildrenMode\)](CollapseOutlineCols.md#texcelfilecollapseoutlinecolsinteger-tcollapsechildrenmode) to collapse or expand all columns in a sheet\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.CollapseOutlineNodeCol(const col: Integer; const collapse: Boolean); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col**|Integer|Column to expand or collapse\. \(1 based\)|
|const|**collapse**|Boolean|If true, the node will be collapsed, else it will be expanded\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

