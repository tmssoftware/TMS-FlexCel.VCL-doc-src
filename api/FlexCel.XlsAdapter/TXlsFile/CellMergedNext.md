---
uid: TXlsFile.CellMergedNext
description: TXlsFile.CellMergedNext
---

# TXlsFile\.CellMergedNext Method

Use this method to enumerate all merged cells in a sheet\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.CellMergedNext(var state: <a href="../../FlexCel.Core/TCellMergedState/index.md">TCellMergedState</a>): <a href="../../FlexCel.Core/TXlsCellRange/index.md">TXlsCellRange</a>; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|var|**state**|[TCellMergedState](../../FlexCel.Core/TCellMergedState/index.md)|This struct holds the current merged cell being enumerated and is used by the method to return the next cell in the enumeration\. To get the first value, create it with TCellMergedState\.Init\(\)|


## Returns

The next merged cell in the sheet\.

## See also

* [TXlsFile](../TXlsFile/index.md)

