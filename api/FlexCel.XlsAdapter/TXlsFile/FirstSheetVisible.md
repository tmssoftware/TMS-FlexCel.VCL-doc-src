---
uid: TXlsFile.FirstSheetVisible
description: TXlsFile.FirstSheetVisible
---

# TXlsFile.FirstSheetVisible Property

This is the first sheet that will be visible in the bar of sheet tabs at the bottom\. Normally you will want this to be 1\.
Note that every time you change [TExcelFile.ActiveSheet](../../FlexCel.Core/TExcelFile/ActiveSheet.md) this value gets reset, because it makes no sense to preserve it\.

If you want to change it, change it before saving\. The same way, to read it, read it just after opening the file\.

Please also note that if the first sheet you select is hidden, FlexCel will ignore this value and select a visible sheet\. \(otherwise Excel would crash\) This property can work in different windows depending on the value of [TExcelFile.ActiveWindow](../../FlexCel.Core/TExcelFile/ActiveWindow.md)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TXlsFile/index.md">TXlsFile</a>.FirstSheetVisible: Integer</code></pre>

## See also

* [TXlsFile](../TXlsFile/index.md)

