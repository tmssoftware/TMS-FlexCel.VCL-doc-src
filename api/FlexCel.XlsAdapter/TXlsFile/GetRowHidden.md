---
uid: TXlsFile.GetRowHidden
description: TXlsFile.GetRowHidden
---

# TXlsFile\.GetRowHidden Method

## Overloads

* [TXlsFile\.GetRowHidden\(Integer\)](#txlsfilegetrowhiddeninteger)
* [TXlsFile\.GetRowHidden\(Integer, Integer\)](#txlsfilegetrowhiddeninteger-integer)

# TXlsFile\.GetRowHidden\(Integer\)
Returns true if the row is hidden\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetRowHidden(const row: Integer): Boolean; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row index \(1 based\)\.|


## Returns

True if the row is hidden\.

## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.GetRowHidden\(Integer, Integer\)
Returns true if the row is hidden\. This method does not care about ActiveSheet\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetRowHidden(const sheet: Integer; const row: Integer): Boolean; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet index \(1 based\) for the row\.|
|const|**row**|Integer|Row index \(1 based\)\.|


## Returns

True if the row is hidden\.

## See also

* [TXlsFile](../TXlsFile/index.md)

