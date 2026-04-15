---
uid: TXlsFile.GetTableName
description: TXlsFile.GetTableName
---

# TXlsFile\.GetTableName Method

If there is a table in the cell at \(row, col\) then this method will return the name of the table\. If not it will return an empty string\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetTableName(const sheet: Integer; const row: Integer; const col: Integer): string; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet where to find the table \(1 based\)|
|const|**row**|Integer|Row, 1 based\.|
|const|**col**|Integer|Column, 1 based\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

