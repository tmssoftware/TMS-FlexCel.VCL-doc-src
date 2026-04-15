---
uid: TExcelFile.SplitWindow
description: TExcelFile.SplitWindow
---

# TExcelFile\.SplitWindow Method

This command is equivalent to Menu\->Window\->Split\. It will split the window in 4 regions\. Note that because Excel works this way, when you [FreezePanes](FreezePanes.md) the windows are unsplitted and vice\-versa See also [GetSplitWindow](GetSplitWindow.md) This property can work in different windows depending on the value of [ActiveWindow](ActiveWindow.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SplitWindow(const xOffset: Integer; const yOffset: Integer); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**xOffset**|Integer|Offset from the left on 1/20 of a point\. Zero for no vertical split\.|
|const|**yOffset**|Integer|Offset from the top on 1/20 of a point\. Zero for no horizontal split\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

