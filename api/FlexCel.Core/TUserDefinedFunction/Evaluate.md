---
uid: TUserDefinedFunction.Evaluate
description: TUserDefinedFunction.Evaluate
---

# TUserDefinedFunction\.Evaluate Method

Override this method to provide your own implementation on the function\.

If this method throws an exception, it will not be handled and the recalculation will be aborted\. So if you want to return an error, return a [TFlxFormulaErrorValue](../TFlxFormulaErrorValue.md) value\.

**Do not use any global variable in this method**, it must be stateless and always return the same value when called with the same arguments\.


See ['Using excels user defined functions udf' in the Api Developer Guide](xref:ApiDeveloperGuide#using-excels-user-defined-functions-udf) for more information\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TUserDefinedFunction/index.md">TUserDefinedFunction</a>.Evaluate(const arguments: <a href="../TUdfEventArgs/index.md">TUdfEventArgs</a>; const parameters: <a href="../TFormulaValue/index.md">TArray&lt;TFormulaValue></a>): <a href="../TFormulaValue/index.md">TFormulaValue</a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**arguments**|[TUdfEventArgs](../TUdfEventArgs/index.md)|Extra objects you can use to evaluate the function\.|
|const|**parameters**|[TArray\<&#8203;TFormula&#8203;Value>](../TFormulaValue/index.md)|Parameters for the function\. When this method is called by FlexCel, this parameter will never be null, but might be an array of zero length if there are no parameters\.<br /><br />Each parameter in the array will always be a [TFormulaValue](../TFormulaValue/index.md)<br />This class provides utility methods like [TryGetDouble](TryGetDouble.md) that will help you get a specific type of object from a parameter\.<br />|


## Returns

Return any object you want here\. Normally a double, a string, a boolean a TFlxFormulaErrorValue or a null\.
If this method returns a class, it will be converted to an allowed value, normally to a string\.
If you want to return an array for an array formula, return a 2\-dimensional array in the result, where the elements of the array are the values you want to return\.


## Examples

See ['Using excels user defined functions udf' in the Api Developer Guide](xref:ApiDeveloperGuide#using-excels-user-defined-functions-udf) for examples\.


## See also

* [TUserDefinedFunction](../TUserDefinedFunction/index.md)

