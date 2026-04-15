---
uid: TVirtualDataTable.CreateState
description: TVirtualDataTable.CreateState
---

# TVirtualDataTable\.CreateState Method

Creates a VirtualDataSetState to be used in a report\. Make sure you override this method on your derived classes and point it to the correct VirtualDataSet descendant\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TVirtualDataTable/index.md">TVirtualDataTable</a>.CreateState(const sort: string; const masterDetailLinks: <a href="../TMasterDetailLink/index.md">TArray&lt;TMasterDetailLink></a>; const splitLink: <a href="../TSplitLink/index.md">TSplitLink</a>): <a href="../TVirtualDataTableState/index.md">TVirtualDataTableState</a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sort**|string|A string showing how to sort this dataset\. This string might be null, empty, or whatever the user wrote on the config sheet\.|
|const|**masterDetailLinks**|[TArray\<&#8203;TMaster&#8203;Detail&#8203;Link>](../TMasterDetailLink/index.md)|A list of the the master datatables and relation fields on the bands outside this one\.<br />You can pass this parameter to the VirtualDataSetState so it can create indexes on the required fields\.<br />This parameter will be an empty array if no master detail relationships apply to the VirtualDataSetState, but it will not be null\.<br />|
|const|**splitLink**|[TSplitLink](../TSplitLink/index.md)|A link to a parent Split datasource with the number of records to split, or null if there is no parent split datasource\.|


## See also

* [TVirtualDataTable](../TVirtualDataTable/index.md)

