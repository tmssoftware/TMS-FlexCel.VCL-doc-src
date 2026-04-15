---
uid: TCellAddress.Create
description: TCellAddress.Create
---

# TCellAddress\.Create Method

## Overloads

* [TCellAddress\.Create\(string\)](#tcelladdresscreatestring)
* [TCellAddress\.Create\(Integer, Integer\)](#tcelladdresscreateinteger-integer)
* [TCellAddress\.Create\(Integer, Integer, Boolean, Boolean\)](#tcelladdresscreateinteger-integer-boolean-boolean)
* [TCellAddress\.Create\(string, Integer, Integer, Boolean, Boolean\)](#tcelladdresscreatestring-integer-integer-boolean-boolean)

# TCellAddress\.Create\(string\)
Creates a Cell Address pointing to \(aCellRef\)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TCellAddress/index.md">TCellAddress</a>.Create(const aCellRef: string): <a href="../TCellAddress/index.md">TCellAddress</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aCellRef**|string|String containing the cell address in Excel notation \(for example "A5"\)\.<br />Absolute references \($A$5\) work too\.<br />|


## See also

* [TCellAddress](../TCellAddress/index.md)

# TCellAddress\.Create\(Integer, Integer\)
Creates Cell Address pointing to \(aRow, aCol\)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TCellAddress/index.md">TCellAddress</a>.Create(const aRow: Integer; const aCol: Integer): <a href="../TCellAddress/index.md">TCellAddress</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aRow**|Integer|Row index of the reference \(1\-based\)\.|
|const|**aCol**|Integer|Column index of the reference \(1\-based\)\.|


## See also

* [TCellAddress](../TCellAddress/index.md)

# TCellAddress\.Create\(Integer, Integer, Boolean, Boolean\)
Creates Cell Address pointing to \(aRow, aCol\) with the corresponding absolute values\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TCellAddress/index.md">TCellAddress</a>.Create(const aRow: Integer; const aCol: Integer; const aRowAbsolute: Boolean; const aColAbsolute: Boolean): <a href="../TCellAddress/index.md">TCellAddress</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aRow**|Integer|Row index of the reference \(1\-based\)\.|
|const|**aCol**|Integer|Column index of the reference \(1\-based\)\.|
|const|**aRowAbsolute**|Boolean|If true row will be an absolute reference\. \(As in A$5\)\.|
|const|**aColAbsolute**|Boolean|If true col will be an absolute reference\. \(As in $A5\)\.|


## See also

* [TCellAddress](../TCellAddress/index.md)

# TCellAddress\.Create\(string, Integer, Integer, Boolean, Boolean\)
Creates Cell Address pointing to \(aRow, aCol\) with the corresponding absolute values\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TCellAddress/index.md">TCellAddress</a>.Create(const aSheet: string; const aRow: Integer; const aCol: Integer; const aRowAbsolute: Boolean; const aColAbsolute: Boolean): <a href="../TCellAddress/index.md">TCellAddress</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aSheet**|string|Sheet name of the reference\.|
|const|**aRow**|Integer|Row index of the reference \(1\-based\)\.|
|const|**aCol**|Integer|Column index of the reference \(1\-based\)\.|
|const|**aRowAbsolute**|Boolean|If true row will be an absolute reference\. \(As in A$5\)\.|
|const|**aColAbsolute**|Boolean|If true col will be an absolute reference\. \(As in $A5\)\.|


## See also

* [TCellAddress](../TCellAddress/index.md)

