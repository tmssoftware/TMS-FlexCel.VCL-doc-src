---
uid: TVirtualDataTableState.MoveMasterRecord
description: TVirtualDataTableState.MoveMasterRecord
---

# TVirtualDataTableState\.MoveMasterRecord Method

This method will be called each time that the master datasource moves its position\. Use it to filter the data returned if this is used on a master\-detail relationship\.


## Remarks

You do not need to implement this method if you are not using Master\-Detail or Split relationships\.

## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TVirtualDataTableState/index.md">TVirtualDataTableState</a>.MoveMasterRecord(const masterDetailLinks: <a href="../TMasterDetailLink/index.md">TArray&lt;TMasterDetailLink></a>; const splitLink: <a href="../TSplitLink/index.md">TSplitLink</a>); virtual;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**masterDetailLinks**|[TArray\<&#8203;TMaster&#8203;Detail&#8203;Link>](../TMasterDetailLink/index.md)|List of all the master tables that are related to this one\.<br />If there are no parents on this VirtualDataTableState, this will be an empty array, not null\.<br />Use it on [GetValue\(Integer\)](GetValue.md#tvirtualdatatablestategetvalueinteger) to filter the data and then return only the records that satisfy the master\-detail relationships on [GetValue\(Integer\)](GetValue.md#tvirtualdatatablestategetvalueinteger)|
|const|**splitLink**|[TSplitLink](../TSplitLink/index.md)|Parent Split table if this dataset is on a Split relationship, or null if there is none\.<br />Use it to know how many records you should retun on [RowCount](RowCount.md)\. Note that a table might be on Master\-Detail relationship  \*and\* split relationship\. In this case you need to first filter the records that are on the master detail relationship, and then apply the split to them\.<br />|


## See also

* [TVirtualDataTableState](../TVirtualDataTableState/index.md)

