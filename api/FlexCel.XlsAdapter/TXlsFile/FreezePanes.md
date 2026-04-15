---
uid: TXlsFile.FreezePanes
description: TXlsFile.FreezePanes
---

# TXlsFile\.FreezePanes Method

This command is equivalent to Menu\->Window\->Freeze Panes\. It will freeze the rows and columns above and to the left from cell\. Note that because Excel works this way, when you [TExcelFile.SplitWindow](../../FlexCel.Core/TExcelFile/SplitWindow.md) the panes are suppressed and vice\-versa See also [TExcelFile.GetFrozenPanes](../../FlexCel.Core/TExcelFile/GetFrozenPanes.md) This property can work in different windows depending on the value of [TExcelFile.ActiveWindow](../../FlexCel.Core/TExcelFile/ActiveWindow.md)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.FreezePanes(const cell: <a href="../../FlexCel.Core/TCellAddress/index.md">TCellAddress</a>); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**cell**|[TCellAddress](../../FlexCel.Core/TCellAddress/index.md)|All rows and columns above and to the left of this cell will be frozen\. Set it to null or "A1" to unfreeze the panes\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

