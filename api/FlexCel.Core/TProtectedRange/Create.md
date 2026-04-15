---
uid: TProtectedRange.Create
description: TProtectedRange.Create
---

# TProtectedRange\.Create Method

## Overloads

* [TProtectedRange\.Create](#tprotectedrangecreate)
* [TProtectedRange\.Create\(string, string, TXlsCellRangeArray\)](#tprotectedrangecreatestring-string-txlscellrangearray)

# TProtectedRange\.Create
Creates an empty protected range\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TProtectedRange/index.md">TProtectedRange</a>.Create: <a href="../TProtectedRange/index.md">TProtectedRange</a>; static; overload;</code></pre>

## See also

* [TProtectedRange](../TProtectedRange/index.md)

# TProtectedRange\.Create\(string, string, TXlsCellRangeArray\)
Creates and initializes a protected range\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TProtectedRange/index.md">TProtectedRange</a>.Create(const aName: string; const aPassword: string; const aRanges: <a href="../TXlsCellRange/index.md">TArray&lt;TXlsCellRange></a>): <a href="../TProtectedRange/index.md">TProtectedRange</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aName**|string|Name for the protected range\.|
|const|**aPassword**|string|Password to modify the cells\. Keep it null if you don't want to set a password\.|
|const|**aRanges**|[TArray\<&#8203;TXls&#8203;Cell&#8203;Range>](../TXlsCellRange/index.md)|Ranges of cells where this protected range applies\. You might pass an array of TXlsCellRanges here or just a single TXlsCellRange object\.|


## See also

* [TProtectedRange](../TProtectedRange/index.md)

