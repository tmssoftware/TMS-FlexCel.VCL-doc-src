---
uid: TXlsFile.GetColFormat
description: TXlsFile.GetColFormat
---

# TXlsFile\.GetColFormat Method

## Overloads

* [TXlsFile\.GetColFormat\(Integer\)](#txlsfilegetcolformatinteger)
* [TXlsFile\.GetColFormat\(Integer, Integer\)](#txlsfilegetcolformatinteger-integer)

# TXlsFile\.GetColFormat\(Integer\)
Gets the XF format for the specified column, \-1 if the column doesn't have format\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetColFormat(const col: Integer): Integer; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col**|Integer|Column index \(1\-based\)|


## Returns

XF format\.

## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.GetColFormat\(Integer, Integer\)
Gets the XF format for the specified column, \-1 if the column doesn't have format\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetColFormat(const sheet: Integer; const col: Integer): Integer; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet index \(1 based\)\.|
|const|**col**|Integer|Column index \(1\-based\)|


## Returns

XF format\.

## See also

* [TXlsFile](../TXlsFile/index.md)

