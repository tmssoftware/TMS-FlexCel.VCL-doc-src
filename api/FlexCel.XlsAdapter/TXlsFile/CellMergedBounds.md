---
uid: TXlsFile.CellMergedBounds
description: TXlsFile.CellMergedBounds
---

# TXlsFile\.CellMergedBounds Method

Merged Range where the cell is\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.CellMergedBounds(const row: Integer; const col: Integer): <a href="../../FlexCel.Core/TXlsCellRange/index.md">TXlsCellRange</a>; override;</code></pre>

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

* [TXlsFile](../TXlsFile/index.md)
* [TExcelFile.MergeCells](../../FlexCel.Core/TExcelFile/MergeCells.md)
* [TExcelFile.UnMergeCells](../../FlexCel.Core/TExcelFile/UnMergeCells.md)
* [TExcelFile.CellMergedListCount](../../FlexCel.Core/TExcelFile/CellMergedListCount.md)
* [TExcelFile.CellMergedList](../../FlexCel.Core/TExcelFile/CellMergedList.md)

