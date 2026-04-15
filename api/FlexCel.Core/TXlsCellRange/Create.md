---
uid: TXlsCellRange.Create
description: TXlsCellRange.Create
---

# TXlsCellRange\.Create Method

## Overloads

* [TXlsCellRange\.Create](#txlscellrangecreate)
* [TXlsCellRange\.Create\(string\)](#txlscellrangecreatestring)
* [TXlsCellRange\.Create\(Integer, Integer, Integer, Integer\)](#txlscellrangecreateinteger-integer-integer-integer)

# TXlsCellRange\.Create
Creates an empty Cell range\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TXlsCellRange/index.md">TXlsCellRange</a>.Create: <a href="../TXlsCellRange/index.md">TXlsCellRange</a>; static; overload;</code></pre>

## See also

* [TXlsCellRange](../TXlsCellRange/index.md)

# TXlsCellRange\.Create\(string\)
Creates a cell range based in an Excel range string, like "A1:A10"

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TXlsCellRange/index.md">TXlsCellRange</a>.Create(const rangeDef: string): <a href="../TXlsCellRange/index.md">TXlsCellRange</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**rangeDef**|string|Definition for the range, in Excel A1 notation\. For example A1:B3|


## See also

* [TXlsCellRange](../TXlsCellRange/index.md)

# TXlsCellRange\.Create\(Integer, Integer, Integer, Integer\)
Creates a new TXlsCellRange class\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TXlsCellRange/index.md">TXlsCellRange</a>.Create(const aFirstRow: Integer; const aFirstCol: Integer; const aLastRow: Integer; const aLastCol: Integer): <a href="../TXlsCellRange/index.md">TXlsCellRange</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aFirstRow**|Integer|First row on range\.|
|const|**aFirstCol**|Integer|First column on range\.|
|const|**aLastRow**|Integer|Last row on range\.|
|const|**aLastCol**|Integer|Last column on range\.|


## See also

* [TXlsCellRange](../TXlsCellRange/index.md)

