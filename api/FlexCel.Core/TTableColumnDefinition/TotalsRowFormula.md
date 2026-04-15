---
uid: TTableColumnDefinition.TotalsRowFormula
description: TTableColumnDefinition.TotalsRowFormula
---

# TTableColumnDefinition.TotalsRowFormula Property

A custom formula for aggregating values from the column\. This formula is only used if [TotalsRowFunction](TotalsRowFunction.md) is set to "Custom"\. Additionally, FlexCel will ignore this value when adding a table with totals and read the formula from the cell itself\.
If the table doesn't have a total row, then this value will be used\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TTableColumnDefinition/index.md">TTableColumnDefinition</a>.TotalsRowFormula: NullableTTableFormula</code></pre>

## See also

* [TTableColumnDefinition](../TTableColumnDefinition/index.md)

