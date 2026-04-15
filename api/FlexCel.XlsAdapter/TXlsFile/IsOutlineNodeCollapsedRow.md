---
uid: TXlsFile.IsOutlineNodeCollapsedRow
description: TXlsFile.IsOutlineNodeCollapsedRow
---

# TXlsFile\.IsOutlineNodeCollapsedRow Method

Returns true when the row is an outline node \(it has a "\+" at the left\) and it is closed \(all children are hidden\)\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.IsOutlineNodeCollapsedRow(const row: Integer): Boolean; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row to test \(1 based\)|


## Returns

True if the row contains a node and it is collapsed, false otherwise\.

## See also

* [TXlsFile](../TXlsFile/index.md)

