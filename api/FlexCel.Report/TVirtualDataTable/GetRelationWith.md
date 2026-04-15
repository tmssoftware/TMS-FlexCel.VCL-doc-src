---
uid: TVirtualDataTable.GetRelationWith
description: TVirtualDataTable.GetRelationWith
---

# TVirtualDataTable\.GetRelationWith Method

Override this method if the datatable has intrinsic relationships that you want to use\.
For example DataSets have DataRelationships, or Entity Framework tables are related as properties from the  master to the detail\. All those relationships that are not explicitly defined in the report should be returned here\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TVirtualDataTable/index.md">TVirtualDataTable</a>.GetRelationWith(const aDetail: <a href="../TVirtualDataTable/index.md">TVirtualDataTable</a>): <a href="../TRelation/index.md">TRelation</a>; virtual;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aDetail**|[TVirtualDataTable](../TVirtualDataTable/index.md)|Detail table from where we want to get the relationship\.|


## See also

* [TVirtualDataTable](../TVirtualDataTable/index.md)

