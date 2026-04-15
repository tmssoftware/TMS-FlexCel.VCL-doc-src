---
uid: TVirtualDataTable.Lookup
description: TVirtualDataTable.Lookup
---

# TVirtualDataTable\.Lookup Method

Looks for a key on this dataset and returns the corresponding value\.
Note: Remember that VirtualDataSet is stateless, so if you use any caching here, make sure you appropiately lock\(\) this method so there is no possibility of one thread reading the cache when the other is updating it\.


## Remarks

You do not need to implement this method unless you want to provide an optimized routine\. There is a default implementation which will look at all the records, cache them in a hash table, and use that for lookup\.
This default implementation should be enough in most cases\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TVirtualDataTable/index.md">TVirtualDataTable</a>.Lookup(const LookupFields: <a href="../TLookupFieldDefinition/index.md">TLookupFieldDefinition</a>; const keyValues: <a href="../../FlexCel.Core/TCellValue/index.md">TArray&lt;TCellValue></a>; const sort: string): <a href="../TReportValue/index.md">TReportValue</a>; virtual;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**LookupFields**|[TLookupField&#8203;Definition](../TLookupFieldDefinition/index.md)|Fields used to do the lookup\.|
|const|**keyValues**|[TArray\<TCellValue>](../../FlexCel.Core/TCellValue/index.md)|A list of the values for the keys, that you should use to locate the right record\.|
|const|**sort**|string|How the data is sorted\. This is relevant for TOP tables where not all data is available\.|


## Returns

The value at "column" , for the record where the columns on "keyNames" have the "keyValues" values\.
If there is more than one record where "keyNames" is equal to "keyValues" you might opt to throw an Exception or just return any of the  valid values, depending on the behavior you want for lookup\.

## See also

* [TVirtualDataTable](../TVirtualDataTable/index.md)

