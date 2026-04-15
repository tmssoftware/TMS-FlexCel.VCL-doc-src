---
uid: ITableDefinition.ColumnInGridFromId
description: ITableDefinition.ColumnInGridFromId
---

# ITableDefinition\.ColumnInGridFromId Method

Returns the position int the Excel grid for a column id\. So for example if the table starts at column 10 in Excel, and aId is the second column of the table, this method will return 11\. If the id doesn't exists, this method will return \-1\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../ITableDefinition/index.md">ITableDefinition</a>.ColumnInGridFromId(const aId: Integer): Integer; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aId**|Integer|Id of the column we want to find\.|


## Returns

\-1 if not found, either the position in the list\.

## See also

* [ITableDefinition](../ITableDefinition/index.md)

