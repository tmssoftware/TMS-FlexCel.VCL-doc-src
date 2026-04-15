---
uid: TExcelFile.UnMergeCells
description: TExcelFile.UnMergeCells
---

# TExcelFile\.UnMergeCells Method

Unmerges the range of cells\. The coordinates have to be exact, if there is no merged cell with the exact coordinates, nothing will be done\. If you want to unmerge all cells inside a range, use [UnMergeAllCellsInRange](UnMergeAllCellsInRange.md) instead\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.UnMergeCells(const firstRow: Integer; const firstCol: Integer; const lastRow: Integer; const lastCol: Integer); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**firstRow**|Integer|First row of the merged cell\.|
|const|**firstCol**|Integer|First column of the merged cell\.|
|const|**lastRow**|Integer|Last row of the merged cell\.|
|const|**lastCol**|Integer|Last column of the merged cell\.|


## See also

* [TExcelFile](../TExcelFile/index.md)
* [CellMergedBounds](CellMergedBounds.md)
* [MergeCells](MergeCells.md)
* [CellMergedListCount](CellMergedListCount.md)
* [CellMergedList](CellMergedList.md)

