---
uid: TVirtualDataTable.GetDistinct
description: TVirtualDataTable.GetDistinct
---

# TVirtualDataTable\.GetDistinct Method

Override this method to return a new VirtualDataSet with unique values\.
Note that the returned dataset will not have all the columns this one has, only the ones defined on "filterFields"

## Remarks

You do not need to implement this method if you do not want to let users create "Distinct\(\)" filters on the config sheet\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TVirtualDataTable/index.md">TVirtualDataTable</a>.GetDistinct(const newDataName: string; const filterFields: TArray&lt;Int32>): <a href="../TVirtualDataTable/index.md">TVirtualDataTable</a>; virtual;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**newDataName**|string|How this new VirtualDataSet will be named\. This is what the user wrote on the config sheet, when creating the distinct dataset\. Note that as with all the VirtualDataSets, this name is meaningless except for error messages\.|
|const|**filterFields**|TArray\<Int32>|Fields where to apply the "distinct" condition\.|


## Returns

A new VirtualDataTable with the filtered data and the new name\.

## See also

* [TVirtualDataTable](../TVirtualDataTable/index.md)

