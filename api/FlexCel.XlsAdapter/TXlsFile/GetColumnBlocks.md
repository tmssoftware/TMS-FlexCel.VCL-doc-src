---
uid: TXlsFile.GetColumnBlocks
description: TXlsFile.GetColumnBlocks
---

# TXlsFile\.GetColumnBlocks Method

This method returns a list of blocks of column information, grouped by columns that have the same properties\.
Since an xlsx file can have 16384 columns, querying every one of them might be slow\. With this method, if columns from 5 to 16384 are hidden, you will get a single block with firstCol = 5 and lastCol = 16384 that is hidden\. If you used [TExcelFile.GetColHidden](../../FlexCel.Core/TExcelFile/GetColHidden.md) instead you would have to call it 16384 times to get the same information\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetColumnBlocks(const sourceSheet: Integer; const firstCol: Integer; const lastCol: Integer): <a href="../../FlexCel.Core/TColumnBlock/index.md">TArray&lt;TColumnBlock></a>; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sourceSheet**|Integer|Sheet where we want to read the columns\. Pass ActiveSheet if you want to read the current sheet\.|
|const|**firstCol**|Integer|First column of the range where we want to get information\. The first block returned might have a firstCol smaller than this value, if the block actually starts before in the file\.|
|const|**lastCol**|Integer|Last column of the range where we want to get information\. The last block returned might have a lastCol bigger than this value, if the block in the file continues after this column\.|


## Returns

A list of blocks of columns that include all the columns between firstCol and lastCol\. The blocks might include more columns outside the range too, and null columns inside the range will not be returned\. All blocks are sorted in ascending order\.

## See also

* [TXlsFile](../TXlsFile/index.md)

