---
uid: TXlsFile.IsDefinedFunction
description: TXlsFile.IsDefinedFunction
---

# TXlsFile\.IsDefinedFunction Method

Returns true if the Custom formula function has been added to the FlexCel recalculating engine\.
Note that internal functions are not returned by this method, but user defined functions pre\-defined in FlexCel will be\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.IsDefinedFunction(const functionName: string; out location: <a href="../../FlexCel.Core/TUserDefinedFunctionLocation.md">TUserDefinedFunctionLocation</a>): Boolean; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**functionName**|string|Name of the function\. Case insensitive\.|
|out|**location**|[TUserDefined&#8203;Function&#8203;Location](../../FlexCel.Core/TUserDefinedFunctionLocation.md)|Returns if the function is defined as an internal or external function\.|


## Returns

True if the name has been added, false if not\.

## See also

* [TXlsFile](../TXlsFile/index.md)

