---
uid: TXlsFile.RecalcAndVerify
description: TXlsFile.RecalcAndVerify
---

# TXlsFile\.RecalcAndVerify Method

Use this method to validate a file\. FlexCel does not support all the range of functions from Excel when recalculating, so unknown functions will return "\#NAME?" errors\. Using this function you can validate your user worksheets and see if all the formulas they use are supported\.


## Remarks

Note that you \*can\* use unsupported functions on FlexCel\. When you open the generated file on Excel it will show ok\. The only problem is if you need to natively print or export to PDF the file\.


Also, take in account that RecalcAndVerify is slower than recalc, as it has to do more work to locate the errors\. Do not use it as a replace for [TExcelFile.Recalc](../../FlexCel.Core/TExcelFile/Recalc.md)



## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.RecalcAndVerify: <a href="../../FlexCel.Core/TUnsupportedFormulaList/index.md">TUnsupportedFormulaList</a>; override;</code></pre>

## See also

* [TXlsFile](../TXlsFile/index.md)

