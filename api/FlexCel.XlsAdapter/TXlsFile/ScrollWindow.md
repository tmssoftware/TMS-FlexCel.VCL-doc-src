---
uid: TXlsFile.ScrollWindow
description: TXlsFile.ScrollWindow
---

# TXlsFile\.ScrollWindow Method

Scrolls the window to a specified place\.
This property can work in different windows depending on the value of [TExcelFile.ActiveWindow](../../FlexCel.Core/TExcelFile/ActiveWindow.md)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.ScrollWindow(const panePosition: <a href="../../FlexCel.Core/TPanePosition.md">TPanePosition</a>; const row: Integer; const col: Integer); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**panePosition**|[TPanePosition](../../FlexCel.Core/TPanePosition.md)|Pane to move\. Note that if you move for example the left column of the upper left pane, you will also move the left column of the lower left pane\.|
|const|**row**|Integer|First visible row\.|
|const|**col**|Integer|First visible column\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

