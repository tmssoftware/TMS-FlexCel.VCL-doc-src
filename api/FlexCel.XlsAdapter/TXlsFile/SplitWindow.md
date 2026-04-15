---
uid: TXlsFile.SplitWindow
description: TXlsFile.SplitWindow
---

# TXlsFile\.SplitWindow Method

This command is equivalent to Menu\->Window\->Split\. It will split the window in 4 regions\. Note that because Excel works this way, when you [TExcelFile.FreezePanes](../../FlexCel.Core/TExcelFile/FreezePanes.md) the windows are unsplitted and vice\-versa See also [TExcelFile.GetSplitWindow](../../FlexCel.Core/TExcelFile/GetSplitWindow.md) This property can work in different windows depending on the value of [TExcelFile.ActiveWindow](../../FlexCel.Core/TExcelFile/ActiveWindow.md)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SplitWindow(const xOffset: Integer; const yOffset: Integer); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**xOffset**|Integer|Offset from the left on 1/20 of a point\. Zero for no vertical split\.|
|const|**yOffset**|Integer|Offset from the top on 1/20 of a point\. Zero for no horizontal split\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

