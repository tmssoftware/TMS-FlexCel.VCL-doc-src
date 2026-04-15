---
uid: TVirtualDataTable.GetColumn
description: TVirtualDataTable.GetColumn
---

# TVirtualDataTable\.GetColumn Method

Returns a column identifier that you can later use on [TVirtualDataTableState.GetValue\(Integer\)](../TVirtualDataTableState/GetValue.md#tvirtualdatatablestategetvalueinteger)\.
Return \-1 if the column does not exist, and make sure this search is case insensitive\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TVirtualDataTable/index.md">TVirtualDataTable</a>.GetColumn(const columnName: string): Integer; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**columnName**|string|Name of the column to search\.|


## Returns

Column identifier if found, \-1 if not found\.

## See also

* [TVirtualDataTable](../TVirtualDataTable/index.md)

