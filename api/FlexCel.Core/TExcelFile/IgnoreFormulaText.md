---
uid: TExcelFile.IgnoreFormulaText
description: TExcelFile.IgnoreFormulaText
---

# TExcelFile.IgnoreFormulaText Property

This is an optimization property\. If you set it to true, methods like GetCellValue or GetNamedRange won't return the formula text, just the formula results\. If you don't care about formula texts, setting this property to true can speed up the processing of huge files\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TExcelFile/index.md">TExcelFile</a>.IgnoreFormulaText: Boolean</code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)

