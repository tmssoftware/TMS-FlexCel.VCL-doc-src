---
uid: TExcelFile.FormulaReferenceStyle
description: TExcelFile.FormulaReferenceStyle
---

# TExcelFile.FormulaReferenceStyle Property

Specifies which reference style to use when entering formulas: A1 or R1C1\. Note that this property is different from [OptionsR1C1](OptionsR1C1.md)\. OptionsR1C1 modifies a property of the file, that handles how references will show in Excel\.

This property modifies how FlexCel parses or returns the formulas, and has no effect at all in the file generated\.


Also note that R1C1 and A1 modes are completely equivalent, and formulas are **always stored as A1** inside the generated files\. This property only affects the parsing of the formulas, the file generated will be exactly the same no matter the value of this property\. And Excel will show it in A1 or R1C1 mode depending only in [OptionsR1C1](OptionsR1C1.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TExcelFile/index.md">TExcelFile</a>.FormulaReferenceStyle: <a href="../TReferenceStyle.md">TReferenceStyle</a></code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)

