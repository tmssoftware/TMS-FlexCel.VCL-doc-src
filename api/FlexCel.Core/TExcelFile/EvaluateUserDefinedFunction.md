---
uid: TExcelFile.EvaluateUserDefinedFunction
description: TExcelFile.EvaluateUserDefinedFunction
---

# TExcelFile\.EvaluateUserDefinedFunction Method

Evaluates a custom function you have added earlier with [AddUserDefinedFunction](AddUserDefinedFunction.md)\. You will not normally need to call this method, but it could be used for testing\.
If the function has not been added with [AddUserDefinedFunction](AddUserDefinedFunction.md), this method will return [TFlxFormulaErrorValue.ErrName](../TFlxFormulaErrorValue.md)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.EvaluateUserDefinedFunction(const functionName: string; const arguments: <a href="../TUdfEventArgs/index.md">TUdfEventArgs</a>; const parameters: <a href="../TFormulaValue/index.md">TArray&lt;TFormulaValue></a>): <a href="../TFormulaValue/index.md">TFormulaValue</a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**functionName**|string|Function you want to evaluate\.|
|const|**arguments**|[TUdfEventArgs](../TUdfEventArgs/index.md)|Extra arguments you can use to evaluate the formula\.|
|const|**parameters**|[TArray\<&#8203;TFormula&#8203;Value>](../TFormulaValue/index.md)|Parameters for the formula\.|


## Returns

The result of evaluating the formula\. It might be a string, a double, a boolean, a TFlxFormulaError or an Array\.

## See also

* [TExcelFile](../TExcelFile/index.md)

