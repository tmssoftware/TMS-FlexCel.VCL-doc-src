---
uid: TExcelFile.RemoveUserDefinedFunction
description: TExcelFile.RemoveUserDefinedFunction
---

# TExcelFile\.RemoveUserDefinedFunction Method

Removes a single function from the FlexCel recalculation engine\. If the function doesn't exist, this  method will return false\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.RemoveUserDefinedFunction(const scope: <a href="../TUserDefinedFunctionScope.md">TUserDefinedFunctionScope</a>; const functionName: string): Boolean; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**scope**|[TUserDefined&#8203;Function&#8203;Scope](../TUserDefinedFunctionScope.md)||
|const|**functionName**|string|Name of the function\. Case insensitive\.|


## Returns

True if the function existed and was removed, false if it didn't exist\.

## See also

* [TExcelFile](../TExcelFile/index.md)

