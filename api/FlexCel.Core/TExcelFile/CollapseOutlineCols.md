---
uid: TExcelFile.CollapseOutlineCols
description: TExcelFile.CollapseOutlineCols
---

# TExcelFile\.CollapseOutlineCols Method

## Overloads

* [TExcelFile\.CollapseOutlineCols\(Integer, TCollapseChildrenMode\)](#texcelfilecollapseoutlinecolsinteger-tcollapsechildrenmode)
* [TExcelFile\.CollapseOutlineCols\(Integer, TCollapseChildrenMode, Integer, Integer\)](#texcelfilecollapseoutlinecolsinteger-tcollapsechildrenmode-integer-integer)

# TExcelFile\.CollapseOutlineCols\(Integer, TCollapseChildrenMode\)
Collapses or expands the column outlines in a sheet to the specified level\. It is equivalent to pressing the  numbers at the left of the outline gutter in Excel\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.CollapseOutlineCols(const level: Integer; const collapseChildren: <a href="../TCollapseChildrenMode.md">TCollapseChildrenMode</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**level**|Integer|Level that we want to display from the outline\. \(1 based\)\.<br />For example, setting Level = 3 is the same as pressing the "3" number at the left of the outline gutter in Excel\.<br />Setting Level = 1 will collapse all groups, Level = 8 will expand all groups\.|
|const|**collapseChildren**|[TCollapseChildren&#8203;Mode](../TCollapseChildrenMode.md)|Determines if the children of the collapsed nodes will be collapsed too\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.CollapseOutlineCols\(Integer, TCollapseChildrenMode, Integer, Integer\)
Collapses or expands the column outlines in a sheet to the specified level\. It is equivalent to pressing the  numbers at the top of the outline gutter in Excel\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.CollapseOutlineCols(const level: Integer; const collapseChildren: <a href="../TCollapseChildrenMode.md">TCollapseChildrenMode</a>; const firstCol: Integer; const lastCol: Integer); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**level**|Integer|Level that we want to display from the outline\. \(1 based\)\.<br />For example, setting Level = 3 is the same as pressing the "3" number at the left of the outline gutter in Excel\.<br />Setting Level = 1 will collapse all groups, Level = 8 will expand all groups\.|
|const|**collapseChildren**|[TCollapseChildren&#8203;Mode](../TCollapseChildrenMode.md)|Determines if the children of the collapsed nodes will be collapsed too\.|
|const|**firstCol**|Integer|This defines the first column of the range to collapse/expand\. Only columns inside that range will be modified\.|
|const|**lastCol**|Integer|This defines the last column of the range to collapse/expand\. Only columns inside that range will be modified\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

