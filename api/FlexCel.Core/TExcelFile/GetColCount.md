---
uid: TExcelFile.GetColCount
description: TExcelFile.GetColCount
---

# TExcelFile\.GetColCount Method

## Overloads

* [TExcelFile\.GetColCount\(Integer\)](#texcelfilegetcolcountinteger)
* [TExcelFile\.GetColCount\(Integer, Boolean\)](#texcelfilegetcolcountinteger-boolean)

# TExcelFile\.GetColCount\(Integer\)
Number of columns actually used on a given sheet\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetColCount(const sheet: Integer): Integer; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet index where you want to find the columns \(1 based\)|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.GetColCount\(Integer, Boolean\)
Number of columns actually used on a given sheet\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetColCount(const sheet: Integer; const includeFormattedColumns: Boolean): Integer; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet index where you want to find the columns \(1 based\)|
|const|**includeFormattedColumns**|Boolean|If true \(the default\) formatted columns \(for example a column you selected and painted yellow\) will be included in the count, even if it doesn't have data\.<br />|


## See also

* [TExcelFile](../TExcelFile/index.md)

