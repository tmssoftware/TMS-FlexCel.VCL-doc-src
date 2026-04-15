---
uid: TExcelFile.IsDefinedFunction
description: TExcelFile.IsDefinedFunction
---

# TExcelFile\.IsDefinedFunction Method

## Overloads

* [TExcelFile\.IsDefinedFunction\(string\)](#texcelfileisdefinedfunctionstring)
* [TExcelFile\.IsDefinedFunction\(string, TUserDefinedFunctionLocation\)](#texcelfileisdefinedfunctionstring-tuserdefinedfunctionlocation)

# TExcelFile\.IsDefinedFunction\(string\)
Returns true if the Custom formula function has been added to the FlexCel recalculating engine\.
Note that internal functions are not returned by this method, but user defined functions pre\-defined in FlexCel will be\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.IsDefinedFunction(const functionName: string): Boolean; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**functionName**|string|Name of the function\. Case insensitive\.|


## Returns

True if the name has been added, false if not\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.IsDefinedFunction\(string, TUserDefinedFunctionLocation\)
Returns true if the Custom formula function has been added to the FlexCel recalculating engine\.
Note that internal functions are not returned by this method, but user defined functions pre\-defined in FlexCel will be\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.IsDefinedFunction(const functionName: string; out location: <a href="../TUserDefinedFunctionLocation.md">TUserDefinedFunctionLocation</a>): Boolean; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**functionName**|string|Name of the function\. Case insensitive\.|
|out|**location**|[TUserDefined&#8203;Function&#8203;Location](../TUserDefinedFunctionLocation.md)|Returns if the function is defined as an internal or external function\.|


## Returns

True if the name has been added, false if not\.

## See also

* [TExcelFile](../TExcelFile/index.md)

