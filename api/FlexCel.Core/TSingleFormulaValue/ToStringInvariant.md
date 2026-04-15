---
uid: TSingleFormulaValue.ToStringInvariant
description: TSingleFormulaValue.ToStringInvariant
---

# TSingleFormulaValue\.ToStringInvariant Method

Converts the formula result to a string with invariant format\. This means that for example the number 1\.2 will be converted to the string '1\.2' even if in the active locale it would '1,2' because the decimal separator is a comma\. To get the number as a string in the current locale, use [ToString](ToString.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TSingleFormulaValue/index.md">TSingleFormulaValue</a>.ToStringInvariant: string;</code></pre>

## See also

* [TSingleFormulaValue](../TSingleFormulaValue/index.md)

