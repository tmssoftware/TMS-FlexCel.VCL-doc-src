---
uid: ITableDefinition.ColumnFromName
description: ITableDefinition.ColumnFromName
---

# ITableDefinition\.ColumnFromName Method

Returns the column definition for a given column name\. If tableXls is null, then this method will return the stored column name\. If not null and the table has headers, this method will try to get the column name from the cell value of the table headers in the Excel file\.

If the column name doesn't exist, this method will return  a TTableColumnDefinition\(null, \-1\);

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../ITableDefinition/index.md">ITableDefinition</a>.ColumnFromName(const columnName: string; const tableXls: TCoreExcelFile; const tableSheet: Integer): <a href="../TTableColumnDefinition/index.md">TTableColumnDefinition</a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**columnName**|string|Column name which we want to find\.|
|const|**tableXls**|TCoreExcelFile|ExcelFile which contains the table\. It can be null, and in this case the stored value of the header will be used\. If not null, we will read the actual cell value in the file for the header, and return that\.|
|const|**tableSheet**|Integer|Sheet where the table is inside tableXls \(1 based\)\.|


## See also

* [ITableDefinition](../ITableDefinition/index.md)

