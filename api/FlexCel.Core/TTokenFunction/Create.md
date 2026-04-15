---
uid: TTokenFunction.Create
description: TTokenFunction.Create
---

# TTokenFunction\.Create Constructor

## Overloads

* [TTokenFunction\.Create\(string, Integer\)](#ttokenfunctioncreatestring-integer)
* [TTokenFunction\.Create\(string, Integer, Boolean\)](#ttokenfunctioncreatestring-integer-boolean)

# TTokenFunction\.Create\(string, Integer\)
Creates a new function token for internal \(not user\-defined\) functions\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TTokenFunction/index.md">TTokenFunction</a>.Create(const aFunctionName: string; const aArgumentCount: Integer);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aFunctionName**|string|Name of the function\.|
|const|**aArgumentCount**|Integer|Number of arguments for this function\. Note that if the function has a fixed number of arguments, this parameter is ignored\.|


## See also

* [TTokenFunction](../TTokenFunction/index.md)

# TTokenFunction\.Create\(string, Integer, Boolean\)
Creates a new function token\. It can be an internal or a user\-defined function\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TTokenFunction/index.md">TTokenFunction</a>.Create(const aFunctionName: string; const aArgumentCount: Integer; const aIsUserDefined: Boolean);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aFunctionName**|string|Name of the function\.|
|const|**aArgumentCount**|Integer|Number of arguments for this function\. Note that if the function has a fixed number of arguments, this parameter is ignored\.|
|const|**aIsUserDefined**|Boolean|If true, the function is used defined, not built\-in in Excel\. Note that some built\-in functions from Excel 2003 like EOMonth, while available in Excel, are implemented as user\-defined functions \(they were available in ToolPacks like the Analysis ToolPack\)\.|


## See also

* [TTokenFunction](../TTokenFunction/index.md)

