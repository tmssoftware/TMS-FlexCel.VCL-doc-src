---
uid: TVirtualDataTableState.TryAggregate
description: TVirtualDataTableState.TryAggregate
---

# TVirtualDataTableState\.TryAggregate Method

This method is used by the "AGGREGATE" tag in a FlexCel report to calculate the maximum/minimum/average/etc of the values in the table\. If you don't implement this method, FlexCel will still calculate those values by looping through the dataset, but if you have a faster way to do it \(like with a "select max\(field\) from table"\) then implement this method and return true\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TVirtualDataTableState/index.md">TVirtualDataTableState</a>.TryAggregate(const aggregateType: <a href="../TAggregateType.md">TAggregateType</a>; const colIndex: Integer; out resultValue: <a href="../../FlexCel.Core/TCellValue/index.md">TCellValue</a>): Boolean; virtual;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aggregateType**|[TAggregateType](../TAggregateType.md)|Which operation to do on the dataset\. \(Max/Min/etc\)|
|const|**colIndex**|Integer|Index of the field in which we want to aggregate\.|
|out|**resultValue**|[TCellValue](../../FlexCel.Core/TCellValue/index.md)|Returns the result of the operation in the dataset\. It should be null, a double or a datetime\.|


## Returns

True if this method is implemented, false if not\. Note that even if we return false here, FlexCel will still calculate the aggregate by looping through all the records\.

## See also

* [TVirtualDataTableState](../TVirtualDataTableState/index.md)

