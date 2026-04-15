---
uid: TExcelFile.FirstSheetVisible
description: TExcelFile.FirstSheetVisible
---

# TExcelFile.FirstSheetVisible Property

This is the first sheet that will be visible in the bar of sheet tabs at the bottom\. Normally you will want this to be 1\.
Note that every time you change [ActiveSheet](ActiveSheet.md) this value gets reset, because it makes no sense to preserve it\.

If you want to change it, change it before saving\. The same way, to read it, read it just after opening the file\.

Please also note that if the first sheet you select is hidden, FlexCel will ignore this value and select a visible sheet\. \(otherwise Excel would crash\) This property can work in different windows depending on the value of [ActiveWindow](ActiveWindow.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TExcelFile/index.md">TExcelFile</a>.FirstSheetVisible: Integer</code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)

