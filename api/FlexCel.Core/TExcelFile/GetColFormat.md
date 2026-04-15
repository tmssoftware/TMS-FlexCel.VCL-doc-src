---
uid: TExcelFile.GetColFormat
description: TExcelFile.GetColFormat
---

# TExcelFile\.GetColFormat Method

## Overloads

* [TExcelFile\.GetColFormat\(Integer\)](#texcelfilegetcolformatinteger)
* [TExcelFile\.GetColFormat\(Integer, Integer\)](#texcelfilegetcolformatinteger-integer)

# TExcelFile\.GetColFormat\(Integer\)
Gets the XF format for the specified column, \-1 if the column doesn't have format\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetColFormat(const col: Integer): Integer; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col**|Integer|Column index \(1\-based\)|


## Returns

XF format\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.GetColFormat\(Integer, Integer\)
Gets the XF format for the specified column, \-1 if the column doesn't have format\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetColFormat(const sheet: Integer; const col: Integer): Integer; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet index \(1 based\)\.|
|const|**col**|Integer|Column index \(1\-based\)|


## Returns

XF format\.

## See also

* [TExcelFile](../TExcelFile/index.md)

