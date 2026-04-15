---
uid: TExcelFile.CellMergedNext
description: TExcelFile.CellMergedNext
---

# TExcelFile\.CellMergedNext Method

Use this method to enumerate all merged cells in a sheet\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.CellMergedNext(var state: <a href="../TCellMergedState/index.md">TCellMergedState</a>): <a href="../TXlsCellRange/index.md">TXlsCellRange</a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|var|**state**|[TCellMergedState](../TCellMergedState/index.md)|This struct holds the current merged cell being enumerated and is used by the method to return the next cell in the enumeration\. To get the first value, create it with TCellMergedState\.Init\(\)|


## Returns

The next merged cell in the sheet\.

## See also

* [TExcelFile](../TExcelFile/index.md)

