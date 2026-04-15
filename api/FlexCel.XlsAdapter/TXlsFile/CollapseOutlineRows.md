---
uid: TXlsFile.CollapseOutlineRows
description: TXlsFile.CollapseOutlineRows
---

# TXlsFile\.CollapseOutlineRows Method

Collapses or expands the row outlines in a sheet to the specified level\. It is equivalent to pressing the  numbers at the top of the outline gutter in Excel\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.CollapseOutlineRows(const level: Integer; const collapseChildren: <a href="../../FlexCel.Core/TCollapseChildrenMode.md">TCollapseChildrenMode</a>; const firstRow: Integer; const lastRow: Integer); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**level**|Integer|Level that we want to show of the outline\. \(1 based\)\.<br />For example, setting Level = 3 is the same as pressing the "3" number at the top of the outline gutter in Excel\.<br />Setting Level = 1 will collapse all groups, Level = 8 will expand all groups\.|
|const|**collapseChildren**|[TCollapseChildren&#8203;Mode](../../FlexCel.Core/TCollapseChildrenMode.md)|Determines if the children of the collapsed nodes will be collapsed too\.|
|const|**firstRow**|Integer|This defines the first row of the range to collapse/expand\. Only rows inside that range will be modified\.|
|const|**lastRow**|Integer|This defines the last row of the range to collapse/expand\. Only rows inside that range will be modified\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

