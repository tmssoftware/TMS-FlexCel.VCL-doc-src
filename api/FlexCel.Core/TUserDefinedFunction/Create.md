---
uid: TUserDefinedFunction.Create
description: TUserDefinedFunction.Create
---

# TUserDefinedFunction\.Create Constructor

## Overloads

* [TUserDefinedFunction\.Create\(string\)](#tuserdefinedfunctioncreatestring)
* [TUserDefinedFunction\.Create\(string, string\)](#tuserdefinedfunctioncreatestring-string)

# TUserDefinedFunction\.Create\(string\)
Initializes the name of the user defined function\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TUserDefinedFunction/index.md">TUserDefinedFunction</a>.Create(const aName: string);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aName**|string|Name to be used in the user defined function\. This is the same name that should be in the xls file\.|


## See also

* [TUserDefinedFunction](../TUserDefinedFunction/index.md)

# TUserDefinedFunction\.Create\(string, string\)
Initializes the name of the user defined function, with a special name for older Excel versions\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TUserDefinedFunction/index.md">TUserDefinedFunction</a>.Create(const aName: string; const aInternalName: string);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aName**|string|Name to be used in the user defined function\. This is the same name that should be in the xls file\.|
|const|**aInternalName**|string|Name that will be used when saving xls \(biff8\) files\. Some functions are saved by Excel 2010 as \.xlfn\_Name when saving xls \(not xlsx\)\. This is the name that should be saved in the xls file, not the real name of the function\.|


## See also

* [TUserDefinedFunction](../TUserDefinedFunction/index.md)

