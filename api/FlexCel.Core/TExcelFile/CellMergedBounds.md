---
uid: TExcelFile.CellMergedBounds
description: TExcelFile.CellMergedBounds
---

# TExcelFile\.CellMergedBounds Method

Merged Range where the cell is\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.CellMergedBounds(const row: Integer; const col: Integer): <a href="../TXlsCellRange/index.md">TXlsCellRange</a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row Index \(1 based\)|
|const|**col**|Integer|Column Index \(1 based\)|


## Returns

The range where the cell is

## Examples

If you have a merged cell in range A1: B2, calling CellMergedBounds on any of the cells: A1, B1, A2, B2 will return A1:B2\.


## See also

* [TExcelFile](../TExcelFile/index.md)
* [MergeCells](MergeCells.md)
* [UnMergeCells](UnMergeCells.md)
* [CellMergedListCount](CellMergedListCount.md)
* [CellMergedList](CellMergedList.md)

