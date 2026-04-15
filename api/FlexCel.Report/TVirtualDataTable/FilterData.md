---
uid: TVirtualDataTable.FilterData
description: TVirtualDataTable.FilterData
---

# TVirtualDataTable\.FilterData Method

This method should return a new VirtualDataTable instance with the data filtered\. If RowFilter is null, this method should return a copy of the dataset with a different name\.
Note that you might have the same data with different states, so this method might be called more than once\.


## Remarks

You do not need to implement this method if you do not want to let users create new filtered datasets on the config sheet\.

## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TVirtualDataTable/index.md">TVirtualDataTable</a>.FilterData(const newDataName: string; const rowFilter: string): <a href="../TVirtualDataTable/index.md">TVirtualDataTable</a>; virtual;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**newDataName**|string|How this new VirtualDataSet will be named\. This is what the user wrote on the config sheet, when creating a filtered dataset\. Note that as with all the VirtualDataSets, this name is meaningless except for error messages\.|
|const|**rowFilter**|string|Filter for the new data\. This can be null, an empty string, or whatever the user wrote on the "filter" column on the config sheet\. Note that if the Filter is "distinct\(\)" this method will not be called, but [GetDistinct](GetDistinct.md) instead\.<br />This method will not be called if the filter is "Split\(\)" either\.|


## Returns

A new VirtualDataTable with the filtered data and the new name\.

## See also

* [TVirtualDataTable](../TVirtualDataTable/index.md)

