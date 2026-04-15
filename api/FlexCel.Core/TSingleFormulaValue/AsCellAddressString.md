---
uid: TSingleFormulaValue.AsCellAddressString
description: TSingleFormulaValue.AsCellAddressString
---

# TSingleFormulaValue\.AsCellAddressString Method

Returns the value of the formula if it contains a range of cells\.
If it contains other datatype, this method will throw an exception\.



Different from [AsCellAddress](AsCellAddress.md), this method will return a string like "A1" instead of an array of [TAddress](../TAddress/index.md) object\.



Check [IsCellAddress](IsCellAddress.md) to see if the formula contains a range of cells\.




## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TSingleFormulaValue/index.md">TSingleFormulaValue</a>.AsCellAddressString: string;</code></pre>

## See also

* [TSingleFormulaValue](../TSingleFormulaValue/index.md)

