---
uid: TExcelFile.SelectCell
description: TExcelFile.SelectCell
---

# TExcelFile\.SelectCell Method

Selects a single cell\. To select multiple cells, use [SelectCells](SelectCells.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SelectCell(const row: Integer; const col: Integer; const aScrollWindow: Boolean);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row to select \(1 based\)|
|const|**col**|Integer|Column to select \(1 based\)|
|const|**aScrollWindow**|Boolean|When true, window will scroll so the selected cell is visible\. This is equivalent to using [ScrollWindow\(Integer, Integer\)](ScrollWindow.md#texcelfilescrollwindowinteger-integer) method and is provided as a shortcut\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

