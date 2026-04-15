---
uid: TTableColumnDefinition.TotalsRowFunction
description: TTableColumnDefinition.TotalsRowFunction
---

# TTableColumnDefinition.TotalsRowFunction Property

An enumeration that specifies what function is used to aggregate the data in a column\.
When set to custom, the value in [TotalsRowFormula](TotalsRowFormula.md) is used instead\.
Additionally, FlexCel will ignore this value when adding a table with totals and read the formula from the cell itself\.
If the table doesn't have a total row, then this value will be used\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TTableColumnDefinition/index.md">TTableColumnDefinition</a>.TotalsRowFunction: <a href="../TTotalsRowFunction.md">TTotalsRowFunction</a></code></pre>

## See also

* [TTableColumnDefinition](../TTableColumnDefinition/index.md)

