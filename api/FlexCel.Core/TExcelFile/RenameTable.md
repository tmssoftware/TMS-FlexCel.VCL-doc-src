---
uid: TExcelFile.RenameTable
description: TExcelFile.RenameTable
---

# TExcelFile\.RenameTable Method

Renames an existing table to a new name, renaming also all references to that table\. Note that the final name of the table might not be the name you specified in newName, if newName already existed\. You need to check the result of this method to know the actual name which the table was renamed to\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.RenameTable(const existingName: string; const newName: string): string; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**existingName**|string|Existing name of the table\.|
|const|**newName**|string|New name of the table\.|


## Returns

The actual new name of the table\. It might be different from newName if newName already existed in the file\.

## See also

* [TExcelFile](../TExcelFile/index.md)

