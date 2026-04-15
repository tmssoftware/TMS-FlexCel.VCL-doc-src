---
uid: TExcelFile.GetTableAtCell
description: TExcelFile.GetTableAtCell
---

# TExcelFile\.GetTableAtCell Method

If there is a table in the cell at \(row, col\) then this method will return the table definition\. If not it will return null\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetTableAtCell(const sheet: Integer; const row: Integer; const col: Integer): <a href="../ITableDefinition/index.md">ITableDefinition</a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet where to find the table \(1 based\)|
|const|**row**|Integer|Row, 1 based\.|
|const|**col**|Integer|Column, 1 based\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

