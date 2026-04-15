---
uid: TUserDefinedFunction.CheckParameters
description: TUserDefinedFunction.CheckParameters
---

# TUserDefinedFunction\.CheckParameters Method

Checks that the parameter array has the expected number of arguments, and that no one is an Error\. If any argument is an error it is returned in ResultError, since the default in Excel is to stop processing arguments in a function when one is an error\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TUserDefinedFunction/index.md">TUserDefinedFunction</a>.CheckParameters(const parameters: <a href="../TFormulaValue/index.md">TArray&lt;TFormulaValue></a>; const expectedCount: Integer; out ResultError: <a href="../TFlxFormulaErrorValue.md">TFlxFormulaErrorValue</a>): Boolean; static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**parameters**|[TArray\<&#8203;TFormula&#8203;Value>](../TFormulaValue/index.md)|Array of parameters to check\.|
|const|**expectedCount**|Integer|Number of parameters expected\. If this number is variable, specify \-1 here\.|
|out|**ResultError**|[TFlxFormulaError&#8203;Value](../TFlxFormulaErrorValue.md)|Returns the error in the parameters\. This parameter is only valid if this function returns false\.|


## Returns

True if all parameters are correct, false otherwise\.

## See also

* [TUserDefinedFunction](../TUserDefinedFunction/index.md)

