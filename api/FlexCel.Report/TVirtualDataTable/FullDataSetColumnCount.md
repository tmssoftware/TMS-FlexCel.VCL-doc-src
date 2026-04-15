---
uid: TVirtualDataTable.FullDataSetColumnCount
description: TVirtualDataTable.FullDataSetColumnCount
---

# TVirtualDataTable\.FullDataSetColumnCount Method

Returns the columns in the table for a full dataset\. Normally this is the same as [ColumnCount](ColumnCount.md) but your implementation might choose to hide some of the fields available in the full ColumnCount when dumping all fields\.
If you change this method, you need also to review [GetFullDataSetColumn](GetFullDataSetColumn.md) so it returns the correct column for the dataset\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TVirtualDataTable/index.md">TVirtualDataTable</a>.FullDataSetColumnCount(const ColumnMapIndex: Integer): Integer; virtual;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**ColumnMapIndex**|Integer|This is the column map index returned by [GetFullDataSetMapId](GetFullDataSetMapId.md)\.|


## See also

* [TVirtualDataTable](../TVirtualDataTable/index.md)

