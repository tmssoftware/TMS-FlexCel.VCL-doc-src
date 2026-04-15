---
uid: TVirtualDataTable.GetDetail
description: TVirtualDataTable.GetDetail
---

# TVirtualDataTable\.GetDetail Method

Override this method if the table has linked tables that you can use for master detail relationships instead of normal relationships\. This is the case for example in Entity Framework\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TVirtualDataTable/index.md">TVirtualDataTable</a>.GetDetail(const dataTableName: string; const dataTable: <a href="../TVirtualDataTable/index.md">TVirtualDataTable</a>): <a href="../TVirtualDataTable/index.md">TVirtualDataTable</a>; virtual;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**dataTableName**|string|Name of the detail dataset we are looking for\.|
|const|**dataTable**|[TVirtualDataTable](../TVirtualDataTable/index.md)|Detail dataset that we are looking for\.|


## Returns

The dataset if it is a detail dataset, null otherwise\.

## See also

* [TVirtualDataTable](../TVirtualDataTable/index.md)

