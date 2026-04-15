---
uid: TXlsFile.SelectCells
description: TXlsFile.SelectCells
---

# TXlsFile\.SelectCells Method

Selects a group of cells on a given pane\. If you just want to select just one cell, you can use the simpler method [TExcelFile.SelectCell](../../FlexCel.Core/TExcelFile/SelectCell.md) This property can work in different windows depending on the value of [TExcelFile.ActiveWindow](../../FlexCel.Core/TExcelFile/ActiveWindow.md)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SelectCells(const cellRange: <a href="../../FlexCel.Core/TXlsCellRange/index.md">TArray&lt;TXlsCellRange></a>); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**cellRange**|[TArray\<&#8203;TXls&#8203;Cell&#8203;Range>](../../FlexCel.Core/TXlsCellRange/index.md)|Cells to select\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

