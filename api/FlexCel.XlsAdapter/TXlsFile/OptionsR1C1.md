---
uid: TXlsFile.OptionsR1C1
description: TXlsFile.OptionsR1C1
---

# TXlsFile.OptionsR1C1 Property

Use this property to change the reference system used in the file\. Note that this option **only changes how Excel and FlexCel will display the file\.** Internally, the formulas will always be stored in A1 format, and converted by Excel to and from R1C1 if this property is true\. FlexCel will also use this property to render the file when it is set to print formulas\.


Also, this property doesn't change how FlexCel will parse or return the formula text in the cells or names\.
By default, even if this property is true, you will need to enter the formulas in FlexCel in A1 mode\. To change the entry mode in FlexCel, please use [TExcelFile.FormulaReferenceStyle](../../FlexCel.Core/TExcelFile/FormulaReferenceStyle.md)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TXlsFile/index.md">TXlsFile</a>.OptionsR1C1: Boolean</code></pre>

## See also

* [TXlsFile](../TXlsFile/index.md)

