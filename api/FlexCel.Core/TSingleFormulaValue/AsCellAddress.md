---
uid: TSingleFormulaValue.AsCellAddress
description: TSingleFormulaValue.AsCellAddress
---

# TSingleFormulaValue\.AsCellAddress Method

Returns the value of the formula if it contains a cell adress\. If it contains other datatype, this method will throw an exception\.



Check [IsCellAddress](IsCellAddress.md) to see if the formula contains a cell address\.




## Remarks

While this method returns an array, as the value is a single cell address, the array will have lenght 1\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TSingleFormulaValue/index.md">TSingleFormulaValue</a>.AsCellAddress: TArray&lt;<a href="../TAddress/index.md">TAddress</a>&gt;;</code></pre>

## See also

* [TSingleFormulaValue](../TSingleFormulaValue/index.md)

