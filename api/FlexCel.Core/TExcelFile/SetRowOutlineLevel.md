---
uid: TExcelFile.SetRowOutlineLevel
description: TExcelFile.SetRowOutlineLevel
---

# TExcelFile\.SetRowOutlineLevel Method

## Overloads

* [TExcelFile\.SetRowOutlineLevel\(Integer, Integer\)](#texcelfilesetrowoutlinelevelinteger-integer)
* [TExcelFile\.SetRowOutlineLevel\(Integer, Integer, Integer\)](#texcelfilesetrowoutlinelevelinteger-integer-integer)

# TExcelFile\.SetRowOutlineLevel\(Integer, Integer\)
Sets the Outline level for a row\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetRowOutlineLevel(const row: Integer; const level: Integer); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row index \(1 based\)|
|const|**level**|Integer|Outline level\. must be between 0 and 7\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetRowOutlineLevel\(Integer, Integer, Integer\)
Sets the Outline level for a row range\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetRowOutlineLevel(const firstRow: Integer; const lastRow: Integer; const level: Integer); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**firstRow**|Integer|Row index of the first row on the range\. \(1 based\)|
|const|**lastRow**|Integer|Row index of the last row on the range\. \(1 based\)|
|const|**level**|Integer|Outline level\. must be between 0 and 7\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

