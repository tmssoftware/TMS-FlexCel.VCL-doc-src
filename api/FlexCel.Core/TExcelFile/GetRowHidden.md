---
uid: TExcelFile.GetRowHidden
description: TExcelFile.GetRowHidden
---

# TExcelFile\.GetRowHidden Method

## Overloads

* [TExcelFile\.GetRowHidden\(Integer\)](#texcelfilegetrowhiddeninteger)
* [TExcelFile\.GetRowHidden\(Integer, Integer\)](#texcelfilegetrowhiddeninteger-integer)

# TExcelFile\.GetRowHidden\(Integer\)
Returns true if the row is hidden\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetRowHidden(const row: Integer): Boolean; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row index \(1 based\)\.|


## Returns

True if the row is hidden\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.GetRowHidden\(Integer, Integer\)
Returns true if the row is hidden\. This method does not care about ActiveSheet\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetRowHidden(const sheet: Integer; const row: Integer): Boolean; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet index \(1 based\) for the row\.|
|const|**row**|Integer|Row index \(1 based\)\.|


## Returns

True if the row is hidden\.

## See also

* [TExcelFile](../TExcelFile/index.md)

