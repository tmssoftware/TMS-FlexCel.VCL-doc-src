---
uid: TVirtualDataTable.GetColumnName
description: TVirtualDataTable.GetColumnName
---

# TVirtualDataTable\.GetColumnName Method

Returns the column name for a column identifier\. This method is the reverse of [GetColumn](GetColumn.md)

## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TVirtualDataTable/index.md">TVirtualDataTable</a>.GetColumnName(const columnIndex: Integer): string; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**columnIndex**|Integer|Column index returned by [GetColumn](GetColumn.md)|


## Returns

The name of the column at columnIndex\. If the columnIndex is not valid it should throw an Exception, since this method will only be called for columnIndexes returned by [GetColumn](GetColumn.md)

## See also

* [TVirtualDataTable](../TVirtualDataTable/index.md)

