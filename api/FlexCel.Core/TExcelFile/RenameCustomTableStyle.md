---
uid: TExcelFile.RenameCustomTableStyle
description: TExcelFile.RenameCustomTableStyle
---

# TExcelFile\.RenameCustomTableStyle Method

Renames an existing custom table style\. Note that this method won't change the table styles from existing tables from oldName to newName\. So after renaming a table style, you should loop in all the tables in the workbook which use that table style, and manually rename their custom table styles too\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.RenameCustomTableStyle(const oldName: string; const newName: string); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**oldName**|string|Existing table style\. If the old table style name doesn't exist, this method will raise an exception\.|
|const|**newName**|string|New name for the table style\. If the new table style already exists, this method will raise an exception\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

