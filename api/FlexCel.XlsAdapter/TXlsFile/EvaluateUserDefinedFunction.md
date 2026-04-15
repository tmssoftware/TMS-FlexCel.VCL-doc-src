---
uid: TXlsFile.EvaluateUserDefinedFunction
description: TXlsFile.EvaluateUserDefinedFunction
---

# TXlsFile\.EvaluateUserDefinedFunction Method

Evaluates a custom function you have added earlier with [TExcelFile.AddUserDefinedFunction](../../FlexCel.Core/TExcelFile/AddUserDefinedFunction.md)\. You will not normally need to call this method, but it could be used for testing\.
If the function has not been added with [TExcelFile.AddUserDefinedFunction](../../FlexCel.Core/TExcelFile/AddUserDefinedFunction.md), this method will return [TFlxFormulaErrorValue.ErrName](../../FlexCel.Core/TFlxFormulaErrorValue.md)\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.EvaluateUserDefinedFunction(const functionName: string; const arguments: <a href="../../FlexCel.Core/TUdfEventArgs/index.md">TUdfEventArgs</a>; const parameters: <a href="../../FlexCel.Core/TFormulaValue/index.md">TArray&lt;TFormulaValue></a>): <a href="../../FlexCel.Core/TFormulaValue/index.md">TFormulaValue</a>; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**functionName**|string|Function you want to evaluate\.|
|const|**arguments**|[TUdfEventArgs](../../FlexCel.Core/TUdfEventArgs/index.md)|Extra arguments you can use to evaluate the formula\.|
|const|**parameters**|[TArray\<&#8203;TFormula&#8203;Value>](../../FlexCel.Core/TFormulaValue/index.md)|Parameters for the formula\.|


## Returns

The result of evaluating the formula\. It might be a string, a double, a boolean, a TFlxFormulaError or an Array\.

## See also

* [TXlsFile](../TXlsFile/index.md)

