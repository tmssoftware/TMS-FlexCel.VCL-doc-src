---
uid: TVirtualDataTable.GetColumnCaption
description: TVirtualDataTable.GetColumnCaption
---

# TVirtualDataTable\.GetColumnCaption Method

Returns the column caption for a column identifier\. This method is used on generic dataset to write the header column\.
For most uses, [GetColumnName](GetColumnName.md) will be used\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TVirtualDataTable/index.md">TVirtualDataTable</a>.GetColumnCaption(const columnIndex: Integer): string; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**columnIndex**|Integer|Column index returned by [GetColumn](GetColumn.md)|


## Returns

The name of the column at columnIndex\. If the columnIndex is not valid it should throw an Exception, since this method will only be called for columnIndexes returned by [GetColumn](GetColumn.md)

## See also

* [TVirtualDataTable](../TVirtualDataTable/index.md)

