---
uid: TXlsFile.UnMergeCells
description: TXlsFile.UnMergeCells
---

# TXlsFile\.UnMergeCells Method

Unmerges the range of cells\. The coordinates have to be exact, if there is no merged cell with the exact coordinates, nothing will be done\. If you want to unmerge all cells inside a range, use [TExcelFile.UnMergeAllCellsInRange](../../FlexCel.Core/TExcelFile/UnMergeAllCellsInRange.md) instead\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.UnMergeCells(const firstRow: Integer; const firstCol: Integer; const lastRow: Integer; const lastCol: Integer); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**firstRow**|Integer|First row of the merged cell\.|
|const|**firstCol**|Integer|First column of the merged cell\.|
|const|**lastRow**|Integer|Last row of the merged cell\.|
|const|**lastCol**|Integer|Last column of the merged cell\.|


## See also

* [TXlsFile](../TXlsFile/index.md)
* [TExcelFile.CellMergedBounds](../../FlexCel.Core/TExcelFile/CellMergedBounds.md)
* [TExcelFile.MergeCells](../../FlexCel.Core/TExcelFile/MergeCells.md)
* [TExcelFile.CellMergedListCount](../../FlexCel.Core/TExcelFile/CellMergedListCount.md)
* [TExcelFile.CellMergedList](../../FlexCel.Core/TExcelFile/CellMergedList.md)

