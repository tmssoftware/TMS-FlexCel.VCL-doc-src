---
uid: TExcelFile.SetColOutlineLevel
description: TExcelFile.SetColOutlineLevel
---

# TExcelFile\.SetColOutlineLevel Method

## Overloads

* [TExcelFile\.SetColOutlineLevel\(Integer, Integer\)](#texcelfilesetcoloutlinelevelinteger-integer)
* [TExcelFile\.SetColOutlineLevel\(Integer, Integer, Integer\)](#texcelfilesetcoloutlinelevelinteger-integer-integer)

# TExcelFile\.SetColOutlineLevel\(Integer, Integer\)
Sets the Outline level for a column\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetColOutlineLevel(const col: Integer; const level: Integer); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col**|Integer|Column index \(1 based\)|
|const|**level**|Integer|Outline level\. must be between 0 and 7\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetColOutlineLevel\(Integer, Integer, Integer\)
Sets the Outline level for a column range\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetColOutlineLevel(const firstCol: Integer; const lastCol: Integer; const level: Integer); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**firstCol**|Integer|Column index of the first column on the range\. \(1 based\)|
|const|**lastCol**|Integer|Column index of the last column on the range\. \(1 based\)|
|const|**level**|Integer|Outline level\. must be between 0 and 7\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

