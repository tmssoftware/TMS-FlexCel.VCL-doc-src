---
uid: ITableDefinition.ColumnFromId
description: ITableDefinition.ColumnFromId
---

# ITableDefinition\.ColumnFromId Method

Returns the column definition for an id, or returns a column with Id = \-1 and name empty if the id doesn't exist\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../ITableDefinition/index.md">ITableDefinition</a>.ColumnFromId(const aId: Integer; const xls: TCoreExcelFile; const tableSheet: Integer): <a href="../TTableColumnDefinition/index.md">TTableColumnDefinition</a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aId**|Integer|Id for the column\.|
|const|**xls**|TCoreExcelFile|Excel file where the table is\. you can set it to null to retrieve the actual value stored in the column\.<br />If not null, this method will try to get the actual name in the cell and return that as the column name\.|
|const|**tableSheet**|Integer|Sheet where the table is\.\(1 based\)|


## See also

* [ITableDefinition](../ITableDefinition/index.md)

