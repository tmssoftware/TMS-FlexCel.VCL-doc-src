---
uid: TXlsFile.GetListOfValues
description: TXlsFile.GetListOfValues
---

# TXlsFile\.GetListOfValues Method

This method will return all numeric values in the collection of ranges, and the rest of cells which are not numeric in nonNumericCells\.
It is for internal use\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.GetListOfValues(const ranges: <a href="../../FlexCel.Core/TXlsCellRange/index.md">TArray&lt;TXlsCellRange></a>; const values: TFList&lt;Double&gt;; const duplicates: HashSet&lt;TCellRowAndCol&gt;; out vSum: Double); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**ranges**|[TArray\<&#8203;TXls&#8203;Cell&#8203;Range>](../../FlexCel.Core/TXlsCellRange/index.md)|Ranges where we want to get the cell values\.|
|const|**values**|TFList\<Double>|List where we will return all values in the cells\.|
|const|**duplicates**|HashSet\<TCellRowAndCol>|If not null, this list will be filled with all the cells which contain duplicated values\.|
|out|**vSum**|Double|Sum of all values in the range\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

