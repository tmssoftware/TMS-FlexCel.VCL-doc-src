---
uid: TXlsFile.IsOutlineNodeCollapsedCol
description: TXlsFile.IsOutlineNodeCollapsedCol
---

# TXlsFile\.IsOutlineNodeCollapsedCol Method

Returns true when the column is an outline node \(it has a "\+" at the top\) and it is closed \(all children are hidden\)\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.IsOutlineNodeCollapsedCol(const col: Integer): Boolean; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col**|Integer|Column to test \(1 based\)|


## Returns

True if the column contains a node and it is collapsed, false otherwise\.

## See also

* [TXlsFile](../TXlsFile/index.md)

