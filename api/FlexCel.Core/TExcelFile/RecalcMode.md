---
uid: TExcelFile.RecalcMode
description: TExcelFile.RecalcMode
---

# TExcelFile.RecalcMode Property

Set this property to change how the file will be recalculated\. Note that this affects only how FlexCel recalculates the file, but not how Excel will recalculate it\. It doesn't change anything in  the generated file\. To change the options for the file, use [OptionsRecalcMode](OptionsRecalcMode.md) instead\.


## Remarks

Setting RecalcMode = Manual might be a little faster for big spreadsheets with \*lots\* of formulas, but they won't preview ok on Excel viewers as FlexCelPrintDocument\. See also [RecalcVersion](RecalcVersion.md) When Manual, you can still call [Recalc\(Boolean\)](Recalc.md#texcelfilerecalcboolean) with "forced" = true to recalculate the sheet\.


Not all functions are supported, those that are not will return a \#NAME? error on a viewer, and will be recalculated by Excel when you open the file\. See [Supported Excel Functions](xref:SupportedExcelFunctions) for a list of supported functions\.



## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TExcelFile/index.md">TExcelFile</a>.RecalcMode: <a href="../TRecalcMode.md">TRecalcMode</a></code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)

