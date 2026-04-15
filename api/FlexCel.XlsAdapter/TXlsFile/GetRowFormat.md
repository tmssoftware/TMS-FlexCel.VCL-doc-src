---
uid: TXlsFile.GetRowFormat
description: TXlsFile.GetRowFormat
---

# TXlsFile\.GetRowFormat Method

## Overloads

* [TXlsFile\.GetRowFormat\(Integer\)](#txlsfilegetrowformatinteger)
* [TXlsFile\.GetRowFormat\(Integer, Integer\)](#txlsfilegetrowformatinteger-integer)

# TXlsFile\.GetRowFormat\(Integer\)
Gets the XF format for the specified row, \-1 if the row doesn't have format\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetRowFormat(const row: Integer): Integer; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row index \(1\-based\)|


## Returns

XF format\.

## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.GetRowFormat\(Integer, Integer\)
Gets the XF format for the specified row, \-1 if the row doesn't have format\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetRowFormat(const sheet: Integer; const row: Integer): Integer; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet index \(1 based\)\.|
|const|**row**|Integer|Row index \(1\-based\)|


## Returns

XF format\.

## See also

* [TXlsFile](../TXlsFile/index.md)

