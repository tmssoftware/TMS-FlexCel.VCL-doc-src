---
uid: TSingleFormulaValue.AsCellRangeString
description: TSingleFormulaValue.AsCellRangeString
---

# TSingleFormulaValue\.AsCellRangeString Method

Returns the value of the formula if it contains a range of cells\.
If it contains other datatype, this method will throw an exception\.



Different from [AsCellRange](AsCellRange.md), this method will return a string like "A1:A10" instead of an array of [TAddress](../TAddress/index.md) object\.



Check [IsCellRange](IsCellRange.md) to see if the formula contains a range of cells\.




## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TSingleFormulaValue/index.md">TSingleFormulaValue</a>.AsCellRangeString: string;</code></pre>

## See also

* [TSingleFormulaValue](../TSingleFormulaValue/index.md)

