---
uid: TTableColumnDefinition.TotalsRowCellStyle
description: TTableColumnDefinition.TotalsRowCellStyle
---

# TTableColumnDefinition.TotalsRowCellStyle Property

Style for the totals row cell in the column, if it doesn't have a given cell style\.
This property has more priority than the table totals row cell style, but less than the cell style\.
FlexCel will ignore this value when adding a table with totals and read the formula from the cell itself\.
If the table doesn't have a total row, then this value will be used\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TTableColumnDefinition/index.md">TTableColumnDefinition</a>.TotalsRowCellStyle: string</code></pre>

## See also

* [TTableColumnDefinition](../TTableColumnDefinition/index.md)

