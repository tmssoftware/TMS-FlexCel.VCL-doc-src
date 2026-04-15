---
uid: TVirtualDataTable.GetFullDataSetColumn
description: TVirtualDataTable.GetFullDataSetColumn
---

# TVirtualDataTable\.GetFullDataSetColumn Method

Maps a normal column to a Full Dataset column, in case you aren't outputting the same fields for full datasets as the fields available for a report\. If you are outputting all the fields, then this returns Column\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TVirtualDataTable/index.md">TVirtualDataTable</a>.GetFullDataSetColumn(const Column: Integer; const ColumnMapIndex: Integer): Integer; virtual;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Column**|Integer|Column we want to map\.|
|const|**ColumnMapIndex**|Integer|An id that you can use to map the column\. This value will be the one returned by [GetFullDataSetMapId](GetFullDataSetMapId.md)|


## See also

* [TVirtualDataTable](../TVirtualDataTable/index.md)

