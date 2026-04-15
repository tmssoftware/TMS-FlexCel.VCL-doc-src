---
uid: TExcelFile.GetRowFormat
description: TExcelFile.GetRowFormat
---

# TExcelFile\.GetRowFormat Method

## Overloads

* [TExcelFile\.GetRowFormat\(Integer\)](#texcelfilegetrowformatinteger)
* [TExcelFile\.GetRowFormat\(Integer, Integer\)](#texcelfilegetrowformatinteger-integer)

# TExcelFile\.GetRowFormat\(Integer\)
Gets the XF format for the specified row, \-1 if the row doesn't have format\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetRowFormat(const row: Integer): Integer; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row index \(1\-based\)|


## Returns

XF format\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.GetRowFormat\(Integer, Integer\)
Gets the XF format for the specified row, \-1 if the row doesn't have format\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetRowFormat(const sheet: Integer; const row: Integer): Integer; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet index \(1 based\)\.|
|const|**row**|Integer|Row index \(1\-based\)|


## Returns

XF format\.

## See also

* [TExcelFile](../TExcelFile/index.md)

