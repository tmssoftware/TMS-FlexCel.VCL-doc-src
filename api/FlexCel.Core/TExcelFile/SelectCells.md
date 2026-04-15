---
uid: TExcelFile.SelectCells
description: TExcelFile.SelectCells
---

# TExcelFile\.SelectCells Method

Selects a group of cells on a given pane\. If you just want to select just one cell, you can use the simpler method [SelectCell](SelectCell.md) This property can work in different windows depending on the value of [ActiveWindow](ActiveWindow.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SelectCells(const cellRange: <a href="../TXlsCellRange/index.md">TArray&lt;TXlsCellRange></a>); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**cellRange**|[TArray\<&#8203;TXls&#8203;Cell&#8203;Range>](../TXlsCellRange/index.md)|Cells to select\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

