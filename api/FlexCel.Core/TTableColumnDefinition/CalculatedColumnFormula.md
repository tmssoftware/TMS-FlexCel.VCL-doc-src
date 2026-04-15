---
uid: TTableColumnDefinition.CalculatedColumnFormula
description: TTableColumnDefinition.CalculatedColumnFormula
---

# TTableColumnDefinition.CalculatedColumnFormula Property

Stores the formula that is used to perform the calculation for each cell in this column\.
Note that the column can have different formulas from this one, but this is normally not the case\.
This formula is also used by Excel to automatically add new formulas when you add new rows to the table\. FlexCel doesn't automatically adds this formula to the new rows, you need to set the cells to the formula manually if you want to\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TTableColumnDefinition/index.md">TTableColumnDefinition</a>.CalculatedColumnFormula: NullableTTableFormula</code></pre>

## See also

* [TTableColumnDefinition](../TTableColumnDefinition/index.md)

