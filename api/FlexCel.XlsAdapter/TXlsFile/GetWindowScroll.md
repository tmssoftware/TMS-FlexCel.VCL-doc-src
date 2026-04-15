---
uid: TXlsFile.GetWindowScroll
description: TXlsFile.GetWindowScroll
---

# TXlsFile\.GetWindowScroll Method

Returns the window scroll for a specified pane\.
This property can work in different windows depending on the value of [TExcelFile.ActiveWindow](../../FlexCel.Core/TExcelFile/ActiveWindow.md)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetWindowScroll(const panePosition: <a href="../../FlexCel.Core/TPanePosition.md">TPanePosition</a>): <a href="../../FlexCel.Core/TCellAddress/index.md">TCellAddress</a>; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**panePosition**|[TPanePosition](../../FlexCel.Core/TPanePosition.md)|Pane to return\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

