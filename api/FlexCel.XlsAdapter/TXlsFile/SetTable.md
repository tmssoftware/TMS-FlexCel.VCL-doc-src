---
uid: TXlsFile.SetTable
description: TXlsFile.SetTable
---

# TXlsFile\.SetTable Method

Changes an existing table\. The table to change is given by the table name in aTable\.
Note that this method won't change the name of the table\. To do so, you need to call [TExcelFile.RenameTable](../../FlexCel.Core/TExcelFile/RenameTable.md)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetTable(aTable: <a href="../../FlexCel.Core/ITableDefinition/index.md">ITableDefinition</a>); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
||**aTable**|[ITableDefinition](../../FlexCel.Core/ITableDefinition/index.md)|Table to modify\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

