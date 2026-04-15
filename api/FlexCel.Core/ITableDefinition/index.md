---
uid: ITableDefinition
description: ITableDefinition
---

# ITableDefinition Interface

Contains the definition of an Excel table\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">ITableDefinition = interface(IInterface);</code></pre>

## Methods

|Name|Description|
|---|---|
|[AddColumn](AddColumn.md)|Adds a column to a table definition\.<br />This is mostly used for tables without headers; as in the tables with headers, columns will be inferred from the cells in the header\.<br />|
|[ClearColumns](ClearColumns.md)|Clears all column definitions in the table\.<br />|
|[ColumnFromId](ColumnFromId.md)|Returns the column definition for an id, or returns a column with Id = \-1 and name empty if the id doesn't exist\.<br />|
|[ColumnFromPos](ColumnFromPos.md)|Returns the column at position columnPosition \(0 based\)\.<br />|
|[ColumnInGridFromId](ColumnInGridFromId.md)|Returns the position int the Excel grid for a column id\. So for example if the table starts at column 10 in Excel, and aId is the second column of the table, this method will return 11\. If the id doesn't exists, this method will return \-1\.<br />|
|[ColumnFromName](ColumnFromName.md)|Returns the column definition for a given column name\. If tableXls is null, then this method will return the stored column name\. If not null and the table has headers, this method will try to get the column name from the cell value of the table headers in the Excel file\.<br /><br />If the column name doesn't exist, this method will return  a TTableColumn&#8203;Definition\(&#8203;null, \-1\);|


## Properties

|Name|Description|
|---|---|
|[Name](Name.md)|The name of the table\.<br />|
|[Range](Range.md)|The range of cells used by the table\.<br />|
|[Comment](Comment.md)|The comment for the table\.<br />|
|[Style](Style.md)|The built in style of the table, if any\.<br />|
|[HasHeaderRow](HasHeaderRow.md)|If true the table has a header row\.<br />|
|[HasTotalsRow](HasTotalsRow.md)|If true, the table has a Totals row\.<br />|
|[HasAutofilter](HasAutofilter.md)|If true, the table has an autofilter\.<br />|
|[ColumnCount](ColumnCount.md)|Returns the number of columns in the table definition\.<br />|


