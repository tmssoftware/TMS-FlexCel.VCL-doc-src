---
uid: TXlsFile.UnMergeAllCellsInRange
description: TXlsFile.UnMergeAllCellsInRange
---

# TXlsFile\.UnMergeAllCellsInRange Method

This method will unmerge all the cells that are inside a range of cells\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.UnMergeAllCellsInRange(const firstRow: Integer; const firstCol: Integer; const lastRow: Integer; const lastCol: Integer; const fullyInside: Boolean); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**firstRow**|Integer|First row of the range\.|
|const|**firstCol**|Integer|First column of the range\.|
|const|**lastRow**|Integer|Last row of the range\.|
|const|**lastCol**|Integer|Last column of the range\.|
|const|**fullyInside**|Boolean|If true, the merged cells have to be completely inside the range to be deleted\.<br />For example, if the file has a merged cell A1:A5, and you call UnMergeAllCellsInRange\(1, 1, 1, 1, true\) A1:A5 won't be unmerged because it isn't completely inside the range\. If false, all merged cells that have at least one cell inside the range will be deleted\. In the example with the merged cell A1:A5, UnMergeAllCellsInRange\(1, 1, 1, 1, false\) would remove the merged cell, because it has the cell A1 inside the range\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

