---
uid: TXlsFile.RemoveUserDefinedFunction
description: TXlsFile.RemoveUserDefinedFunction
---

# TXlsFile\.RemoveUserDefinedFunction Method

Removes a single function from the FlexCel recalculation engine\. If the function doesn't exist, this  method will return false\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.RemoveUserDefinedFunction(const scope: <a href="../../FlexCel.Core/TUserDefinedFunctionScope.md">TUserDefinedFunctionScope</a>; const functionName: string): Boolean; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**scope**|[TUserDefined&#8203;Function&#8203;Scope](../../FlexCel.Core/TUserDefinedFunctionScope.md)||
|const|**functionName**|string|Name of the function\. Case insensitive\.|


## Returns

True if the function existed and was removed, false if it didn't exist\.

## See also

* [TXlsFile](../TXlsFile/index.md)

