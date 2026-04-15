---
uid: TExcelFile.HasAutoFilter
description: TExcelFile.HasAutoFilter
---

# TExcelFile\.HasAutoFilter Method

## Overloads

* [TExcelFile\.HasAutoFilter](#texcelfilehasautofilter)
* [TExcelFile\.HasAutoFilter\(Integer, Integer\)](#texcelfilehasautofilterinteger-integer)

# TExcelFile\.HasAutoFilter
Returns true if the active sheet has any AutoFilter defined\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.HasAutoFilter: Boolean; overload; virtual; abstract;</code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.HasAutoFilter\(Integer, Integer\)
Returns true if a cell has an AutoFilter\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.HasAutoFilter(const row: Integer; const col: Integer): Boolean; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row of the cell we want to find out\. \(1 based\)|
|const|**col**|Integer|Column of the cell we want to find out\. \(1 based\)|


## Returns

True if the cell has an AutoFilter, false otherwise\.

## See also

* [TExcelFile](../TExcelFile/index.md)

