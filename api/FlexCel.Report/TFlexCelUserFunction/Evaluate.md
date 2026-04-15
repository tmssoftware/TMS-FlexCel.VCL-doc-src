---
uid: TFlexCelUserFunction.Evaluate
description: TFlexCelUserFunction.Evaluate
---

# TFlexCelUserFunction\.Evaluate Method

Override this method on a derived class to implement your own defined function\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TFlexCelUserFunction/index.md">TFlexCelUserFunction</a>.Evaluate(const parameters: <a href="../../FlexCel.Core/TFormulaValue/index.md">TArray&lt;TFormulaValue></a>): <a href="../TReportValue/index.md">TReportValue</a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**parameters**|[TArray\<&#8203;TFormula&#8203;Value>](../../FlexCel.Core/TFormulaValue/index.md)|An array of objects\.|


## Returns

The derived class should return the value of the function on the return parameter\.

## See also

* [TFlexCelUserFunction](../TFlexCelUserFunction/index.md)

