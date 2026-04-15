---
uid: TExcelFile.SetObjectAnchor
description: TExcelFile.SetObjectAnchor
---

# TExcelFile\.SetObjectAnchor Method

## Overloads

* [TExcelFile\.SetObjectAnchor\(Integer, TClientAnchor\)](#texcelfilesetobjectanchorinteger-tclientanchor)
* [TExcelFile\.SetObjectAnchor\(Integer, string, TClientAnchor\)](#texcelfilesetobjectanchorinteger-string-tclientanchor)

# TExcelFile\.SetObjectAnchor\(Integer, TClientAnchor\)
Sets the object placement\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetObjectAnchor(const objectIndex: Integer; const objectAnchor: <a href="../TClientAnchor/index.md">TClientAnchor</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1\-based\)|
|const|**objectAnchor**|[TClientAnchor](../TClientAnchor/index.md)|Coordinates of the object\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetObjectAnchor\(Integer, string, TClientAnchor\)
Sets the object placement\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetObjectAnchor(const objectIndex: Integer; const objectPath: string; const objectAnchor: <a href="../TClientAnchor/index.md">TClientAnchor</a>); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1\-based\)|
|const|**objectPath**|string|Object path for the shape if this is a grouped shape\.|
|const|**objectAnchor**|[TClientAnchor](../TClientAnchor/index.md)|Coordinates of the object\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

