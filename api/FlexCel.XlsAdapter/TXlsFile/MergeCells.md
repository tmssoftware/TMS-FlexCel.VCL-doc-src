---
uid: TXlsFile.MergeCells
description: TXlsFile.MergeCells
---

# TXlsFile\.MergeCells Method

Merges a number of cells into one\.


## Remarks

This method might return a bigger range than the one you specify\.
For example, if you have a merged cell \(A1:C1\), calling MergeCells\(1,2,2,2\) will  merge the cell with the existing one, returning ONE merged cell \(A1:C2\), and not \(B1:B2\)



Other thing to consider, is that Excel honors individual linestyles inside a merged cell\.
That is, you can have only the first 2 columns of the merged cell with a line and the others without\.
Normally, after merging the cells, you will want to call [TExcelFile.SetCellFormat\(Integer, Integer, Integer\)](../../FlexCel.Core/TExcelFile/SetCellFormat.md#texcelfilesetcellformatinteger-integer-integer) on the range to make them all similar\. FlexCel does not do it by default, to give the choice to you\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.MergeCells(const firstRow: Integer; const firstCol: Integer; const lastRow: Integer; const lastCol: Integer); override;</code></pre>

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
* [TExcelFile.UnMergeCells](../../FlexCel.Core/TExcelFile/UnMergeCells.md)
* [TExcelFile.CellMergedListCount](../../FlexCel.Core/TExcelFile/CellMergedListCount.md)
* [TExcelFile.CellMergedList](../../FlexCel.Core/TExcelFile/CellMergedList.md)

