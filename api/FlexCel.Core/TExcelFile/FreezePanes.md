---
uid: TExcelFile.FreezePanes
description: TExcelFile.FreezePanes
---

# TExcelFile\.FreezePanes Method

This command is equivalent to Menu\->Window\->Freeze Panes\. It will freeze the rows and columns above and to the left from cell\. Note that because Excel works this way, when you [SplitWindow](SplitWindow.md) the panes are suppressed and vice\-versa See also [GetFrozenPanes](GetFrozenPanes.md) This property can work in different windows depending on the value of [ActiveWindow](ActiveWindow.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.FreezePanes(const cell: <a href="../TCellAddress/index.md">TCellAddress</a>); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**cell**|[TCellAddress](../TCellAddress/index.md)|All rows and columns above and to the left of this cell will be frozen\. Set it to null or "A1" to unfreeze the panes\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

