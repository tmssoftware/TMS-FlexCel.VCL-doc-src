---
uid: TXls3DRange.Create
description: TXls3DRange.Create
---

# TXls3DRange\.Create Method

## Overloads

* [TXls3DRange\.Create](#txls3drangecreate)
* [TXls3DRange\.Create\(TCoreExcelFile, string\)](#txls3drangecreatetcoreexcelfile-string)
* [TXls3DRange\.Create\(Integer, Integer, Integer, Integer, Integer, Integer\)](#txls3drangecreateinteger-integer-integer-integer-integer-integer)
* [TXls3DRange\.Create\(string, Integer, Integer, Integer, Integer, Integer, Integer\)](#txls3drangecreatestring-integer-integer-integer-integer-integer-integer)

# TXls3DRange\.Create
Creates an empty 3d range\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TXls3DRange/index.md">TXls3DRange</a>.Create: <a href="../TXls3DRange/index.md">TXls3DRange</a>; static; overload;</code></pre>

## See also

* [TXls3DRange](../TXls3DRange/index.md)

# TXls3DRange\.Create\(TCoreExcelFile, string\)
Creates a new TXls3DRange from a range string like "Sheet1:Sheet2\!D4"

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TXls3DRange/index.md">TXls3DRange</a>.Create(const xls: TCoreExcelFile; const rangeDef: string): <a href="../TXls3DRange/index.md">TXls3DRange</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**xls**|TCoreExcelFile|Excel file with the sheet definitions\.|
|const|**rangeDef**|string|String defining the name\.|


## See also

* [TXls3DRange](../TXls3DRange/index.md)

# TXls3DRange\.Create\(Integer, Integer, Integer, Integer, Integer, Integer\)
Creates a new TXls3DRange class\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TXls3DRange/index.md">TXls3DRange</a>.Create(const aSheet1: Integer; const aSheet2: Integer; const aFirstRow: Integer; const aFirstCol: Integer; const aLastRow: Integer; const aLastCol: Integer): <a href="../TXls3DRange/index.md">TXls3DRange</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aSheet1**|Integer|First sheet of the range\.|
|const|**aSheet2**|Integer|Second sheet of the range\.|
|const|**aFirstRow**|Integer|First row on range\.|
|const|**aFirstCol**|Integer|First column on range\.|
|const|**aLastRow**|Integer|Last row on range\.|
|const|**aLastCol**|Integer|Last column on range\.|


## See also

* [TXls3DRange](../TXls3DRange/index.md)

# TXls3DRange\.Create\(string, Integer, Integer, Integer, Integer, Integer, Integer\)
Creates a new TXls3DRange class\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TXls3DRange/index.md">TXls3DRange</a>.Create(const aFileName: string; const aSheet1: Integer; const aSheet2: Integer; const aFirstRow: Integer; const aFirstCol: Integer; const aLastRow: Integer; const aLastCol: Integer): <a href="../TXls3DRange/index.md">TXls3DRange</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aFileName**|string|Filename with the range if this range is in a linked file\.|
|const|**aSheet1**|Integer|First sheet of the range\.|
|const|**aSheet2**|Integer|Second sheet of the range\.|
|const|**aFirstRow**|Integer|First row on range\.|
|const|**aFirstCol**|Integer|First column on range\.|
|const|**aLastRow**|Integer|Last row on range\.|
|const|**aLastCol**|Integer|Last column on range\.|


## See also

* [TXls3DRange](../TXls3DRange/index.md)

