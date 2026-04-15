---
uid: TXlsFile.GetTable
description: TXlsFile.GetTable
---

# TXlsFile\.GetTable Method

## Overloads

* [TXlsFile\.GetTable\(Integer\)](#txlsfilegettableinteger)
* [TXlsFile\.GetTable\(string, Boolean\)](#txlsfilegettablestring-boolean)

# TXlsFile\.GetTable\(Integer\)
Returns the table definition for the table at position tableIndex, for the active sheet\. \(1 based\)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetTable(const tableIndex: Integer): <a href="../../FlexCel.Core/ITableDefinition/index.md">ITableDefinition</a>; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**tableIndex**|Integer|Position of the table in the active sheet\. \(1\-based\)|


## Returns

The table definition\. If tableIndex is out of range, then it will throw an Exception\.

## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.GetTable\(string, Boolean\)
Returns the definition for a table in the file\. Note that this method will return any table in the file, not only in the active sheet, as table names are unique in the whole workbook\.
You can find which sheet the table is in with [TExcelFile.GetTableSheet](../../FlexCel.Core/TExcelFile/GetTableSheet.md)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetTable(const tableName: string; const ignoreFormulas: Boolean): <a href="../../FlexCel.Core/ITableDefinition/index.md">ITableDefinition</a>; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**tableName**|string|Name of the table\.|
|const|**ignoreFormulas**|Boolean|If true, this method won't return the formulas for the totals and the column\.<br />This parameter allows to get the table a little faster, when you are not interested in the formulas\.|


## Returns

Null if the table doesn't exist, or the table definition otherwise\.

## See also

* [TXlsFile](../TXlsFile/index.md)

