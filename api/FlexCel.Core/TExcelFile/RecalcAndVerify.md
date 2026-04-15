---
uid: TExcelFile.RecalcAndVerify
description: TExcelFile.RecalcAndVerify
---

# TExcelFile\.RecalcAndVerify Method

Use this method to validate a file\. FlexCel does not support all the range of functions from Excel when recalculating, so unknown functions will return "\#NAME?" errors\. Using this function you can validate your user worksheets and see if all the formulas they use are supported\.


## Remarks

Note that you \*can\* use unsupported functions on FlexCel\. When you open the generated file on Excel it will show ok\. The only problem is if you need to natively print or export to PDF the file\.


Also, take in account that RecalcAndVerify is slower than recalc, as it has to do more work to locate the errors\. Do not use it as a replace for [Recalc](Recalc.md)



## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.RecalcAndVerify: <a href="../TUnsupportedFormulaList/index.md">TUnsupportedFormulaList</a>; virtual; abstract;</code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)

