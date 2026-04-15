---
uid: TVirtualDataTableState.FilteredRowCount
description: TVirtualDataTableState.FilteredRowCount
---

# TVirtualDataTableState\.FilteredRowCount Method

This method will be called when a Split master wants to know how many records its detail has\. For example, if the detail has 30 records and the split is at 10, the Split master will call this method to find out that it has to return 3 on its own record count\.
You need to filter the data here depending on the master detail relationships, but not on the splitLink\.


## Remarks

You do not need to implement this method if you are not using Split relationships\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TVirtualDataTableState/index.md">TVirtualDataTableState</a>.FilteredRowCount(const masterDetailLinks: <a href="../TMasterDetailLink/index.md">TArray&lt;TMasterDetailLink></a>): Integer; virtual;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**masterDetailLinks**|[TArray\<&#8203;TMaster&#8203;Detail&#8203;Link>](../TMasterDetailLink/index.md)|List of all the master tables that are related to this one\.<br />If there are no parents on this VirtualDataTableState, this will be an empty array, not null\.<br />|


## Returns

The count of records for a specific position of the master datasets\.

## See also

* [TVirtualDataTableState](../TVirtualDataTableState/index.md)

