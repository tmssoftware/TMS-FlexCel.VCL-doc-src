---
uid: TExcelFile.SetTable
description: TExcelFile.SetTable
---

# TExcelFile\.SetTable Method

Changes an existing table\. The table to change is given by the table name in aTable\.
Note that this method won't change the name of the table\. To do so, you need to call [RenameTable](RenameTable.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetTable(aTable: <a href="../ITableDefinition/index.md">ITableDefinition</a>); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
||**aTable**|[ITableDefinition](../ITableDefinition/index.md)|Table to modify\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

