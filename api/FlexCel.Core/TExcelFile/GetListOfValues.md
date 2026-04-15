---
uid: TExcelFile.GetListOfValues
description: TExcelFile.GetListOfValues
---

# TExcelFile\.GetListOfValues Method

This method will return all numeric values in the collection of ranges, and the rest of cells which are not numeric in nonNumericCells\.
It is for internal use\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.GetListOfValues(const ranges: <a href="../TXlsCellRange/index.md">TArray&lt;TXlsCellRange></a>; const values: TFList&lt;Double&gt;; const duplicates: HashSet&lt;TCellRowAndCol&gt;; out vSum: Double); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**ranges**|[TArray\<&#8203;TXls&#8203;Cell&#8203;Range>](../TXlsCellRange/index.md)|Ranges where we want to get the cell values\.|
|const|**values**|TFList\<Double>|List where we will return all values in the cells\.|
|const|**duplicates**|HashSet\<TCellRowAndCol>|If not null, this list will be filled with all the cells which contain duplicated values\.|
|out|**vSum**|Double|Sum of all values in the range\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

