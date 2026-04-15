---
uid: TXlsCellRange.CalcTopCell
description: TXlsCellRange.CalcTopCell
---

# TXlsCellRange\.CalcTopCell Method

Returns the minimum top and left coordinates for an array of ranges\. If for example you have C7 and D5, this method will return C5

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TXlsCellRange/index.md">TXlsCellRange</a>.CalcTopCell(const ranges: <a href="../TXlsCellRange/index.md">TArray&lt;TXlsCellRange></a>; const ResultBase1: Boolean): <a href="../TCellAddress/index.md">TCellAddress</a>; static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**ranges**|[TArray\<&#8203;TXls&#8203;Cell&#8203;Range>](../TXlsCellRange/index.md)|An array of ranges, 1 based\.|
|const|**ResultBase1**|Boolean|If true, the address will be in base 1 \(1, 1 is the top cell\)\. If false, \(0, 0\) will be the top cell for the returned address\.|


## See also

* [TXlsCellRange](../TXlsCellRange/index.md)

