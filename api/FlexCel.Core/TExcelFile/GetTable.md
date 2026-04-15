---
uid: TExcelFile.GetTable
description: TExcelFile.GetTable
---

# TExcelFile\.GetTable Method

## Overloads

* [TExcelFile\.GetTable\(string\)](#texcelfilegettablestring)
* [TExcelFile\.GetTable\(Integer\)](#texcelfilegettableinteger)
* [TExcelFile\.GetTable\(string, Boolean\)](#texcelfilegettablestring-boolean)

# TExcelFile\.GetTable\(string\)
Returns the definition for a table in the file\. Note that this method will return any table in the file, not only in the active sheet, as table names are unique in the whole workbook\.
You can find which sheet the table is in with [GetTableSheet](GetTableSheet.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetTable(const tableName: string): <a href="../ITableDefinition/index.md">ITableDefinition</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**tableName**|string|Name of the table\.|


## Returns

Null if the table doesn't exist, or the table definition otherwise\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.GetTable\(Integer\)
Returns the table definition for the table at position tableIndex, for the active sheet\. \(1 based\)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetTable(const tableIndex: Integer): <a href="../ITableDefinition/index.md">ITableDefinition</a>; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**tableIndex**|Integer|Position of the table in the active sheet\. \(1\-based\)|


## Returns

The table definition\. If tableIndex is out of range, then it will throw an Exception\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.GetTable\(string, Boolean\)
Returns the definition for a table in the file\. Note that this method will return any table in the file, not only in the active sheet, as table names are unique in the whole workbook\.
You can find which sheet the table is in with [GetTableSheet](GetTableSheet.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetTable(const tableName: string; const ignoreFormulas: Boolean): <a href="../ITableDefinition/index.md">ITableDefinition</a>; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**tableName**|string|Name of the table\.|
|const|**ignoreFormulas**|Boolean|If true, this method won't return the formulas for the totals and the column\.<br />This parameter allows to get the table a little faster, when you are not interested in the formulas\.|


## Returns

Null if the table doesn't exist, or the table definition otherwise\.

## See also

* [TExcelFile](../TExcelFile/index.md)

