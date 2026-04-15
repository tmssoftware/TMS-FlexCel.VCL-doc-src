---
uid: TSingleFormulaValue.AsRange3DString
description: TSingleFormulaValue.AsRange3DString
---

# TSingleFormulaValue\.AsRange3DString Method

Returns the value of the formula if it contains a range of cells\.
If it contains other datatype, this method will throw an exception\.



Different from [AsRange3D](AsRange3D.md), this method will return a string like "Sheet1:Sheet2\!A1:A10" instead of a [TXls3DRange](../TXls3DRange/index.md) object\.



Check [IsCellRange](IsCellRange.md) to see if the formula contains a range of cells\.




## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TSingleFormulaValue/index.md">TSingleFormulaValue</a>.AsRange3DString: string;</code></pre>

## See also

* [TSingleFormulaValue](../TSingleFormulaValue/index.md)

